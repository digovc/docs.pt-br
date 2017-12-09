---
title: Usando objetos DrawingVisual
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee46c41d6f0f42bbb9f50bd5862f6eb076b34bb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="b714e-102">Usando objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="b714e-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="b714e-103">Este tópico fornece uma visão geral de como usar <xref:System.Windows.Media.DrawingVisual> objetos no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] camada visual.</span><span class="sxs-lookup"><span data-stu-id="b714e-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="b714e-104">Objeto DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="b714e-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="b714e-105">O <xref:System.Windows.Media.DrawingVisual> é uma classe que é usada para renderizar formas, imagens ou texto leve.</span><span class="sxs-lookup"><span data-stu-id="b714e-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="b714e-106">Essa classe é considerada leve porque não fornece layout nem manipulação de eventos, o que melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="b714e-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="b714e-107">Por esse motivo, desenhos são ideais para telas de fundo e clip-art.</span><span class="sxs-lookup"><span data-stu-id="b714e-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="b714e-108">Contêiner de host do DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="b714e-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="b714e-109">Para usar <xref:System.Windows.Media.DrawingVisual> objetos, você precisa criar um contêiner de host para os objetos.</span><span class="sxs-lookup"><span data-stu-id="b714e-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="b714e-110">O objeto contêiner host deve ser derivado do <xref:System.Windows.FrameworkElement> classe, que oferece suporte para o layout e a manipulação de eventos que o <xref:System.Windows.Media.DrawingVisual> classe não possui.</span><span class="sxs-lookup"><span data-stu-id="b714e-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="b714e-111">O objeto do contêiner de host não exibe nenhuma propriedade visível, já que sua função principal é conter objetos filho.</span><span class="sxs-lookup"><span data-stu-id="b714e-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="b714e-112">No entanto, o <xref:System.Windows.UIElement.Visibility%2A> do contêiner host deve ser definida como <xref:System.Windows.Visibility.Visible>; caso contrário, nenhum de seus elementos filho serão visíveis.</span><span class="sxs-lookup"><span data-stu-id="b714e-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="b714e-113">Quando você cria um objeto de contêiner do host para objetos visuais, é necessário armazenar as referências de objeto visual em um <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="b714e-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="b714e-114">Use o <xref:System.Windows.Media.VisualCollection.Add%2A> método para adicionar um objeto visual no contêiner host.</span><span class="sxs-lookup"><span data-stu-id="b714e-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="b714e-115">No exemplo a seguir, um objeto de host do contêiner é criado e três objetos visuais são adicionados ao seu <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="b714e-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="b714e-116">Para o exemplo de código completo do qual o exemplo de código anterior foi extraído, consulte [Exemplo de teste de clique usando DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="b714e-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="b714e-117">Criando objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="b714e-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="b714e-118">Quando você cria um <xref:System.Windows.Media.DrawingVisual> do objeto, ele não tem nenhum conteúdo de desenho.</span><span class="sxs-lookup"><span data-stu-id="b714e-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="b714e-119">Você pode adicionar texto, gráficos ou conteúdo da imagem, recuperando o objeto <xref:System.Windows.Media.DrawingContext> desenhar nele.</span><span class="sxs-lookup"><span data-stu-id="b714e-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="b714e-120">Um <xref:System.Windows.Media.DrawingContext> é retornado ao chamar o <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> método de um <xref:System.Windows.Media.DrawingVisual> objeto.</span><span class="sxs-lookup"><span data-stu-id="b714e-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="b714e-121">Para desenhar um retângulo no <xref:System.Windows.Media.DrawingContext>, use o <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> método o <xref:System.Windows.Media.DrawingContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="b714e-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="b714e-122">Existem métodos semelhantes para desenhar outros tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b714e-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="b714e-123">Quando você terminar de desenhar conteúdo no <xref:System.Windows.Media.DrawingContext>, chame o <xref:System.Windows.Media.DrawingContext.Close%2A> método para fechar o <xref:System.Windows.Media.DrawingContext> e persistir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b714e-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="b714e-124">No exemplo a seguir, uma <xref:System.Windows.Media.DrawingVisual> objeto é criado e um retângulo em sua <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="b714e-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="b714e-125">Criando substituições para membros FrameworkElement</span><span class="sxs-lookup"><span data-stu-id="b714e-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="b714e-126">O objeto do contêiner de host é responsável por gerenciar sua coleção de objetos visuais.</span><span class="sxs-lookup"><span data-stu-id="b714e-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="b714e-127">Isso requer que o contêiner host implemente substituição de membros para derivada <xref:System.Windows.FrameworkElement> classe.</span><span class="sxs-lookup"><span data-stu-id="b714e-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="b714e-128">A lista a seguir descreve os dois membros que você deve substituir:</span><span class="sxs-lookup"><span data-stu-id="b714e-128">The following list describes the two members you must override:</span></span>  
  
-   <span data-ttu-id="b714e-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Retorna um filho no índice especificado da coleção de elementos filho.</span><span class="sxs-lookup"><span data-stu-id="b714e-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <span data-ttu-id="b714e-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Obtém o número de elementos filhos visuais dentro deste elemento.</span><span class="sxs-lookup"><span data-stu-id="b714e-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="b714e-131">No exemplo a seguir, substituições para os dois <xref:System.Windows.FrameworkElement> membros são implementados.</span><span class="sxs-lookup"><span data-stu-id="b714e-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="b714e-132">Fornecendo suporte a teste de clique</span><span class="sxs-lookup"><span data-stu-id="b714e-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="b714e-133">O objeto contêiner host pode fornecer manipulação de eventos, mesmo que ele não exiba nenhuma propriedade visível — no entanto, seu <xref:System.Windows.UIElement.Visibility%2A> propriedade deve ser definida como <xref:System.Windows.Visibility.Visible>.</span><span class="sxs-lookup"><span data-stu-id="b714e-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="b714e-134">Isso permite que você crie uma rotina de manipulação de evento para o contêiner de host que pode capturar eventos de mouse, como a liberação do botão esquerdo do mouse.</span><span class="sxs-lookup"><span data-stu-id="b714e-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="b714e-135">A rotina de manipulação de eventos, em seguida, podem implementar para teste de clique ao invocar o <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b714e-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="b714e-136">O método <xref:System.Windows.Media.HitTestResultCallback> parâmetro se refere a um procedimento definido pelo usuário que você pode usar para determinar a ação resultante de um teste de clique.</span><span class="sxs-lookup"><span data-stu-id="b714e-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="b714e-137">No exemplo a seguir, o suporte para teste de clique é implementado para o objeto do contêiner de host e seus filhos.</span><span class="sxs-lookup"><span data-stu-id="b714e-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="b714e-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b714e-138">See Also</span></span>  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [<span data-ttu-id="b714e-139">Visão geral de renderização de gráficos do WPF</span><span class="sxs-lookup"><span data-stu-id="b714e-139">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="b714e-140">Teste de clique na camada visual</span><span class="sxs-lookup"><span data-stu-id="b714e-140">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)