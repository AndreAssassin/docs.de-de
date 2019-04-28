---
title: -Resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 46122eaa7ca54679c9a52b939f9100c9a0747e7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639083"
---
# <a name="-resource-visual-basic"></a>-Resource (Visual Basic)
Bettet eine verwaltete Ressource in eine Assembly ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden soll. In der Standardeinstellung `filename` in der Assembly öffentlich ist. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.|  
|`identifier`|Dies ist optional. Der logische Name für die Ressource; der Name, der zum Laden der Daten verwendet wird. Der Standardwert ist der Name der Datei. Optional können Sie angeben, ob die Ressource öffentlich oder privat ist, in das Assemblymanifest, wie Sie sich mit den folgenden ist: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `-linkresource` verknüpfen eine Ressource auf eine Assembly, die Ressourcendatei in der Ausgabedatei platziert.  
  
 Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> Informationen). Um auf alle anderen Ressourcen zur Laufzeit zuzugreifen, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Die Kurzform von `-resource` ist `-res`.  
  
 Informationen zum Festlegen `-resource` finden Sie in der Visual Studio-IDE unter [Verwalten von Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
