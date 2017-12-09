---
title: "Gerando um cliente do WCF de metadados de serviço"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27f8f545-cc44-412a-b104-617e0781b803
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9d6418f1f6af544669cf63b48db736d3e144a595
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="generating-a-wcf-client-from-service-metadata"></a><span data-ttu-id="5380f-102">Gerando um cliente do WCF de metadados de serviço</span><span class="sxs-lookup"><span data-stu-id="5380f-102">Generating a WCF Client from Service Metadata</span></span>
<span data-ttu-id="5380f-103">Este tópico descreve como usar as várias opções no Svcutil.exe para gerar os clientes de documentos de metadados.</span><span class="sxs-lookup"><span data-stu-id="5380f-103">This topic describes how to use the various switches in Svcutil.exe to generate clients from metadata documents.</span></span>  
  
 <span data-ttu-id="5380f-104">Documentos de metadados podem estar em um armazenamento durável ou ser recuperados online.</span><span class="sxs-lookup"><span data-stu-id="5380f-104">Metadata documents can be on a durable storage or be retrieved online.</span></span> <span data-ttu-id="5380f-105">Recuperação online segue o protocolo WS-MetadataExchange ou o protocolo de descoberta do Microsoft (DISCO).</span><span class="sxs-lookup"><span data-stu-id="5380f-105">Online retrieval follows either the WS-MetadataExchange protocol or the Microsoft Discovery (DISCO) protocol.</span></span> <span data-ttu-id="5380f-106">Svcutil.exe emite as seguintes solicitações de metadados ao mesmo tempo para recuperar metadados:</span><span class="sxs-lookup"><span data-stu-id="5380f-106">Svcutil.exe issues the following metadata requests simultaneously to retrieve metadata:</span></span>  
  
-   <span data-ttu-id="5380f-107">Solicitação do WS-MetadataExchange (MEX) para o endereço fornecido.</span><span class="sxs-lookup"><span data-stu-id="5380f-107">WS-MetadataExchange (MEX) request to the supplied address.</span></span>  
  
-   <span data-ttu-id="5380f-108">Solicitação MEX para o endereço fornecido com `/mex` anexado.</span><span class="sxs-lookup"><span data-stu-id="5380f-108">MEX request to the supplied address with `/mex` appended.</span></span>  
  
-   <span data-ttu-id="5380f-109">Solicitação DISCO (usando o [DiscoveryClientProtocol](http://go.microsoft.com/fwlink/?LinkId=94777) de serviços Web do ASP.NET) para o endereço fornecido.</span><span class="sxs-lookup"><span data-stu-id="5380f-109">DISCO request (using the [DiscoveryClientProtocol](http://go.microsoft.com/fwlink/?LinkId=94777) from ASP.NET Web services) to the supplied address.</span></span>  
  
 <span data-ttu-id="5380f-110">Svcutil.exe gera o cliente com base no arquivo WSDL Web Services Description Language () ou diretiva recebido do serviço.</span><span class="sxs-lookup"><span data-stu-id="5380f-110">Svcutil.exe generates the client based on the Web Services Description Language (WSDL) or policy file received from the service.</span></span> <span data-ttu-id="5380f-111">O nome de usuário principal (UPN) é gerado pela concatenação do nome de usuário com "@" e, em seguida, adicionar um nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5380f-111">The user principal name (UPN) is generated by concatenating the user name with "@" and then adding a fully-qualified domain name (FQDN).</span></span> <span data-ttu-id="5380f-112">No entanto, para os usuários registrados no Active Directory, esse formato não é válido e o UPN que a ferramenta gera causa uma falha na autenticação Kerberos com a seguinte mensagem de erro: **Falha na tentativa de logon.**</span><span class="sxs-lookup"><span data-stu-id="5380f-112">However, for users who registered on Active Directory, this format is not valid and the UPN that the tool generates causes a failure in the Kerberos authentication with the following error message: **The logon attempt failed.**</span></span> <span data-ttu-id="5380f-113">Para resolver esse problema, corrija o arquivo de cliente que gerou a ferramenta manualmente.</span><span class="sxs-lookup"><span data-stu-id="5380f-113">To resolve this problem, manually fix the client file that the tool generated.</span></span>  
  
```  
svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>  
```  
  
## <a name="referencing-and-sharing-types"></a><span data-ttu-id="5380f-114">Referenciando e tipos de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="5380f-114">Referencing and Sharing Types</span></span>  
  
|<span data-ttu-id="5380f-115">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-115">Option</span></span>|<span data-ttu-id="5380f-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-117">**/Reference:\<caminho do arquivo >**</span><span class="sxs-lookup"><span data-stu-id="5380f-117">**/reference:\<file path>**</span></span>|<span data-ttu-id="5380f-118">Os tipos de referência no assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="5380f-118">References types in the specified assembly.</span></span> <span data-ttu-id="5380f-119">Ao gerar clientes, use esta opção para especificar os assemblies que podem conter tipos que representam os metadados que estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="5380f-119">When generating clients, use this option to specify assemblies that might contain types that represent the metadata being imported.</span></span><br /><br /> <span data-ttu-id="5380f-120">Forma abreviada: `/r`</span><span class="sxs-lookup"><span data-stu-id="5380f-120">Short form: `/r`</span></span>|  
|<span data-ttu-id="5380f-121">**/excludeType:\<tipo >**</span><span class="sxs-lookup"><span data-stu-id="5380f-121">**/excludeType:\<type>**</span></span>|<span data-ttu-id="5380f-122">Especifica um nome de tipo totalmente qualificado ou qualificado do assembly a ser excluído dos tipos de contrato referenciados.</span><span class="sxs-lookup"><span data-stu-id="5380f-122">Specifies a fully-qualified or assembly-qualified type name to be excluded from referenced contract types.</span></span><br /><br /> <span data-ttu-id="5380f-123">Forma abreviada: `/et`</span><span class="sxs-lookup"><span data-stu-id="5380f-123">Short form: `/et`</span></span>|  
  
## <a name="choosing-a-serializer"></a><span data-ttu-id="5380f-124">Escolhendo um serializador</span><span class="sxs-lookup"><span data-stu-id="5380f-124">Choosing a Serializer</span></span>  
  
|<span data-ttu-id="5380f-125">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-125">Option</span></span>|<span data-ttu-id="5380f-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-127">**/Serializer:auto**</span><span class="sxs-lookup"><span data-stu-id="5380f-127">**/serializer:Auto**</span></span>|<span data-ttu-id="5380f-128">Seleciona automaticamente o serializador.</span><span class="sxs-lookup"><span data-stu-id="5380f-128">Automatically selects the serializer.</span></span> <span data-ttu-id="5380f-129">Isso usa o `DataContract` serializador.</span><span class="sxs-lookup"><span data-stu-id="5380f-129">This uses the `DataContract` serializer.</span></span> <span data-ttu-id="5380f-130">Se isso falhar, o `XmlSerializer` é usado.</span><span class="sxs-lookup"><span data-stu-id="5380f-130">If this fails, the `XmlSerializer` is used.</span></span><br /><br /> <span data-ttu-id="5380f-131">Forma abreviada: `/ser:Auto`</span><span class="sxs-lookup"><span data-stu-id="5380f-131">Short Form: `/ser:Auto`</span></span>|  
|<span data-ttu-id="5380f-132">**/Serializer:DataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="5380f-132">**/serializer:DataContractSerializer**</span></span>|<span data-ttu-id="5380f-133">Gera os tipos de dados que usam o `DataContract` serializador para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="5380f-133">Generates data types that use the `DataContract` serializer for serialization and deserialization.</span></span><br /><br /> <span data-ttu-id="5380f-134">Forma abreviada: `/ser:DataContractSerializer`</span><span class="sxs-lookup"><span data-stu-id="5380f-134">Short form: `/ser:DataContractSerializer`</span></span>|  
|<span data-ttu-id="5380f-135">**/Serializer:XmlSerializer**</span><span class="sxs-lookup"><span data-stu-id="5380f-135">**/serializer:XmlSerializer**</span></span>|<span data-ttu-id="5380f-136">Gera os tipos de dados que usam o `XmlSerializer` para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="5380f-136">Generates data types that use the `XmlSerializer` for serialization and deserialization.</span></span><br /><br /> <span data-ttu-id="5380f-137">Forma abreviada: `/ser:XmlSerializer`</span><span class="sxs-lookup"><span data-stu-id="5380f-137">Short form: `/ser:XmlSerializer`</span></span>|  
|<span data-ttu-id="5380f-138">**/importXmlTypes**</span><span class="sxs-lookup"><span data-stu-id="5380f-138">**/importXmlTypes**</span></span>|<span data-ttu-id="5380f-139">Configura o `DataContract` serializador para importar não`DataContract` tipos como `IXmlSerializable` tipos.</span><span class="sxs-lookup"><span data-stu-id="5380f-139">Configures the `DataContract` serializer to import non-`DataContract` types as `IXmlSerializable` types.</span></span><br /><br /> <span data-ttu-id="5380f-140">Forma abreviada: `/ixt`</span><span class="sxs-lookup"><span data-stu-id="5380f-140">Short form: `/ixt`</span></span>|  
|<span data-ttu-id="5380f-141">**/dataContractOnly**</span><span class="sxs-lookup"><span data-stu-id="5380f-141">**/dataContractOnly**</span></span>|<span data-ttu-id="5380f-142">Gera código para `DataContract` tipos somente.</span><span class="sxs-lookup"><span data-stu-id="5380f-142">Generates code for `DataContract` types only.</span></span> <span data-ttu-id="5380f-143">`ServiceContract`tipos são gerados.</span><span class="sxs-lookup"><span data-stu-id="5380f-143">`ServiceContract` types are generated.</span></span><br /><br /> <span data-ttu-id="5380f-144">Você deve especificar somente os arquivos de metadados local para essa opção.</span><span class="sxs-lookup"><span data-stu-id="5380f-144">You should specify only local metadata files for this option.</span></span><br /><br /> <span data-ttu-id="5380f-145">Forma abreviada: `/dconly`</span><span class="sxs-lookup"><span data-stu-id="5380f-145">Short form: `/dconly`</span></span>|  
  
## <a name="choosing-a-language-for-the-client"></a><span data-ttu-id="5380f-146">Escolher um idioma para o cliente</span><span class="sxs-lookup"><span data-stu-id="5380f-146">Choosing a Language for the Client</span></span>  
  
|<span data-ttu-id="5380f-147">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-147">Option</span></span>|<span data-ttu-id="5380f-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-148">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-149">**/idioma:\<idioma >**</span><span class="sxs-lookup"><span data-stu-id="5380f-149">**/language:\<language>**</span></span>|<span data-ttu-id="5380f-150">Especifica a linguagem de programação a ser usada para gerar o código.</span><span class="sxs-lookup"><span data-stu-id="5380f-150">Specifies the programming language to use for code generation.</span></span> <span data-ttu-id="5380f-151">Forneça um nome de idioma registrado no arquivo Machine. config ou o nome totalmente qualificado de uma classe que herda de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="5380f-151">Provide either a language name registered in the Machine.config file or the fully-qualified name of a class that inherits from <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span><br /><br /> <span data-ttu-id="5380f-152">Valores: c#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c + +, mc, cpp</span><span class="sxs-lookup"><span data-stu-id="5380f-152">Values: c#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c++, mc, cpp</span></span><br /><br /> <span data-ttu-id="5380f-153">Padrão: csharp</span><span class="sxs-lookup"><span data-stu-id="5380f-153">Default: csharp</span></span><br /><br /> <span data-ttu-id="5380f-154">Forma abreviada: `/l`</span><span class="sxs-lookup"><span data-stu-id="5380f-154">Short form: `/l`</span></span><br /><br /> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="5380f-155">[Classe CodeDomProvider](http://go.microsoft.com/fwlink/?LinkId=94778).</span><span class="sxs-lookup"><span data-stu-id="5380f-155"> [CodeDomProvider Class](http://go.microsoft.com/fwlink/?LinkId=94778).</span></span>|  
  
## <a name="choosing-a-namespace-for-the-client"></a><span data-ttu-id="5380f-156">Escolhendo um Namespace para o cliente</span><span class="sxs-lookup"><span data-stu-id="5380f-156">Choosing a Namespace for the Client</span></span>  
  
|<span data-ttu-id="5380f-157">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-157">Option</span></span>|<span data-ttu-id="5380f-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-158">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-159">**/namespace:\<cadeia de caracteres, cadeia de caracteres >**</span><span class="sxs-lookup"><span data-stu-id="5380f-159">**/namespace:\<string,string>**</span></span>|<span data-ttu-id="5380f-160">Especifica um mapeamento de um esquema XML ou de WSDL `targetNamespace` para um namespace de tempo de execução (CLR) de linguagem comum.</span><span class="sxs-lookup"><span data-stu-id="5380f-160">Specifies a mapping from a WSDL or XML Schema `targetNamespace` to a common language runtime (CLR) namespace.</span></span> <span data-ttu-id="5380f-161">Usando um caractere curinga (*) para o `targetNamespace` mapeia todos os `targetNamespaces` sem um mapeamento explícito esse namespace CLR.</span><span class="sxs-lookup"><span data-stu-id="5380f-161">Using a wildcard (*) for the `targetNamespace` maps all `targetNamespaces` without an explicit mapping to that CLR namespace.</span></span><br /><br /> <span data-ttu-id="5380f-162">Para certificar-se de que o nome do contrato de mensagem não entrarem em conflito com o nome da operação, qualifique a referência de tipo com dois-pontos duplo (`::`) ou verifique se os nomes são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="5380f-162">To make sure that the message contract name does not collide with the operation name, either qualify the type reference with double colons (`::`) or make sure the names are unique.</span></span><br /><br /> <span data-ttu-id="5380f-163">Padrão: Derivado do namespace de destino do documento do esquema para `DataContracts`.</span><span class="sxs-lookup"><span data-stu-id="5380f-163">Default: Derived from the target namespace of the schema document for `DataContracts`.</span></span> <span data-ttu-id="5380f-164">O namespace padrão é usado para todos os outros tipos gerados.</span><span class="sxs-lookup"><span data-stu-id="5380f-164">The default namespace is used for all other generated types.</span></span><br /><br /> <span data-ttu-id="5380f-165">Forma abreviada: `/n`</span><span class="sxs-lookup"><span data-stu-id="5380f-165">Short form: `/n`</span></span>|  
  
## <a name="choosing-a-data-binding"></a><span data-ttu-id="5380f-166">Escolhendo uma associação de dados</span><span class="sxs-lookup"><span data-stu-id="5380f-166">Choosing a Data Binding</span></span>  
  
|<span data-ttu-id="5380f-167">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-167">Option</span></span>|<span data-ttu-id="5380f-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-168">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-169">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="5380f-169">**/enableDataBinding**</span></span>|<span data-ttu-id="5380f-170">Implementa o <xref:System.ComponentModel.INotifyPropertyChanged> interface em todos os `DataContract` tipos para habilitar a associação de dados.</span><span class="sxs-lookup"><span data-stu-id="5380f-170">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all `DataContract` types to enable data binding.</span></span><br /><br /> <span data-ttu-id="5380f-171">Forma abreviada: `/edb`</span><span class="sxs-lookup"><span data-stu-id="5380f-171">Short form: `/edb`</span></span>|  
  
## <a name="generating-configuration"></a><span data-ttu-id="5380f-172">Gerar a configuração</span><span class="sxs-lookup"><span data-stu-id="5380f-172">Generating Configuration</span></span>  
  
|<span data-ttu-id="5380f-173">Opção</span><span class="sxs-lookup"><span data-stu-id="5380f-173">Option</span></span>|<span data-ttu-id="5380f-174">Descrição</span><span class="sxs-lookup"><span data-stu-id="5380f-174">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5380f-175">**/config:\<configFile >**</span><span class="sxs-lookup"><span data-stu-id="5380f-175">**/config:\<configFile>**</span></span>|<span data-ttu-id="5380f-176">Especifica o nome do arquivo para o arquivo de configuração gerada.</span><span class="sxs-lookup"><span data-stu-id="5380f-176">Specifies the file name for the generated configuration file.</span></span><br /><br /> <span data-ttu-id="5380f-177">Padrão: output.config</span><span class="sxs-lookup"><span data-stu-id="5380f-177">Default: output.config</span></span>|  
|<span data-ttu-id="5380f-178">**/mergeConfig**</span><span class="sxs-lookup"><span data-stu-id="5380f-178">**/mergeConfig**</span></span>|<span data-ttu-id="5380f-179">Mescla a configuração gerada em um arquivo existente, em vez de substituir o arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="5380f-179">Merges the generated configuration into an existing file, instead of overwriting the existing file.</span></span>|  
|<span data-ttu-id="5380f-180">**/noConfig**</span><span class="sxs-lookup"><span data-stu-id="5380f-180">**/noConfig**</span></span>|<span data-ttu-id="5380f-181">Não gera arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="5380f-181">Do not generate configuration files.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5380f-182">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5380f-182">See Also</span></span>  
 [<span data-ttu-id="5380f-183">Uso de metadados</span><span class="sxs-lookup"><span data-stu-id="5380f-183">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="5380f-184">Visão geral da arquitetura de metadados</span><span class="sxs-lookup"><span data-stu-id="5380f-184">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)