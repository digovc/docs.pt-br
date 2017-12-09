---
title: Como distorcer cores
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="b0133-102">Como distorcer cores</span><span class="sxs-lookup"><span data-stu-id="b0133-102">How to: Shear Colors</span></span>
<span data-ttu-id="b0133-103">A distorção aumenta ou diminui um componente de cor em uma quantidade proporcional a outro componente de cor.</span><span class="sxs-lookup"><span data-stu-id="b0133-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="b0133-104">Por exemplo, considere a transformação em que o componente vermelho é aumentado pela metade do valor do componente azul.</span><span class="sxs-lookup"><span data-stu-id="b0133-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="b0133-105">Nessa transformação, a cor (0,2, 0,5, 1) seria (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="b0133-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="b0133-106">O novo componente vermelho é 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="b0133-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0133-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b0133-107">Example</span></span>  
 <span data-ttu-id="b0133-108">O exemplo a seguir constrói um <xref:System.Drawing.Image> objeto do arquivo ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="b0133-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="b0133-109">Em seguida, o código se aplica à transformação de distorção descrita no parágrafo anterior para cada pixel da imagem.</span><span class="sxs-lookup"><span data-stu-id="b0133-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="b0133-110">A ilustração a seguir mostra a imagem original à esquerda e a imagem distorcida à direita.</span><span class="sxs-lookup"><span data-stu-id="b0133-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="b0133-111">![Distorcer cores](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="b0133-111">![Shear Colors](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="b0133-112">A tabela a seguir lista os vetores de cores para as quatro barras antes e depois da transformação de distorção.</span><span class="sxs-lookup"><span data-stu-id="b0133-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="b0133-113">Original</span><span class="sxs-lookup"><span data-stu-id="b0133-113">Original</span></span>|<span data-ttu-id="b0133-114">Distorcido</span><span class="sxs-lookup"><span data-stu-id="b0133-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="b0133-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="b0133-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="b0133-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="b0133-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="b0133-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="b0133-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="b0133-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="b0133-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="b0133-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0133-123">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="b0133-123">Compiling the Code</span></span>  
 <span data-ttu-id="b0133-124">O exemplo anterior é projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b0133-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b0133-125">Substitua `ColorBars.bmp` por um nome de imagem e caminho válidos no sistema.</span><span class="sxs-lookup"><span data-stu-id="b0133-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0133-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b0133-126">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="b0133-127">Elementos Gráficos e Desenho nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b0133-127">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="b0133-128">Recolorindo Imagens</span><span class="sxs-lookup"><span data-stu-id="b0133-128">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)