---
title: elemento &lt;serviceAuthorization&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bc04552b9b2ecd85a520ed16ae9a6ee0dfc98a46
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="4dae5-102">elemento &lt;serviceAuthorization&gt;</span><span class="sxs-lookup"><span data-stu-id="4dae5-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="4dae5-103">Especifica configurações que autorizam o acesso a operações de serviço</span><span class="sxs-lookup"><span data-stu-id="4dae5-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="4dae5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4dae5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4dae5-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="4dae5-105">\<behaviors></span></span>  
<span data-ttu-id="4dae5-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4dae5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4dae5-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4dae5-107">\<behavior></span></span>  
<span data-ttu-id="4dae5-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="4dae5-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dae5-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dae5-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dae5-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4dae5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4dae5-111">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="4dae5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dae5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4dae5-112">Attributes</span></span>  
  
|<span data-ttu-id="4dae5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4dae5-113">Attribute</span></span>|<span data-ttu-id="4dae5-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dae5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4dae5-115">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="4dae5-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="4dae5-116">Um valor booleano que especifica se todas as operações no serviço de representar o chamador.</span><span class="sxs-lookup"><span data-stu-id="4dae5-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="4dae5-117">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="4dae5-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="4dae5-118">Quando uma operação de serviço específico representará o chamador, o contexto do thread é alternado para o contexto do chamador antes de executar o serviço especificado.</span><span class="sxs-lookup"><span data-stu-id="4dae5-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="4dae5-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="4dae5-119">principalPermissionMode</span></span>|<span data-ttu-id="4dae5-120">Define a entidade de segurança usada para executar operações no servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae5-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="4dae5-121">Os valores incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dae5-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="4dae5-122">-Nenhum</span><span class="sxs-lookup"><span data-stu-id="4dae5-122">-   None</span></span><br /><span data-ttu-id="4dae5-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="4dae5-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="4dae5-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="4dae5-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="4dae5-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="4dae5-125">-   Custom</span></span><br /><br /> <span data-ttu-id="4dae5-126">O valor padrão é UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="4dae5-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="4dae5-127">O valor é do tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="4dae5-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="4dae5-128">Para obter mais informações sobre como usar esse atributo, consulte [como: restringir o acesso com a PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="4dae5-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="4dae5-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="4dae5-129">roleProviderName</span></span>|<span data-ttu-id="4dae5-130">Uma cadeia de caracteres que especifica o nome do provedor de função, que fornece informações de função para um aplicativo do Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4dae5-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4dae5-131">O padrão é uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="4dae5-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="4dae5-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="4dae5-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="4dae5-133">Uma cadeia de caracteres que contém o tipo do Gerenciador de autorização de serviço.</span><span class="sxs-lookup"><span data-stu-id="4dae5-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="4dae5-134">Para obter mais informações, consulte <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="4dae5-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dae5-135">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4dae5-135">Child Elements</span></span>  
  
|<span data-ttu-id="4dae5-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dae5-136">Element</span></span>|<span data-ttu-id="4dae5-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dae5-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dae5-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="4dae5-138">authorizationPolicies</span></span>|<span data-ttu-id="4dae5-139">Contém uma coleção de tipos de política de autorização, que pode ser adicionado usando o `add` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="4dae5-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="4dae5-140">Cada política de autorização contém um único necessário `policyType` atributo que é uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4dae5-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4dae5-141">O atributo especifica uma política de autorização, que permite que a transformação de um conjunto de declarações de entrada em outro conjunto de declarações.</span><span class="sxs-lookup"><span data-stu-id="4dae5-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4dae5-142">Controle de acesso pode ser concedido ou negado com base no que.</span><span class="sxs-lookup"><span data-stu-id="4dae5-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4dae5-143">Para obter mais informações, consulte <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="4dae5-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4dae5-144">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4dae5-144">Parent Elements</span></span>  
  
|<span data-ttu-id="4dae5-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dae5-145">Element</span></span>|<span data-ttu-id="4dae5-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dae5-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dae5-147">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4dae5-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4dae5-148">Contém uma coleção de configurações para o comportamento de um serviço.</span><span class="sxs-lookup"><span data-stu-id="4dae5-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dae5-149">Comentários</span><span class="sxs-lookup"><span data-stu-id="4dae5-149">Remarks</span></span>  
 <span data-ttu-id="4dae5-150">Esta seção contém os elementos que afetam a autorização, provedores de função personalizada e representação.</span><span class="sxs-lookup"><span data-stu-id="4dae5-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="4dae5-151">O `principalPermissionMode` atributo especifica os grupos de usuários para usar ao autorizar o uso de um método protegido.</span><span class="sxs-lookup"><span data-stu-id="4dae5-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="4dae5-152">O valor padrão é `UseWindowsGroups` e especifica que os grupos do Windows, como "Administradores" ou "Usuários" são pesquisados para uma tentativa de acessar um recurso de identidade.</span><span class="sxs-lookup"><span data-stu-id="4dae5-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="4dae5-153">Você também pode especificar `UseAspNetRoles` para usar um provedor de função personalizada que está configurado com o \<System. Web > elemento, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="4dae5-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 <span data-ttu-id="4dae5-154">O código a seguir mostra o `roleProviderName` usado com o `principalPermissionMode` atributo.</span><span class="sxs-lookup"><span data-stu-id="4dae5-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 <span data-ttu-id="4dae5-155">Para obter um exemplo detalhado de como usar este elemento de configuração, consulte [autorizar o acesso a operações de serviço](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) e [política de autorização](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4dae5-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dae5-156">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4dae5-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="4dae5-157">Comportamentos de segurança</span><span class="sxs-lookup"><span data-stu-id="4dae5-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="4dae5-158">Autorizando o acesso a operações de serviço</span><span class="sxs-lookup"><span data-stu-id="4dae5-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="4dae5-159">Como: criar um Gerenciador de autorização personalizada para um serviço</span><span class="sxs-lookup"><span data-stu-id="4dae5-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 <span data-ttu-id="4dae5-160">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md) (Como restringir o acesso com a classe PrincipalPermissionAttribute)</span><span class="sxs-lookup"><span data-stu-id="4dae5-160">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>  
 [<span data-ttu-id="4dae5-161">Política de autorização</span><span class="sxs-lookup"><span data-stu-id="4dae5-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)