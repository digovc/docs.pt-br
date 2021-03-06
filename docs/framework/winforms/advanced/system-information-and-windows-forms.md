---
title: Informações do sistema e o Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: 727bcc53750081ae2d957527332ed3199c7d8e8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524109"
---
# <a name="system-information-and-windows-forms"></a>Informações do sistema e o Windows Forms
Às vezes, é necessário obter informações sobre o computador em que o aplicativo está sendo executado para tomar decisões em seu código. Por exemplo, você pode ter uma função que só é aplicável quando conectada a um domínio de rede específico; Nesse caso, você precisaria de uma maneira de determinar o domínio e desabilitar a função se o domínio não estiver presente.  
  
 Aplicativos de formulários do Windows podem usar o <xref:System.Windows.Forms.SystemInformation> classe para determinar um número de itens sobre um computador em tempo de execução. O exemplo a seguir demonstra como usar o <xref:System.Windows.Forms.SystemInformation> classe para recuperar o <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 Todos os membros de <xref:System.Windows.Forms.SystemInformation> classe são somente leitura; não é possível modificar as configurações do usuário. Há mais de 100 membros da classe, retornando informações sobre tudo desde o número de monitores conectados ao computador (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) como o espaçamento de ícones do Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Alguns dos membros mais úteis a <xref:System.Windows.Forms.SystemInformation> classe incluir <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.SystemInformation>  
 [Gerenciamento de Energia nos Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
