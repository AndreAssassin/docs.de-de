---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 15fe62457ed11ffcd08a1db3aa8be57080f22869
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300797"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileName`|Der Pfad der benutzerdefinierten Manifestdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest, das eine angeforderte Ausführungsebene "asInvoker" angibt. Das Manifest erstellt in demselben Ordner, in dem die ausführbare Datei wird erstellt, in der Regel den Ordner "bin\Debug" oder "bin\Release", bei der Verwendung von Visual Studio. Wenn Sie ein benutzerdefiniertes Manifest, z. B. zum Festlegen von einer angeforderten Ausführungsebene "highestAvailable" oder "requireAdministrator", angeben möchten verwenden Sie diese Option, um den Namen der Datei anzugeben.  
  
> [!NOTE]
>  Diese Option und die [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Option schließen sich gegenseitig. Wenn Sie versuchen, beide Optionen in der gleichen Befehlszeile verwenden, erhalten Sie einen Buildfehler.  
  
 Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista. Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Ihre Anwendung werden Virtualisierung, wenn eine der folgenden Bedingungen zutrifft:  
  
1. Sie verwenden die `-nowin32manifest` Option, und Sie bieten kein Manifests in einem späteren Buildschritt oder als Teil einer Windows-Ressourcendatei (. res) mithilfe der `-win32resource` Option.  
  
2. Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen. Sie können auch anzeigen oder bearbeiten Sie die Standarddatei "App.manifest" durch Klicken auf **UAC-Anzeigeeinstellungen** auf die **Anwendung** Registerkarte im Projekt-Designer. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungsmanifest als einen benutzerdefinierten Postbuildschritt oder als Teil der Win32-Ressourcendatei bereitstellen, mit der `-nowin32manifest` Option. Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll. Dadurch wird verhindert, dass den Compiler erstellt und einbettet ein Standardmanifest in der PE-Datei.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt dem Standard-Manifest, dass Visual Basic-Compiler in eine PE einfügt.  
  
> [!NOTE]
>  Der Compiler Fügt einen Standardanwendungsnamen MyApplication.app in das XML-Manifest. Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
