---
title: "Como implementar um cliente do padrão assíncrono baseado em evento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="cec39-102">Como implementar um cliente do padrão assíncrono baseado em evento</span><span class="sxs-lookup"><span data-stu-id="cec39-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="cec39-103">O exemplo de código a seguir demonstra como usar um componente que cumpre o [baseado em evento visão geral do padrão assíncrono](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cec39-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="cec39-104">O formulário para este exemplo usa o `PrimeNumberCalculator` componente descrito em [como: implementar um componente compatível com o padrão assíncrono baseado em evento](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cec39-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="cec39-105">Quando você executa um projeto que usa este exemplo, você verá um formulário de "Número primo Calculadora" com uma grade e dois botões: **iniciar nova tarefa** e **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="cec39-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="cec39-106">Você pode clicar no **iniciar nova tarefa** botão várias vezes consecutivas, e cada clique, uma operação assíncrona será iniciado um cálculo para determinar se um número gerado aleatoriamente é primo.</span><span class="sxs-lookup"><span data-stu-id="cec39-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="cec39-107">O formulário periodicamente exibirá o progresso e os resultados incrementais.</span><span class="sxs-lookup"><span data-stu-id="cec39-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="cec39-108">Cada operação recebe uma ID exclusiva da tarefa</span><span class="sxs-lookup"><span data-stu-id="cec39-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="cec39-109">O resultado da computação é exibido no **resultados** coluna; se o número de teste não é ideal, ele é rotulado como **composto,** e sua primeira divisor é exibida.</span><span class="sxs-lookup"><span data-stu-id="cec39-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="cec39-110">Todas as operações pendentes podem ser canceladas com o **Cancelar** botão.</span><span class="sxs-lookup"><span data-stu-id="cec39-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="cec39-111">Várias seleções podem ser feitas.</span><span class="sxs-lookup"><span data-stu-id="cec39-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cec39-112">A maioria dos números não será primos.</span><span class="sxs-lookup"><span data-stu-id="cec39-112">Most numbers will not be prime.</span></span> <span data-ttu-id="cec39-113">Se você não encontrou um número primo após várias operações concluídas, simplesmente inicie mais tarefas e, eventualmente, você encontrará alguns números primos.</span><span class="sxs-lookup"><span data-stu-id="cec39-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cec39-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cec39-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="cec39-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cec39-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>