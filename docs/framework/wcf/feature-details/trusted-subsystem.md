---
title: "Subsistema de confiança"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1f5ce46b-e259-4bc9-a0b9-89d06fc9341c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3d4979513df5eb6908974480a19374a5c6a2233
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="trusted-subsystem"></a><span data-ttu-id="21b21-102">Subsistema de confiança</span><span class="sxs-lookup"><span data-stu-id="21b21-102">Trusted Subsystem</span></span>
<span data-ttu-id="21b21-103">Um cliente acessa um ou mais serviços Web que são distribuídos em uma rede.</span><span class="sxs-lookup"><span data-stu-id="21b21-103">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="21b21-104">Os serviços Web são projetados para que o acesso aos recursos adicionais (como bancos de dados ou outros serviços da Web) é encapsulado na lógica de negócios do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="21b21-104">The Web services are designed so that access to additional resources (such as databases or other Web services) is encapsulated in the business logic of the Web service.</span></span> <span data-ttu-id="21b21-105">Esses recursos devem ser protegidos contra acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="21b21-105">These resources must be protected against unauthorized access.</span></span> <span data-ttu-id="21b21-106">A ilustração a seguir mostra um processo de subsistema confiável.</span><span class="sxs-lookup"><span data-stu-id="21b21-106">The following illustration depicts a trusted subsystem process.</span></span>  
  
 <span data-ttu-id="21b21-107">![Confiável subsistema](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span><span class="sxs-lookup"><span data-stu-id="21b21-107">![Trusted subsystem](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span></span>  
  
 <span data-ttu-id="21b21-108">As etapas a seguir descrevem o processo de subsistema confiável conforme ilustrado:</span><span class="sxs-lookup"><span data-stu-id="21b21-108">The following steps describe the trusted subsystem process as illustrated:</span></span>  
  
1.  <span data-ttu-id="21b21-109">O cliente envia uma solicitação para o subsistema confiável, juntamente com as credenciais.</span><span class="sxs-lookup"><span data-stu-id="21b21-109">The client submits a request to the trusted subsystem, along with credentials.</span></span>  
  
2.  <span data-ttu-id="21b21-110">Subsistema confiável autentica e autoriza o usuário.</span><span class="sxs-lookup"><span data-stu-id="21b21-110">The trusted subsystem authenticates and authorizes the user.</span></span>  
  
3.  <span data-ttu-id="21b21-111">Subsistema confiável envia uma mensagem de solicitação para o recurso remoto.</span><span class="sxs-lookup"><span data-stu-id="21b21-111">The trusted subsystem sends a request message to the remote resource.</span></span> <span data-ttu-id="21b21-112">Essa solicitação é acompanhada pelas credenciais para o subsistema confiável (ou a conta de serviço sob a qual o processo do subsistema confiável está sendo executado).</span><span class="sxs-lookup"><span data-stu-id="21b21-112">This request is accompanied by the credentials for the trusted subsystem (or the service account under which the trusted subsystem process is being executed).</span></span>  
  
4.  <span data-ttu-id="21b21-113">O recurso de back-end autentica e autoriza o subsistema confiável.</span><span class="sxs-lookup"><span data-stu-id="21b21-113">The back-end resource authenticates and authorizes the trusted subsystem.</span></span> <span data-ttu-id="21b21-114">Em seguida, ele processa a solicitação e envia uma resposta para o subsistema confiável.</span><span class="sxs-lookup"><span data-stu-id="21b21-114">It then processes the request and issues a response to the trusted subsystem.</span></span>  
  
5.  <span data-ttu-id="21b21-115">Subsistema confiável processa a resposta e emite sua própria resposta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="21b21-115">The trusted subsystem processes the response and issues its own response to the client.</span></span>  
  
|<span data-ttu-id="21b21-116">Característica</span><span class="sxs-lookup"><span data-stu-id="21b21-116">Characteristic</span></span>|<span data-ttu-id="21b21-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="21b21-117">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="21b21-118">Modo de segurança</span><span class="sxs-lookup"><span data-stu-id="21b21-118">Security Mode</span></span>|<span data-ttu-id="21b21-119">Mensagem</span><span class="sxs-lookup"><span data-stu-id="21b21-119">Message</span></span>|  
|<span data-ttu-id="21b21-120">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="21b21-120">Interoperability</span></span>|[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="21b21-121">somente.</span><span class="sxs-lookup"><span data-stu-id="21b21-121"> only.</span></span>|  
|<span data-ttu-id="21b21-122">Autenticação (serviço)</span><span class="sxs-lookup"><span data-stu-id="21b21-122">Authentication (service)</span></span>|<span data-ttu-id="21b21-123">Serviço de token de segurança autentica e autoriza os clientes.</span><span class="sxs-lookup"><span data-stu-id="21b21-123">Security token service authenticates and authorizes clients.</span></span>|  
|<span data-ttu-id="21b21-124">Autenticação (cliente)</span><span class="sxs-lookup"><span data-stu-id="21b21-124">Authentication (client)</span></span>|<span data-ttu-id="21b21-125">Subsistema confiável autentica o cliente e o recurso autentica o serviço do subsistema confiável.</span><span class="sxs-lookup"><span data-stu-id="21b21-125">The trusted subsystem authenticates the client and the resource authenticates the trusted subsystem service.</span></span>|  
|<span data-ttu-id="21b21-126">Integridade</span><span class="sxs-lookup"><span data-stu-id="21b21-126">Integrity</span></span>|<span data-ttu-id="21b21-127">Sim</span><span class="sxs-lookup"><span data-stu-id="21b21-127">Yes</span></span>|  
|<span data-ttu-id="21b21-128">Confidencialidade</span><span class="sxs-lookup"><span data-stu-id="21b21-128">Confidentiality</span></span>|<span data-ttu-id="21b21-129">Sim</span><span class="sxs-lookup"><span data-stu-id="21b21-129">Yes</span></span>|  
|<span data-ttu-id="21b21-130">Transporte</span><span class="sxs-lookup"><span data-stu-id="21b21-130">Transport</span></span>|<span data-ttu-id="21b21-131">HTTP entre o cliente e o serviço do subsistema confiável.</span><span class="sxs-lookup"><span data-stu-id="21b21-131">HTTP between client and the trusted subsystem service.</span></span><br /><br /> <span data-ttu-id="21b21-132">NET. TCP entre o serviço do subsistema confiável e o recurso (serviço de back-end).</span><span class="sxs-lookup"><span data-stu-id="21b21-132">NET.TCP between trusted subsystem service and the resource (back-end service).</span></span>|  
|<span data-ttu-id="21b21-133">Associação</span><span class="sxs-lookup"><span data-stu-id="21b21-133">Binding</span></span>|<span data-ttu-id="21b21-134"><xref:System.ServiceModel.WSHttpBinding>e <xref:System.ServiceModel.NetTcpBinding> [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="21b21-134"><xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span></span>|  
  
## <a name="resource-back-end-service"></a><span data-ttu-id="21b21-135">Recursos (serviço de Back-End)</span><span class="sxs-lookup"><span data-stu-id="21b21-135">Resource (Back-End Service)</span></span>  
  
### <a name="code"></a><span data-ttu-id="21b21-136">Código</span><span class="sxs-lookup"><span data-stu-id="21b21-136">Code</span></span>  
 <span data-ttu-id="21b21-137">O código a seguir mostra como criar um ponto de extremidade de serviço para o recurso, que usa a segurança de transporte por meio do protocolo de transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="21b21-137">The following code shows how to create a service endpoint for the resource, which uses transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystemsResource#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsresource/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsResource#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsresource/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="21b21-138">Configuração</span><span class="sxs-lookup"><span data-stu-id="21b21-138">Configuration</span></span>  
 <span data-ttu-id="21b21-139">A configuração a seguir define o mesmo ponto de extremidade usando a configuração.</span><span class="sxs-lookup"><span data-stu-id="21b21-139">The following configuration sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.BackendService"  
               behaviorConfiguration="BackendServiceBehavior">  
        <endpoint address="net.tcp://localhost.com:8001/BackendService"  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="BackendServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, BackendService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="trusted-subsystem"></a><span data-ttu-id="21b21-140">Subsistema de confiança</span><span class="sxs-lookup"><span data-stu-id="21b21-140">Trusted Subsystem</span></span>  
  
### <a name="code"></a><span data-ttu-id="21b21-141">Código</span><span class="sxs-lookup"><span data-stu-id="21b21-141">Code</span></span>  
 <span data-ttu-id="21b21-142">O código a seguir mostra como criar um ponto de extremidade de serviço para o subsistema confiável que usa segurança de mensagem através do protocolo HTTP e um nome de usuário e senha para autenticação.</span><span class="sxs-lookup"><span data-stu-id="21b21-142">The following code shows how to create a service endpoint for the trusted subsystem that uses message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystems#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#1)]
 [!code-vb[TrustedSubSystems#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#1)]  
  
 <span data-ttu-id="21b21-143">O código a seguir mostra um serviço em um subsistema confiável que se comunica com um serviço de back-end usando a segurança de transporte por meio do protocolo de transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="21b21-143">The following code shows a service in a trusted subsystem that communicates with a back-end service using transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystems#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#2)]
 [!code-vb[TrustedSubSystems#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="21b21-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="21b21-144">Configuration</span></span>  
 <span data-ttu-id="21b21-145">A configuração a seguir define o mesmo ponto de extremidade usando a configuração.</span><span class="sxs-lookup"><span data-stu-id="21b21-145">The following configuration sets up the same endpoint using configuration.</span></span> <span data-ttu-id="21b21-146">Observe as duas ligações: uma protege o serviço hospedado no subsistema confiável e o outro se comunica entre o subsistema confiável e o serviço de back-end.</span><span class="sxs-lookup"><span data-stu-id="21b21-146">Note the two bindings: One secures the service hosted in the trusted subsystem and the other communicates between the trusted subsystem and the back-end service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.FacadeService"  
               behaviorConfiguration="FacadeServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/FacadeService"/>  
          </baseAddresses>  
        </host>  
        <endpoint address="http://localhost:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <client>  
      <endpoint name=""   
                address="net.tcp://contoso.com:8001/BackendService"  
                binding="customBinding"  
                bindingConfiguration="ClientBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
      <customBinding>  
        <binding name="ClientBinding">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="FacadeServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                storeLocation="LocalMachine"  
                                storeName="My"  
                                x509FindType="FindBySubjectName" />  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, FacadeService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="21b21-147">Cliente</span><span class="sxs-lookup"><span data-stu-id="21b21-147">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="21b21-148">Código</span><span class="sxs-lookup"><span data-stu-id="21b21-148">Code</span></span>  
 <span data-ttu-id="21b21-149">O código a seguir mostra como criar o cliente se comunica com o subsistema confiável usando segurança de mensagem sobre o protocolo HTTP e um nome de usuário e senha para autenticação.</span><span class="sxs-lookup"><span data-stu-id="21b21-149">The following code shows how to create the client that communicates with the trusted subsystem by using message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystemsClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsclient/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsclient/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="21b21-150">Configuração</span><span class="sxs-lookup"><span data-stu-id="21b21-150">Configuration</span></span>  
 <span data-ttu-id="21b21-151">O código a seguir configura o cliente para usar segurança de mensagem através do protocolo HTTP e um nome de usuário e senha para autenticação.</span><span class="sxs-lookup"><span data-stu-id="21b21-151">The following code configures the client to use message security over the HTTP protocol and a user name and password for authentication.</span></span> <span data-ttu-id="21b21-152">O nome de usuário e a senha só podem ser especificados usando o código (não é configurável).</span><span class="sxs-lookup"><span data-stu-id="21b21-152">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <client>  
        <endpoint name=""   
                  address="http://www.cohowinery.com:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientUserNameBehavior"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientUserNameBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21b21-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="21b21-153">See Also</span></span>  
 [<span data-ttu-id="21b21-154">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="21b21-154">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="21b21-155">Modelo de segurança para o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="21b21-155">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)