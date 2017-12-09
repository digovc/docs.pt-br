---
title: "Noções básicas de autenticação HTTP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9376309a-39e3-4819-b47b-a73982b57620
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b41e47ae4067ac52cc747d675ec5231f25b1352
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="understanding-http-authentication"></a><span data-ttu-id="be020-102">Noções básicas de autenticação HTTP</span><span class="sxs-lookup"><span data-stu-id="be020-102">Understanding HTTP Authentication</span></span>
<span data-ttu-id="be020-103">A autenticação é o processo de identificar se um cliente tem permissão para acessar um recurso.</span><span class="sxs-lookup"><span data-stu-id="be020-103">Authentication is the process of identifying whether a client is eligible to access a resource.</span></span> <span data-ttu-id="be020-104">O protocolo HTTP oferece suporte à autenticação como um meio de negociação de acesso a um recurso seguro.</span><span class="sxs-lookup"><span data-stu-id="be020-104">The HTTP protocol supports authentication as a means of negotiating access to a secure resource.</span></span>  
  
 <span data-ttu-id="be020-105">A solicitação inicial de um cliente normalmente é uma solicitação anônima, não contém informações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="be020-105">The initial request from a client is typically an anonymous request, not containing any authentication information.</span></span> <span data-ttu-id="be020-106">Aplicativos de servidor HTTP podem negar a solicitação anônima ao indicando que a autenticação é necessária.</span><span class="sxs-lookup"><span data-stu-id="be020-106">HTTP server applications can deny the anonymous request while indicating that authentication is required.</span></span> <span data-ttu-id="be020-107">O aplicativo de servidor envia os cabeçalhos de autenticação da Web para indicar os esquemas de autenticação com suporte.</span><span class="sxs-lookup"><span data-stu-id="be020-107">The server application sends WWW-Authentication headers to indicate the supported authentication schemes.</span></span> <span data-ttu-id="be020-108">Este documento descreve vários esquemas de autenticação para HTTP e discute o suporte em [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be020-108">This document describes several authentication schemes for HTTP and discusses their support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="http-authentication-schemes"></a><span data-ttu-id="be020-109">Esquemas de autenticação HTTP</span><span class="sxs-lookup"><span data-stu-id="be020-109">HTTP Authentication Schemes</span></span>  
 <span data-ttu-id="be020-110">O servidor pode especificar vários esquemas de autenticação do cliente escolher.</span><span class="sxs-lookup"><span data-stu-id="be020-110">The server can specify multiple authentication schemes for the client to choose from.</span></span> <span data-ttu-id="be020-111">A tabela a seguir descreve alguns esquemas de autenticação geralmente encontrados em aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="be020-111">The following table describes some of the authentication schemes commonly found in Windows applications.</span></span>  
  
|<span data-ttu-id="be020-112">Esquema de autenticação</span><span class="sxs-lookup"><span data-stu-id="be020-112">Authentication Scheme</span></span>|<span data-ttu-id="be020-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="be020-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="be020-114">Anônimo</span><span class="sxs-lookup"><span data-stu-id="be020-114">Anonymous</span></span>|<span data-ttu-id="be020-115">Uma solicitação anônima não contém informações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="be020-115">An anonymous request does not contain any authentication information.</span></span> <span data-ttu-id="be020-116">Isso é equivalente a conceder todos acesso ao recurso.</span><span class="sxs-lookup"><span data-stu-id="be020-116">This is equivalent to granting everyone access to the resource.</span></span>|  
|<span data-ttu-id="be020-117">Basic</span><span class="sxs-lookup"><span data-stu-id="be020-117">Basic</span></span>|<span data-ttu-id="be020-118">Autenticação básica envia uma cadeia de caracteres codificada em Base64 que contém um nome de usuário e senha para o cliente.</span><span class="sxs-lookup"><span data-stu-id="be020-118">Basic authentication sends a Base64-encoded string that contains a user name and password for the client.</span></span> <span data-ttu-id="be020-119">Base64 não é uma forma de criptografia e deve ser considerado igual a enviar o nome de usuário e senha em texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="be020-119">Base64 is not a form of encryption and should be considered the same as sending the user name and password in clear text.</span></span> <span data-ttu-id="be020-120">Se precisar de um recurso a ser protegida, considere fortemente usando um esquema de autenticação diferente da autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="be020-120">If a resource needs to be protected, strongly consider using an authentication scheme other than basic authentication.</span></span>|  
|<span data-ttu-id="be020-121">Digest</span><span class="sxs-lookup"><span data-stu-id="be020-121">Digest</span></span>|<span data-ttu-id="be020-122">A autenticação Digest é um esquema de desafio / resposta que substitui a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="be020-122">Digest authentication is a challenge-response scheme that is intended to replace Basic authentication.</span></span> <span data-ttu-id="be020-123">O servidor envia uma cadeia de caracteres dos dados aleatórios chamados um *nonce* ao cliente como um desafio.</span><span class="sxs-lookup"><span data-stu-id="be020-123">The server sends a string of random data called a *nonce* to the client as a challenge.</span></span> <span data-ttu-id="be020-124">O cliente responde com um hash que inclui o nome de usuário, senha e nonce entre informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="be020-124">The client responds with a hash that includes the user name, password, and nonce, among additional information.</span></span> <span data-ttu-id="be020-125">A complexidade que apresenta este exchange e o hash de dados tornar mais difícil roubar e reutilizar as credenciais do usuário com esse esquema de autenticação.</span><span class="sxs-lookup"><span data-stu-id="be020-125">The complexity this exchange introduces and the data hashing make it more difficult to steal and reuse the user's credentials with this authentication scheme.</span></span><br /><br /> <span data-ttu-id="be020-126">A autenticação Digest requer o uso de contas de domínio do Windows.</span><span class="sxs-lookup"><span data-stu-id="be020-126">Digest authentication requires the use of Windows domain accounts.</span></span> <span data-ttu-id="be020-127">O resumo de *realm* é o nome de domínio do Windows.</span><span class="sxs-lookup"><span data-stu-id="be020-127">The digest *realm* is the Windows domain name.</span></span> <span data-ttu-id="be020-128">Portanto, você não pode usar um servidor em execução em um sistema operacional que não oferece suporte a domínios do Windows, como o Windows XP Home Edition, com a autenticação Digest.</span><span class="sxs-lookup"><span data-stu-id="be020-128">Therefore, you cannot use a server running on an operating system that does not support Windows domains, such as Windows XP Home Edition, with Digest authentication.</span></span> <span data-ttu-id="be020-129">Por outro lado, quando o cliente é executado em um sistema operacional que não oferece suporte a domínios do Windows, uma conta de domínio deve ser explicitamente especificada durante a autenticação.</span><span class="sxs-lookup"><span data-stu-id="be020-129">Conversely, when the client runs on an operating system that does not support Windows domains, a domain account must be explicitly specified during the authentication.</span></span>|  
|<span data-ttu-id="be020-130">NTLM</span><span class="sxs-lookup"><span data-stu-id="be020-130">NTLM</span></span>|<span data-ttu-id="be020-131">Autenticação NT LAN Manager (NTLM) é um esquema de desafio / resposta que é uma variação protegida da autenticação Digest.</span><span class="sxs-lookup"><span data-stu-id="be020-131">NT LAN Manager (NTLM) authentication is a challenge-response scheme that is a securer variation of Digest authentication.</span></span> <span data-ttu-id="be020-132">NTLM usa as credenciais do Windows para transformar os dados de desafio em vez da senha e nome de usuário sem codificação.</span><span class="sxs-lookup"><span data-stu-id="be020-132">NTLM uses Windows credentials to transform the challenge data instead of the unencoded user name and password.</span></span> <span data-ttu-id="be020-133">A autenticação NTLM exige várias trocas entre o cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="be020-133">NTLM authentication requires multiple exchanges between the client and server.</span></span> <span data-ttu-id="be020-134">O servidor e todos os proxies intermediários devem oferecer suporte a conexões persistentes para concluir com êxito a autenticação.</span><span class="sxs-lookup"><span data-stu-id="be020-134">The server and any intervening proxies must support persistent connections to successfully complete the authentication.</span></span>|  
|<span data-ttu-id="be020-135">Negotiate</span><span class="sxs-lookup"><span data-stu-id="be020-135">Negotiate</span></span>|<span data-ttu-id="be020-136">Negociar autenticação seleciona automaticamente entre o protocolo Kerberos e a autenticação NTLM, dependendo da disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="be020-136">Negotiate authentication automatically selects between the Kerberos protocol and NTLM authentication, depending on availability.</span></span> <span data-ttu-id="be020-137">O protocolo Kerberos é usado se estiver disponível; Caso contrário, a tentativa de NTLM.</span><span class="sxs-lookup"><span data-stu-id="be020-137">The Kerberos protocol is used if it is available; otherwise, NTLM is tried.</span></span> <span data-ttu-id="be020-138">A autenticação Kerberos aprimora significativamente NTLM.</span><span class="sxs-lookup"><span data-stu-id="be020-138">Kerberos authentication significantly improves upon NTLM.</span></span> <span data-ttu-id="be020-139">A autenticação Kerberos é mais rápido do que NTLM e permite o uso da autenticação mútua e a delegação de credenciais para computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="be020-139">Kerberos authentication is both faster than NTLM and allows the use of mutual authentication and delegation of credentials to remote machines.</span></span>|  
|<span data-ttu-id="be020-140">Windows Live ID</span><span class="sxs-lookup"><span data-stu-id="be020-140">Windows Live ID</span></span>|<span data-ttu-id="be020-141">O serviço HTTP do Windows subjacente inclui a autenticação usando protocolos federados.</span><span class="sxs-lookup"><span data-stu-id="be020-141">The underlying Windows HTTP service includes authentication using federated protocols.</span></span> <span data-ttu-id="be020-142">No entanto, os transportes de HTTP padrão em [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] não suporta o uso de esquemas de autenticação federada, como Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="be020-142">However, the standard HTTP transports in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] do not support the use of federated authentication schemes, such as Microsoft Windows Live ID.</span></span> <span data-ttu-id="be020-143">Suporte para esse recurso está disponível atualmente com o uso de segurança de mensagem.</span><span class="sxs-lookup"><span data-stu-id="be020-143">Support for this feature is currently available through the use of message security.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="be020-144">[Federação e Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="be020-144"> [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>|  
  
## <a name="choosing-an-authentication-scheme"></a><span data-ttu-id="be020-145">Escolher um esquema de autenticação</span><span class="sxs-lookup"><span data-stu-id="be020-145">Choosing an Authentication Scheme</span></span>  
 <span data-ttu-id="be020-146">Ao selecionar os possíveis esquemas de autenticação para um servidor HTTP, alguns itens a serem considerados incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="be020-146">When selecting the potential authentication schemes for an HTTP server, a few items to consider include the following:</span></span>  
  
-   <span data-ttu-id="be020-147">Considere se o recurso precisa ser protegido.</span><span class="sxs-lookup"><span data-stu-id="be020-147">Consider whether the resource needs to be protected.</span></span> <span data-ttu-id="be020-148">Usando a autenticação HTTP requer a transmissão de dados mais e pode limitar a interoperabilidade com clientes.</span><span class="sxs-lookup"><span data-stu-id="be020-148">Using HTTP authentication requires transmitting more data and can limit interoperability with clients.</span></span> <span data-ttu-id="be020-149">Permitir acesso anônimo aos recursos que não precisam ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="be020-149">Allow anonymous access to resources that do not need to be protected.</span></span>  
  
-   <span data-ttu-id="be020-150">Se o recurso precisa ser protegida, considere quais esquemas de autenticação fornecem o nível de segurança necessário.</span><span class="sxs-lookup"><span data-stu-id="be020-150">If the resource needs to be protected, consider which authentication schemes provide the required level of security.</span></span> <span data-ttu-id="be020-151">O esquema padrão de autenticação mais fraco discutido aqui é a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="be020-151">The weakest standard authentication scheme discussed here is Basic authentication.</span></span> <span data-ttu-id="be020-152">Autenticação básica não protege as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="be020-152">Basic authentication does not protect the user's credentials.</span></span> <span data-ttu-id="be020-153">O esquema mais forte de autenticação padrão é a autenticação Negotiate, resultando no protocolo Kerberos.</span><span class="sxs-lookup"><span data-stu-id="be020-153">The strongest standard authentication scheme is Negotiate authentication, resulting in the Kerberos protocol.</span></span>  
  
-   <span data-ttu-id="be020-154">Um servidor não deve apresentar (nos cabeçalhos de autenticação WWW) qualquer esquema que não está preparado para aceitar ou que não protege o recurso protegido adequadamente.</span><span class="sxs-lookup"><span data-stu-id="be020-154">A server should not present (in the WWW-Authentication headers) any scheme that it is not prepared to accept or that does not adequately secure the protected resource.</span></span> <span data-ttu-id="be020-155">Os clientes estão livres para escolher entre qualquer um dos esquemas de autenticação que apresenta o servidor.</span><span class="sxs-lookup"><span data-stu-id="be020-155">Clients are free to choose between any of the authentication schemes the server presents.</span></span> <span data-ttu-id="be020-156">Alguns clientes como padrão um esquema de autenticação de baixa segurança ou o esquema de autenticação primeiro na lista do servidor.</span><span class="sxs-lookup"><span data-stu-id="be020-156">Some clients default to a weak authentication scheme or the first authentication scheme in the server's list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be020-157">Consulte também</span><span class="sxs-lookup"><span data-stu-id="be020-157">See Also</span></span>  
 [<span data-ttu-id="be020-158">Visão geral de segurança de transporte</span><span class="sxs-lookup"><span data-stu-id="be020-158">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="be020-159">Usando a representação com segurança de transporte</span><span class="sxs-lookup"><span data-stu-id="be020-159">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 [<span data-ttu-id="be020-160">Delegação e representação</span><span class="sxs-lookup"><span data-stu-id="be020-160">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)