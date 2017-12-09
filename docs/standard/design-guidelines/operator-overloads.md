---
title: Sobrecargas de operador
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffd472a7c410bd541ea0382f05f7ed92acb0e688
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-overloads"></a><span data-ttu-id="230a0-102">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="230a0-102">Operator Overloads</span></span>
<span data-ttu-id="230a0-103">Sobrecargas de operador permitem que os tipos de estrutura apareçam como se fossem primitivos de linguagem internas.</span><span class="sxs-lookup"><span data-stu-id="230a0-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="230a0-104">Embora permitido e útil em algumas situações, as sobrecargas de operador devem ser usadas com cautela.</span><span class="sxs-lookup"><span data-stu-id="230a0-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="230a0-105">Há muitos casos, no qual operador sobrecarga tem sido seja explorada, como quando os designers do framework iniciado usar operadores para operações que devem ser métodos simples.</span><span class="sxs-lookup"><span data-stu-id="230a0-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="230a0-106">As diretrizes a seguir devem ajudar a decidir quando e como usar sobrecarga de operador.</span><span class="sxs-lookup"><span data-stu-id="230a0-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="230a0-107">**X Evite** definindo sobrecargas de operador, exceto em tipos que devem se parecer com os tipos primitivos (internos).</span><span class="sxs-lookup"><span data-stu-id="230a0-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="230a0-108">**✓ CONSIDERE** definindo sobrecargas de operador em um tipo que deve se parecer com um tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="230a0-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="230a0-109">Por exemplo, <xref:System.String?displayProperty=nameWithType> tem `operator==` e `operator!=` definido.</span><span class="sxs-lookup"><span data-stu-id="230a0-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="230a0-110">**FAZER ✓** definir sobrecargas de operador em estruturas que representam números (como <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="230a0-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="230a0-111">**X não** ser bonita ao definir sobrecargas de operador.</span><span class="sxs-lookup"><span data-stu-id="230a0-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="230a0-112">Sobrecarga de operador é útil em casos em que é imediatamente óbvio qual será o resultado da operação.</span><span class="sxs-lookup"><span data-stu-id="230a0-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="230a0-113">Por exemplo, faz sentido para poder subtrair um <xref:System.DateTime> de outro `DateTime` e obter um <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="230a0-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="230a0-114">No entanto, não é apropriado usar o operador de união lógico para consultas união de dois bancos de dados ou usar o operador de deslocamento para gravar em um fluxo.</span><span class="sxs-lookup"><span data-stu-id="230a0-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="230a0-115">**X não** fornecer sobrecargas de operador, a menos que pelo menos um dos operandos é do tipo que define a sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="230a0-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="230a0-116">**FAZER ✓** sobrecarregar os operadores de forma simétrica.</span><span class="sxs-lookup"><span data-stu-id="230a0-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="230a0-117">Por exemplo, se você sobrecarregar o `operator==`, você também deve sobrecarregar o `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="230a0-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="230a0-118">Da mesma forma, se você sobrecarregar o `operator<`, você também deve sobrecarregar o `operator>`, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="230a0-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="230a0-119">**✓ CONSIDERE** fornecer métodos com nomes amigáveis que correspondem a cada operador sobrecarregado.</span><span class="sxs-lookup"><span data-stu-id="230a0-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="230a0-120">Muitos idiomas não dão suporte a sobrecarga de operador.</span><span class="sxs-lookup"><span data-stu-id="230a0-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="230a0-121">Por esse motivo, é recomendável que tipos de operadores de sobrecarga incluem um método secundário com um nome específico do domínio apropriado que fornece funcionalidade equivalente.</span><span class="sxs-lookup"><span data-stu-id="230a0-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="230a0-122">A tabela a seguir contém uma lista de operadores e os nomes de método amigável correspondentes.</span><span class="sxs-lookup"><span data-stu-id="230a0-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="230a0-123">Símbolo do operador c#</span><span class="sxs-lookup"><span data-stu-id="230a0-123">C# Operator Symbol</span></span>|<span data-ttu-id="230a0-124">Nome de metadados</span><span class="sxs-lookup"><span data-stu-id="230a0-124">Metadata Name</span></span>|<span data-ttu-id="230a0-125">Nome Amigável</span><span class="sxs-lookup"><span data-stu-id="230a0-125">Friendly Name</span></span>|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a><span data-ttu-id="230a0-126">Sobrecarga de operador = =</span><span class="sxs-lookup"><span data-stu-id="230a0-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="230a0-127">Sobrecarga `operator ==` é bastante complicada.</span><span class="sxs-lookup"><span data-stu-id="230a0-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="230a0-128">A semântica do operador precisa ser compatível com vários membros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="230a0-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="230a0-129">Operadores de conversão</span><span class="sxs-lookup"><span data-stu-id="230a0-129">Conversion Operators</span></span>  
 <span data-ttu-id="230a0-130">Operadores de conversão são operadores unários que permitem que a conversão de um tipo para outro.</span><span class="sxs-lookup"><span data-stu-id="230a0-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="230a0-131">Os operadores devem ser definidos como membros estáticos em um operando ou o tipo de retorno.</span><span class="sxs-lookup"><span data-stu-id="230a0-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="230a0-132">Há dois tipos de operadores de conversão: implícitas e explícitas.</span><span class="sxs-lookup"><span data-stu-id="230a0-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="230a0-133">**X não** fornecer um operador de conversão se tal conversão não é esperado claramente pelos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="230a0-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="230a0-134">**X não** definir operadores de conversão fora do domínio do tipo.</span><span class="sxs-lookup"><span data-stu-id="230a0-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="230a0-135">Por exemplo, <xref:System.Int32>, <xref:System.Double>, e <xref:System.Decimal> são todos os tipos numéricos, enquanto <xref:System.DateTime> não é.</span><span class="sxs-lookup"><span data-stu-id="230a0-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="230a0-136">Portanto, não deve haver nenhum operador de conversão para converter um `Double(long)` para um `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="230a0-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="230a0-137">Um construtor é preferido nesse caso.</span><span class="sxs-lookup"><span data-stu-id="230a0-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="230a0-138">**X não** fornecer um operador de conversão implícita, se a conversão é potencialmente com perdas.</span><span class="sxs-lookup"><span data-stu-id="230a0-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="230a0-139">Por exemplo, não deve haver uma conversão implícita de `Double` para `Int32` porque `Double` tem um intervalo maior que `Int32`.</span><span class="sxs-lookup"><span data-stu-id="230a0-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="230a0-140">Um operador de conversão explícita pode ser fornecido, mesmo se a conversão é potencialmente com perdas.</span><span class="sxs-lookup"><span data-stu-id="230a0-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="230a0-141">**X não** lançam exceções de conversões implícitas.</span><span class="sxs-lookup"><span data-stu-id="230a0-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="230a0-142">É muito difícil para os usuários finais entender o que está acontecendo, porque ele podem não estar ciente de que uma conversão está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="230a0-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="230a0-143">**FAZER ✓** gerar <xref:System.InvalidCastException?displayProperty=nameWithType> se uma chamada para um operador de conversão resulta em uma conversão de perdas e o contrato do operador não permite conversões com perdas.</span><span class="sxs-lookup"><span data-stu-id="230a0-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="230a0-144">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="230a0-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="230a0-145">*Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="230a0-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230a0-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="230a0-146">See Also</span></span>  
 [<span data-ttu-id="230a0-147">Diretrizes de Design de membro</span><span class="sxs-lookup"><span data-stu-id="230a0-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="230a0-148">Diretrizes de design do Framework</span><span class="sxs-lookup"><span data-stu-id="230a0-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)