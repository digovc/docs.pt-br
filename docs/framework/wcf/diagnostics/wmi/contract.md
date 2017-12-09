---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20dbd0c86f012b6f29b752c4ad9195ce453f78b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="contract"></a><span data-ttu-id="6ad22-102">Contrato</span><span class="sxs-lookup"><span data-stu-id="6ad22-102">Contract</span></span>
<span data-ttu-id="6ad22-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="6ad22-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad22-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ad22-104">Syntax</span></span>  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6ad22-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6ad22-105">Methods</span></span>  
 <span data-ttu-id="6ad22-106">A classe de contrato não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="6ad22-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6ad22-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6ad22-107">Properties</span></span>  
 <span data-ttu-id="6ad22-108">A classe de contrato tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="6ad22-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="6ad22-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="6ad22-109">AppDomainId</span></span>  
 <span data-ttu-id="6ad22-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="6ad22-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="6ad22-111">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-112">A identificação appdomain do appdomain que hospeda o contrato.</span><span class="sxs-lookup"><span data-stu-id="6ad22-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="6ad22-113">Comportamentos</span><span class="sxs-lookup"><span data-stu-id="6ad22-113">Behaviors</span></span>  
 <span data-ttu-id="6ad22-114">Tipo de dados: matriz de comportamento</span><span class="sxs-lookup"><span data-stu-id="6ad22-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="6ad22-115">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-116">Os comportamentos associados a esse contrato.</span><span class="sxs-lookup"><span data-stu-id="6ad22-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="6ad22-117">Nome</span><span class="sxs-lookup"><span data-stu-id="6ad22-117">Name</span></span>  
 <span data-ttu-id="6ad22-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ad22-118">Data type: string</span></span>  
  
 <span data-ttu-id="6ad22-119">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-120">O nome do contrato em WSDL.</span><span class="sxs-lookup"><span data-stu-id="6ad22-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="6ad22-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="6ad22-121">Namespace</span></span>  
 <span data-ttu-id="6ad22-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ad22-122">Data type: string</span></span>  
  
 <span data-ttu-id="6ad22-123">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-124">O namespace do `portType` elemento em WSDL.</span><span class="sxs-lookup"><span data-stu-id="6ad22-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="6ad22-125">Operações</span><span class="sxs-lookup"><span data-stu-id="6ad22-125">Operations</span></span>  
 <span data-ttu-id="6ad22-126">Tipo de dados: matriz de operação</span><span class="sxs-lookup"><span data-stu-id="6ad22-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="6ad22-127">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-128">As operações desse contrato.</span><span class="sxs-lookup"><span data-stu-id="6ad22-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="6ad22-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="6ad22-129">ProcessId</span></span>  
 <span data-ttu-id="6ad22-130">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="6ad22-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="6ad22-131">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-132">O processo de identificação do processo que hospeda o contrato.</span><span class="sxs-lookup"><span data-stu-id="6ad22-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6ad22-133">ref</span><span class="sxs-lookup"><span data-stu-id="6ad22-133">ref</span></span>  
 <span data-ttu-id="6ad22-134">Tipo de dados: contrato</span><span class="sxs-lookup"><span data-stu-id="6ad22-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="6ad22-135">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-136">O tipo de retorno de chamada quando o contrato é um contrato duplex.</span><span class="sxs-lookup"><span data-stu-id="6ad22-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="6ad22-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="6ad22-137">SessionMode</span></span>  
 <span data-ttu-id="6ad22-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ad22-138">Data type: string</span></span>  
  
 <span data-ttu-id="6ad22-139">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-140">Indica se o contrato requer a associação associada a esse contrato use sessões do canal.</span><span class="sxs-lookup"><span data-stu-id="6ad22-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="6ad22-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ad22-141">Type</span></span>  
 <span data-ttu-id="6ad22-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ad22-142">Data type: string</span></span>  
  
 <span data-ttu-id="6ad22-143">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="6ad22-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6ad22-144">O tipo do contrato.</span><span class="sxs-lookup"><span data-stu-id="6ad22-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad22-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ad22-145">Requirements</span></span>  
  
|<span data-ttu-id="6ad22-146">MOF</span><span class="sxs-lookup"><span data-stu-id="6ad22-146">MOF</span></span>|<span data-ttu-id="6ad22-147">Declarado em Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6ad22-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6ad22-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="6ad22-148">Namespace</span></span>|<span data-ttu-id="6ad22-149">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6ad22-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ad22-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6ad22-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>