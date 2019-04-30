---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5dd2829a9a00f869af3d7f370f99361979b8106
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921315"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode

[Wird nur in .NET Framework 4.5.1 und neueren Versionen unterstützt]

Konvertiert den angegebenen Stream in einen Random-Access-Stream.

**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)

## <a name="syntax"></a>Syntax

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a>Parameter

`stream`

Typ: <xref:System.IO.Stream?displayProperty=nameWithType>  
Der zu konvertierende Stream.

## <a name="return-value"></a>Rückgabewert

Typ: <xref:Windows.Storage.Streams.RandomAccessStream>  
Ein [!INCLUDE[wrt](../../../includes/wrt-md.md)] random Access-Stream, der den konvertierten Stream darstellt.

## <a name="exceptions"></a>Ausnahmen

|Ausnahme|Bedingung|
|---------------|---------------|
|<xref:System.NotSupportedException>|Der zu konvertierende Stream unterstützt keine Suchvorgänge.|

## <a name="remarks"></a>Hinweise

Diese Erweiterungsmethode ist nur verfügbar, wenn Sie Windows Store-Apps entwickeln. Diese Methode stellt eine komfortable Möglichkeit des Arbeitens mit Streams in Windows Store-Apps dar. Der .NET-Framework, den Sie konvertieren möchten, muss Suchvorgänge unterstützen. Weitere Informationen finden Sie unter der Methode <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.

> [!IMPORTANT]
> Diese API wird in .NET Framework 4.5.1 und neuer, aber nicht in Version 4.5 unterstützt.

## <a name="version-information"></a>Versionsinformationen

**.NET für Windows Store-apps**

Unterstützt in: Windows 8.1

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
