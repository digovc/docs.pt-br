---
title: Como filtrar dados em uma exibição
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 55ec68e8918c9f7fbc9d3ac0062926cc03cb5e10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556647"
---
# <a name="how-to-filter-data-in-a-view"></a>Como filtrar dados em uma exibição
Este exemplo mostra como filtrar dados em uma exibição.  
  
## <a name="example"></a>Exemplo  
 Para criar um filtro, defina um método que forneça a lógica de filtragem. O método é usado como um retorno de chamada e aceita um parâmetro do tipo `object`. O método a seguir retorna todos os objetos `Order` com a propriedade `filled` definida como "Não", filtrando o resto dos objetos.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 É possível aplicar o filtro, conforme mostrado no exemplo a seguir. Neste exemplo, `myCollectionView` é um <xref:System.Windows.Data.ListCollectionView> objeto.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Para desfazer a filtragem, você pode definir o <xref:System.Windows.Data.CollectionView.Filter%2A> propriedade `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Para obter informações sobre como criar ou obter uma exibição, consulte [Obter a exibição padrão de uma coleção de dados](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Para o exemplo completo, consulte [Classificando e filtrando itens em um exemplo de exibição](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Se o objeto de exibição for proveniente de um <xref:System.Windows.Data.CollectionViewSource> do objeto, você aplicar lógica de filtragem, definindo um manipulador de eventos para o <xref:System.Windows.Data.CollectionViewSource.Filter> evento. No exemplo a seguir, `listingDataView` é uma instância de <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 O seguinte exemplo mostra a implementação do manipulador de eventos do filtro `ShowOnlyBargainsFilter` de exemplo. Este manipulador de eventos usa o <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> propriedade filtrar `AuctionItem` objetos que têm um `CurrentPrice` de US $25 ou maior.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [Visão geral da vinculação de dados](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Classificar dados em uma exibição](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Tópicos de instruções](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
