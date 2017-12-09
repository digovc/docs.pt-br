---
title: '\=Operador'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ba74f7a433687b306e8b4273f3a2a6d60583396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator"></a><span data-ttu-id="ec014-102">\\= Operador</span><span class="sxs-lookup"><span data-stu-id="ec014-102">\\= Operator</span></span>
<span data-ttu-id="ec014-103">Divide o valor de uma variável ou propriedade pelo valor de uma expressão e atribui o resultado de inteiro para a variável ou propriedade.</span><span class="sxs-lookup"><span data-stu-id="ec014-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec014-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ec014-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ec014-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ec014-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ec014-106">Necessário.</span><span class="sxs-lookup"><span data-stu-id="ec014-106">Required.</span></span> <span data-ttu-id="ec014-107">Qualquer variável numérica ou propriedade.</span><span class="sxs-lookup"><span data-stu-id="ec014-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ec014-108">Necessário.</span><span class="sxs-lookup"><span data-stu-id="ec014-108">Required.</span></span> <span data-ttu-id="ec014-109">Qualquer expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="ec014-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec014-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="ec014-110">Remarks</span></span>  
 <span data-ttu-id="ec014-111">O elemento à esquerda do `\=` operador pode ser uma simples variável escalar, uma propriedade ou um elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="ec014-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ec014-112">A variável ou propriedade não pode ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ec014-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ec014-113">O `\=` operador divide o valor de uma variável ou propriedade à sua esquerda pelo valor à direita e atribui o resultado de inteiro para a variável ou propriedade à sua esquerda</span><span class="sxs-lookup"><span data-stu-id="ec014-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="ec014-114">Para obter mais informações sobre divisão, consulte [\ operador (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ec014-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ec014-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ec014-115">Overloading</span></span>  
 <span data-ttu-id="ec014-116">O `\` operador pode ser *sobrecarregado*, o que significa que uma classe ou estrutura pode redefinir seu comportamento quando um operando tem o tipo de classe ou estrutura.</span><span class="sxs-lookup"><span data-stu-id="ec014-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ec014-117">Sobrecarga de `\` operador afeta o comportamento do `\=` operador.</span><span class="sxs-lookup"><span data-stu-id="ec014-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="ec014-118">Se seu código usa `\=` em uma classe ou estrutura que sobrecarrega `\`, certifique-se de compreender o comportamento redefinido.</span><span class="sxs-lookup"><span data-stu-id="ec014-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ec014-119">Para obter mais informações, consulte [procedimentos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ec014-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec014-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ec014-120">Example</span></span>  
 <span data-ttu-id="ec014-121">O exemplo a seguir usa o `\=` operador para dividir uma `Integer` variável por um segundo e atribuir o resultado de inteiro à primeira variável.</span><span class="sxs-lookup"><span data-stu-id="ec014-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ec014-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ec014-122">See Also</span></span>  
 [<span data-ttu-id="ec014-123">\ Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec014-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="ec014-124">Operador / = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec014-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="ec014-125">Operadores de Atribuição</span><span class="sxs-lookup"><span data-stu-id="ec014-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="ec014-126">Operadores Aritméticos</span><span class="sxs-lookup"><span data-stu-id="ec014-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="ec014-127">Precedência do operador no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec014-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ec014-128">Operadores Listados por Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="ec014-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ec014-129">Instruções</span><span class="sxs-lookup"><span data-stu-id="ec014-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)