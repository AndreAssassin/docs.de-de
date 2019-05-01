---
title: IMetaDataConverter::GetTypeLibFromMetaData-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0943971dc4858e2dce4d977f6f906b26f8ad51e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044381"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData-Methode
Ruft einen Zeiger auf ein `ITypeLib` -Instanz, die die Typbibliothek darstellt, die Namen der angegebenen Bibliothek "und"-Modul.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `strModule`  
 [in] Der Name des Moduls für die Typbibliothek.  
  
 `strTlbName`  
 [in] Der Name der Typbibliothek.  
  
 `ppITL`  
 [out] Ein Zeiger auf einen Speicherort, die Adresse des empfängt, die `ITypeLib` -Instanz, die die Typbibliothek darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataConverter-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
