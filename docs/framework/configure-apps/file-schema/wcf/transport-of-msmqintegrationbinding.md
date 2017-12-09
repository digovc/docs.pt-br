---
title: '&lt;transporte&gt; de &lt;msmqIntegrationBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27b2ade7c9033ca82d3249ef18f1004e30c30025
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="b1e8b-102">&lt;transporte&gt; de &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b1e8b-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="b1e8b-103">Define as configurações de segurança para o transporte de integração de enfileiramento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="b1e8b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1e8b-105">\<associações ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-105">\<bindings></span></span>  
<span data-ttu-id="b1e8b-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="b1e8b-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="b1e8b-107">\<associação ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-107">\<binding></span></span>  
<span data-ttu-id="b1e8b-108">\<segurança ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-108">\<security></span></span>  
<span data-ttu-id="b1e8b-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e8b-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b1e8b-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1e8b-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b1e8b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b1e8b-112">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="b1e8b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1e8b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1e8b-113">Attributes</span></span>  
  
|<span data-ttu-id="b1e8b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b1e8b-114">Attribute</span></span>|<span data-ttu-id="b1e8b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1e8b-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="b1e8b-116">Especifica como a mensagem deve ser autenticada pelo transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="b1e8b-117">Se isso for definido como `None`, o valor de `msmqProtectionLevel` atributo também deve ser definido como `None`.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="b1e8b-118">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b1e8b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b1e8b-119">-Nenhum: Nenhuma autenticação.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-119">-   None: No authentication.</span></span><br /><span data-ttu-id="b1e8b-120">-WindowsDomain: O mecanismo de autenticação usa o Active Directory para obter o certificado x. 509 para o SID associado à mensagem.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="b1e8b-121">Isso é usado para verificar a ACL da fila para garantir que o usuário tem permissão para gravar na fila.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="b1e8b-122">-O certificado: O canal obtém o certificado do repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="b1e8b-123">O valor padrão é WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="b1e8b-124">Esse atributo é do tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="b1e8b-125">Especifica o algoritmo a ser usado para criptografia de mensagem no fio durante a transferência de mensagens entre os gerenciadores de fila de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="b1e8b-126">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b1e8b-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b1e8b-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="b1e8b-127">-   RC4Stream</span></span><br /><span data-ttu-id="b1e8b-128">-AES</span><span class="sxs-lookup"><span data-stu-id="b1e8b-128">-   AES</span></span><br /><br /> <span data-ttu-id="b1e8b-129">O valor padrão é RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-129">The default value is RC4Stream.</span></span> <span data-ttu-id="b1e8b-130">Esse atributo é do tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="b1e8b-131">Especifica como a mensagem é protegida no nível de transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="b1e8b-132">A criptografia assegura a integridade da mensagem enquanto EncryptAndSign garante a integridade da mensagem e não-repúdio; ou seja, a mensagem é realmente do remetente e o remetente é quem diz que ser.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="b1e8b-133">-Valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b1e8b-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="b1e8b-134">-Nenhum: Sem proteção.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-134">-   None: No protection.</span></span><br /><span data-ttu-id="b1e8b-135">-Sign: Mensagens são assinadas.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b1e8b-136">-EncryptAndSign: Mensagens são criptografadas e assinadas.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="b1e8b-137">O valor padrão é o sinal.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-137">The default value is Sign.</span></span> <span data-ttu-id="b1e8b-138">Esse atributo é do tipo ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="b1e8b-139">-Especifica o algoritmo a ser usado no cálculo do resumo como parte das assinaturas.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="b1e8b-140">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b1e8b-140">Valid values include the following:</span></span><br /><span data-ttu-id="b1e8b-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="b1e8b-141">-   MD5</span></span><br /><span data-ttu-id="b1e8b-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="b1e8b-142">-   SHA1</span></span><br /><span data-ttu-id="b1e8b-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="b1e8b-143">-   SHA256</span></span><br /><span data-ttu-id="b1e8b-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="b1e8b-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="b1e8b-145">O valor padrão é SHA1.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-145">The default value is SHA1.</span></span> <span data-ttu-id="b1e8b-146">Esse atributo é do tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1e8b-147">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b1e8b-147">Child Elements</span></span>  
 <span data-ttu-id="b1e8b-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b1e8b-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1e8b-149">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b1e8b-149">Parent Elements</span></span>  
  
|<span data-ttu-id="b1e8b-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1e8b-150">Element</span></span>|<span data-ttu-id="b1e8b-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1e8b-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1e8b-152">\<segurança ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="b1e8b-153">Define as configurações de segurança para uma associação de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1e8b-154">Comentários</span><span class="sxs-lookup"><span data-stu-id="b1e8b-154">Remarks</span></span>  
 <span data-ttu-id="b1e8b-155">Esse elemento encapsula as configurações de segurança para o transporte de integração de enfileiramento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="b1e8b-156">As configurações são as mesmas para a integração de enfileiramento de mensagens e de transportes na fila.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="b1e8b-157">Ele permite que você defina o modo de autenticação, o algoritmo de criptografia, algoritmo de Hash seguro e nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="b1e8b-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e8b-158">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b1e8b-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="b1e8b-159">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="b1e8b-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b1e8b-160">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="b1e8b-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="b1e8b-161">[Bindings](../../../../../docs/framework/wcf/bindings.md) (Associações)</span><span class="sxs-lookup"><span data-stu-id="b1e8b-161">[Bindings](../../../../../docs/framework/wcf/bindings.md)</span></span>  
 [<span data-ttu-id="b1e8b-162">Configurando associações fornecidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="b1e8b-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b1e8b-163">Usando associações para configurar clientes e serviços do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b1e8b-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b1e8b-164">\<associação ></span><span class="sxs-lookup"><span data-stu-id="b1e8b-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)