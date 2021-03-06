---
title: Suporte do namespace em DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e91ce2b36462780925dcaef701583a966c5f59b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569445"
---
# <a name="namespace-support-in-the-dom"></a>Suporte do namespace em DOM
O modelo de objeto (DOM) de documento XML é completamente URL ciente. Somente os documentos XML URL cientes são suportados. World Wide Web Consortium (W3C) especifica que os aplicativos DOM que o nível de implementar 1 pode estar ciente não-namespace-, e os recursos do nível 2 DOM são cientes URL. No entanto, todos os recursos em DOM XML são cientes URL, indiferente se o método é recomendação DOM nível de nível 1 ou 2.  
  
 Por exemplo, em uma configuração não-namespace- ciente, a chamada `setAttribute("A:b", "123")`, conforme especificado na recomendação de nível 1 DOM, não resulta em um atributo com um prefixo de `A` e um nome local de `b`. Resultaria em um atributo com o valor `A:b`.  
  
 Em um ambiente URL ciente, na chamada a resultados de `setAttribute("A:b", "123")` de nível 2 DOM em um atributo com um prefixo de `A` e um nome local de `b`. Isso é como os DOM do Microsoft .NET Framework trabalham.  
  
 Portanto, para todos os métodos que têm um parâmetro de nome, esses métodos também têm um prefixo para qualificar o nome. O parâmetro de nome, como `A:b` no método do nível 1 DOM de **setAttribute**, é analisado como segue:  
  
-   Se não houver nenhum caractere dois-pontos (:), então o nome local é definido para o parâmetro de `name` , e o prefixo e o NamespaceURI são cadeias de caracteres vazias.  
  
-   Se um dois-pontos é encontrado, o nome é dividido em duas partes com base na posição do primeiro caractere dois-pontos. O prefixo é definido para a cadeia de caracteres encontrada antes de pontos, e o nome local é definido para a cadeia de caracteres encontrada após os dois-pontos. Para os métodos que não têm um valor de NamespaceURI, o NamespaceURI não é resolvido e o não são definidas para a cadeia de caracteres vazia. Caso contrário, o NamespaceURI é definido para a cadeia de caracteres passada para o método. Se o prefixo for indefinido, o método **Save** e as propriedades **InnerXml** e **OuterXml** falharão.  
  
## <a name="see-also"></a>Consulte também  
 [DOM (Modelo de Objeto do Documento) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
