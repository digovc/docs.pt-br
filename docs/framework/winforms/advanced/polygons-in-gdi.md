---
title: "Polígonos no GDI+"
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
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 740a454873976e407843c417a7b09e5a5218398d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="b87dd-102">Polígonos no GDI+</span><span class="sxs-lookup"><span data-stu-id="b87dd-102">Polygons in GDI+</span></span>
<span data-ttu-id="b87dd-103">Um polígono é uma forma fechada com três ou mais lados retos.</span><span class="sxs-lookup"><span data-stu-id="b87dd-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="b87dd-104">Por exemplo, um triângulo é um polígono com três lados, um retângulo é um polígono com quatro lados e um Pentágono é um polígono com cinco lados.</span><span class="sxs-lookup"><span data-stu-id="b87dd-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="b87dd-105">A ilustração a seguir mostra diversos polígonos.</span><span class="sxs-lookup"><span data-stu-id="b87dd-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="b87dd-106">![Polígonos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="b87dd-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="b87dd-107">Desenhando um polígono</span><span class="sxs-lookup"><span data-stu-id="b87dd-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="b87dd-108">Para desenhar um polígono, é necessário um <xref:System.Drawing.Graphics> objeto, um <xref:System.Drawing.Pen> objeto e uma matriz de <xref:System.Drawing.Point> (ou <xref:System.Drawing.PointF>) objetos.</span><span class="sxs-lookup"><span data-stu-id="b87dd-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="b87dd-109">O <xref:System.Drawing.Graphics> objeto fornece o <xref:System.Drawing.Graphics.DrawPolygon%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b87dd-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="b87dd-110">O <xref:System.Drawing.Pen> objeto armazena atributos, como a largura e a cor da linha usada para renderizar o polígono e a matriz de <xref:System.Drawing.Point> objetos armazena os pontos conectados por linhas retas.</span><span class="sxs-lookup"><span data-stu-id="b87dd-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="b87dd-111">O <xref:System.Drawing.Pen> objeto e a matriz de <xref:System.Drawing.Point> objetos são transmitidos como argumentos para o <xref:System.Drawing.Graphics.DrawPolygon%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b87dd-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="b87dd-112">O exemplo a seguir desenha um polígono com três lados.</span><span class="sxs-lookup"><span data-stu-id="b87dd-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="b87dd-113">Observe que há apenas três pontos em `myPointArray`: (0, 0), (50, 30) e (30, 60).</span><span class="sxs-lookup"><span data-stu-id="b87dd-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="b87dd-114">O <xref:System.Drawing.Graphics.DrawPolygon%2A> método fecha automaticamente o polígono ao desenhar uma linha de (30, 60) para o ponto de partida (0, 0).</span><span class="sxs-lookup"><span data-stu-id="b87dd-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="b87dd-115">A ilustração a seguir mostra o polígono.</span><span class="sxs-lookup"><span data-stu-id="b87dd-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="b87dd-116">![Polígono](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="b87dd-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87dd-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b87dd-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="b87dd-118">Linhas, Curvas e Formas</span><span class="sxs-lookup"><span data-stu-id="b87dd-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b87dd-119">Como Criar uma Caneta</span><span class="sxs-lookup"><span data-stu-id="b87dd-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)