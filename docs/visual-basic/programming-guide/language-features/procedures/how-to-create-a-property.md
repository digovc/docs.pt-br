---
title: Como criar uma propriedade (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 6e3faed9880b6417f17ab8fe84bc5162e803c437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656237"
---
# <a name="how-to-create-a-property-visual-basic"></a>Como criar uma propriedade (Visual Basic)
Coloque uma definição de propriedade entre uma `Property` instrução e um `End Property` instrução. Nessa definição você define um `Get` procedimento, uma `Set` procedimento, ou ambos. Todo o código da propriedade está situado nesses procedimentos.  
  
 O `Get` procedimento recupera o valor da propriedade e o `Set` procedimento armazena um valor. Se você quiser que a propriedade para ter acesso de leitura/gravação, você deve definir ambos os procedimentos. Para uma propriedade somente leitura, você define apenas `Get`, e para uma propriedade somente gravação, você define apenas `Set`.  
  
### <a name="to-create-a-property"></a>Para criar uma propriedade  
  
1.  Fora de qualquer propriedade ou procedimento, utilize uma [declaração de propriedade](../../../../visual-basic/language-reference/statements/property-statement.md), seguido por um `End Property` instrução.  
  
2.  Se a propriedade usa parâmetros, execute o `Property` palavra-chave com o nome do procedimento, a lista de parâmetros entre parênteses.  
  
3.  Siga os parênteses com uma `As` cláusula para especificar o tipo de dados do valor da propriedade. Você deve especificar o tipo de dados, mesmo para uma propriedade somente gravação.  
  
4.  Adicionar `Get` e `Set` procedimentos, conforme apropriado. Consulte as instruções a seguir.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Para criar um procedimento Get que recupera um valor de propriedade  
  
1.  Entre o `Property` e `End Property` escrever instruções, uma [obter instrução](../../../../visual-basic/language-reference/statements/get-statement.md), seguido por um `End Get` instrução. Você não precisa definir nenhum parâmetro para o `Get` procedimento.  
  
2.  Coloque as declarações de código para recuperar o valor da propriedade entre o `Get` e `End Get` instruções. Esse código pode incluir outros cálculos e manipulações de dados, além de gerar e retornar o valor da propriedade.  
  
3.  Use um `Return` instrução para retornar o valor da propriedade para o código de chamada.  
  
 Você deve escrever uma `Get` procedimento para uma propriedade de leitura-gravação e para uma propriedade somente leitura. Você não deve definir um `Get` procedimento para uma propriedade somente gravação.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Para criar um procedimento Set que grava um valor de propriedade  
  
1.  Entre o `Property` e `End Property` instruções, gravar um [instrução Set](../../../../visual-basic/language-reference/statements/set-statement.md), seguido por um `End Set` instrução.  
  
2.  No `Set` instrução, siga o `Set` palavra-chave com uma lista de parâmetros entre parênteses. Esta lista de parâmetros deve incluir pelo menos um parâmetro de valor para o valor passado pelo código de chamada. O nome padrão para este parâmetro de valor é `Value`, mas você pode usar um nome diferente, se apropriado. O parâmetro de valor deve ter os mesmos dados de tipo da propriedade.  
  
3.  Coloque as declarações de código para armazenar um valor na propriedade entre o `Set` e `End Set` instruções. Esse código pode incluir outros cálculos e manipulações de dados, além de validação e o valor da propriedade de armazenamento.  
  
4.  Use o parâmetro de valor para aceitar o valor fornecido pelo código de chamada. Você pode armazenar esse valor diretamente em uma instrução de atribuição ou usá-lo em uma expressão para calcular o valor interno a ser armazenado.  
  
 Você deve escrever uma `Set` procedimento para uma propriedade de leitura-gravação e para uma propriedade somente gravação. Você não deve definir um `Set` procedimento para uma propriedade somente leitura.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir cria uma propriedade de leitura/gravação que armazena um nome completo como dois nomes constituintes, o nome e o sobrenome. Quando o código de chamada lê `fullName`, o `Get` procedimento combina as duas partes e retorna o nome completo. Quando o código de chamada atribui um novo nome completo, o `Set` procedimento tenta dividi-lo em duas partes. Se ele não encontrar um espaço, ele armazena como o nome.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 O exemplo a seguir mostra chamadas típicas para os procedimentos de propriedade `fullName`. A primeira chamada define o valor da propriedade e recupera a segunda chamada.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos](./index.md)  
 [Procedimentos de Propriedade](./property-procedures.md)  
 [Parâmetros e Argumentos de Procedimento](./procedure-parameters-and-arguments.md)  
 [Diferenças entre propriedades e variáveis no Visual Basic](./differences-between-properties-and-variables.md)  
 [Como declarar uma propriedade com níveis de acesso mistos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Como chamar um procedimento de propriedade](./how-to-call-a-property-procedure.md)  
 [Como: declarar e chamar uma propriedade padrão no Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Como inserir um valor em uma propriedade](./how-to-put-a-value-in-a-property.md)  
 Como obter um valor de uma propriedade (Visual Basic)[Como obter um valor de uma propriedade](./how-to-get-a-value-from-a-property.md)
