---
title: "Enumeração ECustomDumpFlavor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="2710f-102">Enumeração ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="2710f-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="2710f-103">Contém valores que indicam quais itens a serem incluídos em um subconjunto personalizado de um heap de despejo quando o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="2710f-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2710f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2710f-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="2710f-105">Membros</span><span class="sxs-lookup"><span data-stu-id="2710f-105">Members</span></span>  
  
|<span data-ttu-id="2710f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2710f-106">Member</span></span>|<span data-ttu-id="2710f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="2710f-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="2710f-108">Especifica que o despejo de pilha personalizado deve iniciar como um minidespejo e incluir dados extras especificados por qualquer [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instâncias passadas para o mesmo método.</span><span class="sxs-lookup"><span data-stu-id="2710f-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="2710f-109">Especifica que o despejo de pilha personalizado deve coletar todos os dados de estado de tempo de execução que não foi alocados dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="2710f-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2710f-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="2710f-110">Remarks</span></span>  
 <span data-ttu-id="2710f-111">Um parâmetro de tipo `ECustomDumpFlavor` é passado para o [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2710f-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2710f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2710f-112">Requirements</span></span>  
 <span data-ttu-id="2710f-113">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2710f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2710f-114">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2710f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2710f-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2710f-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2710f-116">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2710f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2710f-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2710f-117">See Also</span></span>  
 [<span data-ttu-id="2710f-118">Enumeração ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="2710f-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="2710f-119">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="2710f-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="2710f-120">Enumerações de hospedagem</span><span class="sxs-lookup"><span data-stu-id="2710f-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)