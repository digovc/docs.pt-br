---
title: Como pintar uma área com um gradiente radial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: d794f85ce4968e1cf1759df5358834f3b4cdfb50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560635"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Como pintar uma área com um gradiente radial
Este exemplo mostra como usar o <xref:System.Windows.Media.RadialGradientBrush> classe para pintar uma área com um gradiente radial.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa um <xref:System.Windows.Media.RadialGradientBrush> para desenhar um retângulo com um gradiente radial que faz a transição de amarelo para vermelho para azul para verde limão.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 A ilustração a seguir mostra o gradiente do exemplo anterior. Do gradiente foram realçado.  
  
 ![Marcas de gradiente em um gradiente radial](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  Os exemplos neste tópico usam o sistema de coordenadas padrão para definir pontos de controle. O sistema de coordenadas padrão é relativo a uma caixa delimitadora: 0 indica 0% da caixa delimitadora e 1 indica 100% da caixa delimitadora. Você pode alterar esse sistema de coordenadas definindo a <xref:System.Windows.Media.GradientBrush.MappingMode%2A> propriedade para o valor <xref:System.Windows.Media.BrushMappingMode.Absolute>. Um sistema de coordenadas absoluto não é relativo a uma caixa delimitadora. Os valores são interpretados diretamente no espaço local.  
  
 Para mais <xref:System.Windows.Media.RadialGradientBrush> exemplos, consulte o [exemplo pincéis](http://go.microsoft.com/fwlink/?LinkID=159973). Para obter mais informações sobre gradientes e outros tipos de pincéis, veja [Visão geral de pintura com cores sólidas e gradientes](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
