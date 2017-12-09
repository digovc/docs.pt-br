---
title: "Associação de dados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7405cf37aaa21f8773952c9e7ed941bc8ae3150b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding"></a><span data-ttu-id="6a579-102">Associação de dados</span><span class="sxs-lookup"><span data-stu-id="6a579-102">Data Binding</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-103">dá suporte à associação para controles comuns, como controles de grade.</span><span class="sxs-lookup"><span data-stu-id="6a579-103"> supports binding to common controls, such as grid controls.</span></span> <span data-ttu-id="6a579-104">Especificamente, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] define os padrões básicos para associação a uma grade de dados e tratamento de associação de detalhes mestre, em relação ao exibir e atualizar.</span><span class="sxs-lookup"><span data-stu-id="6a579-104">Specifically, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] defines the basic patterns for binding to a data grid and handling master-detail binding, both with regard to display and updating.</span></span>  
  
## <a name="underlying-principle"></a><span data-ttu-id="6a579-105">Princípio subjacente</span><span class="sxs-lookup"><span data-stu-id="6a579-105">Underlying Principle</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-106">converte [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] consultas SQL para execução em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6a579-106"> translates [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries to SQL for execution on a database.</span></span> <span data-ttu-id="6a579-107">Os resultados são `IEnumerable` fortemente tipados.</span><span class="sxs-lookup"><span data-stu-id="6a579-107">The results are strongly typed `IEnumerable`.</span></span> <span data-ttu-id="6a579-108">Como esses objetos são comuns objetos common language runtime (CLR), associação de dados de objeto comum pode ser usada para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="6a579-108">Because these objects are ordinary common language runtime (CLR) objects, ordinary object data binding can be used to display the results.</span></span> <span data-ttu-id="6a579-109">Por outro lado, as operações de alteração (inserções, atualizações e exclusões) exigem etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="6a579-109">On the other hand, change operations (inserts, updates, and deletes) require additional steps.</span></span>  
  
## <a name="operation"></a><span data-ttu-id="6a579-110">Operação</span><span class="sxs-lookup"><span data-stu-id="6a579-110">Operation</span></span>  
 <span data-ttu-id="6a579-111">Implicitamente, a associação aos controles do Windows Forms é realizada por meio da implementação de <xref:System.ComponentModel.IListSource>.</span><span class="sxs-lookup"><span data-stu-id="6a579-111">Implicitly binding to Windows Forms controls is accomplished by implementing <xref:System.ComponentModel.IListSource>.</span></span> <span data-ttu-id="6a579-112">Fontes de dados genéricos <xref:System.Data.Linq.Table%601> (`Table<T>` em c# ou `Table(Of T)` na [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) e genérica `DataQuery` foram atualizadas para implementar <xref:System.ComponentModel.IListSource>.</span><span class="sxs-lookup"><span data-stu-id="6a579-112">Data sources generic <xref:System.Data.Linq.Table%601> (`Table<T>` in C# or `Table(Of T)` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and generic `DataQuery` have been updated to implement <xref:System.ComponentModel.IListSource>.</span></span> <span data-ttu-id="6a579-113">Usuário (IU) da interface associação de dados mecanismos (Windows Forms e Windows Presentation Foundation) ambos os testar se suas fontes de dados implementa <xref:System.ComponentModel.IListSource>.</span><span class="sxs-lookup"><span data-stu-id="6a579-113">User interface (UI) data-binding engines (Windows Forms and Windows Presentation Foundation) both test whether their data source implements <xref:System.ComponentModel.IListSource>.</span></span> <span data-ttu-id="6a579-114">Por isso, escrever uma affectation direta de uma consulta para uma fonte de dados de um controle implicitamente chamadas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] geração de coleção, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="6a579-114">Therefore, writing a direct affectation of a query to a data source of a control implicitly calls [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] collection generation, as in the following example:</span></span>  
  
 [!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
 [!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]  
  
 <span data-ttu-id="6a579-115">O mesmo ocorre com o Windows Presentation Foundation:</span><span class="sxs-lookup"><span data-stu-id="6a579-115">The same occurs with Windows Presentation Foundation:</span></span>  
  
 [!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
 [!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]  
  
 <span data-ttu-id="6a579-116">As gerações de coleção são implementadas por <xref:System.Data.Linq.Table%601> genérico e por `DataQuery` genérico em <xref:System.ComponentModel.IListSource.GetList%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a579-116">Collection generations are implemented by generic <xref:System.Data.Linq.Table%601> and generic `DataQuery` in <xref:System.ComponentModel.IListSource.GetList%2A>.</span></span>  
  
## <a name="ilistsource-implementation"></a><span data-ttu-id="6a579-117">Implementação de IListSource</span><span class="sxs-lookup"><span data-stu-id="6a579-117">IListSource Implementation</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-118">implementa <xref:System.ComponentModel.IListSource> em dois locais:</span><span class="sxs-lookup"><span data-stu-id="6a579-118"> implements <xref:System.ComponentModel.IListSource> in two locations:</span></span>  
  
-   <span data-ttu-id="6a579-119">A fonte de dados é um <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] procura a tabela para preencher um `DataBindingList` coleção que mantém uma referência na tabela.</span><span class="sxs-lookup"><span data-stu-id="6a579-119">The data source is a <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] browses the table to fill a `DataBindingList` collection that keeps a reference on the table.</span></span>  
  
-   <span data-ttu-id="6a579-120">A fonte de dados é um <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="6a579-120">The data source is an <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="6a579-121">Há dois cenários:</span><span class="sxs-lookup"><span data-stu-id="6a579-121">There are two scenarios:</span></span>  
  
    -   <span data-ttu-id="6a579-122">Se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] localiza subjacente <xref:System.Data.Linq.Table%601> do <xref:System.Linq.IQueryable%601>, permite que a fonte para edição e a situação é o mesmo que o primeiro ponto de marcador.</span><span class="sxs-lookup"><span data-stu-id="6a579-122">If [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] finds the underlying <xref:System.Data.Linq.Table%601> from the <xref:System.Linq.IQueryable%601>, the source allows for edition and the situation is the same as in the first bullet point.</span></span>  
  
    -   <span data-ttu-id="6a579-123">Se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] não é possível localizar subjacente <xref:System.Data.Linq.Table%601>, a origem não permite a edição (por exemplo, `groupby`).</span><span class="sxs-lookup"><span data-stu-id="6a579-123">If [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot find the underlying <xref:System.Data.Linq.Table%601>, the source does not allow for edition (for example, `groupby`).</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-124">procura a consulta para preencher um genérico `SortableBindingList`, que é um simples <xref:System.ComponentModel.BindingList%601> que implementa o recurso de classificação para entidades de T para uma determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a579-124"> browses the query to fill a generic `SortableBindingList`, which is a simple <xref:System.ComponentModel.BindingList%601> that implements the sorting feature for T entities for a given property.</span></span>  
  
## <a name="specialized-collections"></a><span data-ttu-id="6a579-125">Coleções especializadas</span><span class="sxs-lookup"><span data-stu-id="6a579-125">Specialized Collections</span></span>  
 <span data-ttu-id="6a579-126">Para muitos recursos descritos anteriormente neste documento, <xref:System.ComponentModel.BindingList%601> foi especializado para algumas classes diferentes.</span><span class="sxs-lookup"><span data-stu-id="6a579-126">For many features described earlier in this document, <xref:System.ComponentModel.BindingList%601> has been specialized to some different classes.</span></span> <span data-ttu-id="6a579-127">Essas classes são `SortableBindingList` genérica e `DataBindingList`genérica.</span><span class="sxs-lookup"><span data-stu-id="6a579-127">These classes are generic `SortableBindingList` and generic `DataBindingList`.</span></span> <span data-ttu-id="6a579-128">As duas são declaradas como internas.</span><span class="sxs-lookup"><span data-stu-id="6a579-128">Both are declared as internal.</span></span>  
  
### <a name="generic-sortablebindinglist"></a><span data-ttu-id="6a579-129">SortableBindingList genérica</span><span class="sxs-lookup"><span data-stu-id="6a579-129">Generic SortableBindingList</span></span>  
 <span data-ttu-id="6a579-130">Essa classe herda de <xref:System.ComponentModel.BindingList%601> e é uma versão classificável de <xref:System.ComponentModel.BindingList%601>.</span><span class="sxs-lookup"><span data-stu-id="6a579-130">This class inherits from <xref:System.ComponentModel.BindingList%601>, and is a sortable version of <xref:System.ComponentModel.BindingList%601>.</span></span> <span data-ttu-id="6a579-131">A classificação é uma solução na memória e nunca entra em contato com o próprio banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6a579-131">Sorting is an in-memory solution and never contacts the database itself.</span></span> <span data-ttu-id="6a579-132"><xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList>, mas, por padrão, não dá suporte à classificação.</span><span class="sxs-lookup"><span data-stu-id="6a579-132"><xref:System.ComponentModel.BindingList%601> implements <xref:System.ComponentModel.IBindingList> but does not support sorting by default.</span></span> <span data-ttu-id="6a579-133">No entanto, <xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList> com virtual *core* métodos.</span><span class="sxs-lookup"><span data-stu-id="6a579-133">However, <xref:System.ComponentModel.BindingList%601> implements <xref:System.ComponentModel.IBindingList> with virtual *core* methods.</span></span> <span data-ttu-id="6a579-134">Você pode substituir esses métodos facilmente.</span><span class="sxs-lookup"><span data-stu-id="6a579-134">You can easily override these methods.</span></span> <span data-ttu-id="6a579-135">`SortableBindingList` genérica substitui <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> e <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a579-135">Generic `SortableBindingList` overrides <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A>, and <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>.</span></span> <span data-ttu-id="6a579-136">`ApplySortCore` é chamada por <xref:System.ComponentModel.IBindingList.ApplySort%2A> e classifica a lista de itens de T para uma determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="6a579-136">`ApplySortCore` is called by <xref:System.ComponentModel.IBindingList.ApplySort%2A> and sorts the list of T items for a given property.</span></span>  
  
 <span data-ttu-id="6a579-137">Uma exceção será gerada se a propriedade não pertencer a T.</span><span class="sxs-lookup"><span data-stu-id="6a579-137">An exception is raised if the property does not belong to T.</span></span>  
  
 <span data-ttu-id="6a579-138">Para obter a classificação, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cria um genérico `SortableBindingList.PropertyComparer` classe que herda de genérica <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> e implementa o comparador padrão para um determinado tipo T, um `PropertyDescriptor`e uma direção.</span><span class="sxs-lookup"><span data-stu-id="6a579-138">To achieve sorting, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a generic `SortableBindingList.PropertyComparer` class that inherits from generic <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> and implements a default comparer for a given type T, a `PropertyDescriptor`, and a direction.</span></span> <span data-ttu-id="6a579-139">Essa classe cria dinamicamente um `Comparer` de T onde T é `PropertyType` de `PropertyDescriptor`.</span><span class="sxs-lookup"><span data-stu-id="6a579-139">This class dynamically creates a `Comparer` of T where T is the `PropertyType` of the `PropertyDescriptor`.</span></span> <span data-ttu-id="6a579-140">Em seguida, o comparador padrão é recuperado do `Comparer` estático genérico.</span><span class="sxs-lookup"><span data-stu-id="6a579-140">Then, the default comparer is retrieved from the static generic `Comparer`.</span></span> <span data-ttu-id="6a579-141">Uma instância padrão é obtida usando reflexão.</span><span class="sxs-lookup"><span data-stu-id="6a579-141">A default instance is obtained by using reflection.</span></span>  
  
 <span data-ttu-id="6a579-142">A `SortableBindingList` genérica também é a classe base para `DataBindingList`.</span><span class="sxs-lookup"><span data-stu-id="6a579-142">Generic `SortableBindingList` is also the base class for `DataBindingList`.</span></span> <span data-ttu-id="6a579-143">A `SortableBindingList` genérica oferece dois métodos virtuais para suspender ou retomar o controle de itens adicionar/remover.</span><span class="sxs-lookup"><span data-stu-id="6a579-143">Generic `SortableBindingList` offers two virtual methods for suspending or resuming items add/remove tracking.</span></span> <span data-ttu-id="6a579-144">Esses dois métodos podem ser usados para recursos base como classificação, mas serão realmente implementados por classes superiores, como `DataBindingList`genérica.</span><span class="sxs-lookup"><span data-stu-id="6a579-144">Those two methods can be used for base features such as sorting, but will really be implemented by upper classes like generic `DataBindingList`.</span></span>  
  
### <a name="generic-databindinglist"></a><span data-ttu-id="6a579-145">DataBindingList genérica</span><span class="sxs-lookup"><span data-stu-id="6a579-145">Generic DataBindingList</span></span>  
 <span data-ttu-id="6a579-146">Esta classe herda de `SortableBindingLIst`genérica.</span><span class="sxs-lookup"><span data-stu-id="6a579-146">This class inherits from generic `SortableBindingLIst`.</span></span> <span data-ttu-id="6a579-147">A `DataBindingList` genérica mantém uma referência na `Table` genérica subjacente da `IQueryable` genérica usada para o preenchimento inicial da coleção.</span><span class="sxs-lookup"><span data-stu-id="6a579-147">Generic `DataBindingList` keeps a reference on the underlying generic `Table` of the generic `IQueryable` used for the initial filling of the collection.</span></span> <span data-ttu-id="6a579-148">A `DatabindingList` genérica adiciona o controle para adicionar/remover itens à coleção substituindo `InsertItem`() e `RemoveItem`().</span><span class="sxs-lookup"><span data-stu-id="6a579-148">Generic `DatabindingList` adds tracking for item add/remove to the collection by overriding `InsertItem`() and `RemoveItem`().</span></span> <span data-ttu-id="6a579-149">Também implementa o recurso abstrato suspender/retomar para tornar o controle condicional.</span><span class="sxs-lookup"><span data-stu-id="6a579-149">It also implements the abstract suspend/resume tracking feature to make tracking conditional.</span></span> <span data-ttu-id="6a579-150">Esse recurso faz a `DataBindingList` genérica tirar proveito de todo o uso polimorfo do recurso de rastreamento das classes pai.</span><span class="sxs-lookup"><span data-stu-id="6a579-150">This feature makes generic `DataBindingList` take advantage of all the polymorphic usage of the tracking feature of the parent classes.</span></span>  
  
## <a name="binding-to-entitysets"></a><span data-ttu-id="6a579-151">Associando a EntitySets</span><span class="sxs-lookup"><span data-stu-id="6a579-151">Binding to EntitySets</span></span>  
 <span data-ttu-id="6a579-152">A associação a `EntitySet` é um caso especial porque `EntitySet` já é uma coleção que implementa <xref:System.ComponentModel.IBindingList>.</span><span class="sxs-lookup"><span data-stu-id="6a579-152">Binding to `EntitySet` is a special case because `EntitySet` is already a collection that implements <xref:System.ComponentModel.IBindingList>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-153">Adiciona a classificação e Cancelando (<xref:System.ComponentModel.ICancelAddNew>) oferecem suporte.</span><span class="sxs-lookup"><span data-stu-id="6a579-153"> adds sorting and canceling (<xref:System.ComponentModel.ICancelAddNew>) support.</span></span> <span data-ttu-id="6a579-154">Uma classe `EntitySet` usa uma lista interna para armazenar entidades.</span><span class="sxs-lookup"><span data-stu-id="6a579-154">An `EntitySet` class uses an internal list to store entities.</span></span> <span data-ttu-id="6a579-155">Essa lista é uma coleção de baixo nível baseada em uma matriz genérica, a classe genérica `ItemList`.</span><span class="sxs-lookup"><span data-stu-id="6a579-155">This list is a low-level collection based on a generic array, the generic `ItemList` class.</span></span>  
  
### <a name="adding-a-sorting-feature"></a><span data-ttu-id="6a579-156">Adicionando um recurso de classificação</span><span class="sxs-lookup"><span data-stu-id="6a579-156">Adding a Sorting Feature</span></span>  
 <span data-ttu-id="6a579-157">Matrizes oferecem um método de classificação (`Array.Sort()`) que pode ser usado com um `Comparer` de T. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usa genérica `SortableBindingList.PropertyComparer` classe descrito anteriormente neste tópico para obter esse `Comparer` para a propriedade e a direção para ser classificada.</span><span class="sxs-lookup"><span data-stu-id="6a579-157">Arrays offer a sort method (`Array.Sort()`) that you can be used with a `Comparer` of T. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses the generic `SortableBindingList.PropertyComparer` class described earlier in this topic to obtain this `Comparer` for the property and the direction to be sorted on.</span></span> <span data-ttu-id="6a579-158">Um método `ApplySort` é adicionado ao `ItemList` genérico para chamar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="6a579-158">An `ApplySort` method is added to generic `ItemList` to call this feature.</span></span>  
  
 <span data-ttu-id="6a579-159">No lado de `EntitySet`, você agora precisa declarar suporte à classificação:</span><span class="sxs-lookup"><span data-stu-id="6a579-159">On the `EntitySet` side, you now have to declare sorting support:</span></span>  
  
-   <span data-ttu-id="6a579-160"><xref:System.ComponentModel.IBindingList.SupportsSorting%2A> retorna `true`.</span><span class="sxs-lookup"><span data-stu-id="6a579-160"><xref:System.ComponentModel.IBindingList.SupportsSorting%2A> returns `true`.</span></span>  
  
-   <span data-ttu-id="6a579-161"><xref:System.ComponentModel.IBindingList.ApplySort%2A> chama `entities.ApplySort()` e, em seguida, `OnListChanged()`.</span><span class="sxs-lookup"><span data-stu-id="6a579-161"><xref:System.ComponentModel.IBindingList.ApplySort%2A> calls `entities.ApplySort()` and then `OnListChanged()`.</span></span>  
  
-   <span data-ttu-id="6a579-162">As propriedades <xref:System.ComponentModel.IBindingList.SortDirection%2A> e <xref:System.ComponentModel.IBindingList.SortProperty%2A> expõem a definição de classificação atual, que é armazenada em membros locais.</span><span class="sxs-lookup"><span data-stu-id="6a579-162"><xref:System.ComponentModel.IBindingList.SortDirection%2A> and <xref:System.ComponentModel.IBindingList.SortProperty%2A> properties expose the current sorting definition, which is stored in local members.</span></span>  
  
 <span data-ttu-id="6a579-163">Quando você usar um BindingSource e associar um EntitySet\<TEntity > para System.Windows.Forms.BindingSource.DataSource, você deve chamar EntitySet\<Tentity >. GetNewBindingList atualizar BindingSource.List.</span><span class="sxs-lookup"><span data-stu-id="6a579-163">When you use a System.Windows.Forms.BindingSource and bind an EntitySet\<TEntity> to the System.Windows.Forms.BindingSource.DataSource, you must call EntitySet\<Tentity>.GetNewBindingList to update BindingSource.List.</span></span>  
  
 <span data-ttu-id="6a579-164">Se você usar um BindingSource e defina a propriedade BindingSource.DataMember e definir BindingSource.DataSource para uma classe que tem uma propriedade denominada no BindingSource.DataMember que expõe o EntitySet\<TEntity >, você não é necessário chamar EntitySet\<Tentity >. GetNewBindingList para atualizar o BindingSource.List, mas você perder a capacidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="6a579-164">If you use a System.Windows.Forms.BindingSource and set the BindingSource.DataMember property and set BindingSource.DataSource to a class that has a property named in the BindingSource.DataMember that exposes the EntitySet\<TEntity>, you don’t have to call EntitySet\<Tentity>.GetNewBindingList to update the BindingSource.List but you lose Sorting capability.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="6a579-165">Cache</span><span class="sxs-lookup"><span data-stu-id="6a579-165">Caching</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6a579-166">consultas implementam <xref:System.ComponentModel.IListSource.GetList%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a579-166"> queries implement <xref:System.ComponentModel.IListSource.GetList%2A>.</span></span> <span data-ttu-id="6a579-167">Quando a classe BindingSource do Windows Forms encontra essa interface, ela chama GetList() três vezes para uma única conexão.</span><span class="sxs-lookup"><span data-stu-id="6a579-167">When the Windows Forms BindingSource class meets this interface, it calls GetList() threes time for a single connection.</span></span> <span data-ttu-id="6a579-168">Para solucionar essa situação, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa um cache por instância para armazenar e sempre retornará o mesmo gerado coleção.</span><span class="sxs-lookup"><span data-stu-id="6a579-168">To work around this situation, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implements a cache per instance to store and always return the same generated collection.</span></span>  
  
## <a name="cancellation"></a><span data-ttu-id="6a579-169">Cancelamento</span><span class="sxs-lookup"><span data-stu-id="6a579-169">Cancellation</span></span>  
 <span data-ttu-id="6a579-170">O <xref:System.ComponentModel.IBindingList> define um método <xref:System.ComponentModel.IBindingList.AddNew%2A> que é usado pelos controles para criar um novo item de uma coleção associada.</span><span class="sxs-lookup"><span data-stu-id="6a579-170"><xref:System.ComponentModel.IBindingList> defines an <xref:System.ComponentModel.IBindingList.AddNew%2A> method that is used by controls to create a new item from a bound collection.</span></span> <span data-ttu-id="6a579-171">O controle `DataGridView` mostra esse recurso muito bem quando a última linha visível contém uma estrela em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="6a579-171">The `DataGridView` control shows this feature very well when the last visible row contains a star in its header.</span></span> <span data-ttu-id="6a579-172">A estrela mostra que você pode adicionar um novo item.</span><span class="sxs-lookup"><span data-stu-id="6a579-172">The star shows you that you can add a new item.</span></span>  
  
 <span data-ttu-id="6a579-173">Além desse recurso, uma coleção também pode implementar <xref:System.ComponentModel.ICancelAddNew>.</span><span class="sxs-lookup"><span data-stu-id="6a579-173">In addition to this feature, a collection can also implement <xref:System.ComponentModel.ICancelAddNew>.</span></span> <span data-ttu-id="6a579-174">Esse recurso permite que os controles cancelem ou validem se o novo item editado foi validado ou não.</span><span class="sxs-lookup"><span data-stu-id="6a579-174">This feature allows for the controls to cancel or validate that the new edited item has been validated or not.</span></span>  
  
 <span data-ttu-id="6a579-175"><xref:System.ComponentModel.ICancelAddNew>é implementado em todos os [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] coleções de ligação de dados (genérico `SortableBindingList` e genérica `EntitySet`).</span><span class="sxs-lookup"><span data-stu-id="6a579-175"><xref:System.ComponentModel.ICancelAddNew> is implemented in all [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] databound collections (generic `SortableBindingList` and generic `EntitySet`).</span></span> <span data-ttu-id="6a579-176">Em ambas as implementações o código executa:</span><span class="sxs-lookup"><span data-stu-id="6a579-176">In both implementations the code performs as follows:</span></span>  
  
-   <span data-ttu-id="6a579-177">Permite que itens sejam inseridos e removidos da coleção.</span><span class="sxs-lookup"><span data-stu-id="6a579-177">Lets items be inserted and then removed from the collection.</span></span>  
  
-   <span data-ttu-id="6a579-178">Não controla as alterações desde que a interface do usuário não confirme a edição.</span><span class="sxs-lookup"><span data-stu-id="6a579-178">Does not track changes as long as the UI does not commit the edition.</span></span>  
  
-   <span data-ttu-id="6a579-179">Não controla as alterações desde que a edição seja cancelada (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).</span><span class="sxs-lookup"><span data-stu-id="6a579-179">Does not track changes as long as the edition is canceled (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).</span></span>  
  
-   <span data-ttu-id="6a579-180">Permite controlar quando a edição é confirmada (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).</span><span class="sxs-lookup"><span data-stu-id="6a579-180">Allows tracking when the edition is committed (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).</span></span>  
  
-   <span data-ttu-id="6a579-181">Permite que a coleção se comporte normalmente se o novo item não for proveniente de <xref:System.ComponentModel.IBindingList.AddNew%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a579-181">Lets the collection behave normally if the new item does not come from <xref:System.ComponentModel.IBindingList.AddNew%2A>.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6a579-182">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6a579-182">Troubleshooting</span></span>  
 <span data-ttu-id="6a579-183">Esta seção chama vários itens que podem ajudar a resolver problemas de seus aplicativos de vinculação de dados do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a579-183">This section calls out several items that might help troubleshoot your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data binding applications.</span></span>  
  
-   <span data-ttu-id="6a579-184">Você deve usar propriedades; usar somente campos não é suficiente.</span><span class="sxs-lookup"><span data-stu-id="6a579-184">You must use properties; using only fields is not sufficient.</span></span> <span data-ttu-id="6a579-185">O Windows Forms requer esse uso.</span><span class="sxs-lookup"><span data-stu-id="6a579-185">Windows Forms require this usage.</span></span>  
  
-   <span data-ttu-id="6a579-186">Por padrão, `image`, `varbinary`, e `timestamp` tipos de banco de dados são mapeados para a matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="6a579-186">By default, `image`, `varbinary`, and `timestamp` database types map to byte array.</span></span> <span data-ttu-id="6a579-187">Como `ToString()` não é suportado nesse cenário, esses objetos não podem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="6a579-187">Because `ToString()` is not supported in this scenario, these objects cannot be displayed.</span></span>  
  
-   <span data-ttu-id="6a579-188">Um membro de classe mapeado para uma chave primária tem um setter, mas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] não oferece suporte à alteração de identidade de objeto.</span><span class="sxs-lookup"><span data-stu-id="6a579-188">A class member mapped to a primary key has a setter, but [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support object identity change.</span></span> <span data-ttu-id="6a579-189">Portanto, a chave primária/exclusiva que é usada no mapeamento não pode ser atualizada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6a579-189">Therefore, the primary/unique key that is used in mapping cannot be updated in the database.</span></span> <span data-ttu-id="6a579-190">Uma alteração na grade faz com que uma exceção ao chamar <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a579-190">A change in the grid causes an exception when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
-   <span data-ttu-id="6a579-191">Se uma entidade estiver associada em duas grades separadas (por exemplo, uma mestra e outra de detalhes), `Delete` na grade mestra não será propagado para a grade de detalhes.</span><span class="sxs-lookup"><span data-stu-id="6a579-191">If an entity is bound in two separate grids (for example, one master and another detail), a `Delete` in the master grid is not propagated to the detail grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a579-192">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6a579-192">See Also</span></span>  
 [<span data-ttu-id="6a579-193">Informações de plano de fundo</span><span class="sxs-lookup"><span data-stu-id="6a579-193">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)