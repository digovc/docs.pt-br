---
title: Como criar e definir um renderizador personalizado para o controle ToolStrip nos Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 0b7a77a4a923065cba8c7ea366826f7b04126f11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527168"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Como criar e definir um renderizador personalizado para o controle ToolStrip nos Windows Forms
<xref:System.Windows.Forms.ToolStrip> controles de dar suporte fácil temas e estilos. Você pode obter aparência e comportamento (e aparência) completamente personalizados, configuração de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propriedade ou o <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propriedade para um renderizador personalizado.  
  
 Você pode atribuir processadores a cada indivíduo <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, ou <xref:System.Windows.Forms.StatusStrip> controle, ou você pode usar o <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> propriedade para afetar todos os objetos, definindo o <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> propriedade <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Retorna <xref:System.Windows.Forms.ToolStripRenderMode.Custom> somente se o valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> não é `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Para criar um renderizador personalizado  
  
1.  Estender o <xref:System.Windows.Forms.ToolStripRenderer> classe.  
  
2.  Implemente a renderização personalizada desejada substituindo o *On...* adequado membros  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Para definir o renderizador personalizado para ser o processador atual  
  
1.  Para definir o renderizador personalizado para um <xref:System.Windows.Forms.ToolStrip>, defina o <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propriedade ao renderizador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  Ou para definir o renderizador personalizado para todos os <xref:System.Windows.Forms.ToolStrip> classes contidas em seu aplicativo: definir o <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propriedade para o renderizador personalizado e defina o <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> propriedade <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [Visão geral do controle ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Arquitetura de controle do ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Resumo da tecnologia de ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
