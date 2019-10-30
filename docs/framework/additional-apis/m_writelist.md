---
title: Connection. m_WriteList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120031"
---
# <a name="connectionm_writelist-field"></a>Connection. m\_beschreitelist-Feld

`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekten, die in die Warteschlange eingereiht werden, um über HTTP gesendet zu werden.

## <a name="syntax"></a>Syntax
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> Das `Connection.m_WriteList` Feld ist privat und sollte nicht direkt im Code verwendet werden.
> 
> Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
