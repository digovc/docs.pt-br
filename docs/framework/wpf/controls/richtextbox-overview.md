---
title: "Visão geral de RichTextBox"
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
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41b423235fc2ed9c0e0612c90017d41ab0e83d0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="richtextbox-overview"></a><span data-ttu-id="0c09a-102">Visão geral de RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0c09a-102">RichTextBox Overview</span></span>
<span data-ttu-id="0c09a-103">O <xref:System.Windows.Controls.RichTextBox> controle permite que você exiba ou edite o conteúdo de fluxo, incluindo parágrafos, imagens, tabelas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0c09a-103">The <xref:System.Windows.Controls.RichTextBox> control enables you to display or edit flow content including paragraphs, images, tables, and more.</span></span> <span data-ttu-id="0c09a-104">Este tópico apresenta o <xref:System.Windows.Controls.TextBox> classe e fornece exemplos de como usá-lo em ambos os [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c09a-104">This topic introduces the <xref:System.Windows.Controls.TextBox> class and provides examples of how to use it in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].</span></span>  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a><span data-ttu-id="0c09a-105">TextBox ou RichTextBox?</span><span class="sxs-lookup"><span data-stu-id="0c09a-105">TextBox or RichTextBox?</span></span>  
 <span data-ttu-id="0c09a-106">Ambos <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.TextBox> permitir aos usuários editar texto, no entanto, os dois controles são usados em cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="0c09a-106">Both <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.TextBox> allow users to edit text, however, the two controls are used in different scenarios.</span></span> <span data-ttu-id="0c09a-107">A <xref:System.Windows.Controls.RichTextBox> é uma opção melhor quando é necessário que o usuário edite texto formatado, imagens, tabelas ou outro conteúdo formatado.</span><span class="sxs-lookup"><span data-stu-id="0c09a-107">A <xref:System.Windows.Controls.RichTextBox> is a better choice when it is necessary for the user to edit formatted text, images, tables, or other rich content.</span></span> <span data-ttu-id="0c09a-108">Por exemplo, a edição de um documento, artigo ou blog que requer formatação, imagens, etc. é melhor realizada usando um <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-108">For example, editing a document, article, or blog that requires formatting, images, etc is best accomplished using a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="0c09a-109">Um <xref:System.Windows.Controls.TextBox> requer menos recursos do sistema, um <xref:System.Windows.Controls.RichTextBox> e é o ideal quando apenas texto sem formatação precisa ser editado (isto é, uso em formulários).</span><span class="sxs-lookup"><span data-stu-id="0c09a-109">A <xref:System.Windows.Controls.TextBox> requires less system resources then a <xref:System.Windows.Controls.RichTextBox> and it is ideal when only plain text needs to be edited (i.e. usage in forms).</span></span> <span data-ttu-id="0c09a-110">Consulte [visão geral da caixa de texto](../../../../docs/framework/wpf/controls/textbox-overview.md) para obter mais informações sobre <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-110">See [TextBox Overview](../../../../docs/framework/wpf/controls/textbox-overview.md) for more information on <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="0c09a-111">A tabela a seguir resume os principais recursos do <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-111">The table below summarizes the main features of <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
|<span data-ttu-id="0c09a-112">Controle</span><span class="sxs-lookup"><span data-stu-id="0c09a-112">Control</span></span>|<span data-ttu-id="0c09a-113">Correção ortográfica em tempo real</span><span class="sxs-lookup"><span data-stu-id="0c09a-113">Real-time Spellchecking</span></span>|<span data-ttu-id="0c09a-114">O menu de contexto</span><span class="sxs-lookup"><span data-stu-id="0c09a-114">Context Menu</span></span>|<span data-ttu-id="0c09a-115">Os comandos de formatação <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)</span><span class="sxs-lookup"><span data-stu-id="0c09a-115">Formatting commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B)</span></span>|<span data-ttu-id="0c09a-116"><xref:System.Windows.Documents.FlowDocument>conteúdo, como imagens, parágrafos, tabelas, etc.</span><span class="sxs-lookup"><span data-stu-id="0c09a-116"><xref:System.Windows.Documents.FlowDocument> content like images, paragraphs, tables, etc.</span></span>|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="0c09a-117">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-117">Yes</span></span>|<span data-ttu-id="0c09a-118">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-118">Yes</span></span>|<span data-ttu-id="0c09a-119">Não</span><span class="sxs-lookup"><span data-stu-id="0c09a-119">No</span></span>|<span data-ttu-id="0c09a-120">Nº</span><span class="sxs-lookup"><span data-stu-id="0c09a-120">No.</span></span>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="0c09a-121">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-121">Yes</span></span>|<span data-ttu-id="0c09a-122">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-122">Yes</span></span>|<span data-ttu-id="0c09a-123">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-123">Yes</span></span>|<span data-ttu-id="0c09a-124">Sim</span><span class="sxs-lookup"><span data-stu-id="0c09a-124">Yes</span></span>|  
  
 <span data-ttu-id="0c09a-125">**Observação:** Embora <xref:System.Windows.Controls.TextBox> não oferece suporte a comandos relacionados com a formatação <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B), muitos comandos básicos são suportados por ambos os controles, como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-125">**Note:** Although <xref:System.Windows.Controls.TextBox> does not support formatting related commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B), many basic commands are supported by both controls such as <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span></span>  
  
 <span data-ttu-id="0c09a-126">Os recursos da tabela acima são abordados em mais detalhes posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0c09a-126">The features from the table above are covered in more detail later.</span></span>  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a><span data-ttu-id="0c09a-127">Criando um RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0c09a-127">Creating a RichTextBox</span></span>  
 <span data-ttu-id="0c09a-128">O código a seguir mostra como criar um <xref:System.Windows.Controls.RichTextBox> que um usuário pode editar conteúdo rico.</span><span class="sxs-lookup"><span data-stu-id="0c09a-128">The code below shows how to create a <xref:System.Windows.Controls.RichTextBox> that a user can edit rich content in.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 <span data-ttu-id="0c09a-129">Especificamente, o conteúdo editado em um <xref:System.Windows.Controls.RichTextBox> é o conteúdo de fluxo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-129">Specifically, the content edited in a <xref:System.Windows.Controls.RichTextBox> is flow content.</span></span> <span data-ttu-id="0c09a-130">O conteúdo de fluxo pode conter vários tipos de elementos incluindo texto formatado, imagens, listas e tabelas.</span><span class="sxs-lookup"><span data-stu-id="0c09a-130">Flow content can contain many types of elements including formatted text, images, lists, and tables.</span></span> <span data-ttu-id="0c09a-131">Consulte [Visão geral de documento dinâmico](../../../../docs/framework/wpf/advanced/flow-document-overview.md) para obter informações aprofundadas sobre documentos de fluxo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-131">See [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md) for in depth information on flow documents.</span></span> <span data-ttu-id="0c09a-132">Para conter conteúdo de fluxo, uma <xref:System.Windows.Controls.RichTextBox> hosts um <xref:System.Windows.Documents.FlowDocument> objeto que por sua vez, contém o conteúdo editável.</span><span class="sxs-lookup"><span data-stu-id="0c09a-132">In order to contain flow content, a <xref:System.Windows.Controls.RichTextBox> hosts a <xref:System.Windows.Documents.FlowDocument> object which in turn contains the editable content.</span></span> <span data-ttu-id="0c09a-133">Para demonstrar o fluxo de conteúdo em um <xref:System.Windows.Controls.RichTextBox>, o código a seguir mostra como criar um <xref:System.Windows.Controls.RichTextBox> com um parágrafo e texto em negrito.</span><span class="sxs-lookup"><span data-stu-id="0c09a-133">To demonstrate flow content in a <xref:System.Windows.Controls.RichTextBox>, the following code shows how to create a <xref:System.Windows.Controls.RichTextBox> with a paragraph and some bolded text.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 <span data-ttu-id="0c09a-134">A ilustração a seguir mostra como esse exemplo é renderizado.</span><span class="sxs-lookup"><span data-stu-id="0c09a-134">The following illustration shows how this sample renders.</span></span>  
  
 <span data-ttu-id="0c09a-135">![RichTextBox com conteúdo](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span><span class="sxs-lookup"><span data-stu-id="0c09a-135">![RichTextBox with content](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span></span>  
  
 <span data-ttu-id="0c09a-136">Elementos como <xref:System.Windows.Documents.Paragraph> e <xref:System.Windows.Documents.Bold> determinam como o conteúdo dentro de um <xref:System.Windows.Controls.RichTextBox> é exibida.</span><span class="sxs-lookup"><span data-stu-id="0c09a-136">Elements like <xref:System.Windows.Documents.Paragraph> and <xref:System.Windows.Documents.Bold> determine how the content inside a <xref:System.Windows.Controls.RichTextBox> appears.</span></span> <span data-ttu-id="0c09a-137">Como um usuário edita <xref:System.Windows.Controls.RichTextBox> conteúdo, eles alteram o conteúdo de fluxo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-137">As a user edits <xref:System.Windows.Controls.RichTextBox> content, they change this flow content.</span></span> <span data-ttu-id="0c09a-138">Para saber mais sobre os recursos do conteúdo de fluxo e como trabalhar com ele, consulte [Visão geral de documento de fluxo](../../../../docs/framework/wpf/advanced/flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c09a-138">To learn more about the features of flow content and how to work with it, see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).</span></span>  
  
 <span data-ttu-id="0c09a-139">**Observação:** de fluxo de conteúdo dentro de um <xref:System.Windows.Controls.RichTextBox> não se comporta exatamente como o conteúdo de fluxo contido em outros controles.</span><span class="sxs-lookup"><span data-stu-id="0c09a-139">**Note:** Flow content inside a <xref:System.Windows.Controls.RichTextBox> does not behave exactly like flow content contained in other controls.</span></span> <span data-ttu-id="0c09a-140">Por exemplo, não há nenhuma coluna em um <xref:System.Windows.Controls.RichTextBox> e, portanto, o comportamento de redimensionamento não automático.</span><span class="sxs-lookup"><span data-stu-id="0c09a-140">For example, there are no columns in a <xref:System.Windows.Controls.RichTextBox> and hence no automatic resizing behavior.</span></span> <span data-ttu-id="0c09a-141">Além disso, é criado em recursos como pesquisa, modo de exibição, navegação de página e zoom não estão disponíveis em um <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-141">Also, built in features like search, viewing mode, page navigation, and zoom are not available within a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a><span data-ttu-id="0c09a-142">Correção ortográfica em tempo real</span><span class="sxs-lookup"><span data-stu-id="0c09a-142">Real-time Spell Checking</span></span>  
 <span data-ttu-id="0c09a-143">Você pode habilitar correção ortográfica em tempo real um <xref:System.Windows.Controls.TextBox> ou <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-143">You can enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="0c09a-144">Quando a verificação ortográfica está ativada, uma linha vermelha aparecerá sob as palavras incorretas (veja a figura abaixo).</span><span class="sxs-lookup"><span data-stu-id="0c09a-144">When spellchecking is turned on, a red line appears underneath any misspelled words (see picture below).</span></span>  
  
 <span data-ttu-id="0c09a-145">![Caixa de texto com verificação ortográfica](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span><span class="sxs-lookup"><span data-stu-id="0c09a-145">![Textbox with spell&#45;checking](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span></span>  
  
 <span data-ttu-id="0c09a-146">Consulte [Habilitar verificação ortográfica em um controle de edição de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md) para saber como habilitar a verificação ortográfica.</span><span class="sxs-lookup"><span data-stu-id="0c09a-146">See [Enable Spell Checking in a Text Editing Control](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md) to learn how to enable spellchecking.</span></span>  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a><span data-ttu-id="0c09a-147">O menu de contexto</span><span class="sxs-lookup"><span data-stu-id="0c09a-147">Context Menu</span></span>  
 <span data-ttu-id="0c09a-148">Por padrão, ambos <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.RichTextBox> têm um menu de contexto que aparece quando um usuário clica com o botão direito dentro do controle.</span><span class="sxs-lookup"><span data-stu-id="0c09a-148">By default, both <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox> have a context menu that appears when a user right-clicks inside the control.</span></span> <span data-ttu-id="0c09a-149">O menu de contexto permite ao usuário recortar, copiar ou colar (veja a figura abaixo).</span><span class="sxs-lookup"><span data-stu-id="0c09a-149">The context menu allows the user to cut, copy, or paste (see illustration below).</span></span>  
  
 <span data-ttu-id="0c09a-150">![TextBox com menu de contexto](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span><span class="sxs-lookup"><span data-stu-id="0c09a-150">![TextBox with context menu](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span></span>  
  
 <span data-ttu-id="0c09a-151">Você pode criar seu próprio menu de contexto personalizado para substituir o padrão.</span><span class="sxs-lookup"><span data-stu-id="0c09a-151">You can create your own custom context menu to override the default one.</span></span> <span data-ttu-id="0c09a-152">Consulte [Posicionar um menu de contexto personalizado em um RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c09a-152">See [Position a Custom Context Menu in a RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md) for more information.</span></span>  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a><span data-ttu-id="0c09a-153">Comando de Edição</span><span class="sxs-lookup"><span data-stu-id="0c09a-153">Editing Commands</span></span>  
 <span data-ttu-id="0c09a-154">Editando comandos permitem que os usuários formatar conteúdo editável em um <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0c09a-154">Editing commands enable users to format editable content inside a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="0c09a-155">Edição de comandos, além de basic <xref:System.Windows.Controls.RichTextBox> inclui formatação de comandos que <xref:System.Windows.Controls.TextBox> não oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="0c09a-155">Besides basic editing commands, <xref:System.Windows.Controls.RichTextBox> includes formatting commands that <xref:System.Windows.Controls.TextBox> does not support.</span></span> <span data-ttu-id="0c09a-156">Por exemplo, quando a edição em um <xref:System.Windows.Controls.RichTextBox>, um usuário pode pressionar Ctr + B para alternar a formatação de texto em negrito.</span><span class="sxs-lookup"><span data-stu-id="0c09a-156">For example, when editing in a <xref:System.Windows.Controls.RichTextBox>, a user could press Ctr+B to toggle bold text formatting.</span></span> <span data-ttu-id="0c09a-157">Consulte <xref:System.Windows.Documents.EditingCommands> para obter uma lista completa dos comandos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0c09a-157">See <xref:System.Windows.Documents.EditingCommands> for a complete list of commands available.</span></span> <span data-ttu-id="0c09a-158">Além de usar atalhos de teclado, você pode associar comandos com outros controles como botões.</span><span class="sxs-lookup"><span data-stu-id="0c09a-158">In addition to using keyboard shortcuts, you can hook commands up to other controls like buttons.</span></span> <span data-ttu-id="0c09a-159">O exemplo a seguir mostra como criar uma barra de ferramentas simples contendo botões que o usuário pode usar para alterar a formatação de texto.</span><span class="sxs-lookup"><span data-stu-id="0c09a-159">The following example shows how to create a simple tool bar containing buttons that the user can use to change text formatting.</span></span>  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 <span data-ttu-id="0c09a-160">A ilustração a seguir mostra como esse exemplo é exibido.</span><span class="sxs-lookup"><span data-stu-id="0c09a-160">The following illustration shows how this sample displays.</span></span>  
  
 <span data-ttu-id="0c09a-161">![RichTextBox com ToolBar](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span><span class="sxs-lookup"><span data-stu-id="0c09a-161">![RichTextBox with ToolBar](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span></span>  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a><span data-ttu-id="0c09a-162">Detectar quando o conteúdo é alterado</span><span class="sxs-lookup"><span data-stu-id="0c09a-162">Detect when Content Changes</span></span>  
 <span data-ttu-id="0c09a-163">Geralmente o <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento deve ser usado para detectar sempre que o texto em uma <xref:System.Windows.Controls.TextBox> ou <xref:System.Windows.Controls.RichTextBox> em vez disso, em seguida, altera <xref:System.Windows.UIElement.KeyDown> como esperado.</span><span class="sxs-lookup"><span data-stu-id="0c09a-163">Usually the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event should be used to detect whenever the text in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox> changes rather then <xref:System.Windows.UIElement.KeyDown> as you might expect.</span></span> <span data-ttu-id="0c09a-164">Consulte [Como detectar quando o texto em um TextBox foi alterado](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md) para ver um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-164">See [Detect When Text in a TextBox Has Changed](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md) for an example.</span></span>  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a><span data-ttu-id="0c09a-165">Salvar, carregar e imprimir conteúdo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0c09a-165">Save, Load, and Print RichTextBox Content</span></span>  
 <span data-ttu-id="0c09a-166">O exemplo a seguir mostra como salvar o conteúdo de um <xref:System.Windows.Controls.RichTextBox> para um arquivo, carregar esse conteúdo de volta para o <xref:System.Windows.Controls.RichTextBox>e imprimir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-166">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span> <span data-ttu-id="0c09a-167">Abaixo está a marcação para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-167">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 <span data-ttu-id="0c09a-168">Abaixo está o código anterior para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c09a-168">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0c09a-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0c09a-169">See Also</span></span>  
 [<span data-ttu-id="0c09a-170">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="0c09a-170">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)  
 [<span data-ttu-id="0c09a-171">Visão geral de TextBox</span><span class="sxs-lookup"><span data-stu-id="0c09a-171">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)