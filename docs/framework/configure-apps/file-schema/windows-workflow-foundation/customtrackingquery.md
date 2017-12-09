---
title: '&lt;customTrackingQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 908c340167d50d4d16e0eeff7cc2e01290b55e7a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="48a9d-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="48a9d-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="48a9d-103">Representa uma coleção de consultas que são usados para controlar os eventos que você define em suas atividades de código.</span><span class="sxs-lookup"><span data-stu-id="48a9d-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="48a9d-104">A consulta é necessária para um participante de rastreamento assinar registros personalizados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="48a9d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="48a9d-105">Para obter mais informações sobre consultas de perfil de controle, consulte [perfis de controle](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="48a9d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="48a9d-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="48a9d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="48a9d-107">\<controle ></span><span class="sxs-lookup"><span data-stu-id="48a9d-107">\<tracking></span></span>  
<span data-ttu-id="48a9d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="48a9d-108">\<trackingProfile></span></span>  
<span data-ttu-id="48a9d-109">\<fluxo de trabalho ></span><span class="sxs-lookup"><span data-stu-id="48a9d-109">\<workflow></span></span>  
<span data-ttu-id="48a9d-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="48a9d-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="48a9d-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="48a9d-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48a9d-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="48a9d-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48a9d-113">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="48a9d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="48a9d-114">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="48a9d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48a9d-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="48a9d-115">Attributes</span></span>  
  
|<span data-ttu-id="48a9d-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="48a9d-116">Attribute</span></span>|<span data-ttu-id="48a9d-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="48a9d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48a9d-118">Nome_da_atividade</span><span class="sxs-lookup"><span data-stu-id="48a9d-118">activityName</span></span>|<span data-ttu-id="48a9d-119">Uma cadeia de caracteres que especifica o nome da atividade que gerou o registro de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="48a9d-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="48a9d-120">name</span><span class="sxs-lookup"><span data-stu-id="48a9d-120">name</span></span>|<span data-ttu-id="48a9d-121">Uma cadeia de caracteres que especifica o nome do registro de controle personalizado que é emitido.</span><span class="sxs-lookup"><span data-stu-id="48a9d-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48a9d-122">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="48a9d-122">Child Elements</span></span>  
 <span data-ttu-id="48a9d-123">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="48a9d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48a9d-124">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="48a9d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="48a9d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="48a9d-125">Element</span></span>|<span data-ttu-id="48a9d-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="48a9d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48a9d-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="48a9d-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="48a9d-128">Uma consulta que é usada para controlar os eventos que você define em suas atividades de código.</span><span class="sxs-lookup"><span data-stu-id="48a9d-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48a9d-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="48a9d-129">See Also</span></span>  
 <span data-ttu-id="48a9d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="48a9d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="48a9d-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="48a9d-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="48a9d-132">Acompanhamento e rastreamento de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="48a9d-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="48a9d-133">Acompanhando perfis</span><span class="sxs-lookup"><span data-stu-id="48a9d-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)