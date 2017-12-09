---
title: "Tipo intrínseco x:Code (XAML)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d1b21e2a654b18547c8da7da724c87946724f71f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="e2b6b-102">Tipo intrínseco x:Code (XAML)</span><span class="sxs-lookup"><span data-stu-id="e2b6b-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="e2b6b-103">Permite que o posicionamento de código dentro de uma produção XAML.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="e2b6b-104">Esse código pode ser compilado ou por qualquer implementação de processador XAML que compila XAML ou à esquerda na produção XAML para uso posterior, como interpretação por um tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="e2b6b-105">Uso de elemento Object do XAML</span><span class="sxs-lookup"><span data-stu-id="e2b6b-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="e2b6b-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="e2b6b-106">Remarks</span></span>  
 <span data-ttu-id="e2b6b-107">O código dentro do `x:Code` elemento de diretiva XAML é ainda interpretado dentro do namespace XML geral e os namespaces XAML fornecidos.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="e2b6b-108">Portanto, é geralmente necessário incluir o código usado para `x:Code` dentro de um `CDATA` segmento.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="e2b6b-109">`x:Code`não é permitido em todos os mecanismos possíveis de implantação de produção XAML.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="e2b6b-110">O código deve ser compilado em estruturas específicas (por exemplo, WPF).</span><span class="sxs-lookup"><span data-stu-id="e2b6b-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="e2b6b-111">Em outras estruturas, `x:Code` uso pode ser geralmente não permitido.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="e2b6b-112">Estruturas que permitem gerenciado `x:Code` de conteúdo, o compilador de idioma correto a ser usado para `x:Code` conteúdo é determinado pelas configurações e destinos do projeto que é usado para compilar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="e2b6b-113">Observações de uso do WPF</span><span class="sxs-lookup"><span data-stu-id="e2b6b-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="e2b6b-114">Código declarado em `x:Code` para WPF tem várias limitações importantes:</span><span class="sxs-lookup"><span data-stu-id="e2b6b-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="e2b6b-115">O `x:Code` elemento de diretiva deve ser um elemento filho imediato do elemento raiz da produção XAML.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="e2b6b-116">[Diretiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md) deve ser fornecido no elemento root pai.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-116">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="e2b6b-117">O código colocado em `x:Code` será tratado pela compilação como dentro do escopo da classe parcial que já está sendo criado para a página XAML.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="e2b6b-118">Portanto, todo código que você definir deve ser membros ou variáveis de classe parcial.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="e2b6b-119">Não é possível definir classes adicionais, que não seja de aninhamento de uma classe dentro da classe parcial (aninhamento é permitido, mas não é comum porque classes aninhadas não podem ser referenciados em XAML).</span><span class="sxs-lookup"><span data-stu-id="e2b6b-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="e2b6b-120">Namespaces CLR que não seja o namespace que é usado para a classe parcial existente não pode ser definido ou adicionado ao.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="e2b6b-121">Referências a entidades de código fora o namespace CLR de classe parcial devem ser totalmente qualificadas.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="e2b6b-122">Se membros que estão sendo declarados são substituições para membros de classe parcial, isso deve ser especificado com a palavra-chave override específico do idioma.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="e2b6b-123">Se membros declarados em `x:Code` escopo estão em conflito com os membros da classe parcial criada fora do XAML, de forma que o compilador informa que o conflito, o arquivo XAML não é possível compilar ou carregar.</span><span class="sxs-lookup"><span data-stu-id="e2b6b-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b6b-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e2b6b-124">See Also</span></span>  
 [<span data-ttu-id="e2b6b-125">Diretiva x:Class</span><span class="sxs-lookup"><span data-stu-id="e2b6b-125">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="e2b6b-126">Code-behind e XAML no WPF</span><span class="sxs-lookup"><span data-stu-id="e2b6b-126">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="e2b6b-127">Visão geral de XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e2b6b-127">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)