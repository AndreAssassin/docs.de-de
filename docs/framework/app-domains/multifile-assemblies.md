---
title: Mehrfachdateiassemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 862fc7012c2c5c84a163d6716dfeb4b97f00cbcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634179"
---
# <a name="multifile-assemblies"></a>Mehrfachdateiassemblys

Sie können Mehrfachdateiassemblys mit dem Befehlszeilencompiler oder in Visual Studio mit Visual C++ erstellen. Eine Datei in der Assembly muss das Assemblymanifest enthalten. Eine Assembly, die eine Anwendung startet, muss außerdem einen Einstiegspunkt enthalten, wie z.B. die Methoden „Main“ oder „WinMain“.

Nehmen Sie z.B. an, dass Sie eine Anwendung haben, die zwei Codemodule enthält, „client.cs“ und „stringer.cs“. „Stringer.cs“ erstellt den Namespace `myStringer`, auf den vom Code in „client.cs“ verwiesen wird. „Client.cs“ enthält die Methode `Main`, die der Einstiegspunkt der Anwendung ist. In diesem Beispiel kompilieren Sie die zwei Codemodule und erstellen dann eine dritte Datei, die das Assemblymanifest enthält, das die Anwendung startet. Das Assemblymanifest verweist sowohl auf das Modul `Client` als auch auf das Modul `Stringer`.

> [!NOTE]
> Mehrfachdateiassemblys können nur einen Einstiegspunkt haben, auch wenn die Assembly über mehrere Codemodule verfügt.

Es gibt mehrere Gründe, sich für eine Mehrfachdateiassembly zu entscheiden:

- Das Kombinieren von Modulen, die in unterschiedlichen Sprachen geschrieben wurden. Dies ist der häufigste Grund für das Erstellen einer Mehrfachdateiassembly.

- Die Optimierung des Herunterladens einer Anwendung durch das Einfügen selten verwendeter Typen in ein Modul, das nur wenn nötig heruntergeladen wird.

    > [!NOTE]
    > Wenn Sie eine Anwendung erstellen, die mit dem `<object>`-Tag mit Microsoft Internet Explorer heruntergeladen wird, ist es wichtig, dass Sie Mehrfachdateiassemblys erstellen. In diesem Szenario erstellen Sie eine von Ihren Codemodulen getrennte Datei, die nur das Assemblymanifest enthält. Internet Explorer lädt zunächst das Assemblymanifest herunter und erstellt anschließend Arbeitsthreads, um alle weiteren erforderlichen Module bzw. Assemblys herunterzuladen. Während des Downloads der Datei, die das Assemblymanifest enthält, reagiert Internet Explorer nicht auf Eingaben des Benutzers. Je kleiner die Datei ist, die das Assemblymanifest enthält, desto kürzer ist die Zeitspanne, in der Internet Explorer nicht reagiert.

- Das Kombinieren von Codemodulen, die von mehreren Entwicklern geschrieben wurden. Obwohl jeder Entwickler jedes Codemodul in eine Assembly kompilieren kann, kann dies dazu führen, dass einige Teile öffentlich gemacht werden, die aber nicht verfügbar gemacht werden, wenn alle Module in eine Mehrfachdateiassembly integriert werden.

Sobald Sie die Assembly erstellt haben, können Sie die Datei signieren, die das Assemblymanifest enthält (und somit auch die Assembly). Alternativ können Sie der Datei auch einen starken Namen geben und sie in den globalen Assemblycache einfügen.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
