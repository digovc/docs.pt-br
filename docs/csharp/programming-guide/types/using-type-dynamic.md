---
title: "Usando o tipo dynamic (Guia de Programação em C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f9ee1f0cae90120692fa4f41d2f432551281ab6d
ms.lasthandoff: 03/13/2017

---
# <a name="using-type-dynamic-c-programming-guide"></a>Usando o tipo dynamic (Guia de Programação em C#)
O [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] apresenta um novo tipo, `dynamic`. O tipo é um tipo estático, mas um objeto do tipo `dynamic` ignora a verificação de tipo estático. Na maioria dos casos, ele funciona como se tivesse o tipo `object`. Em tempo de compilação, supõem-se que um elemento que tem o tipo `dynamic` dá suporte a qualquer operação. Portanto, você não precisa se preocupar se o objeto obtém seu valor de uma API COM, de uma linguagem dinâmica como o IronPython, do HTML DOM (Modelo de Objeto do Documento), a reflexão ou de algum outro lugar no programa. No entanto, se o código não for válido, os erros serão capturados em tempo de execução.  
  
 Por exemplo, se método de instância `exampleMethod1` no código a seguir tiver apenas um parâmetro, o compilador reconhecerá que a primeira chamada para o método, `ec.exampleMethod1(10, 4)`, não é válido porque ele contém dois argumentos. Essa chamada causa um erro do compilador. A segunda chamada para o método, `dynamic_ec.exampleMethod1(10, 4)`, não é verificada pelo compilador porque o tipo de `dynamic_ec` é `dynamic`. Portanto, nenhum erro de compilador é relatado. No entanto, o erro não escapa o aviso indefinidamente. Ele é detectado em tempo de execução e causa uma exceção de tempo de execução.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]  
  
 A função do compilador nesses exemplos é reunir informações sobre o que cada instrução está propondo fazer para o objeto ou expressão que tem o tipo `dynamic`. Em tempo de execução, as informações armazenadas são examinadas e qualquer instrução inválida causa uma exceção de tempo de execução.  
  
 O resultado de operações mais dinâmicas é `dynamic`. Por exemplo, se você passar o ponteiro do mouse sobre o uso de `testSum` no exemplo a seguir, o IntelliSense exibirá o tipo **(variável local) testSum dinâmico**.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]  
  
 Operações em que o resultado não é `dynamic` incluem conversões de `dynamic` em outro tipo e chamadas de construtor que incluem argumentos do tipo `dynamic`. Por exemplo, o tipo de `testInstance` na declaração a seguir é `ExampleClass`, não `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]  
  
 Exemplos de conversão são mostrados na seção a seguir, "Conversões".  
  
## <a name="conversions"></a>Conversões  
 As conversões entre objetos dinâmicos e outros tipos são fáceis. Isso permite que o desenvolvedor mude entre o comportamento dinâmico e o não dinâmico.  
  
 Qualquer objeto pode ser convertido no tipo dinâmico implicitamente, conforme mostrado nos exemplos a seguir.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]  
  
 Por outro lado, uma conversão implícita pode ser aplicada dinamicamente a qualquer expressão do tipo `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]  
  
## <a name="overload-resolution-with-arguments-of-type-dynamic"></a>Resolução de sobrecarga com argumentos de tipo dynamic  
 A resolução de sobrecarga ocorre em tempo de execução em vez de em tempo de compilação se um ou mais dos argumentos em uma chamada de método tem o tipo `dynamic` ou se o receptor da chamada do método é do tipo `dynamic`. No exemplo a seguir, se o único método `exampleMethod2` acessível for definido para obter um argumento de cadeia de caracteres, enviar `d1` como o argumento não causará um erro de compilador, mas causará uma exceção de tempo de execução. A resolução de sobrecarga falha em tempo de execução porque o tipo de tempo de execução de `d1` é `int` e `exampleMethod2` requer uma cadeia de caracteres.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]  
  
## <a name="dynamic-language-runtime"></a>Dynamic Language Runtime  
 O DLR (Dynamic Language Runtime) é uma nova API no [!INCLUDE[net_v40_short](../../../csharp/programming-guide/types/includes/net_v40_short_md.md)]. Ele fornece a infraestrutura que dá suporte ao tipo `dynamic` em C# e também à implementação das linguagens de programação dinâmicas como IronPython e IronRuby. Para obter mais informações sobre o DLR, consulte [Visão geral do Dynamic Language Runtime](http://msdn.microsoft.com/library/f769a271-8aff-4bea-bfab-6160217ce23d).  
  
## <a name="com-interop"></a>Interoperabilidade COM  
 O [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] inclui vários recursos que aprimoram a experiência de interoperar com APIs COM como as APIs de Automação do Office. Entre os aperfeiçoamentos estão o uso do tipo `dynamic` e de [argumentos nomeados e opcionais](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Muitos métodos COM permitem variação nos tipos de argumento e tipo de retorno, especificando os tipos como `object`. Isso exigiu a conversão explícita dos valores para coordenar com variáveis fortemente tipadas no C#. Se você compilar usando a opção [/link (opções do compilador C#)](../../../csharp/language-reference/compiler-options/link-compiler-option.md), a introdução do tipo `dynamic` permitirá que você trate as ocorrências de `object` em assinaturas COM como se fossem do tipo `dynamic` e, portanto, evitar muito da conversão. Por exemplo, as seguintes instruções de contrastam como acessar uma célula em uma planilha do Microsoft Office Excel com o tipo `dynamic` e sem o tipo `dynamic`.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]  
  
## <a name="related-topics"></a>Tópicos relacionados  
  
|Título|Descrição|  
|-----------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Descreve o uso da palavra-chave `dynamic`.|  
|[Visão geral do Dynamic Language Runtime](http://msdn.microsoft.com/library/f769a271-8aff-4bea-bfab-6160217ce23d)|Fornece uma visão geral do DLR, que é um ambiente de tempo de execução que adiciona um conjunto de serviços para as linguagens dinâmicas para o CLR (Common Language Runtime).|  
|[Passo a passo: Criando e usando objetos dinâmicos](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|Fornece instruções passo a passo para criar um objeto dinâmico personalizado e para criar um projeto que acessa uma biblioteca `IronPython`.|  
|[Como acessar objetos de interoperabilidade do Office usando recursos do Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Demonstra como criar um projeto que usa argumentos nomeados e opcionais, o tipo `dynamic` e outros aprimoramentos que simplificam o acesso aos objetos de API do Office.|