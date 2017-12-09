---
title: "Rastreamento analítico com ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42683acdfe2e63d59a13496b210f83fb97c02de7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="41431-102">Rastreamento analítico com ETW</span><span class="sxs-lookup"><span data-stu-id="41431-102">Analytic Tracing with ETW</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="41431-103">rastreamento analítico oferece uma maneira de capturar informações de diagnóstico durante a execução de um [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] serviço.</span><span class="sxs-lookup"><span data-stu-id="41431-103"> analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="41431-104">eventos de rastreamento analítico são emitidos em pontos importantes a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] pilha para permitir a solução de problemas de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] serviços em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="41431-104"> analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="41431-105">Rastreamento analítico para [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services tem um impacto mínimo sobre o desempenho de um produto de servidor que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] serviços como esses eventos são emitidos com muita eficiência em uma sessão de rastreamento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="41431-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41431-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="41431-106">In This Section</span></span>  
 [<span data-ttu-id="41431-107">Visão geral de rastreamento analítico</span><span class="sxs-lookup"><span data-stu-id="41431-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="41431-108">Discute como [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] rastreamento analítico funciona em [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41431-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="41431-109">Rastreamento analítico habilitado dinamicamente</span><span class="sxs-lookup"><span data-stu-id="41431-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="41431-110">Descreve como habilitar ou desabilitar o rastreamento dinamicamente com o ETW.</span><span class="sxs-lookup"><span data-stu-id="41431-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="41431-111">Configurando o rastreamento de fluxo de mensagem</span><span class="sxs-lookup"><span data-stu-id="41431-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="41431-112">Descreve como configurar o rastreamento de fluxo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="41431-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="41431-113">Referência de evento de rastreamento analítico</span><span class="sxs-lookup"><span data-stu-id="41431-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="41431-114">Mostra uma tabela de IDs de eventos com níveis de evento, mensagens de eventos e as palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="41431-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41431-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="41431-115">See Also</span></span>  
 [<span data-ttu-id="41431-116">Serviços WCF e rastreamento de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="41431-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="41431-117">Rastreamento de eventos de rastreamento de evento no Windows</span><span class="sxs-lookup"><span data-stu-id="41431-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)