---
title: Konfigurieren der Umleitung der Assemblybindung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5df468b87c62f454f6a42fa7a80d92e5ec199fd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151540"
---
# <a name="configuring-assembly-binding-redirection"></a>Konfigurieren der Umleitung der Assemblybindung
Standardmäßig verwenden Anwendungen eine Reihe von .NET Framework-Assemblys, die mit der Laufzeitversion bereitgestellt werden, die zum Kompilieren der Anwendung verwendet wird. Mithilfe des **appliesTo**-Attributs im [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)-Element in einer Anwendungskonfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version der .NET Framework-Assemblys umleiten. Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird. Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>**-Element für alle Versionen von .NET Framework.  
  
 Das **appliesTo**-Attribut wurde mit .NET Framework Version 1.1 eingeführt. Es wird von .NET Framework Version 1.0 ignoriert. Dies bedeutet, dass alle **\<assemblyBinding>**-Elemente bei Verwendung von .NET Framework Version 1.0 angewendet werden, auch wenn das **appliesTo**-Attribut angegeben wurde.  
  
> [!NOTE]
>  Verwenden Sie das **appliesTo**-Attribut, um die Umleitung der Assemblybindung auf eine spezielle Version der Runtime zu beschränken.  
  
 Um zum Beispiel die Assemblybindung einer .NET Framework 1.0-Assembly umzuleiten, müssten Sie den folgenden XML-Code in die Anwendungskonfigurationsdatei einfügen.  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>   
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 Bei **\<assemblyBinding>**-Elemente wird die Reihenfolge beachtet. Sie sollten zuerst Umleitungsinformationen für die Assemlybindungen aller .NET Framework 1.0-Assemblys eingeben, gefolgt von den Umleitungsinformationen für die Assemblybindungen beliebiger .NET Framework 1.1-Assemblys. Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework-Assemblyumleitungen ein, bei denen nicht das **appliesTo** -Attribut verwendet wird und die daher für alle Versionen .NET Framework-Versionen gelten. Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.  
  
 Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 1.0-Assembly und eines anderen Verweises auf eine .NET Framework 1.1-Assembly müssten Sie nach dem Muster im folgenden Pseudocode vorgehen.  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">   
  <!-- .NET Framework version 1.0 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">   
  <!-- .NET Framework version 1.1 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="...">   
  <!-- Redirects meant for all versions of the .NET Framework. -->   
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a>Fehler beim Debuggen der Konfigurationsdatei  
 Die Laufzeit analysiert Konfigurationsdateien einmal, wenn eine Anwendungsdomäne erstellt wird, und lädt dann Code in diese Anwendungsdomäne. Die Common Language Runtime behandelt Fehler in einer Konfigurationsdatei, indem der jeweilige Eintrag ignoriert wird. Zur Laufzeit wird die gesamte Konfigurationsdatei ignoriert, wenn sie fehlerhaft formatierte XLM enthält. Bei ungültiger XML werden nur die ungültigen Abschnitte ignoriert.  
  
 Sie können feststellen, ob eine Konfigurationsdatei genutzt wird, indem Sie ermitteln, ob Umleitungen der Assemblybindung auftreten. Verwenden Sie die [Assemblybindungs-Protokollanzeige (Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), um zu sehen, welche Assemblys geladen werden. Um alle Assemblybindungen anzuzeigen, müssen Sie in der Registrierung einen Eintrag für **ForceLog** anlegen.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
