---
title: "Método CloseAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: CloseAssembly
helpviewer_keywords: CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be68348b619f342eca4841a6052088bf7152f453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="e0e0e-102">Método CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="e0e0e-102">CloseAssembly Method</span></span>
<span data-ttu-id="e0e0e-103">Finaliza as operações de assembly.</span><span class="sxs-lookup"><span data-stu-id="e0e0e-103">Finalizes assembly operations.</span></span> <span data-ttu-id="e0e0e-104">Chame este método antes de iniciar um novo assembly ou módulo não associado.</span><span class="sxs-lookup"><span data-stu-id="e0e0e-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e0e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e0e0e-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0e0e-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e0e0e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e0e0e-107">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="e0e0e-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0e0e-108">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e0e0e-108">Return Value</span></span>  
 <span data-ttu-id="e0e0e-109">Retorna S_OK se o método for bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="e0e0e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e0e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0e0e-110">Requirements</span></span>  
 <span data-ttu-id="e0e0e-111">Requer alink.h.</span><span class="sxs-lookup"><span data-stu-id="e0e0e-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e0e-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e0e0e-112">See Also</span></span>  
 [<span data-ttu-id="e0e0e-113">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="e0e0e-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e0e0e-114">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="e0e0e-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e0e0e-115">API do ALink</span><span class="sxs-lookup"><span data-stu-id="e0e0e-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)