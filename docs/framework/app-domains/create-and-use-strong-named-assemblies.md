---
title: Erstellen und Verwenden von Assemblys mit starkem Namen
ms.date: 08/01/2017
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 629a59cd28e58e4b08805e3bb742d12e9cacbebd
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377882"
---
# <a name="create-and-use-strong-named-assemblies"></a>Erstellen und Verwenden von Assemblys mit starkem Namen

Ein starker Name setzt sich aus der Identität der Assembly – dem einfachen Textnamen, der Versionsnummer und Kulturinformationen (falls vorhanden) – sowie einem öffentlichen Schlüssel und einer digitalen Signatur zusammen. Er wird mithilfe des entsprechenden privaten Schlüssels aus einer Assemblydatei generiert. (Die Assemblydatei enthält das Assemblymanifest, das wiederum die Namen und Hashes aller Dateien enthält, die die Assembly bilden.)

> [!WARNING]
> Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.

Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden. Andernfalls ist die Integrität der Assembly mit starkem Namen beeinträchtigt.

## <a name="strong-name-scenario"></a>Szenario für starken Namen

Im folgenden Szenario wird kurz umrissen, wie eine Assembly mit einem starken Namen signiert und wie später mit diesem Namen auf sie verwiesen wird.

1. Assembly A wird auf eine der folgenden Weisen mit einem starken Namen erstellt:

    - Durch Verwenden einer Entwicklungsumgebung, die das Erstellen starker Namen unterstützt, wie z.B. Visual Studio.

    - Durch Erstellen eines kryptografischen Schlüsselpaars mithilfe des [Strong Name-Tools (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) und Zuweisen dieses Schlüsselpaars zur Assembly unter Verwendung eines Befehlszeilencompilers oder mit dem [Assemblylinker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md). Das Windows Software Development Kit (SDK) stellt sowohl Sn.exe als auch Al.exe zur Verfügung.

2. Die Entwicklungsumgebung oder das Tool signiert den Hash der Datei, die das Assemblymanifest enthält, mit dem privaten Schlüssel des Entwicklers. Diese digitale Signatur wird in der PE (Portable Executable)-Datei gespeichert, die das Manifest von Assembly A enthält.

3. Assembly B ist ein Consumer von Assembly A. Der Referenzabschnitt des Manifests von Assembly B enthält ein Token, das den öffentlichen Schlüssel von Assembly A darstellt. Ein Token ist ein Teilabschnitt des vollständigen öffentlichen Schlüssels und wird aus Platzgründen oft an Stelle des eigentlichen Schlüssels verwendet.

4. Die Common Language Runtime überprüft die starke Namenssignatur, wenn die Assembly im globalen Assemblycache platziert wird. Beim Binden mit starken Namen zur Runtime vergleicht die Common Language Runtime den im Manifest von Assembly B gespeicherten Schlüssel mit dem Schlüssel, der verwendet wurde, um den starken Namen von Assembly A zu generieren. Wenn die Sicherheitstests von .NET Framework durchlaufen und die Bindung abgeschlossen wurde, garantiert Assembly B, dass Bits von Assembly A nicht verändert wurden, und dass sie tatsächlich von den Entwicklern von Assembly A stammen.

> [!NOTE]
> Dieses Szenario löst keine Vertrauenswürdigkeitsprobleme. Assemblys können neben starken Namen auch vollständige Microsoft Authenticode-Signaturen tragen. Authenticode-Signaturen enthalten ein Zertifikat, das Vertrauenswürdigkeit bescheinigt. Beachten Sie unbedingt, dass bei starken Namen nicht erforderlich ist, Code auf diese Weise zu signieren. Starke Namen bieten lediglich eine eindeutige Identität.

## <a name="bypass-signature-verification-of-trusted-assemblies"></a>Umgehen der Signaturüberprüfung für vertrauenswürdige Assemblys

Ab [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)] werden Signaturen mit starkem Namen nicht überprüft, wenn ein Assembly in eine vollständig vertrauenswürdige Anwendungsdomäne geladen wird, wie etwa die Standardanwendungsdomäne für die Zone `MyComputer`. Dies wird Strong-Name-Bypass-Feature genannt. In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys immer erfolgreich, unabhängig von deren Signatur. Das Strong-Name-Bypass-Feature vermeidet in dieser Situation den Aufwand der Überprüfung der Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys. Dies ermöglicht ein schnelleres Laden der Assemblys.

Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:

- Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName>-Beweis (hat z. B. `MyComputer`-Zonenbeweis)

- Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>

- Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>

- Nicht verzögert signiert

Diese Funktion kann für einzelne Anwendungen oder einen Computer deaktiviert werden. Weitere Informationen finden Sie unter [How to: Deaktivieren der Strong-Name-Bypass-Funktion](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)|Beschreibt das Erstellen eines kryptografischen Schlüsselpaars zum Signieren einer Assembly.|
|[Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)|Beschreibt das Erstellen einer Assembly mit starkem Namen.|
|[Verbesserte starke Namen](../../../docs/framework/app-domains/enhanced-strong-naming.md)|Beschreibt Erweiterungen der starken Namen in .NET Framework 4.5.|
|[Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../../docs/framework/app-domains/how-to-reference-a-strong-named-assembly.md)|Beschreibt, wie auf Typen oder Ressourcen in einer Assembly mit starkem Namen zur Kompilier- oder Laufzeit verwiesen wird.|
|[Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)|Beschreibt, wie die Funktion, die die Validierung von Signaturen mit starkem Namen umgeht, deaktiviert wird. Diese Funktion kann für alle oder bestimmte Anwendungen deaktiviert werden.|
|[Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)|Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.|
|[So erstellen Sie eine Assembly in Visual Studio](/visualstudio/ide/managing-assembly-and-manifest-signing#how-to-sign-an-assembly-in-visual-studio)|Erläutert das Signieren einer Assembly mit einem starken Namen nach dem Erstellen der Assembly.|
|[Sn.exe (Strong Name-Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)|Beschreibt das Tool, das in .NET Framework enthalten ist, mit dem Assemblys mit starken Namen erstellt werden können. Dieses Tool stellt Optionen zum Verwalten von Schlüsseln, Erzeugen und Überprüfen von Signaturen bereit.|
|[Al.exe (Assembly Linker-Tool)](../../../docs/framework/tools/al-exe-assembly-linker.md)|Beschreibt das Tool, das in .NET Framework enthalten ist, mit dem eine Datei generiert wird, die ein Assemblymanifest von Modulen oder Ressourcendateien besitzt.|
