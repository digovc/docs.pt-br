---
title: "Como criar um serviço de dados usando uma fonte de dados do ADO.NET Entity Framework (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77a4b90b16a92e993d9283932b2a609f874c7568
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="4d816-102">Como criar um serviço de dados usando uma fonte de dados do ADO.NET Entity Framework (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="4d816-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
<span data-ttu-id="4d816-103">O [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expõe dados de entidade como um serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] exposes entity data as a data service.</span></span> <span data-ttu-id="4d816-104">Esses dados de entidade são fornecidos pelo [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando a fonte de dados é um banco de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="4d816-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="4d816-105">Este tópico mostra como criar um modelo de dados com base no [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] em um aplicativo da Web [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] baseado em um banco de dados existente e usar esse modelo de dados para criar um novo serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="4d816-106">O [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] também fornece uma ferramenta de linha de comando que pode gerar um modelo do [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fora de um projeto do [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d816-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="4d816-107">Para obter mais informações, consulte [como: Use EdmGen.exe para gerar o modelo e os arquivos de mapeamento](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="4d816-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="4d816-108">Para adicionar um modelo do Entity Framework que está baseado em um banco de dados existente para um aplicativo da Web existente</span><span class="sxs-lookup"><span data-stu-id="4d816-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="4d816-109">Sobre o **projeto** menu, clique em **adicionar novo item**.</span><span class="sxs-lookup"><span data-stu-id="4d816-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="4d816-110">No **modelos** painel, clique no **dados** categoria e selecione **modelo de dados de entidade ADO.NET**.</span><span class="sxs-lookup"><span data-stu-id="4d816-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="4d816-111">Digite o nome do modelo e, em seguida, clique em **adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4d816-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="4d816-112">A primeira página do assistente do [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] é exibida.</span><span class="sxs-lookup"><span data-stu-id="4d816-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="4d816-113">No **escolher o modelo de conteúdo** caixa de diálogo, selecione **gerar do banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="4d816-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="4d816-114">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4d816-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="4d816-115">Clique o **nova Conexão** botão.</span><span class="sxs-lookup"><span data-stu-id="4d816-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="4d816-116">No **propriedades de Conexão** caixa de diálogo, digite o nome do servidor, selecione o método de autenticação, digite o nome do banco de dados e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="4d816-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4d816-117">O **escolha sua Conexão de dados**caixa de diálogo é atualizada com as configurações de conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="4d816-118">Certifique-se de que o **salvar configurações de conexão de entidade no App. config como:** caixa de seleção é marcada.</span><span class="sxs-lookup"><span data-stu-id="4d816-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="4d816-119">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4d816-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="4d816-120">No **escolher seus objetos de banco de dados** objetos de selecionar tudo do banco de dados de caixa de diálogo que você pretende expor no serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d816-121">Os objetos incluídos no modelo de dados não são expostos automaticamente pelo serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="4d816-122">Eles devem ser explicitamente expostos pelo próprio serviço.</span><span class="sxs-lookup"><span data-stu-id="4d816-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="4d816-123">Para obter mais informações, consulte [Configurando o serviço de dados](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d816-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="4d816-124">Clique em **concluir** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="4d816-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="4d816-125">Isso cria um modelo de dados padrão com base no banco de dados específico.</span><span class="sxs-lookup"><span data-stu-id="4d816-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="4d816-126">O [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] permite personalizar o modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="4d816-127">Para obter mais informações, consulte [Tarefas](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="4d816-127">For more information, see [Tasks](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="4d816-128">Para criar o serviço de dados usando o novo modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4d816-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="4d816-129">No [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra o arquivo .edmx que representa o modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="4d816-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="4d816-130">No **modelo navegador**, o modelo, clique **propriedades**e, em seguida, anote o nome do contêiner de entidade.</span><span class="sxs-lookup"><span data-stu-id="4d816-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="4d816-131">Em **Solution Explorer**, clique no nome do seu [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] do projeto e, em seguida, clique em **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="4d816-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="4d816-132">No **Adicionar Novo Item** caixa de diálogo, selecione **WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="4d816-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="4d816-133">Forneça um nome para o serviço e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="4d816-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4d816-134">O [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] cria a marcação XML e arquivos de código para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="4d816-134">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="4d816-135">Por padrão, a janela do editor de códigos é aberta.</span><span class="sxs-lookup"><span data-stu-id="4d816-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="4d816-136">No código para o serviço de dados, substitua o comentário `/* TODO: put your data source class name here */` na definição de classe que define o serviço de dados com o tipo que herda da classe <xref:System.Data.Objects.ObjectContext> e que é o contêiner de entidade do modelo de dados, que foi observado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="4d816-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="4d816-137">No código para o serviço de dados, permita que os clientes autorizados acessem os conjuntos de entidades que o serviço de dados expõe.</span><span class="sxs-lookup"><span data-stu-id="4d816-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="4d816-138">Para obter mais informações, consulte [criando o serviço de dados](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="4d816-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="4d816-139">Para testar o serviço de dados Northwind.svc usando um navegador da Web, siga as instruções no tópico [acessando o serviço de um navegador da Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="4d816-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d816-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4d816-140">See Also</span></span>  
 <span data-ttu-id="4d816-141">[Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md) (Definindo o WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="4d816-141">[Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)</span></span>  
 [<span data-ttu-id="4d816-142">Provedores de serviços de dados</span><span class="sxs-lookup"><span data-stu-id="4d816-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="4d816-143">Como: criar um serviço de dados usando o provedor de reflexão</span><span class="sxs-lookup"><span data-stu-id="4d816-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="4d816-144">Como: criar um serviço de dados usando um LINQ para a fonte de dados SQL</span><span class="sxs-lookup"><span data-stu-id="4d816-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)