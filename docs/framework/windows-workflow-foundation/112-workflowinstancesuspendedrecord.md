---
title: 112 - WorkflowInstanceSuspendedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc825c7c-8c90-48f7-9336-9a978a8246c6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b62d4c55f216ccb09d14515800fccd29fe974
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="112---workflowinstancesuspendedrecord"></a><span data-ttu-id="4014c-102">112 - WorkflowInstanceSuspendedRecord</span><span class="sxs-lookup"><span data-stu-id="4014c-102">112 - WorkflowInstanceSuspendedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="4014c-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4014c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4014c-104">Id</span><span class="sxs-lookup"><span data-stu-id="4014c-104">Id</span></span>|<span data-ttu-id="4014c-105">112</span><span class="sxs-lookup"><span data-stu-id="4014c-105">112</span></span>|  
|<span data-ttu-id="4014c-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4014c-106">Keywords</span></span>|<span data-ttu-id="4014c-107">EndToEndMonitoring, solução de problemas, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="4014c-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="4014c-108">Nível</span><span class="sxs-lookup"><span data-stu-id="4014c-108">Level</span></span>|<span data-ttu-id="4014c-109">Informações</span><span class="sxs-lookup"><span data-stu-id="4014c-109">Information</span></span>|  
|<span data-ttu-id="4014c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4014c-110">Channel</span></span>|<span data-ttu-id="4014c-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="4014c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4014c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4014c-112">Description</span></span>  
 <span data-ttu-id="4014c-113">Este evento é emitido pelo participante de rastreamento de ETW quando uma instância de fluxo de trabalho se chama o registro de WorkflowInstanceSuspended.</span><span class="sxs-lookup"><span data-stu-id="4014c-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4014c-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="4014c-114">Message</span></span>  
 <span data-ttu-id="4014c-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, razão = %5, anotações = %6 ProfileName, %7 =</span><span class="sxs-lookup"><span data-stu-id="4014c-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7</span></span>  
  
## <a name="details"></a><span data-ttu-id="4014c-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4014c-116">Details</span></span>  
  
|<span data-ttu-id="4014c-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="4014c-117">Data Item Name</span></span>|<span data-ttu-id="4014c-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="4014c-118">Data Item Type</span></span>|<span data-ttu-id="4014c-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="4014c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4014c-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4014c-120">InstanceId</span></span>|<span data-ttu-id="4014c-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="4014c-121">xs:GUID</span></span>|<span data-ttu-id="4014c-122">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="4014c-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4014c-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="4014c-123">RecordNumber</span></span>|<span data-ttu-id="4014c-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="4014c-124">xs:long</span></span>|<span data-ttu-id="4014c-125">O número de sequência do registro emitido</span><span class="sxs-lookup"><span data-stu-id="4014c-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="4014c-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="4014c-126">EventTime</span></span>|<span data-ttu-id="4014c-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="4014c-127">xs:dateTime</span></span>|<span data-ttu-id="4014c-128">A hora UTC quando o evento foi emitido</span><span class="sxs-lookup"><span data-stu-id="4014c-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="4014c-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="4014c-129">ActivityDefinitionId</span></span>|<span data-ttu-id="4014c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-130">xs:string</span></span>|<span data-ttu-id="4014c-131">O nome da atividade raiz no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="4014c-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="4014c-132">Motivo</span><span class="sxs-lookup"><span data-stu-id="4014c-132">Reason</span></span>|<span data-ttu-id="4014c-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-133">xs:string</span></span>|<span data-ttu-id="4014c-134">A razão para o fluxo de trabalho foi suspendida</span><span class="sxs-lookup"><span data-stu-id="4014c-134">The reason the workflow was suspended</span></span>|  
|<span data-ttu-id="4014c-135">Anotações</span><span class="sxs-lookup"><span data-stu-id="4014c-135">Annotations</span></span>|<span data-ttu-id="4014c-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-136">xs:string</span></span>|<span data-ttu-id="4014c-137">As anotações que foram adicionadas a este evento.</span><span class="sxs-lookup"><span data-stu-id="4014c-137">The annotations that were added to this event.</span></span>  <span data-ttu-id="4014c-138">Os valores são armazenados em um elemento xml no formato \<itens >\< nome do item = "annotationName" type="System.String" > annotationValue\</item > \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="4014c-138">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="4014c-139">Se nenhuma anotação é especificada, em seguida, a cadeia de caracteres contém \<itens / >.</span><span class="sxs-lookup"><span data-stu-id="4014c-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="4014c-140">O tamanho do evento de ETW é limitado pelo tamanho do buffer de ETW ou pela carga máxima útil para um evento de ETW.</span><span class="sxs-lookup"><span data-stu-id="4014c-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="4014c-141">Se o tamanho do evento excede os limites ETW, o evento é truncado descartando as anotações e substituindo o valor anotação com \<itens >...  \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="4014c-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="4014c-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="4014c-142">ProfileName</span></span>|<span data-ttu-id="4014c-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-143">xs:string</span></span>|<span data-ttu-id="4014c-144">O nome ou o perfil de rastreamento que levam a este evento que está sendo emitido</span><span class="sxs-lookup"><span data-stu-id="4014c-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="4014c-145">HostReference</span><span class="sxs-lookup"><span data-stu-id="4014c-145">HostReference</span></span>|<span data-ttu-id="4014c-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-146">xs:string</span></span>|<span data-ttu-id="4014c-147">Hospedados para serviços da Web, este campo identifica unicamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="4014c-147">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="4014c-148">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName' exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'</span><span class="sxs-lookup"><span data-stu-id="4014c-148">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="4014c-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4014c-149">AppDomain</span></span>|<span data-ttu-id="4014c-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="4014c-150">xs:string</span></span>|<span data-ttu-id="4014c-151">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4014c-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|