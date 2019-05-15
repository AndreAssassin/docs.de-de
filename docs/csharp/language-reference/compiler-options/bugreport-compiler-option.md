---
title: -bugreport (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: f25455fac84903f9c39861e1f6863f6b2f6928f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587388"
---
# <a name="-bugreport-c-compiler-options"></a>-bugreport (C#-Compileroptionen)
Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Der Name der Datei, die den Problembericht enthalten soll.  
  
## <a name="remarks"></a>Anmerkungen  
 Die Option **-bugreport** gibt an, dass die folgende Informationen in `file` eingefügt werden soll:  
  
- Eine Kopie aller Quellcodedateien in der Kompilierung.  
  
- Eine Liste der bei der Kompilierung verwendeten Compileroptionen.  
  
- Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.  
  
- Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET Framework und dem SDK enthaltene Assemblys.  
  
- Compilerausgabe, falls vorhanden.  
  
- Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
- Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
 Wenn diese Option mit **-errorreport:prompt** oder **-errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.  
  
 Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
 Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
- [-errorreport (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
