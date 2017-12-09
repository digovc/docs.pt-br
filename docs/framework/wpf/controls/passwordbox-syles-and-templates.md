---
title: Estilos e modelos PasswordBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17a9292ef6aeba157780be5ec87d67725eb833a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="fc5c1-102">Estilos e modelos PasswordBox</span><span class="sxs-lookup"><span data-stu-id="fc5c1-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="fc5c1-103">Este tópico descreve os estilos e modelos para o <xref:System.Windows.Controls.PasswordBox> controle.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="fc5c1-104">Você pode modificar o padrão <xref:System.Windows.Controls.ControlTemplate> para que o controle uma aparência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fc5c1-105">Para obter mais informações, consulte [Personalizando a aparência de um controle existente criando um ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="fc5c1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="fc5c1-106">PasswordBox partes</span><span class="sxs-lookup"><span data-stu-id="fc5c1-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="fc5c1-107">A tabela a seguir lista as partes nomeadas para o <xref:System.Windows.Controls.PasswordBox> controle.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="fc5c1-108">Parte</span><span class="sxs-lookup"><span data-stu-id="fc5c1-108">Part</span></span>|<span data-ttu-id="fc5c1-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="fc5c1-109">Type</span></span>|<span data-ttu-id="fc5c1-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="fc5c1-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fc5c1-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="fc5c1-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fc5c1-112">Um elemento visual que pode conter um <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="fc5c1-113">O texto do <xref:System.Windows.Controls.PasswordBox> é exibido neste elemento.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="fc5c1-114">Estados de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="fc5c1-114">PasswordBox States</span></span>  
 <span data-ttu-id="fc5c1-115">A tabela a seguir lista os estados visuais para o <xref:System.Windows.Controls.PasswordBox> controle.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="fc5c1-116">Nome do VisualState</span><span class="sxs-lookup"><span data-stu-id="fc5c1-116">VisualState Name</span></span>|<span data-ttu-id="fc5c1-117">Nome do VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fc5c1-117">VisualStateGroup Name</span></span>|<span data-ttu-id="fc5c1-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="fc5c1-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fc5c1-119">Normal</span><span class="sxs-lookup"><span data-stu-id="fc5c1-119">Normal</span></span>|<span data-ttu-id="fc5c1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-120">CommonStates</span></span>|<span data-ttu-id="fc5c1-121">O estado padrão.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-121">The default state.</span></span>|  
|<span data-ttu-id="fc5c1-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fc5c1-122">MouseOver</span></span>|<span data-ttu-id="fc5c1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-123">CommonStates</span></span>|<span data-ttu-id="fc5c1-124">O ponteiro do mouse é posicionado sobre o controle.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="fc5c1-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="fc5c1-125">Disabled</span></span>|<span data-ttu-id="fc5c1-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-126">CommonStates</span></span>|<span data-ttu-id="fc5c1-127">O controle está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-127">The control is disabled.</span></span>|  
|<span data-ttu-id="fc5c1-128">Focalizado</span><span class="sxs-lookup"><span data-stu-id="fc5c1-128">Focused</span></span>|<span data-ttu-id="fc5c1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-129">FocusStates</span></span>|<span data-ttu-id="fc5c1-130">O controle tem foco.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-130">The control has focus.</span></span>|  
|<span data-ttu-id="fc5c1-131">Sem foco</span><span class="sxs-lookup"><span data-stu-id="fc5c1-131">Unfocused</span></span>|<span data-ttu-id="fc5c1-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-132">FocusStates</span></span>|<span data-ttu-id="fc5c1-133">O controle não tem foco.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="fc5c1-134">Válido</span><span class="sxs-lookup"><span data-stu-id="fc5c1-134">Valid</span></span>|<span data-ttu-id="fc5c1-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-135">ValidationStates</span></span>|<span data-ttu-id="fc5c1-136">O controle usa o <xref:System.Windows.Controls.Validation> classe e o <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriedade anexada é `false`.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fc5c1-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fc5c1-137">InvalidFocused</span></span>|<span data-ttu-id="fc5c1-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-138">ValidationStates</span></span>|<span data-ttu-id="fc5c1-139">O <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> é de propriedade anexada `true` tem o controle tem foco.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fc5c1-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fc5c1-140">InvalidUnfocused</span></span>|<span data-ttu-id="fc5c1-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc5c1-141">ValidationStates</span></span>|<span data-ttu-id="fc5c1-142">O <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> é de propriedade anexada `true` tem o controle não tem foco.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="fc5c1-143">Exemplo de ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="fc5c1-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="fc5c1-144">O exemplo a seguir mostra como definir um <xref:System.Windows.Controls.ControlTemplate> para o <xref:System.Windows.Controls.PasswordBox> controle.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="fc5c1-145">O exemplo anterior usa um ou mais dos seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fc5c1-146">Para ver o exemplo completo, consulte [Styling with ControlTemplates Sample (Estilos com a amostra ControlTemplates)](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="fc5c1-146">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5c1-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fc5c1-147">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="fc5c1-148">Estilos e modelos de controle</span><span class="sxs-lookup"><span data-stu-id="fc5c1-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="fc5c1-149">Personalização do controle</span><span class="sxs-lookup"><span data-stu-id="fc5c1-149">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="fc5c1-150">Estilo e modelagem</span><span class="sxs-lookup"><span data-stu-id="fc5c1-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="fc5c1-151">Personalizando a aparência de um controle existente criando um ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fc5c1-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)