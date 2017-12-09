---
title: "Para analisar o código-fonte LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e1677d8e30b083efe99f916b28672ddb6c3dd99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="d7c42-102">Para analisar o código-fonte LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d7c42-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="d7c42-103">Usando as seguintes etapas, você pode produzir o código-fonte de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de base de dados de exemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="d7c42-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="d7c42-104">Você pode comparar elementos modelo de objeto com os elementos de base de dados melhor para ver como os itens diferentes são mapeados.</span><span class="sxs-lookup"><span data-stu-id="d7c42-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7c42-105">Os desenvolvedores que usam [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] podem usar [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para gerar este código.</span><span class="sxs-lookup"><span data-stu-id="d7c42-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="d7c42-106">Se você ainda não tiver o base de dados de exemplo Northwind no seu computador de desenvolvimento, você poderá baixá-lo gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="d7c42-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="d7c42-107">Para obter mais informações, consulte [baixando bancos de dados de exemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d7c42-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="d7c42-108">Use a ferramenta de linha de comando SqlMetal para gerar um arquivo de origem Visual Basic ou C#.</span><span class="sxs-lookup"><span data-stu-id="d7c42-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="d7c42-109">Para obter mais informações, consulte [SqlMetal.exe (ferramenta de geração de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="d7c42-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="d7c42-110">Digitando os seguintes comandos em um prompt de comando, você pode gerar os arquivos de origem Visual Basic e C# que incluem procedimentos armazenados e funções:</span><span class="sxs-lookup"><span data-stu-id="d7c42-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="d7c42-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d7c42-111">See Also</span></span>  
 [<span data-ttu-id="d7c42-112">Referência</span><span class="sxs-lookup"><span data-stu-id="d7c42-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="d7c42-113">Informações de plano de fundo</span><span class="sxs-lookup"><span data-stu-id="d7c42-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)