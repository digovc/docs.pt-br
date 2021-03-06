---
title: Considerações sobre procedimentos de sobrecarga (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654324"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Considerações sobre procedimentos de sobrecarga (Visual Basic)
Ao sobrecarregar um procedimento, você deve usar outro *assinatura* para cada versão sobrecarregada. Geralmente, isso significa que cada versão deve especificar uma lista de parâmetros diferentes. Para obter mais informações, consulte "Assinatura diferente" em [sobrecarga de procedimento](./procedure-overloading.md).  
  
 Você pode sobrecarregar uma `Function` procedimento com uma `Sub` procedimento e vice-versa, que tenham assinaturas diferentes. Duas sobrecargas não podem diferir somente em que um tem um valor de retorno e o outro não.  
  
 Você pode sobrecarregar uma propriedade da mesma maneira que você sobrecarregar um procedimento e com as mesmas restrições. No entanto, você não pode sobrecarregar um procedimento com uma propriedade, ou vice-versa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativas para versões sobrecarregadas  
 Às vezes, você tem alternativas para versões sobrecarregadas, particularmente quando a presença de argumentos é opcional ou seu número é variável.  
  
 Tenha em mente que argumentos opcionais não são necessariamente suportados por todos os idiomas e matrizes de parâmetros são limitadas ao Visual Basic. Se você estiver escrevendo um procedimento que pode ser chamado de código escrito em qualquer um dos vários idiomas diferentes, versões sobrecarregadas oferecem maior flexibilidade.  
  
### <a name="overloads-and-optional-arguments"></a>Sobrecargas e argumentos opcionais  
 Quando o código de chamada pode opcionalmente fornecer ou omitir um ou mais argumentos, você pode definir várias versões sobrecarregados ou usar parâmetros opcionais.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usar versões sobrecarregadas  
 Você pode considerar definir uma série de versões sobrecarregadas nos seguintes casos:  
  
-   A lógica no código do procedimento é significativamente diferente dependendo se o código de chamada fornece um argumento opcional ou não.  
  
-   O código do procedimento não pode testar com confiança se o código de chamada forneceu um argumento opcional. Esse é o caso, por exemplo, se não houver nenhum candidato possível para um valor padrão que o código de chamada pode não ser esperado para fornecer.  
  
#### <a name="when-to-use-optional-parameters"></a>Quando usar parâmetros opcionais  
 Talvez você prefira uma ou mais parâmetros opcionais nos seguintes casos:  
  
-   A única ação necessária quando o código de chamada não fornece um argumento opcional é definir o parâmetro para um valor padrão. Nesse caso, o código do procedimento pode ser menos complicado se você definir uma única versão com um ou mais `Optional` parâmetros.  
  
 Para obter mais informações, consulte [parâmetros opcionais](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Sobrecargas e ParamArrays  
 Quando o código de chamada pode passar um número variável de argumentos, você pode definir várias versões sobrecarregados ou usar uma matriz de parâmetros.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usar versões sobrecarregadas  
 Você pode considerar definir uma série de versões sobrecarregadas nos seguintes casos:  
  
-   Você sabe que o código de chamada nunca passa mais do que um pequeno número de valores para a matriz de parâmetros.  
  
-   A lógica no código do procedimento é significativamente diferente dependendo de quantos valores o código de chamada passa.  
  
-   O código de chamada pode passar valores de diferentes tipos de dados.  
  
#### <a name="when-to-use-a-parameter-array"></a>Quando usar uma matriz de parâmetros  
 Melhor você é atendidas por um `ParamArray` parâmetro nos seguintes casos:  
  
-   Não é possível prever quantos valores o código de chamada pode passar para a matriz de parâmetros, e pode ser um número grande.  
  
-   A lógica do procedimento se presta a iteração de todos os valores que o código de chamada passa, executando essencialmente as mesmas operações em cada valor.  
  
 Para obter mais informações, consulte [matrizes de parâmetro](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Sobrecargas implícitas para parâmetros opcionais  
 Um procedimento com um [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parâmetro é equivalente a dois procedimentos sobrecarregados, um com o parâmetro opcional e outro sem ele. Você não pode sobrecarregar tal procedimento com uma lista de parâmetros correspondentes a qualquer uma delas. As declarações a seguir ilustram isso.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Para um procedimento com mais de um parâmetro opcional, há um conjunto de sobrecargas implícitas, acessou pela lógica semelhante ao exemplo anterior.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Sobrecargas implícitas para um parâmetro ParamArray  
 O compilador considera um procedimento com um [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parâmetro deverá ter um número infinito de sobrecargas, com diferenças no que o código de chamada passa para a matriz de parâmetros, da seguinte maneira:  
  
-   Uma sobrecarga para quando o código de chamada não fornece um argumento para o `ParamArray`  
  
-   Uma sobrecarga para quando o código de chamada fornece uma matriz unidimensional do `ParamArray` tipo de elemento  
  
-   Para cada inteiro positivo, uma sobrecarga para quando o código de chamada fornece esse número de argumentos, cada uma da `ParamArray` tipo de elemento  
  
 As seguintes declarações ilustram essas sobrecargas implícitas.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 Você não pode sobrecarregar tal procedimento com uma lista de parâmetros que usa uma matriz unidimensional para a matriz de parâmetros. No entanto, você pode usar as assinaturas das outras sobrecargas implícitas. As declarações a seguir ilustram isso.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programação sem tipo como uma alternativa para sobrecarga  
 Se você quiser permitir que o código de chamada passe diferentes tipos de dados para um parâmetro, uma abordagem alternativa é programação sem tipo. Você pode definir o tipo de comutador para a verificação `Off` com o o [instrução Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ou [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opção de compilador. Em seguida, você não precisa declarar o tipo de dados do parâmetro. No entanto, essa abordagem tem as seguintes desvantagens comparadas à sobrecarga:  
  
-   Programação sem tipo produz código de execução menos eficiente.  
  
-   O procedimento deve testar cada tipo de dados que ele prevê que está sendo passado.  
  
-   O compilador não pode sinalizar um erro se o código de chamada passa um tipo de dados que o procedimento não oferece suporte.  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos](./index.md)  
 [Parâmetros e Argumentos de Procedimento](./procedure-parameters-and-arguments.md)  
 [Solução de problemas de Procedimentos](./troubleshooting-procedures.md)  
 [Como definir várias versões de um procedimento](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Como chamar um procedimento sobrecarregado](./how-to-call-an-overloaded-procedure.md)  
 [Como sobrecarregar um procedimento que usa parâmetros opcionais](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Como sobrecarregar um procedimento que usa um número indefinido de parâmetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Resolução de Sobrecarga](./overload-resolution.md)  
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
