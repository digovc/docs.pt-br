---
title: LINHA (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 396b81e01d057f1d5c357f18d833a973777c07ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="row-entity-sql"></a><span data-ttu-id="b7884-102">LINHA (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b7884-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="b7884-103">Constrói registros anônimos e tipados estruturalmente de um ou mais valores.</span><span class="sxs-lookup"><span data-stu-id="b7884-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7884-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7884-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b7884-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="b7884-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b7884-106">Qualquer expressão de consulta válida que retorna um valor para construir em seguida o tipo.</span><span class="sxs-lookup"><span data-stu-id="b7884-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="b7884-107">Especifica um alias para uma linha no tipo especificado valor.</span><span class="sxs-lookup"><span data-stu-id="b7884-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="b7884-108">Se não for fornecido um alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta gerar um alias com base no [!INCLUDE[esql](../../../../../../includes/esql-md.md)] regras de geração de alias.</span><span class="sxs-lookup"><span data-stu-id="b7884-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7884-109">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="b7884-109">Return Value</span></span>  
 <span data-ttu-id="b7884-110">Um tipo de linha.</span><span class="sxs-lookup"><span data-stu-id="b7884-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7884-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="b7884-111">Remarks</span></span>  
 <span data-ttu-id="b7884-112">Usar construtores de linha no [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para construir estruturalmente tipados, anônimos registros de um ou mais valores.</span><span class="sxs-lookup"><span data-stu-id="b7884-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="b7884-113">O tipo do resultado de um construtor de linha é um tipo de linha cujos tipos de campo correspondem aos tipos de valores que foram usados para construir a linha.</span><span class="sxs-lookup"><span data-stu-id="b7884-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="b7884-114">Por exemplo, a expressão a seguir constrói um valor do tipo `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="b7884-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="b7884-115">Se você não fornecer um alias para um construtor de expressão em seguida, Entity Framework tentará gerar um.</span><span class="sxs-lookup"><span data-stu-id="b7884-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="b7884-116">Para obter mais informações, consulte a seção "Regras de alias" o [identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) tópico.</span><span class="sxs-lookup"><span data-stu-id="b7884-116">For more information, see the "Aliasing Rules" section of the [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="b7884-117">As seguintes regras se aplicam para o construtor de serrilha de expressão em uma linha:</span><span class="sxs-lookup"><span data-stu-id="b7884-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="b7884-118">O construtor das expressões em uma linha não pode referenciar outras alias no mesmo construtor.</span><span class="sxs-lookup"><span data-stu-id="b7884-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="b7884-119">Duas expressões no mesmo construtor de linha não podem ter as mesmas alias.</span><span class="sxs-lookup"><span data-stu-id="b7884-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="b7884-120">Para obter mais informações sobre os construtores de consulta, consulte [construindo tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b7884-120">For more information about query constructors, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7884-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b7884-121">Example</span></span>  
 <span data-ttu-id="b7884-122">A seguinte consulta SQL Entity usa o operador de LINHA para construir registros anônimos, estrutural tipados.</span><span class="sxs-lookup"><span data-stu-id="b7884-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="b7884-123">A consulta é baseada no modelo de vendas AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b7884-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b7884-124">Para compilar e executar essa consulta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7884-124">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b7884-125">Siga o procedimento [como: executar uma consulta que retorna resultados de StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b7884-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b7884-126">Passe a consulta a seguir como um argumento para o método `ExecuteStructuralTypeQuery`:</span><span class="sxs-lookup"><span data-stu-id="b7884-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="b7884-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b7884-127">See Also</span></span>  
 [<span data-ttu-id="b7884-128">Construindo tipos</span><span class="sxs-lookup"><span data-stu-id="b7884-128">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="b7884-129">Referência de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b7884-129">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="b7884-130">Definições de tipo</span><span class="sxs-lookup"><span data-stu-id="b7884-130">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)