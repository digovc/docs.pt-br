---
title: "Método IDebugAutoAttach::AutoAttach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebugAutoAttach.AutoAttach
api_location: diasymreader.dll
api_type: COM
f1_keywords: IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 359aaf96c42a661657028d508f096f9625d4ba71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="3d81a-102">Método IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="3d81a-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="3d81a-103">Executa automaticamente do servidor chamado depurador anexar.</span><span class="sxs-lookup"><span data-stu-id="3d81a-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d81a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d81a-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d81a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3d81a-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="3d81a-106">[in] Sempre definido como `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="3d81a-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="3d81a-107">[in] Processar ID, normalmente é recuperado com o `GetCurrentProcessId` função.</span><span class="sxs-lookup"><span data-stu-id="3d81a-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="3d81a-108">[in] Tipo de programa: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, ou `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="3d81a-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="3d81a-109">[in] ID do programa.</span><span class="sxs-lookup"><span data-stu-id="3d81a-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="3d81a-110">[in] Cadeia de caracteres passada, o verbo debug.</span><span class="sxs-lookup"><span data-stu-id="3d81a-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d81a-111">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="3d81a-111">Return Value</span></span>  
 <span data-ttu-id="3d81a-112">S_OK se o método for bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="3d81a-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d81a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d81a-113">Requirements</span></span>  
 <span data-ttu-id="3d81a-114">**Cabeçalho:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="3d81a-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d81a-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3d81a-115">See Also</span></span>  
 [<span data-ttu-id="3d81a-116">Interface IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="3d81a-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)