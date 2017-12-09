---
title: Controlando perfis
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5bd1a0b5b34c8d812362d492b03e57c73a41c5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="tracking-profiles"></a><span data-ttu-id="87246-102">Controlando perfis</span><span class="sxs-lookup"><span data-stu-id="87246-102">Tracking Profiles</span></span>
<span data-ttu-id="87246-103">Controlando os perfis contêm consultas de rastreamento que permitem um participante de rastreamento assinar eventos de fluxo de trabalho que são emitidas quando o estado de uma instância de fluxo de trabalho se altera em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="87246-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>  
  
## <a name="tracking-profiles"></a><span data-ttu-id="87246-104">Controlando perfis</span><span class="sxs-lookup"><span data-stu-id="87246-104">Tracking Profiles</span></span>  
 <span data-ttu-id="87246-105">Controlando os perfis são usados para especificar que as informações de rastreamento é emitida para uma instância de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="87246-106">Se nenhum perfil for especificado, então todos os eventos de rastreamento são emitidas.</span><span class="sxs-lookup"><span data-stu-id="87246-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="87246-107">Se um perfil for especificado, então os eventos de rastreamento especificados no perfil serão emitidos.</span><span class="sxs-lookup"><span data-stu-id="87246-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="87246-108">Dependendo dos requisitos de monitoramento, você pode escrever um perfil que é muito geral, que assina um pequeno conjunto de alterações de estado de alto nível em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="87246-109">Inversamente, você pode criar um perfil muito detalhado cujos eventos resultantes são muito ricos reconstruir posteriormente um fluxo detalhado de execução.</span><span class="sxs-lookup"><span data-stu-id="87246-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="87246-110">Controlando os perfis manifestam-se como elementos XML em um arquivo de configuração padrão de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ou especificados no código.</span><span class="sxs-lookup"><span data-stu-id="87246-110">Tracking profiles manifest themselves as XML elements within a standard [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration file or specified in code.</span></span> <span data-ttu-id="87246-111">O exemplo a seguir é de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] que controla o perfil em um arquivo de configuração que permite que um participante de rastreamento assine os eventos de fluxo de trabalho `Started` e de `Completed` .</span><span class="sxs-lookup"><span data-stu-id="87246-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <tracking>    
      <trackingProfile name="Sample Tracking Profile">  
        <workflow activityDefinitionId="*">  
          <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                <state name="Started"/>  
                <state name="Completed"/>  
              </states>  
            </workflowInstanceQuery>  
          </workflowInstanceQueries>  
        </workflow>  
      </trackingProfile>          
    </profiles>  
  </tracking>  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="87246-112">O exemplo a seguir mostra o perfil equivalente de rastreamento criado usando código.</span><span class="sxs-lookup"><span data-stu-id="87246-112">The following example shows the equivalent tracking profile created using code.</span></span>  
  
```csharp  
TrackingProfile profile = new TrackingProfile()  
{  
    Name = "CustomTrackingProfile",  
    Queries =   
    {  
        new WorkflowInstanceQuery()  
        {  
            // Limit workflow instance tracking records for started and  
            // completed workflow states.  
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },  
        }  
    }  
};  
```  
  
 <span data-ttu-id="87246-113">Controlando registros são filtrados com o modo de visibilidade em um perfil de rastreamento usando o atributo <xref:System.Activities.Tracking.ImplementationVisibility> .</span><span class="sxs-lookup"><span data-stu-id="87246-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="87246-114">Uma atividade composto é uma atividade de nível superior que contém outras atividades que formam a sua implementação.</span><span class="sxs-lookup"><span data-stu-id="87246-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="87246-115">O modo de visibilidade especifica os registros de rastreamento de atividades emissores compostas em uma atividade de fluxo de trabalho, para especificar se as atividades que formam a implementação estão sendo controladas.</span><span class="sxs-lookup"><span data-stu-id="87246-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span>  <span data-ttu-id="87246-116">O modo de visibilidade se aplica a nível de perfil de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="87246-117">A filtragem de registros de controle para atividades individuais em um fluxo de trabalho é controlada por consultas no perfil de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="87246-118">Para obter mais informações, consulte o **tipos de consulta de perfil de rastreamento** seção neste documento.</span><span class="sxs-lookup"><span data-stu-id="87246-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>  
  
 <span data-ttu-id="87246-119">Os dois modos de visibilidade especificado pelo atributo de `implementationVisibility` no perfil de rastreamento são `RootScope` e `All`.</span><span class="sxs-lookup"><span data-stu-id="87246-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="87246-120">Usar o modo de `RootScope` suprime os registros de controle para as atividades que formam a implementação de uma atividade em casos onde uma atividade composta não é a raiz de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span>  <span data-ttu-id="87246-121">Isso significa que, quando uma atividade que é implementada usando outras atividades é adicionada a um fluxo de trabalho, e `implementationVisibility` definido como RootScope, somente a última atividade de nível superior dentro da atividade composto é rastreada.</span><span class="sxs-lookup"><span data-stu-id="87246-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="87246-122">Se uma atividade é a raiz de fluxo de trabalho, então a implementação da atividade é o próprio fluxo de trabalho e os registros de rastreamento são emitidas para as atividades que formam a implementação.</span><span class="sxs-lookup"><span data-stu-id="87246-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="87246-123">Usar qualquer modo permite que todos os registros de rastreamento ser emitida para atividades raiz e todas as suas atividades compostas.</span><span class="sxs-lookup"><span data-stu-id="87246-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>  
  
 <span data-ttu-id="87246-124">Por exemplo, suponha que *MyActivity* é uma atividade composta cuja implementação contém duas atividades, *atividade1* e *atividade2*.</span><span class="sxs-lookup"><span data-stu-id="87246-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span>  <span data-ttu-id="87246-125">Quando essa atividade é adicionada a um fluxo de trabalho e controle está habilitado com um perfil de rastreamento com `implementationVisibility` definida como `RootScope`, registros de rastreamento são emitidos apenas para *MyActivity*.</span><span class="sxs-lookup"><span data-stu-id="87246-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span>  <span data-ttu-id="87246-126">No entanto, os registros não são emitidos para atividades *atividade1* e *atividade2*.</span><span class="sxs-lookup"><span data-stu-id="87246-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="87246-127">No entanto, se o `implementationVisisbility` de atributo para o perfil de rastreamento é definido como `All`, e registros de rastreamento são emitidos não apenas para *MyActivity*, mas também para atividades *atividade1* e  *Atividade2*.</span><span class="sxs-lookup"><span data-stu-id="87246-127">However, if the `implementationVisisbility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="87246-128">O sinalizador de `implementationVisibility` se aplica aos seguintes tipos de registro de acompanhamento:</span><span class="sxs-lookup"><span data-stu-id="87246-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>  
  
-   <span data-ttu-id="87246-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="87246-129">ActivityStateRecord</span></span>  
  
-   <span data-ttu-id="87246-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="87246-130">FaultPropagationRecord</span></span>  
  
-   <span data-ttu-id="87246-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="87246-131">CancelRequestedRecord</span></span>  
  
-   <span data-ttu-id="87246-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="87246-132">ActivityScheduledRecord</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87246-133">CustomTrackingRecords emitiu-se de implementação de atividade não é filtrado para fora pela configuração de implementationVisibility.</span><span class="sxs-lookup"><span data-stu-id="87246-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>  
  
 <span data-ttu-id="87246-134">A funcionalidade de `implementationVisibility` é especificado como <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> no perfil de rastreamento em código como segue:</span><span class="sxs-lookup"><span data-stu-id="87246-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>  
  
```  
TrackingProfile sampleTrackingProfile = new TrackingProfile()  
{  
    Name = "Sample Tracking Profile",  
    ImplementationVisibility = ImplementationVisibility.RootScope  
};  
```  
  
 <span data-ttu-id="87246-135">A funcionalidade de `implementationVisibility` é especificado como <xref:System.Activities.Tracking.ImplementationVisibility.All> no perfil de rastreamento em um arquivo de configuração como segue:</span><span class="sxs-lookup"><span data-stu-id="87246-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>  
  
```xml  
<tracking>  
      <profiles>  
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">  
          <workflow activityDefinitionId="*">  
...  
         </workflow>  
        </trackingProfile>  
      </profiles>  
</tracking>  
```  
  
 <span data-ttu-id="87246-136">`ImplementationVisibility` que define o perfil de rastreamento é opcional.</span><span class="sxs-lookup"><span data-stu-id="87246-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="87246-137">Por padrão, o valor é definido como `RootScope`.</span><span class="sxs-lookup"><span data-stu-id="87246-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="87246-138">Os valores para este atributo são também maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="87246-138">The values for this attribute are also case-sensitive.</span></span>  
  
### <a name="tracking-profile-query-types"></a><span data-ttu-id="87246-139">Controlando tipos de consulta de perfil</span><span class="sxs-lookup"><span data-stu-id="87246-139">Tracking Profile Query Types</span></span>  
 <span data-ttu-id="87246-140">Controlando os perfis são estruturados como as assinaturas declarativas para controlar os registros que permitem que você possa ver o tempo de execução de fluxo de trabalho para o controle específico registro.</span><span class="sxs-lookup"><span data-stu-id="87246-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="87246-141">Há vários tipos de consulta que permitem autenticação para classes diferentes de objetos de <xref:System.Activities.Tracking.TrackingRecord> .</span><span class="sxs-lookup"><span data-stu-id="87246-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="87246-142">Controlar perfis pode ser especificado na configuração ou com o código.</span><span class="sxs-lookup"><span data-stu-id="87246-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="87246-143">Aqui estão os tipos de consulta mais comuns:</span><span class="sxs-lookup"><span data-stu-id="87246-143">Here are the most common query types:</span></span>  
  
-   <span data-ttu-id="87246-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - use isso para controlar as alterações do ciclo de vida de instância de fluxo de trabalho como `Started` precedente- demonstrado e `Completed`.</span><span class="sxs-lookup"><span data-stu-id="87246-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="87246-145"><xref:System.Activities.Tracking.WorkflowInstanceQuery> é usado para assinar seguintes a <xref:System.Activities.Tracking.TrackingRecord> os objetos:</span><span class="sxs-lookup"><span data-stu-id="87246-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
     <span data-ttu-id="87246-146">Os estados a que pode ser assinado são especificados na classe de <xref:System.Activities.Tracking.WorkflowInstanceStates> .</span><span class="sxs-lookup"><span data-stu-id="87246-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>  
  
     <span data-ttu-id="87246-147">A configuração ou código usada para assinar os registros de acompanhamento de instância nível de fluxo de trabalho do estado da instância de `Started` que usa <xref:System.Activities.Tracking.WorkflowInstanceQuery> são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <workflowInstanceQueries>  
        <workflowInstanceQuery>  
          <states>  
            <state name="Started"/>  
          </states>  
        </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new WorkflowInstanceQuery()  
            {  
                States = { WorkflowInstanceStates.Started}                                                                     
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="87246-148"><xref:System.Activities.Tracking.ActivityStateQuery> - use isso para controlar as alterações do ciclo de vida de atividades que compõem uma instância de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="87246-149">Por exemplo, convém manter o controle de toda vez que a atividade "Enviar email" é concluído em uma instância de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="87246-150">Esta consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.ActivityStateRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="87246-151">Os estados disponíveis para assinar a são especificados em <xref:System.Activities.Tracking.ActivityStates>.</span><span class="sxs-lookup"><span data-stu-id="87246-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>  
  
     <span data-ttu-id="87246-152">A configuração e o código usados para assinar o estado da atividade que controla os registros que usam <xref:System.Activities.Tracking.ActivityStateQuery> para atividades de `SendEmailActivity` são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>  
  
    ```xml  
    <activityStateQueries>  
      <activityStateQuery activityName="SendEmailActivity">  
        <states>  
          <state name="Closed"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new ActivityStateQuery()  
            {                              
                ActivityName = "SendEmailActivity",  
                States = { ActivityStates.Closed }  
            }  
        }  
    };  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="87246-153">Se vários elementos de activityStateQuery têm o mesmo nome, somente os estados no último elemento são usados no perfil de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>  
  
-   <span data-ttu-id="87246-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - esta consulta permite que você controla uma atividade agendada para execução por uma atividade pai.</span><span class="sxs-lookup"><span data-stu-id="87246-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="87246-155">A consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.ActivityScheduledRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>  
  
     <span data-ttu-id="87246-156">A configuração e o código usados para assinar os registros filho relacionados à atividade de `SendEmailActivity` que está sendo agendada usando <xref:System.Activities.Tracking.ActivityScheduledQuery> são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <activityScheduledQueries>  
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
     </activityScheduledQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new ActivityScheduledQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="87246-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - use isso para controlar a manipulação de falhas que ocorrem dentro de uma atividade.</span><span class="sxs-lookup"><span data-stu-id="87246-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="87246-158">A consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.FaultPropagationRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>  
  
     <span data-ttu-id="87246-159">A configuração e o código usados para assinar os registros relacionados à propagação de falha que usa <xref:System.Activities.Tracking.FaultPropagationQuery> são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <faultPropagationQueries>  
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />  
    </faultPropagationQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new FaultPropagationQuery()  
            {  
                FaultSourceActivityName = "SendEmailActivity",  
                FaultHandlerActivityName = "NotificationsFaultHandler"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="87246-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - use isso para controlar solicitações cancelar uma atividade filho pela atividade pai.</span><span class="sxs-lookup"><span data-stu-id="87246-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="87246-161">A consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.CancelRequestedRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>  
  
     <span data-ttu-id="87246-162">A configuração e o código usado para assinar os registros relacionados ao uso de cancelamento de atividade <xref:System.Activities.Tracking.CancelRequestedQuery> é mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <cancelRequestedQueries>  
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
    </cancelRequestedQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CancelRequestedQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="87246-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - use isso para eventos de rastreamento que você define nas atividades de código.</span><span class="sxs-lookup"><span data-stu-id="87246-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="87246-164">A consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.CustomTrackingRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>  
  
     <span data-ttu-id="87246-165">A configuração e o código usados para assinar os registros relacionados aos registros personalizados de rastreamento que usam <xref:System.Activities.Tracking.CustomTrackingQuery> são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <customTrackingQueries>  
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />  
    </customTrackingQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CustomTrackingQuery()   
            {  
                Name = "EmailAddress",  
                ActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="87246-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - use isso para controlar a ressunção de um indexador em uma instância de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="87246-167">Esta consulta é necessária para que <xref:System.Activities.Tracking.TrackingParticipant> assine a <xref:System.Activities.Tracking.BookmarkResumptionRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="87246-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>  
  
     <span data-ttu-id="87246-168">A configuração e o código usados para assinar os registros relacionados à ressunção do indexador que usa <xref:System.Activities.Tracking.BookmarkResumptionQuery> são mostrados no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <bookmarkResumptionQueries>  
      <bookmarkResumptionQuery name="SentEmailBookmark" />  
    </bookmarkResumptionQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new BookmarkResumptionQuery()  
            {  
                Name = "sentEmailBookmark"  
            }  
        }  
    };  
    ```  
  
### <a name="annotations"></a><span data-ttu-id="87246-169">Anotações</span><span class="sxs-lookup"><span data-stu-id="87246-169">Annotations</span></span>  
 <span data-ttu-id="87246-170">As anotações permitem que você marca arbitrariamente registros de rastreamento com um valor que pode ser configurado após tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="87246-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="87246-171">Por exemplo, convém vários registros de rastreamento em vários fluxos de trabalho sejam marcados com "Servidor de email" = = "Email Server1".</span><span class="sxs-lookup"><span data-stu-id="87246-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="87246-172">Isso facilita localizar todos os registros com essa marca ao consultar o rastreamento registra posteriormente.</span><span class="sxs-lookup"><span data-stu-id="87246-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
 <span data-ttu-id="87246-173">Para fazer isso, uma anotação é adicionada a uma consulta de rastreamento conforme mostrado no exemplo o seguir.</span><span class="sxs-lookup"><span data-stu-id="87246-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="87246-174">Como criar um perfil de rastreamento</span><span class="sxs-lookup"><span data-stu-id="87246-174">How to Create a Tracking Profile</span></span>  
 <span data-ttu-id="87246-175">Controlando a consulta elementos são usados para criar um perfil de rastreamento usando um arquivo de configuração XML ou código de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87246-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]code.</span></span>  <span data-ttu-id="87246-176">Aqui está um exemplo de um perfil de rastreamento criado usando um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="87246-176">Here is an example of a tracking profile created using a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>  
    <profiles>  
      <trackingProfile name="Sample Tracking Profile ">  
        <workflow activityDefinitionId="*">  
          <!--Specify the tracking profile query elements to subscribe for tracking records-->  
        </workflow>  
      </trackingProfile>  
    </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
> [!WARNING]
>  <span data-ttu-id="87246-177">Para um WF usando o host serviço de fluxo de trabalho, o perfil de rastreamento é normalmente criado usando um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="87246-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="87246-178">Também é possível criar um perfil de rastreamento com o código usando o perfil de rastreamento e a consulta API de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>  
  
 <span data-ttu-id="87246-179">Um perfil configurado como um arquivo de configuração XML é aplicado a um participante de rastreamento que usa uma extensão de comportamento.</span><span class="sxs-lookup"><span data-stu-id="87246-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="87246-180">Isso é adicionado a um WorkflowServiceHost conforme descrito na seção posterior [configurar rastreamento para um fluxo de trabalho](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="87246-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="87246-181">A verbosidade de registros de rastreamento emissores pelo host é determinada pelas configurações dentro do perfil de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="87246-182">Um participante de rastreamento assina controlar registros adicionando consultas a um perfil de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="87246-183">Para assinar todos os registros de controle, é necessário especificar todas as consultas de controle usando o perfil de rastreamento "*" nos campos nome de cada uma das consultas.</span><span class="sxs-lookup"><span data-stu-id="87246-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "*" in the name fields in each of the queries.</span></span>  
  
 <span data-ttu-id="87246-184">Aqui estão alguns dos exemplos comuns de perfis de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-184">Here are some of the common examples of tracking profiles.</span></span>  
  
-   <span data-ttu-id="87246-185">Um perfil de controle para obter registros e falhas de instância de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87246-185">A tracking profile to obtain workflow instance records and faults.</span></span>  
  
```xml  
<trackingProfile name="Instance and Fault Records">  
  <workflow activityDefinitionId="*">  
    <workflowInstanceQueries>  
      <workflowInstanceQuery>  
        <states>  
          <state name="*" />  
        </states>  
      </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    <activityStateQueries>  
      <activityStateQuery activityName="*">  
        <states>  
          <state name="Faulted"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  </workflow>  
</trackingProfile>  
```  
  
1.  <span data-ttu-id="87246-186">Um perfil de rastreamento para obter todos os registros personalizados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87246-186">A tracking profile to obtain all custom tracking records.</span></span>  
  
```xml  
<trackingProfile name="Instance_And_Custom_Records">  
  <workflow activityDefinitionId="*">  
    <customTrackingQueries>  
      <customTrackingQuery name="*" activityName="*" />  
    </customTrackingQueries>  
  </workflow>  
</trackingProfile>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87246-187">Consulte também</span><span class="sxs-lookup"><span data-stu-id="87246-187">See Also</span></span>  
 [<span data-ttu-id="87246-188">Rastreamento de SQL</span><span class="sxs-lookup"><span data-stu-id="87246-188">SQL Tracking</span></span>](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)  
 [<span data-ttu-id="87246-189">Monitoramento do Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="87246-189">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="87246-190">Monitoramento de aplicativos com App Fabric</span><span class="sxs-lookup"><span data-stu-id="87246-190">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)