---
title: Como herdar Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e986c79887ad19c77761b5ce134e4a3d68200d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="aad4a-102">Como herdar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aad4a-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="aad4a-103">Criar novo Windows Forms herdando de formulários base é uma maneira prática de duplicar seus melhores esforços sem passar pelo processo de recriar inteiramente um formulário toda vez que precisar dele.</span><span class="sxs-lookup"><span data-stu-id="aad4a-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="aad4a-104">Para mais informações sobre herdar formulários em tempo de design usando a caixa de diálogo **Selecionador de Herança** e como distinguir visualmente entre níveis de segurança de controles herdados, consulte [Como herdar formulários usando a caixa de diálogo selecionador de herança](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="aad4a-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="aad4a-105">**Observação** para herdar de um formulário, o arquivo ou namespace que contém esse formulário deve ter sido incorporado em um arquivo executável ou DLL.</span><span class="sxs-lookup"><span data-stu-id="aad4a-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="aad4a-106">Para compilar o projeto, escolha **Compilar** no menu **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="aad4a-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="aad4a-107">Além disso, uma referência ao namespace deve ser adicionada à classe que herda o formulário.</span><span class="sxs-lookup"><span data-stu-id="aad4a-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="aad4a-108">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="aad4a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aad4a-109">Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="aad4a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aad4a-110">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="aad4a-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="aad4a-111">Herdar um formulário programaticamente</span><span class="sxs-lookup"><span data-stu-id="aad4a-111">To inherit a form programmatically</span></span>  
  
1.  <span data-ttu-id="aad4a-112">Em sua classe, adicione uma referência ao namespace que contém o formulário que se deseja herdar.</span><span class="sxs-lookup"><span data-stu-id="aad4a-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2.  <span data-ttu-id="aad4a-113">Na definição de classe, adicione uma referência ao formulário de onde será herdado.</span><span class="sxs-lookup"><span data-stu-id="aad4a-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="aad4a-114">A referência deve incluir o namespace que contém o formulário seguido por uma vírgula, depois o nome do próprio formulário base.</span><span class="sxs-lookup"><span data-stu-id="aad4a-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="aad4a-115">Ao herdar formulários, tenha em mente que podem surgir problemas em relação a manipuladores de eventos sendo chamado duas vezes, porque cada evento está sendo manipulado pela classe base e pela classe herdada.</span><span class="sxs-lookup"><span data-stu-id="aad4a-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="aad4a-116">para mais informações sobre como evitar esse problema, consulte [Solucionando problemas de manipuladores de eventos herdados no Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="aad4a-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad4a-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="aad4a-117">See Also</span></span>  
 [<span data-ttu-id="aad4a-118">Instrução Inherits</span><span class="sxs-lookup"><span data-stu-id="aad4a-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="aad4a-119">Instrução Imports (Tipo e Namespace .NET)</span><span class="sxs-lookup"><span data-stu-id="aad4a-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="aad4a-120">using</span><span class="sxs-lookup"><span data-stu-id="aad4a-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)  
 [<span data-ttu-id="aad4a-121">Efeitos da Modificação da Aparência de um Formulário Base</span><span class="sxs-lookup"><span data-stu-id="aad4a-121">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [<span data-ttu-id="aad4a-122">Herança Visual dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aad4a-122">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)