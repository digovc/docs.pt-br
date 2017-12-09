---
title: "Padrão de codificação de instância"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a874f88b787a99af0461ff47c3ae246442af2f19
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="56d4e-102">Padrão de codificação de instância</span><span class="sxs-lookup"><span data-stu-id="56d4e-102">Instance Encoding Option</span></span>
<span data-ttu-id="56d4e-103">O **a opção de codificação de instância** propriedade do repositório de instância de fluxo de trabalho de SQL permite que você especifique se o provedor de persistência do SQL deve compactar as informações de estado da instância de fluxo de trabalho usando o algoritmo GZip antes de salvar o informações no banco de dados de persistência.</span><span class="sxs-lookup"><span data-stu-id="56d4e-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="56d4e-104">Os valores permitidos para essa propriedade são: GZip e quaisquer.</span><span class="sxs-lookup"><span data-stu-id="56d4e-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="56d4e-105">O valor padrão é None.</span><span class="sxs-lookup"><span data-stu-id="56d4e-105">The default value is None.</span></span> <span data-ttu-id="56d4e-106">A lista a seguir descreve as opções.</span><span class="sxs-lookup"><span data-stu-id="56d4e-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="56d4e-107">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="56d4e-107">**GZip**.</span></span> <span data-ttu-id="56d4e-108">O provedor de persistência codificação informações de estado usando o algoritmo de GZip antes de manter informações de estado na base de dados de persistência.</span><span class="sxs-lookup"><span data-stu-id="56d4e-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="56d4e-109">**Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="56d4e-109">**None**.</span></span> <span data-ttu-id="56d4e-110">O provedor de persistência não codificação informações de estado antes de salvar informações na base de dados de persistência.</span><span class="sxs-lookup"><span data-stu-id="56d4e-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="56d4e-111">Informações de estado da instância de fluxo de trabalho de codificação que usa o GZip reduz o consumo de memória na base de dados SQL e também reduz o consumo de rede se o base de dados reside em um outro computador na rede do computador no qual o host serviço de fluxo de trabalho está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="56d4e-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="56d4e-112">Uma orientação geral é definir o **a opção de codificação de instância** propriedade **nenhum** se o estado da instância de fluxo de trabalho for pequeno.</span><span class="sxs-lookup"><span data-stu-id="56d4e-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>