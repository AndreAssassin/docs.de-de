---
title: GetPropertyHandle-Funktion (Referenz zur nicht verwalteten API)
description: GetPropertyHandle-Funktion gibt ein eindeutige Handle, das eine Eigenschaft identifiziert.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1397188b38066bac6375da0c76e7d66724a75d7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636241"
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle-Funktion

Gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.

`wszPropertyName`\
[in] Eine Null-terminierte Zeichenfolge des UTF16-codierte Zeichen, die den Eigenschaftennamen enthält.

`pType`\
[out] Ein Zeiger auf eine [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) -Enumerationsmember, der den CIM-Typ der Eigenschaft darstellt.

`pHandle`\
[out] Ein Zeiger auf eine ganze Zahl, die das Eigenschaftshandle enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Eigenschaftenname wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Die angeforderte Eigenschaft ist vom Typ sind `CIM_OBJECT` oder `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) Methode.

Sie können dieses Handle verwenden, um Eigenschaften zu identifizieren, bei Verwendung [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Methoden zum Lesen oder Schreiben von Eigenschaftswerten.

Handles können nicht für die Eigenschaften aller Datentypen abgerufen werden `CIM_OBJECT` und `CIM_ARRAY`. Handles Arbeit, die über alle Instanzen einer Klasse zurückgegeben.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
