---
title: RelativeSource MarkupExtension
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41978e7b91c50b33649bd88e23d22fce7a272c5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="32f64-102">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="32f64-102">RelativeSource MarkupExtension</span></span>
<span data-ttu-id="32f64-103">Especifica as propriedades de um <xref:System.Windows.Data.RelativeSource> origem de associação a ser usado dentro de um [extensão de marcação de associação](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), ou ao definir o <xref:System.Windows.Data.Binding.RelativeSource%2A> propriedade de um <xref:System.Windows.Data.Binding> elemento estabelecido em XAML.</span><span class="sxs-lookup"><span data-stu-id="32f64-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="32f64-104">Uso do Atributo XAML</span><span class="sxs-lookup"><span data-stu-id="32f64-104">XAML Attribute Usage</span></span>  
  
```xml  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="32f64-105">Uso de atributo XAML (aninhado em uma extensão de associação)</span><span class="sxs-lookup"><span data-stu-id="32f64-105">XAML Attribute Usage (nested within Binding extension)</span></span>  
  
```xml  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="32f64-106">Uso de elemento Object do XAML</span><span class="sxs-lookup"><span data-stu-id="32f64-106">XAML Object Element Usage</span></span>  
  
```xml  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="32f64-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="32f64-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`modeEnumValue`|<span data-ttu-id="32f64-108">Um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="32f64-108">One of the following:</span></span><br /><br /> <span data-ttu-id="32f64-109">-O token de cadeia de caracteres `Self`; corresponde a um <xref:System.Windows.Data.RelativeSource> criado com seus <xref:System.Windows.Data.RelativeSource.Mode%2A> propriedade definida como <xref:System.Windows.Data.RelativeSourceMode.Self>.</span><span class="sxs-lookup"><span data-stu-id="32f64-109">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="32f64-110">-O token de cadeia de caracteres `TemplatedParent`; corresponde a um <xref:System.Windows.Data.RelativeSource> criado com seus <xref:System.Windows.Data.RelativeSource.Mode%2A> propriedade definida como <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span><span class="sxs-lookup"><span data-stu-id="32f64-110">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="32f64-111">-O token de cadeia de caracteres `PreviousData`; corresponde a um <xref:System.Windows.Data.RelativeSource> criado com seus <xref:System.Windows.Data.RelativeSource.Mode%2A> propriedade definida como <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span><span class="sxs-lookup"><span data-stu-id="32f64-111">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="32f64-112">– Veja abaixo para obter informações sobre o modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="32f64-112">-   See below for information on `FindAncestor` mode.</span></span>|  
|`FindAncestor`|<span data-ttu-id="32f64-113">O token da cadeia de caracteres `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="32f64-113">The string token `FindAncestor`.</span></span> <span data-ttu-id="32f64-114">Ao usar este token entra-se em um modo por meio do qual `RelativeSource` especifica um tipo de ancestral e opcionalmente um nível de ancestral.</span><span class="sxs-lookup"><span data-stu-id="32f64-114">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="32f64-115">Isso corresponde a <xref:System.Windows.Data.RelativeSource>, conforme criado com a propriedade <xref:System.Windows.Data.RelativeSource.Mode%2A>, definida como <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span><span class="sxs-lookup"><span data-stu-id="32f64-115">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|  
|`typeName`|<span data-ttu-id="32f64-116">Necessário para o modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="32f64-116">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="32f64-117">O nome de um tipo que preenche a propriedade <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="32f64-117">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|  
|`intLevel`|<span data-ttu-id="32f64-118">Opcional para o modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="32f64-118">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="32f64-119">Um nível de ancestral (avaliado de acordo com a direção do pai na árvore lógica).</span><span class="sxs-lookup"><span data-stu-id="32f64-119">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32f64-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="32f64-120">Remarks</span></span>  
 <span data-ttu-id="32f64-121">Usos de associação `{RelativeSource TemplatedParent}` são técnicas-chave que atendem a um conceito maior de separação de uma interface do usuário do controle e uma lógica do controle.</span><span class="sxs-lookup"><span data-stu-id="32f64-121">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="32f64-122">Isso habilita a associação a partir da definição de modelo a um pai modelo (instância do objeto de tempo de execução em que o modelo é aplicado).</span><span class="sxs-lookup"><span data-stu-id="32f64-122">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="32f64-123">Nesse caso, a [Extensão de Marcação TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) é, na verdade, uma abreviação da seguinte expressão de associação: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="32f64-123">For this case, the [TemplateBinding Markup Extension](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="32f64-124">Os usos `TemplateBinding` ou `{RelativeSource TemplatedParent}` são ambos relevantes apenas no XAML que define um modelo.</span><span class="sxs-lookup"><span data-stu-id="32f64-124">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="32f64-125">Para obter mais informações, consulte [Extensão de marcação TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)</span><span class="sxs-lookup"><span data-stu-id="32f64-125">For more information, see [TemplateBinding Markup Extension](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)</span></span>  
  
 <span data-ttu-id="32f64-126">O `{RelativeSource FindAncestor}` é usado principalmente em modelos de controle ou em composições de interface do usuário independentes previsíveis para casos em que um controle deve estar sempre em uma árvore visual de um determinado tipo de ancestral.</span><span class="sxs-lookup"><span data-stu-id="32f64-126">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="32f64-127">Por exemplo, os itens de um controle de itens podem utilizar os usos `FindAncestor` para se associar às propriedades do ancestral pai do controle de itens.</span><span class="sxs-lookup"><span data-stu-id="32f64-127">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="32f64-128">Ou, os elementos que fazem parte da composição de controle em um modelo podem usar associações `FindAncestor` para elementos pai na mesma estrutura da composição.</span><span class="sxs-lookup"><span data-stu-id="32f64-128">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>  
  
 <span data-ttu-id="32f64-129">Na sintaxe de elemento de objeto do modo `FindAncestor` exibida nas seções de Sintaxe XAML, a segunda sintaxe de elemento de objeto é usada especificamente para o modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="32f64-129">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="32f64-130">O modo `FindAncestor` requer um valor <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="32f64-130">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="32f64-131">Você deve definir <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como um atributo usando um [x: tipo de extensão de marcação](../../../../docs/framework/xaml-services/x-type-markup-extension.md) referência para o tipo de ancestral a ser procurado.</span><span class="sxs-lookup"><span data-stu-id="32f64-131">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../../docs/framework/xaml-services/x-type-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="32f64-132">O valor <xref:System.Windows.Data.RelativeSource.AncestorType%2A> é usado quando a requisição de associação é processada em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="32f64-132">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>  
  
 <span data-ttu-id="32f64-133">Para o modo `FindAncestor`, a propriedade opcional <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> pode ajudar a desambiguar a consulta de ancestral em casos em que exista possivelmente mais de um ancestral daquele tipo na árvore de elemento.</span><span class="sxs-lookup"><span data-stu-id="32f64-133">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>  
  
 <span data-ttu-id="32f64-134">Para obter mais informações sobre como usar o modo `FindAncestor`, consulte <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="32f64-134">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>  
  
 <span data-ttu-id="32f64-135">`{RelativeSource Self}` é útil para cenários em que uma propriedade de uma instância deve depender do valor de outra propriedade da mesma instância e não existe nenhuma relação geral da propriedade de dependência (como a coerção) entre as duas propriedades.</span><span class="sxs-lookup"><span data-stu-id="32f64-135">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="32f64-136">Embora seja raro duas propriedades existirem em um objeto de modo que os valores sejam literalmente idênticos (e tipados de modo idêntica), você também pode aplicar um parâmetro de `Converter` a uma associação que tenha `{RelativeSource Self}` e usar o conversor para converter entre os tipos de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="32f64-136">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="32f64-137">Outro cenário para `{RelativeSource Self}` é como parte de um <xref:System.Windows.MultiDataTrigger>.</span><span class="sxs-lookup"><span data-stu-id="32f64-137">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>  
  
 <span data-ttu-id="32f64-138">Por exemplo, o seguinte XAML define um elemento <xref:System.Windows.Shapes.Rectangle> de modo que não importa qual valor é inserido para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sempre será um quadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="32f64-138">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>  
  
 <span data-ttu-id="32f64-139">O `{RelativeSource PreviousData}` é útil em modelos de dados ou em casos em que as associações estão usando uma coleção como a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="32f64-139">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="32f64-140">Você pode usar `{RelativeSource PreviousData}` para realçar relacionamentos entre itens de dados adjacentes na coleção.</span><span class="sxs-lookup"><span data-stu-id="32f64-140">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="32f64-141">Uma técnica relacionada é estabelecer um <xref:System.Windows.Data.MultiBinding> entre os itens atuais e anteriores na fonte de dados, e usar um conversor nessa associação para determinar a diferença entre os dois itens e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="32f64-141">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>  
  
 <span data-ttu-id="32f64-142">No exemplo a seguir, o primeiro <xref:System.Windows.Controls.TextBlock> no modelo de itens exibe o número atual.</span><span class="sxs-lookup"><span data-stu-id="32f64-142">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="32f64-143">A segunda <xref:System.Windows.Controls.TextBlock> associação é uma <xref:System.Windows.Data.MultiBinding> que tem duas uma <xref:System.Windows.Data.Binding> consistuents: o registro atual e uma associação que deliberadamente usa o registro de dados anterior usando `{RelativeSource PreviousData}`.</span><span class="sxs-lookup"><span data-stu-id="32f64-143">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> consistuents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="32f64-144">Em seguida, um conversor em <xref:System.Windows.Data.MultiBinding> calcula a diferença e retorne à associação.</span><span class="sxs-lookup"><span data-stu-id="32f64-144">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>  
  
```xml  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 <span data-ttu-id="32f64-145">A descrição de vinculação de dados como um conceito não é abordado aqui; consulte [Visão geral de vinculação de dados](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="32f64-145">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="32f64-146">No [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementação do processador XAML, o tratamento para esta extensão de marcação é definida pelo <xref:System.Windows.Data.RelativeSource> classe.</span><span class="sxs-lookup"><span data-stu-id="32f64-146">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>  
  
 <span data-ttu-id="32f64-147">`RelativeSource` é uma extensão da marcação.</span><span class="sxs-lookup"><span data-stu-id="32f64-147">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="32f64-148">Extensões de marcação são tipicamente implementadas quando existe um requisito que permite que valores de atributo sejam diferentes de valores literais ou nomes de manipuladores, e o requisito é mais global do que simplesmente colocar conversores de tipo em certos tipos ou propriedades.</span><span class="sxs-lookup"><span data-stu-id="32f64-148">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="32f64-149">Todas as extensões de marcação em XAML usam os caracteres `{` e `}` na sintaxe de atributo, que é a convenção pela qual o processador XAML reconhece que uma extensão de marcação precisa processar o atributo.</span><span class="sxs-lookup"><span data-stu-id="32f64-149">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="32f64-150">Para obter mais informações, consulte [Extensões de marcação e XAML do WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="32f64-150">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f64-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="32f64-151">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="32f64-152">Estilo e modelagem</span><span class="sxs-lookup"><span data-stu-id="32f64-152">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="32f64-153">Visão geral de XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="32f64-153">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="32f64-154">Extensões de marcação e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="32f64-154">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="32f64-155">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="32f64-155">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="32f64-156">Visão geral das declarações de associação</span><span class="sxs-lookup"><span data-stu-id="32f64-156">Binding Declarations Overview</span></span>](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [<span data-ttu-id="32f64-157">Extensão de marcação x:Type</span><span class="sxs-lookup"><span data-stu-id="32f64-157">x:Type Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-type-markup-extension.md)