---
title: ISOF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 980256f4a1f2ef2055d46ead6c89b60650f4cdfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="isof-entity-sql"></a><span data-ttu-id="961b2-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="961b2-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="961b2-103">Determina se o tipo de uma expressão é do tipo especificado ou um de seus subtipos.</span><span class="sxs-lookup"><span data-stu-id="961b2-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961b2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="961b2-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="961b2-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="961b2-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="961b2-106">Qualquer expressão de consulta válida para determinar o tipo de.</span><span class="sxs-lookup"><span data-stu-id="961b2-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="961b2-107">NOT</span><span class="sxs-lookup"><span data-stu-id="961b2-107">NOT</span></span>  
 <span data-ttu-id="961b2-108">Nega o resultado de EDM.Boolean de ESTÁ DE.</span><span class="sxs-lookup"><span data-stu-id="961b2-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="961b2-109">SOMENTE</span><span class="sxs-lookup"><span data-stu-id="961b2-109">ONLY</span></span>  
 <span data-ttu-id="961b2-110">Especifica que É returns `true` somente se `expression` é do tipo `type` e não qualquer um de seus subtipos.</span><span class="sxs-lookup"><span data-stu-id="961b2-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="961b2-111">O tipo para testar `expression` contra.</span><span class="sxs-lookup"><span data-stu-id="961b2-111">The type to test `expression` against.</span></span> <span data-ttu-id="961b2-112">O tipo URL deve ser qualificada.</span><span class="sxs-lookup"><span data-stu-id="961b2-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="961b2-113">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="961b2-113">Return Value</span></span>  
 <span data-ttu-id="961b2-114">`true` se `expression` é do tipo T e T é um tipo base, ou um tipo derivado de `type`; se `expression` nulo é nulo em tempo de execução; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="961b2-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="961b2-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="961b2-115">Remarks</span></span>  
 <span data-ttu-id="961b2-116">As expressões `expression IS NOT OF (type)` e `expression IS NOT OF (ONLY type)` são sintaticamente equivalentes à `NOT (expression IS OF (type))` e `NOT (expression IS OF (ONLY type))`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="961b2-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="961b2-117">A tabela a seguir mostra o comportamento do operador de `IS OF` sobre alguns padrões e típicos do canto.</span><span class="sxs-lookup"><span data-stu-id="961b2-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="961b2-118">Todas as exceções são geradas do lado do cliente antes que o provedor obtenha chamado:</span><span class="sxs-lookup"><span data-stu-id="961b2-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="961b2-119">Padrão</span><span class="sxs-lookup"><span data-stu-id="961b2-119">Pattern</span></span>|<span data-ttu-id="961b2-120">Comportamento</span><span class="sxs-lookup"><span data-stu-id="961b2-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="961b2-121">o zero ESTÁ DE (EntityType)</span><span class="sxs-lookup"><span data-stu-id="961b2-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="961b2-122">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-122">Throws</span></span>|  
|<span data-ttu-id="961b2-123">o zero ESTÁ DE (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="961b2-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="961b2-124">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-124">Throws</span></span>|  
|<span data-ttu-id="961b2-125">o zero ESTÁ DE (RowType)</span><span class="sxs-lookup"><span data-stu-id="961b2-125">null IS OF (RowType)</span></span>|<span data-ttu-id="961b2-126">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-126">Throws</span></span>|  
|<span data-ttu-id="961b2-127">O DELEITE (zero) COMO EntityType ESTÁ DE (EntityType)</span><span class="sxs-lookup"><span data-stu-id="961b2-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="961b2-128">Retorna DBNull</span><span class="sxs-lookup"><span data-stu-id="961b2-128">Returns DBNull</span></span>|  
|<span data-ttu-id="961b2-129">O DELEITE (zero) COMO ComplexType ESTÁ DE (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="961b2-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="961b2-130">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-130">Throws</span></span>|  
|<span data-ttu-id="961b2-131">O DELEITE (zero) COMO RowType ESTÁ DE (RowType)</span><span class="sxs-lookup"><span data-stu-id="961b2-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="961b2-132">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-132">Throws</span></span>|  
|<span data-ttu-id="961b2-133">EntityType ESTÁ DE (EntityType)</span><span class="sxs-lookup"><span data-stu-id="961b2-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="961b2-134">Retorna retificam/falso</span><span class="sxs-lookup"><span data-stu-id="961b2-134">Returns true/false</span></span>|  
|<span data-ttu-id="961b2-135">ComplexType ESTÁ DE (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="961b2-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="961b2-136">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-136">Throws</span></span>|  
|<span data-ttu-id="961b2-137">RowType ESTÁ DE (RowType)</span><span class="sxs-lookup"><span data-stu-id="961b2-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="961b2-138">Gera</span><span class="sxs-lookup"><span data-stu-id="961b2-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="961b2-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="961b2-139">Example</span></span>  
 <span data-ttu-id="961b2-140">O seguinte [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta usa o operador é de para determinar o tipo de uma expressão de consulta e, em seguida, usa o operador de tratar para converter um objeto do tipo de curso em uma coleção de objetos do tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="961b2-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="961b2-141">A consulta se baseia o [modelo School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="961b2-141">The query is based on the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="961b2-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="961b2-142">See Also</span></span>  
 [<span data-ttu-id="961b2-143">Referência de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="961b2-143">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)