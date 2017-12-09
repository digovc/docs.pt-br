---
title: "Tratamento avançado de erros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 046907af6a8f88760f2be12c3c5608b16a24b28a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="advanced-error-handling"></a><span data-ttu-id="4d149-102">Tratamento avançado de erros</span><span class="sxs-lookup"><span data-stu-id="4d149-102">Advanced Error Handling</span></span>
<span data-ttu-id="4d149-103">Este exemplo demonstra o [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] o serviço de roteamento.</span><span class="sxs-lookup"><span data-stu-id="4d149-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="4d149-104">O serviço de roteamento é um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] componente que torna mais fácil incluir um roteador baseado em conteúdo em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4d149-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="4d149-105">Este exemplo mostra como o serviço de roteamento de maneira inteligente recupera de erros, usando transações e outros conceitos mensagens mais complexos, como multicast.</span><span class="sxs-lookup"><span data-stu-id="4d149-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d149-106">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="4d149-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4d149-107">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4d149-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4d149-108">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="4d149-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4d149-109">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="4d149-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="4d149-110">Detalhes de exemplo</span><span class="sxs-lookup"><span data-stu-id="4d149-110">Sample Details</span></span>  
 <span data-ttu-id="4d149-111">Neste exemplo, o serviço de roteamento está configurado para ler uma mensagem de uma fila do MSMQ e multicast essa mensagem para duas listas de filas.</span><span class="sxs-lookup"><span data-stu-id="4d149-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="4d149-112">Uma lista é usada para filas de serviço e outro é usado para filas de registro em log.</span><span class="sxs-lookup"><span data-stu-id="4d149-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="4d149-113">Porque, por padrão, o MSMQ associação que o serviço de roteamento está configurado para usar oferece suporte ao uso de transações, o serviço de roteamento certifica-se de que a mensagem é recebida pelo menos uma fila em cada lista e transacional antes de relatar para o (a fila de entrada `InQ`) que a mensagem foi roteada com êxito.</span><span class="sxs-lookup"><span data-stu-id="4d149-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="4d149-114">Assim, no caso em que ambas as filas de serviço ou ambas as filas de log estão disponíveis, o serviço de roteamento de relatórios que não foi possível rotear a mensagem e a fila de entrada deve executar alguma ação.</span><span class="sxs-lookup"><span data-stu-id="4d149-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="4d149-115">Essa ação consiste em mover a mensagem à fila de mensagens mortas do sistema.</span><span class="sxs-lookup"><span data-stu-id="4d149-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4d149-116">Para usar este exemplo</span><span class="sxs-lookup"><span data-stu-id="4d149-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="4d149-117">Instale o MSMQ antes de executar este exemplo.</span><span class="sxs-lookup"><span data-stu-id="4d149-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="4d149-118">Se o MSMQ não está instalado, uma mensagem de exceção é retornada quando a execução do exemplo.</span><span class="sxs-lookup"><span data-stu-id="4d149-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="4d149-119">Instruções de instalação do MSMQ podem ser encontradas em [instalar o enfileiramento de mensagens (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="4d149-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="4d149-120">Usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AdvancedErrorHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="4d149-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="4d149-121">Pressione **F5** ou **CTRL + SHIFT + B** em [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d149-121">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="4d149-122">Se você compilar o aplicativo com CTRL + SHIFT + B, você deve iniciar o aplicativo. / RoutingService/bin/debug/RoutingService.exe.</span><span class="sxs-lookup"><span data-stu-id="4d149-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="4d149-123">Na janela do console, pressione ENTER para iniciar o cliente.</span><span class="sxs-lookup"><span data-stu-id="4d149-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="4d149-124">O cliente retorna diversas estatísticas sobre as filas para cada caso.</span><span class="sxs-lookup"><span data-stu-id="4d149-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="4d149-125">A seguir está a saída retornada para o caso 1 (sem falhas).</span><span class="sxs-lookup"><span data-stu-id="4d149-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="4d149-126">A seguir está a saída retornada para o caso 3 (serviço primário e o log de falhas de fila).</span><span class="sxs-lookup"><span data-stu-id="4d149-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="4d149-127">A seguir está a saída retornada para caso 4 (fila de serviço primário e falhas de fila de log primários e de backup).</span><span class="sxs-lookup"><span data-stu-id="4d149-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="4d149-128">A seguir está a saída retornada para caso 2 (Falha de fila de serviço principal).</span><span class="sxs-lookup"><span data-stu-id="4d149-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="4d149-129">Configuráveis por meio de código ou App. config</span><span class="sxs-lookup"><span data-stu-id="4d149-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="4d149-130">O vem de exemplo configurado para usar um arquivo App. config para definir o comportamento do roteador.</span><span class="sxs-lookup"><span data-stu-id="4d149-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="4d149-131">Você também pode alterar o nome do arquivo RoutingService\App.config para algo diferente para que ele não é reconhecido e alterar o valor da `configDriven` campo RoutingService\Program.cs para `false` para usar a configuração definida no código.</span><span class="sxs-lookup"><span data-stu-id="4d149-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="4d149-132">Um método resulta no mesmo comportamento do roteador.</span><span class="sxs-lookup"><span data-stu-id="4d149-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="4d149-133">Cenário</span><span class="sxs-lookup"><span data-stu-id="4d149-133">Scenario</span></span>  
 <span data-ttu-id="4d149-134">Este exemplo demonstra que o serviço de roteamento pode lidar com recursos de mensagens avançados, como transações e contexto de recebimento e que ele possa utilizar esses recursos como parte de lidar corretamente com cenários de erro.</span><span class="sxs-lookup"><span data-stu-id="4d149-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="4d149-135">Cenário do mundo real</span><span class="sxs-lookup"><span data-stu-id="4d149-135">Real World Scenario</span></span>  
 <span data-ttu-id="4d149-136">A Contoso deseja utilizar transacional recebe por meio do serviço de roteamento para assegurar que todos os serviços necessários recebam informações mesmo durante a condições de erro.</span><span class="sxs-lookup"><span data-stu-id="4d149-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="4d149-137">Além disso, eles gostariam erros devem ser tratados corretamente e automaticamente e falhas a ser relatado no caso de que uma mensagem seja entregue mesmo quando lógica de tratamento de erro é utilizado.</span><span class="sxs-lookup"><span data-stu-id="4d149-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="4d149-138">Para essa finalidade, eles configurar o serviço de roteamento de failover para pontos de extremidade específicos, conforme o esperado e o serviço de roteamento trata as situações de erro, que inclui a criação, conclusão de e/anulando a reversão de transações/receber contextos como é necessário.</span><span class="sxs-lookup"><span data-stu-id="4d149-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d149-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4d149-139">See Also</span></span>  
 [<span data-ttu-id="4d149-140">Exemplos de persistência e hospedagem de AppFabric</span><span class="sxs-lookup"><span data-stu-id="4d149-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)