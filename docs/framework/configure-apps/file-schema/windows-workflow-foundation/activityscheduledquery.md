---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32b0e1b068e1f6fef3ce18b0e4dfa628ccaa8a79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="3581c-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3581c-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="3581c-103">Representa uma coleção de consultas que são usados para controlar uma atividade agendada para execução por uma atividade pai.</span><span class="sxs-lookup"><span data-stu-id="3581c-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3581c-104">A consulta é necessária para um participante de rastreamento assinar os registros de atividade agendada.</span><span class="sxs-lookup"><span data-stu-id="3581c-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3581c-105">Para obter mais informações sobre consultas de perfil de controle, consulte [perfis de controle](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3581c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3581c-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3581c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3581c-107">\<controle ></span><span class="sxs-lookup"><span data-stu-id="3581c-107">\<tracking></span></span>  
<span data-ttu-id="3581c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3581c-108">\<trackingProfile></span></span>  
<span data-ttu-id="3581c-109">\<fluxo de trabalho ></span><span class="sxs-lookup"><span data-stu-id="3581c-109">\<workflow></span></span>  
<span data-ttu-id="3581c-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="3581c-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="3581c-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3581c-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3581c-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3581c-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3581c-113">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3581c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3581c-114">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="3581c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3581c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3581c-115">Attributes</span></span>  
  
|<span data-ttu-id="3581c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3581c-116">Attribute</span></span>|<span data-ttu-id="3581c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="3581c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3581c-118">Nome_da_atividade</span><span class="sxs-lookup"><span data-stu-id="3581c-118">activityName</span></span>|<span data-ttu-id="3581c-119">Uma cadeia de caracteres que especifica o nome da atividade que está solicitando o cancelamento.</span><span class="sxs-lookup"><span data-stu-id="3581c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3581c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3581c-120">childActivityName</span></span>|<span data-ttu-id="3581c-121">Uma cadeia de caracteres que especifica o nome da atividade filho para o qual o cancelamento foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="3581c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3581c-122">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="3581c-122">Child Elements</span></span>  
 <span data-ttu-id="3581c-123">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3581c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3581c-124">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="3581c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3581c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3581c-125">Element</span></span>|<span data-ttu-id="3581c-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="3581c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3581c-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3581c-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="3581c-128">Uma consulta que é usada para controlar uma atividade agendada para execução por uma atividade pai.</span><span class="sxs-lookup"><span data-stu-id="3581c-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3581c-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3581c-129">See Also</span></span>  
 <span data-ttu-id="3581c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3581c-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3581c-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3581c-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3581c-132">Acompanhamento e rastreamento de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="3581c-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3581c-133">Acompanhando perfis</span><span class="sxs-lookup"><span data-stu-id="3581c-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)