---
title: Associações do Windows Communcation Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: 373f7feb64d69373630c942750f264d559643a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489658"
---
# <a name="windows-communcation-foundation-bindings"></a>Associações do Windows Communcation Foundation
Windows Communication Foundation (WCF) separa como o software para um aplicativo é gravado de como ele se comunica com outros softwares. Associações são usadas para especificar o transporte, a codificação e detalhes de protocolo necessárias para clientes e serviços para se comunicar entre si. WCF usa associações para gerar a representação eletrônica subjacente do ponto de extremidade, para a maioria dos detalhes da associação deve ser aceito por terceiros que estão se comunicando. A maneira mais fácil de fazer isso é para clientes de um serviço usar a mesma associação que o ponto de extremidade para o serviço usa. Para obter mais informações sobre como fazer isso, consulte [usando associações para clientes e configurar o Windows Communication Foundation Services](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).  
  
 Uma associação é composta de uma coleção de elementos de associação. Cada elemento descreve alguns aspectos de como o ponto de extremidade se comunica com os clientes. Uma associação deve incluir pelo menos um elemento de associação de transporte, pelo menos um elemento de associação codificação de mensagens (que pode fornecer o elemento de associação de transporte por padrão), e qualquer número de outros elementos de associação de protocolo. O processo que cria um tempo de execução sem essa descrição permite que cada elemento de associação contribuir código para esse tempo de execução.  
  
 O WCF oferece associações que contêm as seleções comuns de elementos de associação. Eles podem ser usados com as configurações padrão ou você pode modificar esses valores padrão de acordo com os requisitos de usuário. Essas associações fornecidas pelo sistema têm propriedades que permitem o controle direto sobre os elementos de associação e suas configurações. Você pode trabalhar facilmente lado a lado com várias versões de uma associação, fornecendo a cada versão da associação de seu próprio nome. Para obter detalhes, consulte [Configuring System-Provided associações](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).  
  
 Se você precisar de uma coleção de elementos de associação não fornecido por um essas associações fornecidas pelo sistema, você pode criar uma associação personalizada que consiste a coleção de elementos necessários de associação. Essas associações personalizadas são fáceis de criar e fazer não exigem uma nova classe, mas não fornecem propriedades para controlar os elementos de associação ou em suas configurações. Você pode acessar os elementos de associação e modificar as configurações por meio da coleção que os contém. Para obter detalhes, consulte [personalizado associações](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>Nesta seção  
 [Configurando associações fornecidas pelo sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 Descreve como usar e modificar as associações WCF fornece para dar suporte a cenários comuns.  
  
 [Usando associações para configurar clientes e serviços do Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 Descreve como definir associações do Windows Communication Foundation (WCF) para serviços e clientes imperativa no código e declarativamente usando a configuração.  
  
 [Associações personalizadas](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 Descreve o que um <xref:System.ServiceModel.Channels.CustomBinding> é e quando ele é usado.  
  
## <a name="reference"></a>Referência  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Estendendo associações](../../../../docs/framework/wcf/extending/extending-bindings.md)
