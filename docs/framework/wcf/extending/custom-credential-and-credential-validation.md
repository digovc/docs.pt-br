---
title: "Credencial personalizada e validação de credencial"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 021a4e206a5abfb3508e8e548114de7e61dd2d04
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="d8ed3-102">Credencial personalizada e validação de credencial</span><span class="sxs-lookup"><span data-stu-id="d8ed3-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="d8ed3-103">Segurança em [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] baseia-se a troca de credenciais entre clientes e serviços.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-103">Security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="d8ed3-104">A maioria dos cenários de segurança podem ser satisfeitos usando tipos comuns de credenciais, como Windows (Kerberos), nome de usuário e senhas e certificados.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="d8ed3-105">No entanto, se um novo tipo de credencial for necessário, os tópicos nesta seção explicam como manipular e validar os novos tipos.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8ed3-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d8ed3-106">In This Section</span></span>  
 [<span data-ttu-id="d8ed3-107">Como: criar um serviço que utiliza um validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="d8ed3-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="d8ed3-108">Explica como personalizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validação herdando do <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-108">Explains how to customize [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="d8ed3-109">Passo a passo: Criando credenciais de serviço e cliente personalizados</span><span class="sxs-lookup"><span data-stu-id="d8ed3-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="d8ed3-110">Demonstra como estender o <xref:System.ServiceModel.Description.ClientCredentials> e <xref:System.ServiceModel.Description.ServiceCredentials> classes para acomodar novos tipos de credenciais.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="d8ed3-111">Este é o primeiro em uma série de tópicos que permitem a criação de tipos de credencial personalizada.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="d8ed3-112">Como: criar um provedor de Token de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="d8ed3-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="d8ed3-113">Explica como criar um provedor de token de segurança para lidar com novos tipos de credenciais e retornar novos tokens para a credencial.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="d8ed3-114">Este é o segundo tópico na série.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="d8ed3-115">Como: criar um autenticador de Token de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="d8ed3-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="d8ed3-116">Explica como criar um autenticador personalizado para autenticar um novo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="d8ed3-117">Este é o terceiro tópico na série.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d8ed3-118">Referência</span><span class="sxs-lookup"><span data-stu-id="d8ed3-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="d8ed3-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="d8ed3-119">Related Sections</span></span>  
 [<span data-ttu-id="d8ed3-120">Autenticação</span><span class="sxs-lookup"><span data-stu-id="d8ed3-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="d8ed3-121">Federação e Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d8ed3-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="d8ed3-122">Autorização</span><span class="sxs-lookup"><span data-stu-id="d8ed3-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8ed3-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d8ed3-123">See Also</span></span>  
 [<span data-ttu-id="d8ed3-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="d8ed3-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)