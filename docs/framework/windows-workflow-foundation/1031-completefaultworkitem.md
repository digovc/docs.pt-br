---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="13925-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="13925-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="13925-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="13925-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13925-104">ID</span><span class="sxs-lookup"><span data-stu-id="13925-104">ID</span></span>|<span data-ttu-id="13925-105">1031</span><span class="sxs-lookup"><span data-stu-id="13925-105">1031</span></span>|  
|<span data-ttu-id="13925-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="13925-106">Keywords</span></span>|<span data-ttu-id="13925-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="13925-107">WFRuntime</span></span>|  
|<span data-ttu-id="13925-108">Nível</span><span class="sxs-lookup"><span data-stu-id="13925-108">Level</span></span>|<span data-ttu-id="13925-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="13925-109">Verbose</span></span>|  
|<span data-ttu-id="13925-110">Canal</span><span class="sxs-lookup"><span data-stu-id="13925-110">Channel</span></span>|<span data-ttu-id="13925-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="13925-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13925-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="13925-112">Description</span></span>  
 <span data-ttu-id="13925-113">Indica que um FaultWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="13925-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13925-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="13925-114">Message</span></span>  
 <span data-ttu-id="13925-115">Um FaultWorkItem concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="13925-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="13925-116">A exceção é propagada de atividade “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="13925-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13925-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="13925-117">Details</span></span>  
  
|<span data-ttu-id="13925-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="13925-118">Data Item Name</span></span>|<span data-ttu-id="13925-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="13925-119">Data Item Type</span></span>|<span data-ttu-id="13925-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="13925-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13925-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="13925-121">FaultActivity</span></span>|<span data-ttu-id="13925-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-122">xs:string</span></span>|<span data-ttu-id="13925-123">O nome do tipo de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="13925-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="13925-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="13925-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="13925-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-125">xs:string</span></span>|<span data-ttu-id="13925-126">O nome para exibição de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="13925-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="13925-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="13925-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="13925-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-128">xs:string</span></span>|<span data-ttu-id="13925-129">A identificação de instância de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="13925-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="13925-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="13925-130">ExceptionActivity</span></span>|<span data-ttu-id="13925-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-131">xs:string</span></span>|<span data-ttu-id="13925-132">O nome do tipo de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="13925-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13925-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="13925-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="13925-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-134">xs:string</span></span>|<span data-ttu-id="13925-135">O nome para exibição de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="13925-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13925-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="13925-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="13925-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-137">xs:string</span></span>|<span data-ttu-id="13925-138">A identificação de instância de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="13925-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13925-139">Exceção</span><span class="sxs-lookup"><span data-stu-id="13925-139">Exception</span></span>|<span data-ttu-id="13925-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-140">xs:string</span></span>|<span data-ttu-id="13925-141">Os detalhes de exceção para a exceção</span><span class="sxs-lookup"><span data-stu-id="13925-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="13925-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="13925-142">AppDomain</span></span>|<span data-ttu-id="13925-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="13925-143">xs:string</span></span>|<span data-ttu-id="13925-144">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="13925-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|