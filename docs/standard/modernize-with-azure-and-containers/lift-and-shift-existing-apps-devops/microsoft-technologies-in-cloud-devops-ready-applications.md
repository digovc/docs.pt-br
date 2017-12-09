---
title: Tecnologias da Microsoft em aplicativos em nuvem devops pronto
description: "Arquitetura de Microservices .NET para aplicativos .NET em contêineres | Tecnologias da Microsoft em aplicativos prontos para nuvem DevOps"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: a7ce240ee89321f79b10a701cd26fa84b6006f83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a><span data-ttu-id="1be70-103">Tecnologias da Microsoft em aplicativos em nuvem devops pronto</span><span class="sxs-lookup"><span data-stu-id="1be70-103">Microsoft technologies in cloud devops-ready applications</span></span>

<span data-ttu-id="1be70-104">A lista a seguir descreve as ferramentas, tecnologias e soluções que são reconhecidas como os requisitos para aplicativos de nuvem DevOps pronto.</span><span class="sxs-lookup"><span data-stu-id="1be70-104">The following list describes the tools, technologies, and solutions that are recognized as requirements for Cloud DevOps-Ready apps.</span></span> <span data-ttu-id="1be70-105">Você pode adotar aplicativos prontos para nuvem DevOps seletivamente ou gradualmente, dependendo de suas prioridades.</span><span class="sxs-lookup"><span data-stu-id="1be70-105">You can adopt Cloud DevOps-Ready apps selectively or gradually, depending on your priorities.</span></span>

-   <span data-ttu-id="1be70-106">**Infraestrutura de nuvem**: A infraestrutura que fornece a plataforma de computação, sistema operacional, rede e armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1be70-106">**Cloud infrastructure**: The infrastructure that provides the compute platform, operating system, network, and storage.</span></span> <span data-ttu-id="1be70-107">Microsoft Azure está posicionado nesse nível.</span><span class="sxs-lookup"><span data-stu-id="1be70-107">Microsoft Azure is positioned at this level.</span></span>

-   <span data-ttu-id="1be70-108">**Tempo de execução**: essa camada fornece o ambiente para o aplicativo seja executado.</span><span class="sxs-lookup"><span data-stu-id="1be70-108">**Runtime**: This layer provides the environment for the application to run.</span></span> <span data-ttu-id="1be70-109">Se você estiver usando contêineres, essa camada geralmente é baseada em [mecanismo do Docker](https://docs.docker.com/engine/), em execução em hosts Linux ou em hosts do Windows.</span><span class="sxs-lookup"><span data-stu-id="1be70-109">If you are using containers, this layer usually is based on [Docker Engine](https://docs.docker.com/engine/), running either on Linux hosts or on Windows hosts.</span></span> <span data-ttu-id="1be70-110">([Contêineres do Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) têm suporte começando com o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="1be70-110">([Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) are supported beginning with Windows Server 2016.</span></span> <span data-ttu-id="1be70-111">Contêineres do Windows é a melhor escolha para aplicativos existentes do .NET Framework que são executados no Windows.)</span><span class="sxs-lookup"><span data-stu-id="1be70-111">Windows Containers is the best choice for existing .NET Framework applications that run on Windows.)</span></span>

-   <span data-ttu-id="1be70-112">**Gerenciado nuvem**: quando você escolher uma opção de nuvem gerenciado, você pode evitar a despesa e complexidade do gerenciamento e os patches de sistema operacional subjacentes infraestrutura, máquinas virtuais, de suporte e configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="1be70-112">**Managed cloud**: When you choose a managed cloud option, you can avoid the expense and complexity of managing and supporting the underlying infrastructure, VMs, OS patches, and networking configuration.</span></span> <span data-ttu-id="1be70-113">Se você optar por migrar usando IaaS, você é responsável para todas as tarefas e os custos associados.</span><span class="sxs-lookup"><span data-stu-id="1be70-113">If you choose to migrate by using IaaS, you are responsible for all of these tasks, and for associated costs.</span></span> <span data-ttu-id="1be70-114">Uma opção de nuvem gerenciado, você pode gerenciar apenas os aplicativos e serviços que você desenvolve.</span><span class="sxs-lookup"><span data-stu-id="1be70-114">In a managed cloud option, you manage only the applications and services that you develop.</span></span> <span data-ttu-id="1be70-115">O provedor de serviços de nuvem normalmente gerencia todo o resto.</span><span class="sxs-lookup"><span data-stu-id="1be70-115">The cloud service provider typically manages everything else.</span></span> <span data-ttu-id="1be70-116">Exemplos de serviços de nuvem gerenciados no Azure [banco de dados do SQL Azure](https://azure.microsoft.com/services/sql-database), [Cache Redis do Azure](https://azure.microsoft.com/services/cache/), [o banco de dados do Azure Cosmos](https://azure.microsoft.com/services/cosmos-db/), [armazenamento do Azure](https://azure.microsoft.com/services/storage/), [Banco de dados do azure para MySQL](https://azure.microsoft.com/services/mysql/), [banco de dados do Azure para PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Active Directory do Azure](https://azure.microsoft.com/services/active-directory/)e os serviços de computação como gerenciados [escalas de VM define](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [do serviço de aplicativo do Azure](https://azure.microsoft.com/services/app-service/), e [serviço de contêiner do Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="1be70-116">Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Container Service](https://azure.microsoft.com/services/container-service/).</span></span>

-   <span data-ttu-id="1be70-117">**Desenvolvimento de aplicativos**: você pode escolher entre vários idiomas quando você criar aplicativos que são executados em contêineres.</span><span class="sxs-lookup"><span data-stu-id="1be70-117">**Application development**: You can choose from many languages when you build applications that run in containers.</span></span> <span data-ttu-id="1be70-118">Este guia, vamos nos concentrar em [.NET](https://www.microsoft.com/net), mas, você pode desenvolver aplicativos baseados no contêiner por meio de outras linguagens, como Node.js, Python, Java/Spring ou GoLang.</span><span class="sxs-lookup"><span data-stu-id="1be70-118">In this guide, we focus on [.NET](https://www.microsoft.com/net), but, you can develop container-based apps by using other languages, like Node.js, Python, Spring/Java, or GoLang.</span></span>

-   <span data-ttu-id="1be70-119">**Monitoramento de telemetria, registro em log e auditoria**: A capacidade de auditoria e monitorar aplicativos e contêineres que estão em execução na nuvem é essencial para qualquer aplicativo de nuvem DevOps pronto.</span><span class="sxs-lookup"><span data-stu-id="1be70-119">**Monitoring, telemetry, logging, and auditing**: The ability to monitor and audit applications and containers that are running in the cloud is critical for any Cloud DevOps-Ready application.</span></span> <span data-ttu-id="1be70-120">[Informações de aplicativo do Azure](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) são as principais ferramentas da Microsoft que fornecem monitoramento e auditoria para aplicativos de nuvem DevOps pronto.</span><span class="sxs-lookup"><span data-stu-id="1be70-120">[Azure Application Insights](https://azure.microsoft.com/services/application-insights/) and [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) are the main Microsoft tools that provide monitoring and auditing for Cloud DevOps-Ready apps.</span></span>

-   <span data-ttu-id="1be70-121">**Provisionamento**: ferramentas de automação ajudarão-lo a provisionar a infraestrutura e implantar um aplicativo em vários ambientes (produção, teste, preparação).</span><span class="sxs-lookup"><span data-stu-id="1be70-121">**Provisioning**: Automation tools help you provision the infrastructure and deploy an application to multiple environments (production, testing, staging).</span></span> <span data-ttu-id="1be70-122">Você pode usar ferramentas como o Chef e Puppet para gerenciar o ambiente e a configuração de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1be70-122">You can use tools like Chef and Puppet to manage an application's configuration and environment.</span></span> <span data-ttu-id="1be70-123">Essa camada também pode ser implementada por meio de abordagens mais simples e mais diretas.</span><span class="sxs-lookup"><span data-stu-id="1be70-123">This layer also can be implemented by using simpler and more direct approaches.</span></span> <span data-ttu-id="1be70-124">Por exemplo, você pode implantar diretamente usando a interface de linha de comando do Azure (Azure CLI) ferramentas e, em seguida, usar a implantação contínua e pipelines de gerenciamento de versão [do Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span><span class="sxs-lookup"><span data-stu-id="1be70-124">For example, you can deploy directly by using Azure command-line interface (Azure CLI) tooling, and then use the continuous deployment and release management pipelines in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span></span>

-   <span data-ttu-id="1be70-125">**Ciclo de vida do aplicativo**: [do Visual Studio Team Services](https://www.visualstudio.com/team-services/) e outras ferramentas, como Jenkins, são servidores de automação de compilação que ajudarão-lo a implementam pipelines CI/CD, incluindo o gerenciamento de versão.</span><span class="sxs-lookup"><span data-stu-id="1be70-125">**Application lifecycle**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) and other tools, like Jenkins, are build automation servers that help you implement CI/CD pipelines, including release management.</span></span>

<span data-ttu-id="1be70-126">As próximas seções deste capítulo e o passo a passo relacionado, concentre-se especificamente nos detalhes sobre a camada de tempo de execução (contêineres do Windows).</span><span class="sxs-lookup"><span data-stu-id="1be70-126">The next sections of this chapter, and the related walkthroughs, focus specifically on details about the runtime layer (Windows Containers).</span></span> <span data-ttu-id="1be70-127">O guia descreve as maneiras que você pode implantar VMs de contêineres do Windows no Windows Server 2016 (e versões posteriores).</span><span class="sxs-lookup"><span data-stu-id="1be70-127">The guidance describes the ways you can deploy Windows Containers on Windows Server 2016 (and later versions) VMs.</span></span> <span data-ttu-id="1be70-128">Ele também aborda as camadas de orchestrator mais avançadas, como o Azure Service Fabric, Kubernetes e serviço de contêiner do Azure.</span><span class="sxs-lookup"><span data-stu-id="1be70-128">It also covers more advanced orchestrator layers, like Azure Service Fabric, Kubernetes, and Azure Container Service.</span></span> <span data-ttu-id="1be70-129">Configurar camadas orchestrator é um requisito fundamental para modernizar existente do .NET Framework (Windows) aplicativos como aplicativos prontos para nuvem DevOps.</span><span class="sxs-lookup"><span data-stu-id="1be70-129">Setting up orchestrator layers is a fundamental requirement for modernizing existing .NET Framework (Windows-based) applications as Cloud DevOps-Ready applications.</span></span>

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a><span data-ttu-id="1be70-130">Aplicativos monolíticos *pode* estar pronta para a nuvem DevOps</span><span class="sxs-lookup"><span data-stu-id="1be70-130">Monolithic applications *can* be Cloud DevOps-Ready</span></span>

<span data-ttu-id="1be70-131">É importante destacar que monolítico aplicativos (que não são baseados em microservices) *pode* ser aplicativos prontos para nuvem DevOps.</span><span class="sxs-lookup"><span data-stu-id="1be70-131">It's important to highlight that monolithic applications (applications that are not based on microservices) *can* be Cloud DevOps-Ready applications.</span></span> <span data-ttu-id="1be70-132">Você pode criar e operar monolíticos aplicativos que aproveitam a modelo de computação usando uma combinação de contêineres, fornecimento contínuo e DevOps em nuvem.</span><span class="sxs-lookup"><span data-stu-id="1be70-132">You can build and operate monolithic applications that take advantage of the cloud computing model by using a combination of containers, continuous delivery, and DevOps.</span></span> <span data-ttu-id="1be70-133">Se um aplicativo monolítico existente é adequado para suas metas de negócios, você pode modernizá-lo e torná-la pronta para a nuvem DevOps.</span><span class="sxs-lookup"><span data-stu-id="1be70-133">If an existing monolithic application is right for your business goals, you can modernize it and make it Cloud DevOps-Ready.</span></span>

<span data-ttu-id="1be70-134">Da mesma forma, se monolítico aplicativos podem ser aplicativos prontos para nuvem DevOps, outras arquiteturas mais complexas como aplicativos de N camadas também podem ser modernizadas como aplicativos prontos para nuvem DevOps.</span><span class="sxs-lookup"><span data-stu-id="1be70-134">Similarly, if monolithic applications can be Cloud DevOps-Ready applications, other, more complex architectures like N-Tier applications also can be modernized as Cloud DevOps-Ready applications.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1be70-135">[Anterior](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Próximo](what-about-cloud-optimized-applications.md)</span><span class="sxs-lookup"><span data-stu-id="1be70-135">[Previous](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Next](what-about-cloud-optimized-applications.md)</span></span>