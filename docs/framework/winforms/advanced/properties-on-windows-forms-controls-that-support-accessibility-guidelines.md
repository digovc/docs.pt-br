---
title: Propriedades em controles dos Windows Forms de suporte a diretrizes de acessibilidade
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ca18b35b90b028054e68a0a14fecc819a6c20b9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="efa9a-102">Propriedades em controles dos Windows Forms de suporte a diretrizes de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="efa9a-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="efa9a-103">Os controles na caixa de ferramentas padrão para Windows Forms oferecem suporte a muitas das diretrizes de acessibilidade, incluindo exibição do foco do teclado e dos elementos da tela.</span><span class="sxs-lookup"><span data-stu-id="efa9a-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="efa9a-104">Planejando acessibilidade</span><span class="sxs-lookup"><span data-stu-id="efa9a-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="efa9a-105">As propriedades dos controles podem ser usadas para dar suporte a outras diretrizes de acessibilidade, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="efa9a-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="efa9a-106">Além disso, é preciso usar menus para fornecer acesso aos recursos do programa.</span><span class="sxs-lookup"><span data-stu-id="efa9a-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="efa9a-107">Propriedades do controle</span><span class="sxs-lookup"><span data-stu-id="efa9a-107">Control Property</span></span>|<span data-ttu-id="efa9a-108">Considerações sobre acessibilidade</span><span class="sxs-lookup"><span data-stu-id="efa9a-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="efa9a-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="efa9a-109">AccessibleDescription</span></span>|<span data-ttu-id="efa9a-110">A descrição é relatada para auxiliares de acessibilidade, tais como leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="efa9a-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="efa9a-111">Os auxiliares de acessibilidade são programas e dispositivos especializados que ajudam as pessoas com deficiência a usar computadores de forma mais eficaz.</span><span class="sxs-lookup"><span data-stu-id="efa9a-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="efa9a-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="efa9a-112">AccessibleName</span></span>|<span data-ttu-id="efa9a-113">O nome a ser relatado aos auxiliares de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="efa9a-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="efa9a-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="efa9a-114">AccessibleRole</span></span>|<span data-ttu-id="efa9a-115">Descreve o uso do elemento na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="efa9a-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="efa9a-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="efa9a-116">TabIndex</span></span>|<span data-ttu-id="efa9a-117">Cria um caminho de navegação sensível pelo formulário.</span><span class="sxs-lookup"><span data-stu-id="efa9a-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="efa9a-118">É importante para os controles sem rótulos intrínsecos, como caixas de texto, ter seu rótulo associado imediatamente antes deles na ordem de tabulação.</span><span class="sxs-lookup"><span data-stu-id="efa9a-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="efa9a-119">Texto</span><span class="sxs-lookup"><span data-stu-id="efa9a-119">Text</span></span>|<span data-ttu-id="efa9a-120">Use o caractere "&" para criar teclas de acesso.</span><span class="sxs-lookup"><span data-stu-id="efa9a-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="efa9a-121">O uso de teclas de acesso é parte do fornecimento de acesso documentado do teclado para recursos.</span><span class="sxs-lookup"><span data-stu-id="efa9a-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="efa9a-122">Tamanho da fonte</span><span class="sxs-lookup"><span data-stu-id="efa9a-122">Font Size</span></span>|<span data-ttu-id="efa9a-123">Se o tamanho da fonte não for ajustável, ele deverá ser definido como 10 pontos ou maior.</span><span class="sxs-lookup"><span data-stu-id="efa9a-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="efa9a-124">Uma vez definido o tamanho da fonte do formulário, todos os controles adicionados depois ao formulário terão o mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="efa9a-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="efa9a-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="efa9a-125">Forecolor</span></span>|<span data-ttu-id="efa9a-126">Se essa propriedade for definida como padrão, as preferências de cores do usuário serão usadas no formulário.</span><span class="sxs-lookup"><span data-stu-id="efa9a-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="efa9a-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="efa9a-127">Backcolor</span></span>|<span data-ttu-id="efa9a-128">Se essa propriedade for definida como padrão, as preferências de cores do usuário serão usadas no formulário.</span><span class="sxs-lookup"><span data-stu-id="efa9a-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="efa9a-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="efa9a-129">BackgroundImage</span></span>|<span data-ttu-id="efa9a-130">Deixe essa propriedade em branco para tornar o texto mais legível.</span><span class="sxs-lookup"><span data-stu-id="efa9a-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efa9a-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="efa9a-131">See Also</span></span>  
 [<span data-ttu-id="efa9a-132">Instruções passo a passo: criando um aplicativo acessível baseado no Windows</span><span class="sxs-lookup"><span data-stu-id="efa9a-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)