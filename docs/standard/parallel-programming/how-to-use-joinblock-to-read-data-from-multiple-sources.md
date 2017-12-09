---
title: "Como: Usar JoinBlock para ler dados de várias fontes"
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
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41445e4874b94809840ecf9ebda6f27ccc955c9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a><span data-ttu-id="459e2-102">Como: Usar JoinBlock para ler dados de várias fontes</span><span class="sxs-lookup"><span data-stu-id="459e2-102">How to: Use JoinBlock to Read Data From Multiple Sources</span></span>
<span data-ttu-id="459e2-103">Este documento explica como usar o <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> classe para executar uma operação quando os dados estão disponíveis de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="459e2-103">This document explains how to use the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class to perform an operation when data is available from multiple sources.</span></span> <span data-ttu-id="459e2-104">Ele também demonstra como usar o modo não greedy para habilitar vários blocos de junção compartilhar uma fonte de dados com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="459e2-104">It also demonstrates how to use non-greedy mode to enable multiple join blocks to share a data source more efficiently.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="459e2-105">A biblioteca de fluxo de dados TPL (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) não é distribuído com o [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="459e2-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="459e2-106">Para instalar o <xref:System.Threading.Tasks.Dataflow> namespace, abra seu projeto no [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], escolha **gerenciar pacotes NuGet** no menu projeto e pesquise online o `Microsoft.Tpl.Dataflow` pacote.</span><span class="sxs-lookup"><span data-stu-id="459e2-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="459e2-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="459e2-107">Example</span></span>  
 <span data-ttu-id="459e2-108">O exemplo a seguir define três tipos de recursos, `NetworkResource`, `FileResource`, e `MemoryResource`e executa operações quando os recursos estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="459e2-108">The following example defines three resource types, `NetworkResource`, `FileResource`, and `MemoryResource`, and performs operations when resources become available.</span></span> <span data-ttu-id="459e2-109">Este exemplo requer uma `NetworkResource` e `MemoryResource` par para realizar a primeira operação e um `FileResource` e `MemoryResource` par para realizar a operação de segundo.</span><span class="sxs-lookup"><span data-stu-id="459e2-109">This example requires a `NetworkResource` and `MemoryResource` pair in order to perform the first operation and a `FileResource` and `MemoryResource` pair in order to perform the second operation.</span></span> <span data-ttu-id="459e2-110">Para habilitar essas operações ocorrem quando todos os recursos necessários estão disponíveis, este exemplo usa o <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> classe.</span><span class="sxs-lookup"><span data-stu-id="459e2-110">To enable these operations to occur when all required resources are available, this example uses the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class.</span></span> <span data-ttu-id="459e2-111">Quando um <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objeto recebe dados de todas as origens, ele propaga esses dados ao destino, que neste exemplo é um <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objeto.</span><span class="sxs-lookup"><span data-stu-id="459e2-111">When a <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> object receives data from all sources, it propagates that data to its target, which in this example is an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="459e2-112">Ambos <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> leem objetos de um pool compartilhado de `MemoryResource` objetos.</span><span class="sxs-lookup"><span data-stu-id="459e2-112">Both <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects read from a shared pool of `MemoryResource` objects.</span></span>  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 <span data-ttu-id="459e2-113">Para habilitar o uso eficiente do pool compartilhado de `MemoryResource` objetos, este exemplo especifica um <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> objeto que tem o <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> propriedade definida como `False` criar <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objetos que atuam no modo não greedy.</span><span class="sxs-lookup"><span data-stu-id="459e2-113">To enable efficient use of the shared pool of `MemoryResource` objects, this example specifies a <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> property set to `False` to create <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects that act in non-greedy mode.</span></span> <span data-ttu-id="459e2-114">Um bloco de junção não greedy adia todas as mensagens recebidas até que um esteja disponível em cada origem.</span><span class="sxs-lookup"><span data-stu-id="459e2-114">A non-greedy join block postpones all incoming messages until one is available from each source.</span></span> <span data-ttu-id="459e2-115">Se qualquer uma das mensagens adiadas foram aprovados pelo outro bloco, bloco de junção reinicia o processo.</span><span class="sxs-lookup"><span data-stu-id="459e2-115">If any of the postponed messages were accepted by another block, the join block restarts the process.</span></span> <span data-ttu-id="459e2-116">Modo não greedy permite que os blocos de junção que compartilham um ou mais blocos de código-fonte para acelerar o andamento enquanto esperam os outros blocos de dados.</span><span class="sxs-lookup"><span data-stu-id="459e2-116">Non-greedy mode enables join blocks that share one or more source blocks to make forward progress as the other blocks wait for data.</span></span> <span data-ttu-id="459e2-117">Neste exemplo, se um `MemoryResource` objeto é adicionado para o `memoryResources` pool, a primeira associação bloco para receber sua segunda fonte de dados pode tornar o progresso.</span><span class="sxs-lookup"><span data-stu-id="459e2-117">In this example, if a `MemoryResource` object is added to the `memoryResources` pool, the first join block to receive its second data source can make forward progress.</span></span> <span data-ttu-id="459e2-118">Se usar o modo greedy neste exemplo, o que é o padrão, um bloco de junção pode levar a `MemoryResource` do objeto e aguarde até que o segundo recurso se torne disponível.</span><span class="sxs-lookup"><span data-stu-id="459e2-118">If this example were to use greedy mode, which is the default, one join block might take the `MemoryResource` object and wait for the second resource to become available.</span></span> <span data-ttu-id="459e2-119">No entanto, se o bloco de junção tem sua segunda fonte de dados disponível, ele não pode fazer progresso de porque o `MemoryResource` objeto tiver sido tomado por outro bloco de junção.</span><span class="sxs-lookup"><span data-stu-id="459e2-119">However, if the other join block has its second data source available, it cannot make forward progress because the `MemoryResource` object has been taken by the other join block.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="459e2-120">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="459e2-120">Compiling the Code</span></span>  
 <span data-ttu-id="459e2-121">Copie o código de exemplo e cole-o em um projeto do Visual Studio ou colá-lo em um arquivo chamado `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), e, em seguida, execute o seguinte comando em uma janela de Prompt de comando do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="459e2-121">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="459e2-122">**CSC.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span><span class="sxs-lookup"><span data-stu-id="459e2-122">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="459e2-123">**Vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span><span class="sxs-lookup"><span data-stu-id="459e2-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="459e2-124">Programação robusta</span><span class="sxs-lookup"><span data-stu-id="459e2-124">Robust Programming</span></span>  
 <span data-ttu-id="459e2-125">O uso de junções não greedy também pode ajudar a evitar o deadlock em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="459e2-125">The use of non-greedy joins can also help you prevent deadlock in your application.</span></span> <span data-ttu-id="459e2-126">Em um aplicativo de software, *deadlock* ocorre quando dois ou mais processos cada mantenha um recurso e mutuamente Aguarde até que outro processo liberar algum outro recurso.</span><span class="sxs-lookup"><span data-stu-id="459e2-126">In a software application, *deadlock* occurs when two or more processes each hold a resource and mutually wait for another process to release some other resource.</span></span> <span data-ttu-id="459e2-127">Considere um aplicativo que define duas <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objetos.</span><span class="sxs-lookup"><span data-stu-id="459e2-127">Consider an application that defines two <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects.</span></span> <span data-ttu-id="459e2-128">Os dois objetos leem dados de dois blocos de código-fonte compartilhado.</span><span class="sxs-lookup"><span data-stu-id="459e2-128">Both objects each read data from two shared source blocks.</span></span> <span data-ttu-id="459e2-129">No modo greedy, se lê de um bloco de junção da primeira fonte e o segundo bloco de junção lê da fonte de segundo, o aplicativo pode bloqueio porque ambos os blocos de junção mutuamente Aguarde até que o outro para liberar seus recursos.</span><span class="sxs-lookup"><span data-stu-id="459e2-129">In greedy mode, if one join block reads from the first source and the second join block reads from the second source, the application might deadlock because both join blocks mutually wait for the other to release its resource.</span></span> <span data-ttu-id="459e2-130">No modo não greedy, cada bloco de junção leituras de suas fontes somente quando todos os dados estão disponíveis e, portanto, o risco de deadlock é eliminado.</span><span class="sxs-lookup"><span data-stu-id="459e2-130">In non-greedy mode, each join block reads from its sources only when all data is available, and therefore, the risk of deadlock is eliminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459e2-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="459e2-131">See Also</span></span>  
 [<span data-ttu-id="459e2-132">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="459e2-132">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)