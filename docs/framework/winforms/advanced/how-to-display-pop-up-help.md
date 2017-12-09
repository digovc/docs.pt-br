---
title: Como exibir ajuda pop-up
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5f57e0a7981e8cae93960c8ffc3ed2168594cf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="d9bd6-102">Como exibir ajuda pop-up</span><span class="sxs-lookup"><span data-stu-id="d9bd6-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="d9bd6-103">É uma maneira de exibir a Ajuda em formulários do Windows por meio do **ajuda** botão, localizado no lado direito da barra de título, acessível por meio de <xref:System.Windows.Forms.Form.HelpButton%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="d9bd6-104">Esse tipo de exibição de Ajuda é adequado para uso com caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="d9bd6-105">Caixas de diálogo mostradas modalmente (com o <xref:System.Windows.Forms.Form.ShowDialog%2A> método) tem problemas ao trazer ajuda externa sistemas, como caixas de diálogo modais precisam ser fechadas antes que o foco pode alternar para outra janela.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="d9bd6-106">Além disso, usar o botão **Ajuda** requer que não nenhum botão **Minimizar** ou **Maximizar** seja mostrado na barra de título.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="d9bd6-107">Isso é uma convenção padrão de caixas de diálogo, enquanto formulários geralmente têm os botões **Minimizar** e **Maximizar**.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="d9bd6-108">Lembre-se de que você também pode usar o <xref:System.Windows.Forms.HelpProvider> componente para vincular controles a arquivos em um sistema de Ajuda, mesmo se você tiver implementado Ajuda pop-up.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="d9bd6-109">Para obter mais informações, consulte [Fornecer ajuda em um aplicativo do Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="d9bd6-109">For more information, see [Providing Help in a Windows Application](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9bd6-110">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d9bd6-111">Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d9bd6-112">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="d9bd6-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="d9bd6-113">Exibir a Ajuda pop-up</span><span class="sxs-lookup"><span data-stu-id="d9bd6-113">To display pop-up Help</span></span>  
  
1.  <span data-ttu-id="d9bd6-114">Arraste um componente [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) da Caixa de ferramentas para seu formulário.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-114">Drag a [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="d9bd6-115">Ele ficará na bandeja na parte inferior do Designer de Formulários do Windows.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="d9bd6-116">Na janela Propriedades, defina o <xref:System.Windows.Forms.Form.HelpButton%2A> propriedade `true`.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="d9bd6-117">Isso exibirá um botão com um ponto de interrogação no lado direito da barra de título do formulário.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3.  <span data-ttu-id="d9bd6-118">Para que o <xref:System.Windows.Forms.Form.HelpButton%2A> para exibir o formulário <xref:System.Windows.Forms.Form.MinimizeBox%2A> e <xref:System.Windows.Forms.Form.MaximizeBox%2A> propriedades devem ser definidas como `false`, o <xref:System.Windows.Forms.Form.ControlBox%2A> propriedade definida como `true`e o <xref:System.Windows.Forms.Form.FormBorderStyle%2A> propriedade com um dos seguintes valores: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle> , <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> ou <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4.  <span data-ttu-id="d9bd6-119">Selecione o controle para o qual você deseja exibir a Ajuda no seu formulário e defina a cadeia de caracteres de Ajuda na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="d9bd6-120">Esta é a cadeia de texto que será exibida em uma janela similar a uma [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d9bd6-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span></span>  
  
5.  <span data-ttu-id="d9bd6-121">Pressione **F5**.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-121">Press **F5**.</span></span>  
  
6.  <span data-ttu-id="d9bd6-122">Pressione o botão **Ajuda** na barra de título e clique no controle no qual você definiu a cadeia de caracteres de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="d9bd6-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9bd6-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d9bd6-123">See Also</span></span>  
 [<span data-ttu-id="d9bd6-124">Ajuda de Controle Usando ToolTips</span><span class="sxs-lookup"><span data-stu-id="d9bd6-124">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="d9bd6-125">Integrando a Ajuda do Usuário nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9bd6-125">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="d9bd6-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9bd6-126">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)