---
title: "Como classificar dados em uma exibição"
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c39cec8aaf12b268790c19751562b16fa34cfdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="3528f-102">Como classificar dados em uma exibição</span><span class="sxs-lookup"><span data-stu-id="3528f-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="3528f-103">Este exemplo descreve como classificar dados em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="3528f-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3528f-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3528f-104">Example</span></span>  
 <span data-ttu-id="3528f-105">O exemplo a seguir cria um simples <xref:System.Windows.Controls.ListBox> e um <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="3528f-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="3528f-106">O <xref:System.Windows.Controls.Primitives.ButtonBase.Click> manipulador de eventos do botão contém a lógica para classificar os itens a <xref:System.Windows.Controls.ListBox> em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="3528f-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="3528f-107">Você pode fazer isso porque a adição de itens para um <xref:System.Windows.Controls.ListBox> dessa maneira adiciona ao <xref:System.Windows.Controls.ItemCollection> do <xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.ItemCollection> deriva o <xref:System.Windows.Data.CollectionView> classe.</span><span class="sxs-lookup"><span data-stu-id="3528f-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="3528f-108">Se você estiver associando seu <xref:System.Windows.Controls.ListBox> para uma coleção usando o <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propriedade, você pode usar a mesma técnica para classificar.</span><span class="sxs-lookup"><span data-stu-id="3528f-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="3528f-109">Desde que você tenha uma referência ao objeto de exibição, é possível usar a mesma técnica para classificar o conteúdo de outros modos de exibição de coleção.</span><span class="sxs-lookup"><span data-stu-id="3528f-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="3528f-110">Para um exemplo de como obter uma exibição, consulte [Obter a exibição padrão de uma coleção de dados](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="3528f-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="3528f-111">Para outro exemplo, consulte [Classificar uma coluna GridView quando um cabeçalho é clicado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="3528f-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="3528f-112">Para obter mais informações sobre modos de exibição, consulte associação a coleções em [Visão geral da vinculação de dados](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3528f-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="3528f-113">Para obter um exemplo de como aplicar a lógica de classificação em [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], consulte [Classificar e agrupar dados usando um modo de exibição em XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="3528f-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3528f-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3528f-114">See Also</span></span>  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [<span data-ttu-id="3528f-115">Classificar uma coluna GridView quando um cabeçalho é clicado</span><span class="sxs-lookup"><span data-stu-id="3528f-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [<span data-ttu-id="3528f-116">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="3528f-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3528f-117">Filtrar dados em uma exibição</span><span class="sxs-lookup"><span data-stu-id="3528f-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="3528f-118">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="3528f-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)