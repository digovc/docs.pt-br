---
title: Operador Xor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 34d317da5d85127e371c2df7229e0f0873972f50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604790"
---
# <a name="xor-operator-visual-basic"></a>Operador Xor (Visual Basic)
Executa uma exclusão lógica em duas `Boolean` expressões ou uma exclusão bit a bit em duas expressões numéricas.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Partes  
 `result`  
 Necessário. Qualquer `Boolean` ou variável numérica. Para comparação Boolean, `result` é a exclusão lógica (disjunção lógica exclusiva) de dois `Boolean` valores. Para operações bit a bit, `result` é um valor numérico que representa a exclusão bit a bit (disjunção bit a bit exclusiva) dos dois padrões numéricos de bits.  
  
 `expression1`  
 Necessário. Qualquer `Boolean` ou expressão numérica.  
  
 `expression2`  
 Necessário. Qualquer `Boolean` ou expressão numérica.  
  
## <a name="remarks"></a>Comentários  
 Para comparação Boolean, `result` é `True` se e somente se exatamente um `expression1` e `expression2` é avaliada como `True`. Ou seja, se e somente se `expression1` e `expression2` avaliar como oposto `Boolean` valores. A tabela a seguir ilustra como `result` é determinado.  
  
|Se `expression1` é|E `expression2` é|O valor de `result` é|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  Em uma comparação booliana, o `Xor` operador sempre avalia as duas expressões, que podem incluir chamadas de procedimento. Não há nenhum equivalente de curto-circuito para `Xor`, porque o resultado sempre depende dos dois operandos. Para *curto-circuito* operadores lógicos, consulte [operador AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) e [operador OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Para operações bit a bit, o `Xor` operador executa uma comparação bit a bit de bits posicionados identicamente em duas expressões numéricas e configura o bit no correspondente `result` acordo com a tabela a seguir.  
  
|Se bit no `expression1` é|E o bit na `expression2` é|O bit `result` é|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Como os operadores lógicos e bit a bit possuem uma precedência inferior que outros operadores aritméticos e relacionais, quaisquer operações bit a bit devem ser entre parênteses para garantir execução precisa.  
  
 Por exemplo, 5 `Xor` 3 é 6. Para ver por que isso assim, converta 5 e 3 em suas representações binárias, 101 e 011. Em seguida, use a tabela anterior para determinar que 101 Xor 011 é 110, que é a representação binária do número decimal 6.  
  
## <a name="data-types"></a>Tipos de Dados  
 Se os operandos consistem em uma `Boolean` expressão e uma expressão numérica, Visual Basic converte o `Boolean` expressão para um valor numérico (-1 para `True` e 0 para `False`) e executa uma operação bit a bit.  
  
 Para uma `Boolean` comparação, o tipo de dados do resultado é `Boolean`. Para obter uma comparação bit a bit, o tipo de dados do resultado é um tipo numérico apropriado para os tipos de dados de `expression1` e `expression2`. Consulte a tabela "Comparações relacionais e bit a bit" [tipos de dados de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 O `Xor` operador pode ser *sobrecarregado*, o que significa que uma classe ou estrutura pode redefinir seu comportamento quando um operando tem o tipo de classe ou estrutura. Se seu código usa esse operador em uma classe ou estrutura, certifique-se de que compreender o comportamento redefinido. Para obter mais informações, consulte [procedimentos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa o `Xor` operador para executar exclusão lógica (disjunção lógica exclusiva) em duas expressões. O resultado é um `Boolean` valor que representa se exatamente uma das expressões é `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 O exemplo anterior produz resultados `False`, `True`, e `False`, respectivamente.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa o `Xor` operador para executar exclusão lógica (disjunção lógica exclusiva) nos bits individuais de duas expressões numéricas. O bit no padrão resultante é definido se exatamente um dos bits correspondentes nos dois operandos é definido como 1.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 O exemplo anterior produz resultados 2, 12 e 14, respectivamente.  
  
## <a name="see-also"></a>Consulte também  
 [Operadores lógicos/bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedência do operador no Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores Listados por Funcionalidade](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores lógicos e bit a bit no Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
