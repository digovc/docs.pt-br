---
title: '&lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f62a43f1f8d3d025f62efca341c35e4af590abd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="53686-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="53686-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="53686-103">Representa uma coleção de certificados x. 509 que são fornecidos para autenticar as credenciais de segurança emitidas a partir de um Token de segurança serviço (STS).</span><span class="sxs-lookup"><span data-stu-id="53686-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="53686-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="53686-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53686-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="53686-105">\<behaviors></span></span>  
<span data-ttu-id="53686-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="53686-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="53686-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="53686-107">\<behavior></span></span>  
<span data-ttu-id="53686-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="53686-108">\<serviceCredentials></span></span>  
<span data-ttu-id="53686-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="53686-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="53686-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="53686-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53686-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53686-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53686-112">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="53686-112">Attributes and Elements</span></span>  
 <span data-ttu-id="53686-113">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="53686-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53686-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="53686-114">Attributes</span></span>  
 <span data-ttu-id="53686-115">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="53686-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53686-116">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="53686-116">Child Elements</span></span>  
  
|<span data-ttu-id="53686-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="53686-117">Element</span></span>|<span data-ttu-id="53686-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="53686-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53686-119">\<add></span><span class="sxs-lookup"><span data-stu-id="53686-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="53686-120">Adiciona um certificado x. 509 à coleção.</span><span class="sxs-lookup"><span data-stu-id="53686-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53686-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="53686-121">Parent Elements</span></span>  
  
|<span data-ttu-id="53686-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="53686-122">Element</span></span>|<span data-ttu-id="53686-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="53686-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53686-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="53686-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="53686-125">Especifica um token emitido como uma credencial de serviço.</span><span class="sxs-lookup"><span data-stu-id="53686-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53686-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="53686-126">Remarks</span></span>  
 <span data-ttu-id="53686-127">O cenário de token emitido tem três etapas.</span><span class="sxs-lookup"><span data-stu-id="53686-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="53686-128">O primeiro estágio, um cliente tentar acessar um serviço é chamado um *do serviço de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="53686-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="53686-129">O serviço de token seguro, em seguida, autentica o cliente e subsequentemente emite para o cliente um token, normalmente um token de segurança asserções SAML (Markup Language).</span><span class="sxs-lookup"><span data-stu-id="53686-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="53686-130">O cliente, em seguida, retorne para o serviço com o token.</span><span class="sxs-lookup"><span data-stu-id="53686-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="53686-131">O serviço examina o token de dados que permite que o serviço autenticar o token e, portanto, o cliente.</span><span class="sxs-lookup"><span data-stu-id="53686-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="53686-132">Para autenticar o token, o certificado usa o serviço de token seguro deve ser conhecida para o serviço.</span><span class="sxs-lookup"><span data-stu-id="53686-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="53686-133">O [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento é o repositório de todos esses certificados de serviço de token seguro.</span><span class="sxs-lookup"><span data-stu-id="53686-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="53686-134">Para adicionar certificados, use o [ \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="53686-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="53686-135">Inserir uma [ \<Adicionar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="53686-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="53686-136">Por padrão, os certificados devem ser obtidos de um serviço de token seguro.</span><span class="sxs-lookup"><span data-stu-id="53686-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="53686-137">Esses "conhecidos" certificados Certifique-se de que apenas legítimas clientes podem acessar um serviço.</span><span class="sxs-lookup"><span data-stu-id="53686-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="53686-138">Para examinar as condições exigidas para um cliente seja autenticado por um serviço federado, bem como para obter mais informações sobre este elemento de configuração, consulte [como: configurar credenciais em um serviço de Federação](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="53686-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="53686-139">Para obter mais informações sobre cenários federados, consulte [federação e Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="53686-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="53686-140">Para obter um exemplo que mostra como preencher a coleção na configuração, consulte [ \<Adicionar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="53686-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53686-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53686-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="53686-142">\<add></span><span class="sxs-lookup"><span data-stu-id="53686-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="53686-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="53686-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="53686-144">Comportamentos de segurança</span><span class="sxs-lookup"><span data-stu-id="53686-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="53686-145">Como: configurar as credenciais em um serviço de Federação</span><span class="sxs-lookup"><span data-stu-id="53686-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="53686-146">Trabalhar com certificados</span><span class="sxs-lookup"><span data-stu-id="53686-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="53686-147">Federação e Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="53686-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="53686-148">\<add></span><span class="sxs-lookup"><span data-stu-id="53686-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="53686-149">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="53686-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)