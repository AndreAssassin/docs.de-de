---
title: Ressourcen in .NET-Apps
ms.date: 07/25/2018
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- deploying applications [.NET Core], resources
- application resources
- resource files
- satellite assemblies
- localization
- packaging application resources
- localizing resources
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64f3f2bb54bd454ef037da2f7e10dd9067bf2217
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045600"
---
# <a name="resources-in-net-apps"></a>Ressourcen in .NET-Apps
Fast jede professionell erstellte App benötigt Ressourcen. Dabei handelt es sich um nicht ausführbare Daten, die logisch mit einer App bereitgestellt werden. Eine Ressource kann in einer App als Fehlermeldung oder als Teil der Benutzeroberfläche angezeigt werden. Ressourcen können verschiedene Formen von Daten enthalten, z. B. Zeichenfolgen, Bilder und beibehaltene Objekte. (Objekte, die beibehalten werden, müssen serialisierbar sein, um in eine Ressourcendatei geschrieben werden zu können.) Durch Speichern von Daten in einer Ressourcendatei können Sie die Daten ändern, ohne die gesamte App neu kompilieren zu müssen. Außerdem können Sie dadurch die Daten an einem einzigen Ort speichern und müssen nicht auf hartcodierte Daten zurückgreifen, die an mehreren Orten gespeichert wird.  
  
 .NET Framework und .NET Core stellen umfassende Unterstützung zum Erstellen und Lokalisieren von Ressourcen zur Verfügung. Außerdem unterstützt .NET ein einfaches Modell zum Verpacken und Bereitstellen lokalisierter Ressourcen.  
  
 Weitere Informationen zu Ressourcen in ASP.NET finden Sie unter [Übersicht über Ressourcen der ASP.NET-Webseite](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).  
  
## <a name="creating-and-localizing-resources"></a>Erstellen und Lokalisieren von Ressourcen  

In einer nicht lokalisierten App können Sie Ressourcendateien als Repository für App-Daten verwenden. Dies gilt besonders für Zeichenfolgen, die andernfalls an mehreren Stellen im Quellcode hartcodiert wären. Im Allgemeinen werden Ressourcen als Textdateien (.txt) oder XML-Dateien (.resx) erstellt und dann mit [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md) in binäre .resources-Dateien kompiliert. Diese Dateien können dann durch einen Sprachcompiler in die ausführbare Datei der App eingebettet werden. Weitere Informationen zum Erstellen von Ressourcen finden Sie unter [Erstellen von Ressourcendateien](creating-resource-files-for-desktop-apps.md).  

Sie können die Ressourcen der App auch für bestimmte Kulturen lokalisieren. Dadurch können Sie lokalisierte (übersetzte) Versionen der Apps erstellen. Wenn Sie eine App entwickeln, die lokalisierte Ressourcen verwendet, legen Sie eine Kultur als neutrale bzw. Ausweichkultur fest, deren Ressourcen verwendet werden, wenn keine passenden Ressourcen verfügbar sind. In der Regel werden die Ressourcen der neutralen Kultur in der ausführbaren Datei der App gespeichert. Die verbleibenden Ressourcen für einzelne lokalisierte Kulturen werden in eigenständigen Satellitenassemblys gespeichert. Weitere Informationen finden Sie unter [Erstellen von Satellitenassemblys](creating-satellite-assemblies-for-desktop-apps.md).  
  
## <a name="packaging-and-deploying-resources"></a>Verpacken und Bereitstellen von Ressourcen  
 Lokalisierte App-Ressourcen werden in [Satellitenassemblys](packaging-and-deploying-resources-in-desktop-apps.md) bereitgestellt. Eine Satellitenassembly enthält die Ressourcen einer einzelnen Kultur. Sie enthält keinen App-Code. Im Satellitenassembly-Bereitstellungsmodell erstellen Sie eine App mit einer Standardassembly (in der Regel die Hauptassembly) und einer Satellitenassembly für jede Kultur, die von der App unterstützt wird. Da die Satellitenassemblys kein Teil der Hauptassembly sind, können Sie die Ressourcen problemlos entsprechend einer bestimmten Kultur ersetzen oder aktualisieren, ohne die Hauptassembly der App ersetzen zu müssen.  
  
 Überlegen Sie genau, aus welchen Ressourcen die Standardressourcenassembly der App bestehen soll. Da diese ein Teil der Hauptassembly ist, müssen Sie nach jeder Änderung daran auch die Hauptassembly ersetzen. Wenn Sie keine Standardressource angeben, wird eine Ausnahme ausgelöst, wenn der [Ressourcenfallback-Prozess](packaging-and-deploying-resources-in-desktop-apps.md) versucht, sie zu finden. In einer gut entworfenen App sollte die Verwendung von Ressourcen nie Ausnahmen auslösen.  
  
 Weitere Informationen finden Sie im Artikel [Verpacken und Bereitstellen von Ressourcen](packaging-and-deploying-resources-in-desktop-apps.md).  
  
## <a name="retrieving-resources"></a>Abrufen von Ressourcen  
 Zur Laufzeit werden von einer App die passenden lokalisierten Ressourcen auf Threadbasis entsprechend der Kultur geladen, die von der <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft angegeben wird. Dieser Eigenschaftswert wird wie folgt abgeleitet:  
  
- Durch direktes Zuweisen eines <xref:System.Globalization.CultureInfo>-Objekts, das die lokalisierte Kultur darstellt, zur <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft.  
  
- Wenn keine Kultur explizit zugeordnet wurde, durch Abrufen der Benutzeroberflächenkultur des Standardthreads von der <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft.  
  
- Wenn keine Benutzeroberflächenkultur des Standardthreads explizit zugeordnet wurde, durch Abrufen der Kultur für den aktuellen Benutzer auf dem lokalen Computer. Dazu rufen unter Windows ausgeführte .NET Implementierungen die Windows-Funktion [`GetUserDefaultUILanguage`](/windows/desktop/api/winnls/nf-winnls-getuserdefaultuilanguage) auf.  
  
 Weitere Informationen darüber, wie die aktuelle Benutzeroberflächenkultur festgelegt wird, finden Sie auf den Referenzseiten <xref:System.Globalization.CultureInfo> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>.  
  
 Sie können Ressourcen dann für die aktuelle Benutzeroberflächenkultur oder für eine bestimmte Kultur abrufen, indem Sie die <xref:System.Resources.ResourceManager?displayProperty=nameWithType>-Klasse verwenden. Die <xref:System.Resources.ResourceManager>-Klasse wird zwar am häufigsten zum Abrufen von Ressourcen verwendet, der <xref:System.Resources?displayProperty=nameWithType>-Namespace enthält jedoch weitere Typen, die Sie zum Abrufen von Ressourcen verwenden können. Dazu gehören:  
  
- Die <xref:System.Resources.ResourceReader>-Klasse, mit der Sie Ressourcen auflisten können, die in eine Assembly eingebettet oder in einer eigenständigen binären ".resources"-Datei gespeichert sind. Dies ist nützlich, wenn Sie die genauen Namen der Ressourcen nicht kennen, die zur Laufzeit verfügbar sind.  
  
- Die <xref:System.Resources.ResXResourceReader>-Klasse, mit der Sie Ressourcen aus einer XML-Datei (.resx) abrufen können.  
  
- Die <xref:System.Resources.ResourceSet>-Klasse, mit der Sie Ressourcen einer bestimmten Kultur abrufen können, ohne Fallbackregeln zu beachten. Die Ressourcen können in einer Assembly oder einer eigenständigen binären ".resources"-Datei gespeichert werden. Sie können auch eine <xref:System.Resources.IResourceReader>-Implementierung entwickeln, die Ihnen ermöglicht, mit der <xref:System.Resources.ResourceSet>-Klasse Ressourcen aus einer anderen Quelle abzurufen.  
  
- Die <xref:System.Resources.ResXResourceSet>-Klasse, mit der Sie alle Elemente in einer XML-Ressourcendatei in den Speicher abrufen können.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.CultureInfo>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>
- [Grundlagen der Anwendung](../../standard/application-essentials.md)
- [Erstellen von Ressourcendateien](creating-resource-files-for-desktop-apps.md)
- [Verpacken und Bereitstellen von Ressourcen](packaging-and-deploying-resources-in-desktop-apps.md)
- [Erstellen von Satellitenassemblys](creating-satellite-assemblies-for-desktop-apps.md)
- [Abrufen von Ressourcen](retrieving-resources-in-desktop-apps.md)
