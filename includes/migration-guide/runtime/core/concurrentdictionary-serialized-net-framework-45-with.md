---
ms.openlocfilehash: f9d7b8d22818245b96cafffe3732bdfe82ff69d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804069"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Ein in .NET Framework 4.5 mit NetDataContractSerializer serialisiertes ConcurrentDictionary-Element kann nicht von .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden

|   |   |
|---|---|
|Details|Aufgrund von Typänderungen können <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekte, die unter Verwendung von <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> mit .NET Framework 4.5 serialisiert werden, nicht in .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden. Beachten Sie jedoch, dass die Serialisierung mit .NET Framework 4.5.x und die Deserialisierung mit .NET Framework 4.5 funktionieren. Genauso funktioniert die versionsübergreifende Serialisierung in .NET Framework 4.x mit .NET Framework 4.6. Dies hat keine Auswirkungen auf die (De-)Serialisierung einer einzelnen Version von .NET Framework.|
|Vorschlag|Wenn Sie ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>-Element zwischen .NET Framework 4.5 und .NET Framework 4.5.1/4.5.2 (de-)serialisieren müssen, sollten Sie statt <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> ein Serialisierungsmodul wie <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> verwenden. Das Problem könnte möglicherweise aber auch durch ein Upgrade auf .NET Framework 4.6 gelöst werden, da es in dieser Version behoben wird.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|
