---
title: Lendo um documento XML no DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="f2b72-102">Lendo um documento XML no DOM</span><span class="sxs-lookup"><span data-stu-id="f2b72-102">Reading an XML Document into the DOM</span></span>
<span data-ttu-id="f2b72-103">As informações XML são lidas na memória em diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="f2b72-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="f2b72-104">Podem ser lidas de uma cadeia de caracteres, de um fluxo, de uma URL, de um leitor de texto ou de uma classe derivada de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f2b72-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="f2b72-105">O método <xref:System.Xml.XmlDocument.Load%2A> leva o documento para a memória e tem métodos sobrecarregados disponíveis para utilizar dados de cada um dos diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="f2b72-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="f2b72-106">Existe também um método <xref:System.Xml.XmlDocument.LoadXml%2A> que lê XML de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f2b72-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="f2b72-107">Diferentes métodos de <xref:System.Xml.XmlDocument.Load%2A> afetam os nós que são criados quando o DOM (Document Object Model) é carregado.</span><span class="sxs-lookup"><span data-stu-id="f2b72-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="f2b72-108">A tabela a seguir lista as diferenças entre alguns dos métodos de <xref:System.Xml.XmlDocument.Load%2A> e os tópicos que os abordam.</span><span class="sxs-lookup"><span data-stu-id="f2b72-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="f2b72-109">Assunto</span><span class="sxs-lookup"><span data-stu-id="f2b72-109">Subject</span></span>|<span data-ttu-id="f2b72-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="f2b72-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="f2b72-111">Criação de nós de espaços em branco</span><span class="sxs-lookup"><span data-stu-id="f2b72-111">Creation of white space nodes</span></span>|<span data-ttu-id="f2b72-112">O objeto usado para carregar o DOM tem um efeito no espaço em branco e nos nós de espaço em branco significativos gerados no DOM.</span><span class="sxs-lookup"><span data-stu-id="f2b72-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="f2b72-113">Para obter mais informações, consulte [espaço em branco e o espaço em branco significativo tratamento durante o carregamento de DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="f2b72-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="f2b72-114">Carregando o XML a partir de um nó específico ou carregando todo o documento XML</span><span class="sxs-lookup"><span data-stu-id="f2b72-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="f2b72-115">Usando o <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> dados de método podem ser carregados de um nó específico no DOM.</span><span class="sxs-lookup"><span data-stu-id="f2b72-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="f2b72-116">Para obter mais informações, consulte [carregar dados de um leitor](../../../../docs/standard/data/xml/load-data-from-a-reader.md).</span><span class="sxs-lookup"><span data-stu-id="f2b72-116">For more information, see [Load Data from a Reader](../../../../docs/standard/data/xml/load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="f2b72-117">Validando o XML à medida que é carregado</span><span class="sxs-lookup"><span data-stu-id="f2b72-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="f2b72-118">Os dados XML carregados no DOM podem ser validados à medida que são carregados.</span><span class="sxs-lookup"><span data-stu-id="f2b72-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="f2b72-119">Isso é feito usando um <xref:System.Xml.XmlReader> de validação.</span><span class="sxs-lookup"><span data-stu-id="f2b72-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="f2b72-120">Para obter mais informações sobre como validar XML quando ele é carregado, consulte [Validando um documento XML no DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="f2b72-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="f2b72-121">O exemplo a seguir mostra o XML que está sendo carregado com o método <xref:System.Xml.XmlDocument.LoadXml%2A> e os dados salvos subsequentemente em um arquivo de texto chamado `data.xml`.</span><span class="sxs-lookup"><span data-stu-id="f2b72-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2b72-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f2b72-122">See Also</span></span>  
 [<span data-ttu-id="f2b72-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="f2b72-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)