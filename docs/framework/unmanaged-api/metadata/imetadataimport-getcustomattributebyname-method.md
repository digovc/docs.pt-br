---
title: Método IMetaDataImport::GetCustomAttributeByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c25304bef4d240eedea749bb2829595056f9b74d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449241"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Método IMetaDataImport::GetCustomAttributeByName
Obtém o atributo personalizado, considerando o nome e proprietário.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `tkObj`  
 [in] Um token de metadados que representa o objeto que possui o atributo personalizado.  
  
 `szName`  
 [in] O nome do atributo personalizado.  
  
 `ppData`  
 [out] Um ponteiro para uma matriz de dados que é o valor do atributo personalizado.  
  
 `pcbData`  
 [out] O tamanho em bytes dos dados retornados em *`ppData`.  
  
## <a name="remarks"></a>Comentários  
 É permitido definir vários atributos personalizados para o mesmo proprietário; eles ainda podem ter o mesmo nome. No entanto, `GetCustomAttributeByName` retorna apenas uma instância. (`GetCustomAttributeByName` retorna a primeira instância que ele encontrar.) Para localizar todas as instâncias de um atributo personalizado, chame o [Enumcustomattributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Interface IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interface IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
