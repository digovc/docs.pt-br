---
title: HttpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 612f2eb04ae3449fddc8fb871683b26138d046d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="4cd39-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4cd39-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="4cd39-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4cd39-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd39-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4cd39-104">Syntax</span></span>  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4cd39-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4cd39-105">Methods</span></span>  
 <span data-ttu-id="4cd39-106">A classe HttpTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="4cd39-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4cd39-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4cd39-107">Properties</span></span>  
 <span data-ttu-id="4cd39-108">A classe HttpTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="4cd39-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="4cd39-109">allowCookies</span><span class="sxs-lookup"><span data-stu-id="4cd39-109">AllowCookies</span></span>  
 <span data-ttu-id="4cd39-110">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="4cd39-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4cd39-111">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-112">Um valor que indica se o cliente aceita cookies e os propaga em solicitações futuras.</span><span class="sxs-lookup"><span data-stu-id="4cd39-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="4cd39-113">authenticationScheme</span><span class="sxs-lookup"><span data-stu-id="4cd39-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="4cd39-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-114">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-115">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-116">O esquema de autenticação usado para autenticar solicitações de cliente processadas por um ouvinte HTTP.</span><span class="sxs-lookup"><span data-stu-id="4cd39-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="4cd39-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="4cd39-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="4cd39-118">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="4cd39-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4cd39-119">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-120">Um valor que indica se os proxies são ignorados para endereços locais.</span><span class="sxs-lookup"><span data-stu-id="4cd39-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="4cd39-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="4cd39-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="4cd39-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-122">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-123">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-124">Um valor que indica se o nome do host é usado para acessar o serviço ao fazer correspondência no URI.</span><span class="sxs-lookup"><span data-stu-id="4cd39-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="4cd39-125">keepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="4cd39-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="4cd39-126">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="4cd39-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4cd39-127">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-128">Quando habilitada, as conexões HTTP são mantidas ativas independentemente do nível de atividade.</span><span class="sxs-lookup"><span data-stu-id="4cd39-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="4cd39-129">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="4cd39-129">MaxBufferSize</span></span>  
 <span data-ttu-id="4cd39-130">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="4cd39-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="4cd39-131">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-132">O tamanho máximo do pool de buffers.</span><span class="sxs-lookup"><span data-stu-id="4cd39-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="4cd39-133">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="4cd39-133">ProxyAddress</span></span>  
 <span data-ttu-id="4cd39-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-134">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-135">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-136">Um URI que contém o endereço do proxy a ser usado para solicitações HTTP.</span><span class="sxs-lookup"><span data-stu-id="4cd39-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="4cd39-137">proxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="4cd39-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="4cd39-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-138">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-139">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-140">O esquema de autenticação usado para autenticar solicitações de cliente processadas por um proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="4cd39-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="4cd39-141">território</span><span class="sxs-lookup"><span data-stu-id="4cd39-141">Realm</span></span>  
 <span data-ttu-id="4cd39-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-142">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-143">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-144">O realm de autenticação.</span><span class="sxs-lookup"><span data-stu-id="4cd39-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="4cd39-145">transferMode</span><span class="sxs-lookup"><span data-stu-id="4cd39-145">TransferMode</span></span>  
 <span data-ttu-id="4cd39-146">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd39-146">Data type: string</span></span>  
  
 <span data-ttu-id="4cd39-147">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-148">Um valor que especifica se as mensagens são armazenados em buffer ou transmitidas ou uma solicitação ou resposta.</span><span class="sxs-lookup"><span data-stu-id="4cd39-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="4cd39-149">unsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="4cd39-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="4cd39-150">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="4cd39-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="4cd39-151">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-152">Um valor que indica se o compartilhamento de Conexão não segura está habilitada no servidor.</span><span class="sxs-lookup"><span data-stu-id="4cd39-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="4cd39-153">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="4cd39-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="4cd39-154">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="4cd39-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="4cd39-155">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="4cd39-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4cd39-156">Um valor que indica se as configurações de proxy de todo o computador são usadas em vez de configurações específicas do usuário.</span><span class="sxs-lookup"><span data-stu-id="4cd39-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd39-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cd39-157">Requirements</span></span>  
  
|<span data-ttu-id="4cd39-158">MOF</span><span class="sxs-lookup"><span data-stu-id="4cd39-158">MOF</span></span>|<span data-ttu-id="4cd39-159">Declarado em Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4cd39-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4cd39-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="4cd39-160">Namespace</span></span>|<span data-ttu-id="4cd39-161">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4cd39-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4cd39-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4cd39-162">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>