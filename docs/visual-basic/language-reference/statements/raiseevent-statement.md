---
title: Instrução RaiseEvent
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 19949fbdb1c1c54556876323d839b16fc01608f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605336"
---
# <a name="raiseevent-statement"></a>Instrução RaiseEvent
Gatilhos de um evento declarado no nível de módulo dentro de uma classe, formulário ou documento.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Partes  
 `eventname`  
 Necessário. Nome do evento disparar.  
  
 `argumentlist`  
 Opcional. Lista delimitada por vírgulas de variáveis, matrizes ou expressões. O `argumentlist` argumento deve ser delimitado por parênteses. Se não houver nenhum argumento, os parênteses devem ser omitidos.  
  
## <a name="remarks"></a>Comentários  
 Obrigatório `eventname` é o nome de um evento declarado dentro do módulo. Ele segue as convenções de nomenclatura de variável do Visual Basic.  
  
 Se o evento não foi declarado no módulo no qual ele é gerado, ocorrerá um erro. O fragmento de código a seguir ilustra uma declaração de evento e um procedimento no qual o evento é gerado.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Não é possível usar `RaiseEvent` para gerar eventos que não são explicitamente declarados no módulo. Por exemplo, todos os formulários herdam um <xref:System.Windows.Forms.Control.Click> eventos de <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, não pode ser gerado usando `RaiseEvent` em um formulário derivado. Se você declarar um `Click` evento no módulo de formulário, ele sombreia do formulário próprio <xref:System.Windows.Forms.Control.Click> eventos. Você ainda pode invocar o formulário <xref:System.Windows.Forms.Control.Click> evento chamando o <xref:System.Windows.Forms.Control.OnClick%2A> método.  
  
 Por padrão, um evento definido no Visual Basic gera seus manipuladores de eventos na ordem em que as conexões são estabelecidas. Como os eventos podem ter `ByRef` parâmetros, um processo que se conecta tardia pode receber parâmetros que foram alterados por um manipulador de eventos anterior. Depois de executar os manipuladores de eventos, o controle é retornado para a sub-rotina que gerou o evento.  
  
> [!NOTE]
>  Eventos não compartilhado não devem ser gerados dentro do construtor da classe na qual eles são declarados. Embora esses eventos não causam erros de tempo de execução, eles podem não ser detectadas por manipuladores de evento associado. Use o `Shared` modificador para criar um evento compartilhado, se você precisar gerar um evento de um construtor.  
  
> [!NOTE]
>  Você pode alterar o comportamento padrão de eventos, definindo um evento personalizado. Para eventos personalizados, o `RaiseEvent` instrução invoca o evento `RaiseEvent` acessador. Para obter mais informações sobre eventos personalizados, consulte [instrução Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa os eventos a contagem regressiva de 10 segundos para 0. O código ilustra vários métodos relacionados a eventos, propriedades e instruções, inclusive o `RaiseEvent` instrução.  
  
 A classe que gera um evento é a origem do evento e os métodos que processam o evento são os manipuladores de eventos. Uma fonte de evento pode ter vários manipuladores de eventos que ela gera. Quando a classe gera o evento, esse evento é gerado em cada classe que decidiu manipular eventos para essa instância do objeto.  
  
 O exemplo também usa um formulário (`Form1`) com um botão (`Button1`) e uma caixa de texto (`TextBox1`). Quando você clica no botão, a primeira caixa de texto exibe uma contagem regressiva de 10 para 0 segundos. Depois de decorrido o tempo total (10 segundos), a primeira caixa de texto exibe "Concluído".  
  
 O código para `Form1` Especifica os estados de terminal e inicias do formulário. Ele também contém o código executado quando os eventos são gerados.  
  
 Para usar este exemplo, abra um novo projeto de aplicativo do Windows, adicione um botão chamado `Button1` e uma caixa de texto denominada `TextBox1` ao formulário principal, chamado `Form1`. Em seguida, clique com botão direito do formulário e clique em **Exibir código** para abrir o Editor de código.  
  
 Adicionar um `WithEvents` variável para a seção de declarações de `Form1` classe.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Exemplo  
 Adicione o seguinte código para o código para `Form1`. Substituir qualquer procedimentos duplicados que podem existir, como `Form_Load`, ou `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Pressione F5 para executar o exemplo anterior e clique no botão **iniciar**. A primeira caixa de texto inicia a contagem regressiva de segundos. Depois de decorrido o tempo total (10 segundos), a primeira caixa de texto exibe "Concluído".  
  
> [!NOTE]
>  O `My.Application.DoEvents` método não processa os eventos exatamente da mesma maneira como faz o formulário. Para permitir que o formulário para manipular os eventos diretamente, você pode usar multithreading. Para obter mais informações, consulte [Threading](../../programming-guide/concepts/threading/index.md).  
  
## <a name="see-also"></a>Consulte também  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Instrução Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Instrução AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Instrução RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
