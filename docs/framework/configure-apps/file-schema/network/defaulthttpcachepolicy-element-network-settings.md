---
title: "&lt;defaultHttpCachePolicy&gt; elemento (configurações de rede)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f2db2fd10ca20209c21c8add71d8ee4f26951ca6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="16ce1-102">&lt;defaultHttpCachePolicy&gt; elemento (configurações de rede)</span><span class="sxs-lookup"><span data-stu-id="16ce1-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="16ce1-103">Descreve se o cache de HTTP está ativo e descreve a política de cache padrão.</span><span class="sxs-lookup"><span data-stu-id="16ce1-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="16ce1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="16ce1-104">\<configuration></span></span>  
<span data-ttu-id="16ce1-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="16ce1-105">\<system.net></span></span>  
<span data-ttu-id="16ce1-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="16ce1-106">\<requestCaching></span></span>  
<span data-ttu-id="16ce1-107">\<defaultHttpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="16ce1-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ce1-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="16ce1-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16ce1-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="16ce1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="16ce1-110">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="16ce1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16ce1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="16ce1-111">Attributes</span></span>  
  
|<span data-ttu-id="16ce1-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="16ce1-112">Attribute</span></span>|<span data-ttu-id="16ce1-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="16ce1-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="16ce1-114">Especifica o intervalo de tempo máximo antes de um objeto armazenado em cache está marcado como expirada.</span><span class="sxs-lookup"><span data-stu-id="16ce1-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="16ce1-115">Especifica o tempo máximo após o tempo de atualização computada antes que um objeto armazenado em cache está marcado como expirada.</span><span class="sxs-lookup"><span data-stu-id="16ce1-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="16ce1-116">Especifica o tempo mínimo de um objeto armazenado em cache para ser considerado atualizado.</span><span class="sxs-lookup"><span data-stu-id="16ce1-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="16ce1-117">Especifica se a política de cache é automático ou se o cache é ignorado.</span><span class="sxs-lookup"><span data-stu-id="16ce1-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="16ce1-118">O valor padrão é `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="16ce1-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16ce1-119">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="16ce1-119">Child Elements</span></span>  
 <span data-ttu-id="16ce1-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="16ce1-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16ce1-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="16ce1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="16ce1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="16ce1-122">Element</span></span>|<span data-ttu-id="16ce1-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="16ce1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16ce1-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="16ce1-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="16ce1-125">Controla o mecanismo de cache para solicitações de rede.</span><span class="sxs-lookup"><span data-stu-id="16ce1-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16ce1-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="16ce1-126">Remarks</span></span>  
 <span data-ttu-id="16ce1-127">O valor para o `policyLevel` atributo seja `BypassCache` ou `Default`.</span><span class="sxs-lookup"><span data-stu-id="16ce1-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="16ce1-128">Valores para o `maximumAge`, `maximumStale`, e `minimumFresh` elementos são um intervalo de tempo explícito com um formato de *d*. *hh*:*mm*:*ss* (dias, horas, minutos e segundos), ou as constantes `minValue` ou `maxValue`, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="16ce1-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="16ce1-129">Arquivos de Configuração</span><span class="sxs-lookup"><span data-stu-id="16ce1-129">Configuration Files</span></span>  
 <span data-ttu-id="16ce1-130">Esse elemento pode ser usado no arquivo de configuração do aplicativo ou o arquivo de configuração de máquina (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="16ce1-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16ce1-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="16ce1-131">Example</span></span>  
 <span data-ttu-id="16ce1-132">O exemplo a seguir mostra como especificar um tempo de novo mínimo de seis horas, um tempo de duração máxima de dois dias e um máximo obsoletas de quatro horas.</span><span class="sxs-lookup"><span data-stu-id="16ce1-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="16ce1-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="16ce1-133">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="16ce1-134">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="16ce1-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)