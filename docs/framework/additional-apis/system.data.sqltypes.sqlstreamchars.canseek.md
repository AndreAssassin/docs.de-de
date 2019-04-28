---
title: SqlStreamChars.CanSeek-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 52f88a3551e20c74d7a1144c3cd6859a023980db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675174"
---
# <a name="sqlstreamcharscanseek-property"></a>SqlStreamChars.CanSeek-Eigenschaft

Ruft beim Überschreiben in einer abgeleiteten Klasse ruft einen Wert, der angibt, ob der aktuelle Stream Suchvorgänge unterstützt. Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Eigenschaftswert

<xref:System.Boolean>\
`true` Wenn der aktuelle Stream Suchvorgänge unterstützt; andernfalls `false`.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.CanSeek` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.