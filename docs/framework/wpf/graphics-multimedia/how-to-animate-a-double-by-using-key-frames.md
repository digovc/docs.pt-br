---
title: Como animar um duplo usando quadros-chave
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
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c4ec6554ee024450e397ee7757649be7537eaae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="83350-102">Como animar um duplo usando quadros-chave</span><span class="sxs-lookup"><span data-stu-id="83350-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="83350-103">Este exemplo mostra como animar o valor de uma propriedade que utiliza um <xref:System.Double> usando quadros chave.</span><span class="sxs-lookup"><span data-stu-id="83350-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83350-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="83350-104">Example</span></span>  
 <span data-ttu-id="83350-105">O exemplo a seguir move um retângulo por uma tela.</span><span class="sxs-lookup"><span data-stu-id="83350-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="83350-106">O exemplo usa o <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classe para animar a <xref:System.Windows.Media.TranslateTransform.X%2A> propriedade de um <xref:System.Windows.Media.TranslateTransform> aplicado a um <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="83350-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="83350-107">Essa animação, que se repete indefinidamente, usa três quadros chave da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="83350-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="83350-108">Durante os primeiros três segundos, usa uma instância do <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> classe para mover o retângulo ao longo de um caminho a uma taxa constante de sua posição inicial até a posição 500.</span><span class="sxs-lookup"><span data-stu-id="83350-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="83350-109">Quadros-chave lineares como <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> criam uma transição linear suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="83350-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="83350-110">No final do quarto segundo, usa uma instância do <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> classe repentinamente mover o retângulo para a próxima posição.</span><span class="sxs-lookup"><span data-stu-id="83350-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="83350-111">Quadros chave discretos como <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> criar saltos repentinos entre valores.</span><span class="sxs-lookup"><span data-stu-id="83350-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="83350-112">Neste exemplo, o retângulo está na posição inicial e, de repente, aparece na posição 500.</span><span class="sxs-lookup"><span data-stu-id="83350-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3.  <span data-ttu-id="83350-113">Os últimos dois segundos, usa uma instância do <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> classe para mover o retângulo de volta para sua posição inicial.</span><span class="sxs-lookup"><span data-stu-id="83350-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="83350-114">Quadros-chave spline como <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> criar uma transição de variável entre valores de acordo com o valor de <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="83350-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="83350-115">Neste exemplo, o retângulo começa a se mover lentamente e acelera exponencialmente em direção ao final do segmento de tempo.</span><span class="sxs-lookup"><span data-stu-id="83350-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="83350-116">Para ver o exemplo completo, consulte [Exemplo de animação de quadro-chave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="83350-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="83350-117">Para manter a consistência com outros exemplos de animação, as versões de código deste exemplo usam um <xref:System.Windows.Media.Animation.Storyboard> objeto ao qual aplicar o <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="83350-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="83350-118">Como alternativa, ao aplicar uma única animação no código, é mais simples usar o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método em vez de usar um <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="83350-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="83350-119">Para obter um exemplo, consulte [Animar uma propriedade sem usar um storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="83350-119">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83350-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="83350-120">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [<span data-ttu-id="83350-121">Visão geral das animações de quadro-chave</span><span class="sxs-lookup"><span data-stu-id="83350-121">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="83350-122">Tópicos explicativos sobre quadros-chave</span><span class="sxs-lookup"><span data-stu-id="83350-122">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)