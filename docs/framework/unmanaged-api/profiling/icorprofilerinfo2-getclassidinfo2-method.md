---
title: ICorProfilerInfo2::GetClassIDInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b98746be189e211572e5517aac1f06825973b39
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168858"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>ICorProfilerInfo2::GetClassIDInfo2-Methode
Ruft das übergeordnete Modul und die Metadaten für die offene generische Methodendefinition der angegebenen Klasse token der `ClassID` der übergeordneten Klasse, und die `ClassID` für jedes Typargument, falls vorhanden, der-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, für die Informationen abgerufen werden sollen.  
  
 `pModuleId`  
 [out] Zeiger auf die ID des übergeordneten Moduls für die offenen generischen Definition der angegebenen Klasse.  
  
 `pTypeDefToken`  
 [out] Zeiger auf das Metadatentoken für die offene generische Methodendefinition der angegebenen Klasse.  
  
 `pParentClassId`  
 [out] Der Zeiger auf die ID der übergeordneten Klasse.  
  
 `cNumTypeArgs`  
 [in] Die Größe des `typeArgs`-Arrays.  
  
 `pcNumTypeArgs`  
 [out] Der Zeiger auf die Gesamtzahl der verfügbaren Elemente.  
  
 `typeArgs`  
 [out] Ein Array von `ClassID`-Werten, von denen jedes die ID eines Typarguments der Klasse darstellt. Wenn die Methode zurückkehrt, enthält `typeArgs` einige verfügbare oder alle verfügbaren `ClassID` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetClassIDInfo2` Methode ähnelt der [ICorProfilerInfo:: GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) -Methode, aber `GetClassIDInfo2` Ruft zusätzliche Informationen über einen generischen Typ ab.  
  
 Der Profilercode kann Aufrufen [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) zum Abrufen einer [Metadaten](../../../../docs/framework/unmanaged-api/metadata/index.md) Schnittstelle für ein bestimmtes Modul. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.  
  
 Nachdem `GetClassIDInfo2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `typeArgs`-Puffer groß genug war, um alle `ClassID`-Werte aufzunehmen. Vergleichen Sie zu diesem Zweck den Wert, auf den `pcNumTypeArgs` verweist, mit dem Wert des Parameters `cNumTypeArgs`. Wenn `pcNumTypeArgs` auf einen Wert verweist, der größer als `cNumTypeArgs` ist, weisen Sie einen größeren `typeArgs`-Puffer zu, aktualisieren Sie `cNumTypeArgs` mit der neuen Größe, und rufen Sie `GetClassIDInfo2` erneut auf.  
  
 Alternativ können Sie zuerst `GetClassIDInfo2` mit einem `typeArgs`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die `typeArgs`Puffergröße dann auf den Wert festlegen, der von `pcNumTypeArgs` zurückgegeben wurde, und `GetClassIDInfo2` dann erneut aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
