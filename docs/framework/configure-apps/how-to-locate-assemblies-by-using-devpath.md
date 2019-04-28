---
title: 'Vorgehensweise: Suchen von Assemblys mit DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 5c4041f42b0a9d1d1e4bc8438e662911534daa42
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775829"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Vorgehensweise: Suchen von Assemblys mit DEVPATH
Entwickler sollten sicherstellen, dass eine freigegebene Assembly, die sie erstellen mit mehreren Anwendungen funktioniert. Anstatt kontinuierlich platzieren die Assembly im globalen Assemblycache während des Entwicklungszyklus, kann Entwickler eine DEVPATH-Umgebungsvariable erstellen, die in das Ausgabeverzeichnis des Builds für die Assembly verweist.  
  
 Nehmen wir beispielsweise an, dass Sie eine freigegebene Assembly, die mit dem Namen MySharedAssembly erstellen und das Ausgabeverzeichnis C:\MySharedAssembly\Debug ist. Sie können in der Variablen DEVPATH C:\MySharedAssembly\Debug einbinden. Sie müssen angeben, die [ \<DevelopmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) Element in der Computerkonfigurationsdatei. Dieses Element weist die common Language Runtime DEVPATH verwenden, um Assemblys zu suchen.  
  
 Die freigegebene Assembly muss von der Laufzeit erkannt werden.  Zum Angeben eines privaten Verzeichnisses für das Auflösen von Assembly-Verweise verwendet die [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oder [ \<probing > Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie in beschrieben [Angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  Sie können auch die Assembly in einem Unterverzeichnis des Anwendungsverzeichnisses einfügen. Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)(Seite möglicherweise auf Englisch).  
  
> [!NOTE]
>  Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen.  
  
 Das folgende Beispiel zeigt, wie Sie dazu führen, dass die Runtime sucht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben wird.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Diese Einstellung wird standardmäßig auf "false".  
  
> [!NOTE]
>  Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung. Die Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen finden Sie in die DEVPATH. Sie verwendet einfach die erste Assembly gefundenen.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
