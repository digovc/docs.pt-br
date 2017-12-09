---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a008919cc068ca5cdd841ec67f1a7194bbffcd8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="44ead-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="44ead-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="44ead-103">Especifica configurações de autenticação de certificado de ponto a ponto usado por um remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="44ead-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="44ead-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="44ead-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="44ead-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="44ead-105">\<behaviors></span></span>  
<span data-ttu-id="44ead-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="44ead-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="44ead-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="44ead-107">\<behavior></span></span>  
<span data-ttu-id="44ead-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="44ead-108">\<serviceCredentials></span></span>  
<span data-ttu-id="44ead-109">\<par ></span><span class="sxs-lookup"><span data-stu-id="44ead-109">\<peer></span></span>  
<span data-ttu-id="44ead-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="44ead-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ead-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="44ead-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44ead-112">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="44ead-112">Attributes and Elements</span></span>  
 <span data-ttu-id="44ead-113">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="44ead-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44ead-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="44ead-114">Attributes</span></span>  
  
|<span data-ttu-id="44ead-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="44ead-115">Attribute</span></span>|<span data-ttu-id="44ead-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="44ead-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="44ead-117">Enumeração opcional.</span><span class="sxs-lookup"><span data-stu-id="44ead-117">Optional enumeration.</span></span> <span data-ttu-id="44ead-118">Especifica um dos cinco modos usados para validar credenciais.</span><span class="sxs-lookup"><span data-stu-id="44ead-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="44ead-119">Esse atributo é do tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="44ead-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="44ead-120">Se definido como `Custom`, em seguida, um `customCertificateValidator` também deve ser fornecido.</span><span class="sxs-lookup"><span data-stu-id="44ead-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="44ead-121">Cadeia de caracteres opcional.</span><span class="sxs-lookup"><span data-stu-id="44ead-121">Optional string.</span></span> <span data-ttu-id="44ead-122">Especifica um tipo e assembly usados para validar um tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="44ead-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="44ead-123">Esse atributo deve ser definido quando `certificateValidationMode` é definido como `Custom`.</span><span class="sxs-lookup"><span data-stu-id="44ead-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="44ead-124">Esse atributo é do tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="44ead-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="44ead-125">Fornece um par de padrão de validador de certificado que verifica o certificado de ponto a ponto em relação ao armazenamento de pessoas confiáveis.</span><span class="sxs-lookup"><span data-stu-id="44ead-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="44ead-126">Ele também verifica se o certificado se encadeia uma raiz válido.</span><span class="sxs-lookup"><span data-stu-id="44ead-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="44ead-127">Você pode implementar um validador personalizado para especificar um comportamento diferente e usar esse atributo para apontar para o validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="44ead-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="44ead-128">Enumeração opcional.</span><span class="sxs-lookup"><span data-stu-id="44ead-128">Optional enumeration.</span></span> <span data-ttu-id="44ead-129">Especifica o modo de revogação de certificado.</span><span class="sxs-lookup"><span data-stu-id="44ead-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="44ead-130">Esse atributo é do tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="44ead-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="44ead-131">O sistema verifica se o certificado de ponto a ponto não foi revogado por procurar na lista de certificados revogados.</span><span class="sxs-lookup"><span data-stu-id="44ead-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="44ead-132">Essa verificação pode ser executada através da verificação online ou em uma lista de revogação em cache.</span><span class="sxs-lookup"><span data-stu-id="44ead-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="44ead-133">Verificação de revogação pode ser desativado por configuração deste atributo como NoCheck.</span><span class="sxs-lookup"><span data-stu-id="44ead-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="44ead-134">Enumeração opcional.</span><span class="sxs-lookup"><span data-stu-id="44ead-134">Optional enumeration.</span></span> <span data-ttu-id="44ead-135">Especifica o local de armazenamento confiável em que o certificado de ponto a ponto é validado pelo [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] sistema de segurança.</span><span class="sxs-lookup"><span data-stu-id="44ead-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="44ead-136">Esse atributo é do tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="44ead-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44ead-137">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="44ead-137">Child Elements</span></span>  
 <span data-ttu-id="44ead-138">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="44ead-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44ead-139">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="44ead-139">Parent Elements</span></span>  
  
|<span data-ttu-id="44ead-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="44ead-140">Element</span></span>|<span data-ttu-id="44ead-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="44ead-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44ead-142">\<par ></span><span class="sxs-lookup"><span data-stu-id="44ead-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="44ead-143">Especifica as credenciais atuais de um nó ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="44ead-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44ead-144">Comentários</span><span class="sxs-lookup"><span data-stu-id="44ead-144">Remarks</span></span>  
 <span data-ttu-id="44ead-145">Esse elemento deve ser configurado se você escolher autenticação de mensagem.</span><span class="sxs-lookup"><span data-stu-id="44ead-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="44ead-146">Para canais de saída, cada mensagem é assinada usando o certificado fornecido pelo [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="44ead-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="44ead-147">Todas as mensagens, antes da entrega para o aplicativo, são verificados em relação a credencial de mensagem usando o validador especificado pelo `customCertificateValidatorType` atributos desse elemento.</span><span class="sxs-lookup"><span data-stu-id="44ead-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="44ead-148">O validador pode aceitar ou rejeitar a credencial.</span><span class="sxs-lookup"><span data-stu-id="44ead-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ead-149">Consulte também</span><span class="sxs-lookup"><span data-stu-id="44ead-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="44ead-150">Trabalhar com certificados</span><span class="sxs-lookup"><span data-stu-id="44ead-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="44ead-151">Rede ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="44ead-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="44ead-152">Autenticação de mensagens de canal par</span><span class="sxs-lookup"><span data-stu-id="44ead-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="44ead-153">Autenticação personalizada de canal par</span><span class="sxs-lookup"><span data-stu-id="44ead-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="44ead-154">Protegendo aplicativos de canal par</span><span class="sxs-lookup"><span data-stu-id="44ead-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)