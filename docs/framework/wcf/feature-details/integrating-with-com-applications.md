---
title: "Integração com aplicativos COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfe452b41c39598e237633490d09cd267fda04ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="8e18e-102">Integração com aplicativos COM</span><span class="sxs-lookup"><span data-stu-id="8e18e-102">Integrating with COM Applications</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="8e18e-103">serviços podem ser integrados diretamente em seu código existente usando o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e18e-103"> services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="8e18e-104">O moniker de serviço pode ser usado em ambientes de desenvolvimento todo com base no intervalo de COM, como Office VBA, Visual Basic 6.0 ou Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="8e18e-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e18e-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8e18e-105">In This Section</span></span>  
 [<span data-ttu-id="8e18e-106">Integração com visão geral de aplicativos COM</span><span class="sxs-lookup"><span data-stu-id="8e18e-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="8e18e-107">Fornece uma visão geral das partes principais do processo de integração.</span><span class="sxs-lookup"><span data-stu-id="8e18e-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="8e18e-108">Como: registrar e configurar um Moniker de serviço</span><span class="sxs-lookup"><span data-stu-id="8e18e-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="8e18e-109">Para usar o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de um aplicativo COM o identificador de origem do serviço, registrar os tipos de atributo necessários com e configurar o aplicativo COM e o moniker com a configuração de associação necessária.</span><span class="sxs-lookup"><span data-stu-id="8e18e-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="8e18e-110">Como: usar o Moniker de serviço do Windows Communication Foundation sem registro</span><span class="sxs-lookup"><span data-stu-id="8e18e-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="8e18e-111">Explica como obter a definição de contrato na forma de um documento WSDL Web Services Definition Language () ou de um ponto de extremidade do WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="8e18e-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="8e18e-112">Como: usar um Moniker de serviço com contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="8e18e-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="8e18e-113">Descreve como chamar um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de exemplo usando um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker WSDL.</span><span class="sxs-lookup"><span data-stu-id="8e18e-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="8e18e-114">Como: usar um Moniker de serviço com contratos de troca de metadados</span><span class="sxs-lookup"><span data-stu-id="8e18e-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="8e18e-115">Descreve como chamar um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de exemplo usando um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker que especifica um ponto de extremidade Mex.</span><span class="sxs-lookup"><span data-stu-id="8e18e-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="8e18e-116">Como: especificar credenciais de segurança de canal</span><span class="sxs-lookup"><span data-stu-id="8e18e-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="8e18e-117">O [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] suporta moniker de serviço a `IChannelCredentials` interface que permite uma variedade de métodos alternativos para especificar credenciais de canal.</span><span class="sxs-lookup"><span data-stu-id="8e18e-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8e18e-118">Referência</span><span class="sxs-lookup"><span data-stu-id="8e18e-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="8e18e-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8e18e-119">See Also</span></span>  
 [<span data-ttu-id="8e18e-120">Integrando aplicativos COM+</span><span class="sxs-lookup"><span data-stu-id="8e18e-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)