---
title: "Chamadas de segurança não autorizadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d66e700aa3aee0e577955a978cff0f5cedd84851
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="security-calls-not-authorized"></a><span data-ttu-id="12a2c-102">Chamadas de segurança não autorizadas</span><span class="sxs-lookup"><span data-stu-id="12a2c-102">Security Calls Not Authorized</span></span>
<span data-ttu-id="12a2c-103">Nome do contador: Chamadas de segurança não autorizadas.</span><span class="sxs-lookup"><span data-stu-id="12a2c-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="12a2c-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="12a2c-104">Description</span></span>  
 <span data-ttu-id="12a2c-105">Esse contador é incrementado quando o <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> método retornará `false`.</span><span class="sxs-lookup"><span data-stu-id="12a2c-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="12a2c-106">Ele indica que a mensagem de entrada é de um usuário válido e protegido adequadamente, mas o usuário não está autorizado a realizar tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="12a2c-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>