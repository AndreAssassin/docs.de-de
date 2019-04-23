---
title: -target:winexe (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 3c16bf8aed0d281b2b5a3f9c6ae06f343b1eff7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307305"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (C#-Compileroptionen)
Die Option **-target:winexe** bewirkt, dass der Compiler ein ausführbares Windows-Programm (EXE) erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Anmerkungen  
 Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt. Ein Windows-Programm stellt eine Benutzeroberfläche entweder aus der .NET Framework-Bibliothek oder mit den Windows-APIs bereit.  
  
 Verwenden Sie [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), um eine Konsolenanwendung zu erstellen.  
  
 Sofern Sie nicht die Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält.  
  
 Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) verwendet, um das Windows-Programm zu erstellen.  
  
 Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden. Sollte Ihr Code mehr als eine Klasse mit einer **Main**-Methode enthalten, können Sie mit der Option [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) angeben, welche Klasse die **Main**-Methode enthält.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3. Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs` in ein Windows-Programm:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>Siehe auch

- [-target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
