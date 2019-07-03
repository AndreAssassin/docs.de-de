---
title: Erstellen von Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e544976b0b801b08af238b2aeb36b5611154379
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832897"
---
# <a name="creating-assemblies"></a>Erstellen von Assemblys

Sie können Einfach- oder Mehrfachdateiassemblys mit einer IDE wie Visual Studio oder mit den vom Windows Software Development Kit (SDK) bereitgestellten Compilern und Tools entwickeln. Die einfachste Assembly ist eine einzelne Datei mit einem einfachen Namen. Diese wird in eine einzige Anwendungsdomäne geladen. Auf diese Assembly kann nicht von anderen Assemblys außerhalb des Anwendungsverzeichnisses verwiesen werden. Außerdem wird sie keiner Versionsüberprüfung unterzogen. Um die Anwendung, die aus der Assembly besteht, zu deinstallieren, müssen Sie nur das Verzeichnis löschen, in dem sie sich befindet. Viele Entwickler benötigen nur eine Assembly mit diesen Funktionen, um eine Anwendung bereitzustellen.

Sie können eine Mehrfachdateiassembly aus mehreren Codemodulen und Ressourcendateien erstellen. Außerdem können Sie eine Assembly erstellen, die von mehrere Anwendungen verwendet werden kann. Eine freigegebene Assembly muss einen starken Namen haben. Sie kann im globalen Assemblycache bereitgestellt werden.

Beim Gruppieren von Codemodulen und Ressourcen in Assemblys stehen Ihnen mehrere Optionen zur Verfügung. Diese hängen von folgenden Faktoren ab:

- Versionskontrolle

     Gruppieren von Modulen, die die gleichen Versionsinformationen haben sollten

- Bereitstellung

     Gruppieren von Modulen und Ressourcen, die Ihr Bereitstellungsmodell unterstützen

- Wiederverwendung

     Gruppieren von Modulen, wenn diese logisch für bestimmte Zwecke zusammen verwendet werden können. Beispielsweise eine Assembly, die aus Typen und Klassen besteht, die unregelmäßig zur Wartung eines Programms verwendet werden, kann in die gleiche Assembly platziert werden. Zusätzlich sollten Typen, die Sie für mehrere Anwendungen freigeben möchten, in einer Assembly gruppiert sein. Diese Assembly sollte mit einem starken Namen signiert werden.

- Sicherheit

     Gruppieren von Modulen, die Typen enthalten, die die gleichen Sicherheitsberechtigungen erfordern

- Bewerten

     Gruppieren von Modulen, die Typen enthalten, deren Sichtbarkeit auf die gleiche Assembly eingeschränkt sein soll

Wenn Sie Assemblys der Common Language Runtime für nicht verwaltete COM-Anwendungen verfügbar machen, müssen Sie auf Besonderheiten achten. Weitere Informationen zum Arbeiten mit nicht verwaltetem Code finden Sie unter [Exposing .NET Framework Components to COM (Verfügbarmachen von .NET Framework-Komponenten in COM)](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Siehe auch

- [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md)
- [Vorgehensweise: Erstellen einer Einzeldateiassembly](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)
