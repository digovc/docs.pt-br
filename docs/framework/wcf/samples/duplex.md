---
title: Duplex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88ad38a6a93a897e2362d61c1166b87813ab7859
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="duplex"></a><span data-ttu-id="54b17-102">Duplex</span><span class="sxs-lookup"><span data-stu-id="54b17-102">Duplex</span></span>
<span data-ttu-id="54b17-103">O exemplo Duplex demonstra como definir e implementar um contrato duplex.</span><span class="sxs-lookup"><span data-stu-id="54b17-103">The Duplex sample demonstrates how to define and implement a duplex contract.</span></span> <span data-ttu-id="54b17-104">Comunicação duplex ocorre quando um cliente estabelece uma sessão com um serviço e fornece o serviço de um canal em que o serviço pode enviar mensagens de volta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="54b17-104">Duplex communication occurs when a client establishes a session with a service and gives the service a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="54b17-105">Este exemplo se baseia o [Introdução](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="54b17-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="54b17-106">Um contrato duplex é definido como um par de interfaces — uma interface principal do cliente para o serviço e uma interface de retorno de chamada do serviço ao cliente.</span><span class="sxs-lookup"><span data-stu-id="54b17-106">A duplex contract is defined as a pair of interfaces—a primary interface from the client to the service and a callback interface from the service to the client.</span></span> <span data-ttu-id="54b17-107">Neste exemplo, o `ICalculatorDuplex` interface permite que o cliente executar operações matemáticas, calculando o resultado em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="54b17-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating the result over a session.</span></span> <span data-ttu-id="54b17-108">O serviço retorna resultados sobre o `ICalculatorDuplexCallback` interface.</span><span class="sxs-lookup"><span data-stu-id="54b17-108">The service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="54b17-109">Um contrato duplex requer uma sessão, porque um contexto deve ser estabelecido para correlacionar o conjunto de mensagens sendo enviadas entre o cliente e o serviço.</span><span class="sxs-lookup"><span data-stu-id="54b17-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54b17-110">As instruções de procedimento e a compilação de configuração para este exemplo estão localizadas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="54b17-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="54b17-111">Neste exemplo, o cliente é um aplicativo de console (.exe) e o serviço é hospedado por serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="54b17-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="54b17-112">O contrato duplex é definido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="54b17-112">The duplex contract is defined as follows:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,  
                 CallbackContract=typeof(ICalculatorDuplexCallback))]  
public interface ICalculatorDuplex  
{  
    [OperationContract(IsOneWay = true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
}  
  
public interface ICalculatorDuplexCallback  
{  
    [OperationContract(IsOneWay = true)]  
    void Result(double result);  
    [OperationContract(IsOneWay = true)]  
    void Equation(string eqn);  
}  
```  
  
 <span data-ttu-id="54b17-113">O `CalculatorService` classe implementa primário `ICalculatorDuplex` interface.</span><span class="sxs-lookup"><span data-stu-id="54b17-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="54b17-114">O serviço usa o <xref:System.ServiceModel.InstanceContextMode.PerSession> modo de instância para manter o resultado para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="54b17-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="54b17-115">Uma propriedade privada denominada `Callback` é usada para acessar o canal de retorno de chamada para o cliente.</span><span class="sxs-lookup"><span data-stu-id="54b17-115">A private property named `Callback` is used to access the callback channel to the client.</span></span> <span data-ttu-id="54b17-116">O serviço usa o retorno de chamada para enviar mensagens ao cliente por meio da interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="54b17-116">The service uses the callback for sending messages back to the client through the callback interface.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorDuplex  
{  
    double result = 0.0D;  
    string equation;  
  
    public CalculatorService()  
    {  
        equation = result.ToString();  
    }  
  
    public void Clear()  
    {  
        Callback.Equation(equation + " = " + result.ToString());  
        equation = result.ToString();  
    }  
  
    public void AddTo(double n)  
    {  
        result += n;  
        equation += " + " + n.ToString();  
        Callback.Result(result);  
    }  
    ...  
    ICalculatorDuplexCallback Callback  
    {  
        get  
        {  
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="54b17-117">O cliente deve fornecer uma classe que implementa a interface de retorno de chamada do contrato duplex, para receber mensagens do serviço.</span><span class="sxs-lookup"><span data-stu-id="54b17-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="54b17-118">No exemplo, um `CallbackHandler` classe é definida para implementar o `ICalculatorDuplexCallback` interface.</span><span class="sxs-lookup"><span data-stu-id="54b17-118">In the sample, a `CallbackHandler` class is defined to implement the `ICalculatorDuplexCallback` interface.</span></span>  
  
```  
public class CallbackHandler : ICalculatorDuplexCallback  
{  
   public void Result(double result)  
   {  
      Console.WriteLine("Result({0})", result);  
   }  
  
   public void Equation(string equation)  
   {  
      Console.WriteLine("Equation({0}", equation);  
   }  
}  
```  
  
 <span data-ttu-id="54b17-119">O proxy gerado para um contrato duplex requer um <xref:System.ServiceModel.InstanceContext> será fornecido após a construção.</span><span class="sxs-lookup"><span data-stu-id="54b17-119">The proxy that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> to be provided upon construction.</span></span> <span data-ttu-id="54b17-120">Isso <xref:System.ServiceModel.InstanceContext> é usado como o site para um objeto que implementa a interface de retorno de chamada e manipula mensagens que são enviadas de volta do serviço.</span><span class="sxs-lookup"><span data-stu-id="54b17-120">This <xref:System.ServiceModel.InstanceContext> is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="54b17-121">Um <xref:System.ServiceModel.InstanceContext> é construído com uma instância do `CallbackHandler` classe.</span><span class="sxs-lookup"><span data-stu-id="54b17-121">An <xref:System.ServiceModel.InstanceContext> is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="54b17-122">Esse objeto manipula mensagens enviadas do serviço para o cliente na interface de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="54b17-122">This object handles messages sent from the service to the client on the callback interface.</span></span>  
  
```  
// Construct InstanceContext to handle messages on callback interface.  
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());  
  
// Create a client.  
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);  
  
Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");  
Console.WriteLine();  
  
// Call the AddTo service operation.  
double value = 100.00D;  
client.AddTo(value);  
  
// Call the SubtractFrom service operation.  
value = 50.00D;  
client.SubtractFrom(value);  
  
// Call the MultiplyBy service operation.  
value = 17.65D;  
client.MultiplyBy(value);  
  
// Call the DivideBy service operation.  
value = 2.00D;  
client.DivideBy(value);  
  
// Complete equation.  
client.Clear();  
  
Console.ReadLine();  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 <span data-ttu-id="54b17-123">A configuração foi modificada para fornecer uma associação que dá suporte à comunicação de sessão e comunicação duplex.</span><span class="sxs-lookup"><span data-stu-id="54b17-123">The configuration has been modified to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="54b17-124">O `wsDualHttpBinding` oferece suporte à comunicação de sessão e permite a comunicação duplex, fornecendo duas conexões HTTP, uma para cada direção.</span><span class="sxs-lookup"><span data-stu-id="54b17-124">The `wsDualHttpBinding` supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span> <span data-ttu-id="54b17-125">Sobre o serviço, a única diferença na configuração é a associação que é usada.</span><span class="sxs-lookup"><span data-stu-id="54b17-125">On the service, the only difference in configuration is the binding that is used.</span></span> <span data-ttu-id="54b17-126">No cliente, você deve configurar um endereço que o servidor pode usar para se conectar ao cliente, conforme mostrado no exemplo de configuração.</span><span class="sxs-lookup"><span data-stu-id="54b17-126">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
  <endpoint name=""  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="wsDualHttpBinding"   
            bindingConfiguration="DuplexBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
</client>  
  
<bindings>  
  <!-- Configure a binding that support duplex communication. -->  
  <wsDualHttpBinding>  
    <binding name="DuplexBinding"   
             clientBaseAddress="http://localhost:8000/myClient/">  
    </binding>  
  </wsDualHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="54b17-127">Quando você executar o exemplo, você pode ver as mensagens que são retornadas ao cliente na interface de retorno de chamada que é enviada do serviço.</span><span class="sxs-lookup"><span data-stu-id="54b17-127">When you run the sample, you see the messages that are returned to the client on the callback interface that is sent from the service.</span></span> <span data-ttu-id="54b17-128">Cada resultado intermediário é exibido, seguido por toda a equação após a conclusão de todas as operações.</span><span class="sxs-lookup"><span data-stu-id="54b17-128">Each intermediate result is displayed, followed by the entire equation upon the completion of all operations.</span></span> <span data-ttu-id="54b17-129">Pressione ENTER para fechar o cliente.</span><span class="sxs-lookup"><span data-stu-id="54b17-129">Press ENTER to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="54b17-130">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="54b17-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="54b17-131">Certifique-se de que você executou o [único procedimento de instalação para os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54b17-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="54b17-132">Para criar a edição do c#, C++ ou Visual Basic .NET da solução, siga as instruções em [compilar os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54b17-132">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="54b17-133">Para executar o exemplo em uma configuração ou entre computadores, siga as instruções em [executando os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54b17-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="54b17-134">Ao executar o cliente em uma configuração entre computadores, certifique-se de substituir "localhost" em ambos o `address` atributo do [ponto de extremidade](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento e o `clientBaseAddress` atributo do [ \< associação >](../../../../docs/framework/misc/binding.md) elemento o [ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento com o nome da máquina apropriada, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="54b17-134">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [endpoint](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element and the `clientBaseAddress` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown in the following:</span></span>  
  
    ```xml  
    <client>  
    <endpoint name = ""  
    address="http://service_machine_name/servicemodelsamples/service.svc"  
    ... />  
    </client>  
    ...  
    <wsDualHttpBinding>  
    <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">  
    </binding>  
    </wsDualHttpBinding>  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="54b17-135">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="54b17-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="54b17-136">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="54b17-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="54b17-137">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="54b17-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="54b17-138">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="54b17-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`  
  
## <a name="see-also"></a><span data-ttu-id="54b17-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="54b17-139">See Also</span></span>