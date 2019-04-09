---
title: ISymUnmanagedReader-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0782533f773b69eeeb0b89175e5b22c61e822ed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147211"
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader-Schnittstelle
Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Sucht ein Dokument an.|  
|[GetDocuments-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Gibt ein Array aller im Symbolspeicher definierten Dokumente.|  
|[GetDocumentVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Ruft die angegebene Version des angegebenen Dokuments ab.|  
|[GetGlobalVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Gibt alle globale Variablen zurück.|  
|[GetMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Ruft ein Methodenobjekt des Symbolreaders, mit dem angegebenen ein Methodentoken ab.|  
|[GetMethodByVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Ruft ein Methodenobjekt des Symbolreaders, wenn ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.|  
|[GetMethodFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Gibt die Methode, die den Haltepunkt an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodsFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Gibt ein Array der Methoden, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Ruft die Methodenversion ab.|  
|[GetNamespaces-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Ruft die Namespaces, die auf diesem Symbolspeicher mit globalem Gültigkeitsbereich definiert.|  
|[GetSymAttribute-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.|  
|[GetSymbolStoreFileName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Enthält den Namen der Datei auf dem Datenträger von den Symbolspeicher.|  
|[GetUserEntryPoint-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurden, zurück, falls vorhanden.|  
|[GetVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Zurückgeben einer nicht-lokalen Variablen, erhält die über- und Namen.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Initialisiert den Symbolreader mit der Metadaten-Importer-Tool-Schnittstelle, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.|  
|[ReplaceSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.|  
|[UpdateSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
