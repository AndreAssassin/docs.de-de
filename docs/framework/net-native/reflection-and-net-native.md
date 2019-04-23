---
title: Reflektion und .NET Native
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c92d71c9862dfbdace4de2e30cf48ace7becfd0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105851"
---
# <a name="reflection-and-net-native"></a>Reflektion und .NET Native
Die verwaltete Entwicklung in .NET Framework unterstützt Metaprogrammierung durch die Reflektions-API. Durch Reflektion können Sie Objekte in einer App überprüfen, Methoden für bei der Überprüfung ermittelte Objekte aufrufen und neue Typen zur Laufzeit generieren. Außerdem werden viele weitere Szenarien mit dynamischem Code unterstützt. Zudem werden die Serialisierung und Deserialisierung unterstützt, wodurch die Feldwerte eines Objekts beibehalten und später wiederhergestellt werden können. All diese Szenarien erfordern den .NET Framework Just-In-Time-Compiler (JIT) zur Generierung von nativem Code basierend auf verfügbaren Metadaten.  
  
 Die [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Laufzeit enthält keinen JIT-Compiler. Daher muss sämtlicher notwendiger systemeigener Code vorab generiert werden. Eine Reihe von Heuristiken wird verwendet, um zu bestimmen, welcher Code generiert werden soll, aber diese Heuristiken können nicht alle möglichen Metaprogrammierungsszenarien abdecken.  Daher müssen Sie mit [Laufzeitanweisungen](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) Hinweise für diese Metaprogrammierungsszenarios bereitstellen. Wenn die erforderlichen Metadaten oder der Implementierungscode nicht zur Laufzeit verfügbar sind, wird durch die App [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) oder[MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) ausgelöst. Es sind zwei Problembehandlungen verfügbar, die den entsprechenden Eintrag für die Laufzeitdirektivendatei zur Beseitigung der Ausnahme generieren:  
  
-   Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
  
-   Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
> [!NOTE]
>  Eine Übersicht über den .NET Native-Kompilierungsprozess mit Hintergrundinformationen, die verdeutlichen, warum eine Laufzeitdirektivendatei erforderlich ist, finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
 Darüber hinaus ermöglicht [!INCLUDE[net_native](../../../includes/net-native-md.md)] keine Reflektion über private Member der .NET Framework-Klassenbibliothek. Beispielsweise gibt ein Aufruf der <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType>-Eigenschaft zum Abrufen der Felder einer .NET Framework-Klassenbibliothek nur öffentliche oder geschützte Felder zurück.  
  
 Die folgenden Themen enthalten die konzeptionelle Dokumentation und die Referenzdokumentation, die Sie benötigen, um Reflektion und Serialisierung in Ihren Apps zu unterstützen:  
  
-   [APIs That Rely on Reflection (APIs, die die Reflektion benötigen)](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
-   [Reflektions-API-Referenz](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
-   [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>Siehe auch

- [Kompilieren von Apps mit .NET Native](../../../docs/framework/net-native/index.md)
- [.NET Native and Compilation (.NET Native und Kompilierung)](../../../docs/framework/net-native/net-native-and-compilation.md)
