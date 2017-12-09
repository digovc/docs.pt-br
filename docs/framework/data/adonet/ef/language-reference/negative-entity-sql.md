---
title: '- (Negativo) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0cc2ca457fe8666bddd6f4ab40d2823d9d44c591
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="947fb-102">- (Negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="947fb-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="947fb-103">Retorna o negativo o valor de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="947fb-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="947fb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="947fb-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="947fb-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="947fb-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="947fb-106">Qualquer expressão válida de qualquer dos tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="947fb-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="947fb-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="947fb-107">Result Types</span></span>  
 <span data-ttu-id="947fb-108">O tipo de dados de `expression`.</span><span class="sxs-lookup"><span data-stu-id="947fb-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="947fb-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="947fb-109">Remarks</span></span>  
 <span data-ttu-id="947fb-110">Se `expression` é um tipo sem sinal, o tipo do resultado será o tipo com sinal que relaciona o melhor para o tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="947fb-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="947fb-111">Por exemplo, se `expression` é de bytes de tipo, um valor do tipo Int16 será retornado.</span><span class="sxs-lookup"><span data-stu-id="947fb-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="947fb-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="947fb-112">Example</span></span>  
 <span data-ttu-id="947fb-113">A seguinte consulta SQL Entity usa o operador - aritmético para retornar o negativo o valor de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="947fb-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="947fb-114">A consulta é baseada no modelo de vendas AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="947fb-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="947fb-115">Para compilar e executar essa consulta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="947fb-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="947fb-116">Siga o procedimento [como: executar uma consulta que retorna resultados de StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="947fb-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="947fb-117">Passe a consulta a seguir como um argumento para o método `ExecuteStructuralTypeQuery`:</span><span class="sxs-lookup"><span data-stu-id="947fb-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="947fb-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="947fb-118">See Also</span></span>  
 [<span data-ttu-id="947fb-119">Referência de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="947fb-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)