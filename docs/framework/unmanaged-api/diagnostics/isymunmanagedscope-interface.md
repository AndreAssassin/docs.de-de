---
title: ISymUnmanagedScope-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761636"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope-Schnittstelle
Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetChildren-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|Ruft die untergeordneten Elemente dieses Bereichs ab.|  
|[GetEndOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|Ruft den Endoffset für diesen Bereich ab.|  
|[GetLocalCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.|  
|[GetLocals-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|Ruft ab, die lokalen Variablen, die innerhalb dieses Bereichs definiert.|  
|[GetMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|Ruft die Methode ab, die dieser Bereich enthält.|  
|[GetNamespaces-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|Ruft die Namespaces, die innerhalb dieses Bereichs verwendet werden.|  
|[GetParent-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|Ruft den übergeordneten Bereich dieses Bereichs ab.|  
|[GetStartOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|Ruft den Anfangsoffset für diesen Bereich ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
