---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20d411fbe052940fd8fc752e74d012f28ffa441b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="59791-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="59791-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="59791-103">Contém uma coleção de elementos de configuração que especificam contas de usuário para processos que hospedam [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] serviços e recebem acesso de conexão para o serviço de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="59791-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="59791-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="59791-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59791-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59791-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59791-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="59791-106">Attributes and Elements</span></span>  
 <span data-ttu-id="59791-107">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="59791-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59791-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="59791-108">Attributes</span></span>  
 <span data-ttu-id="59791-109">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="59791-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59791-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="59791-110">Child Elements</span></span>  
  
|<span data-ttu-id="59791-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="59791-111">Attribute</span></span>|<span data-ttu-id="59791-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="59791-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="59791-113">\<add></span><span class="sxs-lookup"><span data-stu-id="59791-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="59791-114">Adiciona uma conta de usuário para processos que hospedam [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] serviços e recebem acesso de conexão para o serviço de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="59791-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59791-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="59791-115">Parent Elements</span></span>  
  
|<span data-ttu-id="59791-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="59791-116">Element</span></span>|<span data-ttu-id="59791-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="59791-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59791-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) ou [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="59791-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="59791-119">Especifica as configurações para o Pipe de rede ou serviços de compartilhamento de TCP.</span><span class="sxs-lookup"><span data-stu-id="59791-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59791-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59791-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>