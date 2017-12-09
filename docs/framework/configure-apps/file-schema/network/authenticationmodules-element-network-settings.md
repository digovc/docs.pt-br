---
title: "&lt;authenticationModules&gt; elemento (configurações de rede)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fe2e1757a3e2da5c2aa6084c0eb21164de3ece0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="03763-102">&lt;authenticationModules&gt; elemento (configurações de rede)</span><span class="sxs-lookup"><span data-stu-id="03763-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="03763-103">Especifica os módulos usados para autenticar solicitações de rede.</span><span class="sxs-lookup"><span data-stu-id="03763-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="03763-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03763-104">\<configuration></span></span>  
<span data-ttu-id="03763-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="03763-105">\<system.net></span></span>  
<span data-ttu-id="03763-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="03763-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03763-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="03763-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03763-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="03763-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03763-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="03763-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03763-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="03763-110">Attributes</span></span>  
 <span data-ttu-id="03763-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="03763-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03763-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="03763-112">Child Elements</span></span>  
  
|<span data-ttu-id="03763-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="03763-113">**Element**</span></span>|<span data-ttu-id="03763-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="03763-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="03763-115">add</span><span class="sxs-lookup"><span data-stu-id="03763-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="03763-116">Adiciona um módulo de autenticação para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="03763-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="03763-117">clear</span><span class="sxs-lookup"><span data-stu-id="03763-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="03763-118">Limpa todos os módulos de autenticação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="03763-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="03763-119">remove</span><span class="sxs-lookup"><span data-stu-id="03763-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="03763-120">Remove um módulo de autenticação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="03763-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03763-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="03763-121">Parent Elements</span></span>  
  
|<span data-ttu-id="03763-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="03763-122">**Element**</span></span>|<span data-ttu-id="03763-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="03763-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="03763-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="03763-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="03763-125">Contém configurações que especificam como o .NET Framework se conecta à rede.</span><span class="sxs-lookup"><span data-stu-id="03763-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03763-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="03763-126">Remarks</span></span>  
 <span data-ttu-id="03763-127">O `authenticationModule` elemento Especifica os módulos de autenticação que realizar o processo de autenticação com um servidor.</span><span class="sxs-lookup"><span data-stu-id="03763-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="03763-128">Um módulo de autenticação deve implementar o <xref:System.Net.IAuthenticationModule> interface.</span><span class="sxs-lookup"><span data-stu-id="03763-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="03763-129">Arquivos de Configuração</span><span class="sxs-lookup"><span data-stu-id="03763-129">Configuration Files</span></span>  
 <span data-ttu-id="03763-130">Esse elemento pode ser usado no arquivo de configuração do aplicativo ou o arquivo de configuração de máquina (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="03763-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03763-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="03763-131">Example</span></span>  
 <span data-ttu-id="03763-132">O exemplo a seguir permite que um módulo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="03763-132">The following example enables an authentication module.</span></span> <span data-ttu-id="03763-133">Você deve substituir os valores de versão e PublicKeyToken com os valores corretos para o módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="03763-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03763-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="03763-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="03763-135">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="03763-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)