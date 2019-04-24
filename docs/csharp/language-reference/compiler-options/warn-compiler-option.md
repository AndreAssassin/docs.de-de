---
title: -warn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 17dd992edbec5ce444b53ed42b2b486282618672
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315802"
---
# <a name="-warn-c-compiler-options"></a>-warn (C#-Compileroptionen)
Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Argumente  
 `option`  
 Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur sehr schwerwiegende Warnungen an; höhere Zahlen zeigen mehr Warnungen an. Gültige Werte sind 0–4:  
  
|Warnstufe|Bedeutung|  
|-------------------|-------------|  
|0|Deaktiviert die Ausgabe aller Warnungmeldungen|  
|1|Zeigt schwerwiegende Warnmeldungen an|  
|2|Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern|  
|3|Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden|  
|4 (Standard)|Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an|  
  
## <a name="remarks"></a>Anmerkungen  
 Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach. Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../../../csharp/language-reference/compiler-messages/index.md).  
  
 Verwenden Sie [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln. Verwenden Sie [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.  
  
 **-w** ist die Kurzform von **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3. Ändern Sie die Eigenschaft **Warnstufe**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
