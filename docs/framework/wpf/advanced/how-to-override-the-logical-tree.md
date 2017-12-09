---
title: "Como substituir a árvore lógica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6045d3505981d93f07347ebd49d57cd759774
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="e063c-102">Como substituir a árvore lógica</span><span class="sxs-lookup"><span data-stu-id="e063c-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="e063c-103">Embora não seja necessário na maioria dos casos, autores de controle avançados têm a opção de substituir a árvore lógica.</span><span class="sxs-lookup"><span data-stu-id="e063c-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e063c-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e063c-104">Example</span></span>  
 <span data-ttu-id="e063c-105">Este exemplo descreve como subclasse <xref:System.Windows.Controls.StackPanel> para substituir a árvore lógica, nesse caso, para impor um comportamento que o painel somente pode ter e processará apenas um único elemento filho.</span><span class="sxs-lookup"><span data-stu-id="e063c-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="e063c-106">Isso não é necessariamente um comportamento praticamente desejável, mas é mostrado aqui como um meio de que ilustra o cenário para substituir a árvore lógica normal de um elemento.</span><span class="sxs-lookup"><span data-stu-id="e063c-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="e063c-107">Para obter mais informações sobre a árvore lógica, consulte [Árvores no WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="e063c-107">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>