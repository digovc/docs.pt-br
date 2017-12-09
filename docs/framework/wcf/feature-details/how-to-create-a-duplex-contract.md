---
title: Como criar um contrato duplex
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
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30fc31055563db75512639bf7fb3b9119be280e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="ac0f9-102">Como criar um contrato duplex</span><span class="sxs-lookup"><span data-stu-id="ac0f9-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="ac0f9-103">Este tópico mostra as etapas básicas para criar métodos que usam um contrato duplex (bidirecional).</span><span class="sxs-lookup"><span data-stu-id="ac0f9-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="ac0f9-104">Um contrato duplex permite que os clientes e os servidores se comuniquem entre si independentemente, de modo que qualquer um possa iniciar chamadas para o outro.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="ac0f9-105">O contrato duplex é um dos três padrões de mensagem disponíveis para serviços do [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac0f9-105">The duplex contract is one of three message patterns available to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="ac0f9-106">Os outros padrões de duas mensagens são unidirecionais e solicitação-resposta.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="ac0f9-107">Um contrato duplex consiste de dois contratos unidirecionais entre o cliente e o servidor e não exige que as chamadas de método sejam correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="ac0f9-108">Use esse tipo de contrato quando o serviço tiver que consultar o cliente para obter mais informações ou explicitamente gerar eventos no cliente.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ac0f9-109">criar um aplicativo cliente para um contrato duplex, consulte [como: serviços do Access com um contrato Duplex](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="ac0f9-109"> creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="ac0f9-110">Para obter um exemplo de funcionamento, consulte o [Duplex](../../../../docs/framework/wcf/samples/duplex.md) exemplo.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-110">For a working sample, see the [Duplex](../../../../docs/framework/wcf/samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="ac0f9-111">Para criar um contrato duplex</span><span class="sxs-lookup"><span data-stu-id="ac0f9-111">To create a duplex contract</span></span>  
  
1.  <span data-ttu-id="ac0f9-112">Crie a interface que compõem o lado do servidor do contrato duplex.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2.  <span data-ttu-id="ac0f9-113">Aplique a classe <xref:System.ServiceModel.ServiceContractAttribute> à interface.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  <span data-ttu-id="ac0f9-114">Declare as assinaturas de método na interface.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-114">Declare the method signatures in the interface.</span></span>  
  
4.  <span data-ttu-id="ac0f9-115">Aplique a classe <xref:System.ServiceModel.OperationContractAttribute> a cada assinatura de método que deve ser parte do contrato público.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5.  <span data-ttu-id="ac0f9-116">Crie a interface de retorno de chamada que define o conjunto de operações que o serviço pode chamar no cliente.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  <span data-ttu-id="ac0f9-117">Declare as assinaturas de método na interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-117">Declare the method signatures in the callback interface.</span></span>  
  
7.  <span data-ttu-id="ac0f9-118">Aplique a classe <xref:System.ServiceModel.OperationContractAttribute> a cada assinatura de método que deve ser parte do contrato público.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8.  <span data-ttu-id="ac0f9-119">Vincular as duas interfaces em um contrato duplex definindo a propriedade <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> na interface primária para o tipo da interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="ac0f9-120">Para chamar métodos no cliente</span><span class="sxs-lookup"><span data-stu-id="ac0f9-120">To call methods on the client</span></span>  
  
1.  <span data-ttu-id="ac0f9-121">Na implementação de serviço do contrato primário, declare uma variável para a interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2.  <span data-ttu-id="ac0f9-122">Defina a variável para a referência de objeto retornada pelo método <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> da classe <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  <span data-ttu-id="ac0f9-123">Chame os métodos definidos pela interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac0f9-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ac0f9-124">Example</span></span>  
 <span data-ttu-id="ac0f9-125">O exemplo de código a seguir demonstra a comunicação duplex.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="ac0f9-126">O contrato do serviço contém operações de serviço para avançar e voltar.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="ac0f9-127">O contrato do cliente contém uma operação de serviço para relatar sua posição.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   <span data-ttu-id="ac0f9-128">Aplicar os atributos <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> permite a geração automática de definições do contrato de serviço na linguagem WSDL.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
-   <span data-ttu-id="ac0f9-129">Use o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar o documento WSDL e o código (opcional) e a configuração para um cliente.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
-   <span data-ttu-id="ac0f9-130">Os pontos de extremidade que expõem serviços duplex devem ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="ac0f9-131">Quando um serviço recebe uma mensagem duplex, ele olha o ReplyTo na mensagem de entrada para determinar para onde enviar a resposta.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="ac0f9-132">Se o canal não estiver protegido, um cliente não confiável poderá enviar uma mensagem mal-intencionada com um ReplyTo do computador de destino, resultando em uma negação de serviço do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="ac0f9-133">Com mensagens normais de solicitação-resposta, isso não é um problema, pois o ReplyTo é ignorado e a resposta é enviada no canal no qual a mensagem original chegou.</span><span class="sxs-lookup"><span data-stu-id="ac0f9-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0f9-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ac0f9-134">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="ac0f9-135">Como: acessar serviços com um contrato Duplex</span><span class="sxs-lookup"><span data-stu-id="ac0f9-135">How to: Access Services with a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="ac0f9-136">Duplex</span><span class="sxs-lookup"><span data-stu-id="ac0f9-136">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)  
 <span data-ttu-id="ac0f9-137">[Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md) (Serviços de design e implantação)</span><span class="sxs-lookup"><span data-stu-id="ac0f9-137">[Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md)</span></span>  
 <span data-ttu-id="ac0f9-138">[How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) (Como definir um contrato de serviço)</span><span class="sxs-lookup"><span data-stu-id="ac0f9-138">[How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)</span></span>  
 [<span data-ttu-id="ac0f9-139">Sessão</span><span class="sxs-lookup"><span data-stu-id="ac0f9-139">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)