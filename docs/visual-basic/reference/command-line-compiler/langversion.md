---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839721"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Bewirkt, dass den Compiler nur Syntax akzeptiert, die in der angegebenen Version des Visual Basic-Sprache enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumente  
 `version`  
 Erforderlich. Die Sprachversion, die während der Kompilierung verwendet werden. Gültige Werte sind `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` und `latest`.

 Die ganze Zahlen kann auch angegeben werden mithilfe von `.0` als Nebenversion, z. B. `11.0`.

 Sie können die Liste aller möglichen Werte anzeigen, indem Sie die Angabe `-langversion:?` in der Befehlszeile.  
  
## <a name="remarks"></a>Hinweise  
 Die `-langversion` Option gibt an, welche Syntax, die der Compiler akzeptiert. Wenn Sie angeben, dass die Sprachversion 9.0 ist, generiert der Compiler z. B. Fehler für die Syntax, die nur in Version 10.0 und höher ist.  
  
 Sie können diese Option verwenden, wenn Sie Anwendungen, die verschiedene Versionen von .NET Framework abzielen entwickeln. Wenn Sie .NET Framework 3.5 verwenden möchten, können Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie die Syntax von, Sprachversion 10.0 nicht verwenden.  
  
 Sie können festlegen, `-langversion` direkt nur mithilfe der Befehlszeile aus. Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Festlegen einer bestimmten .NET-Framework-Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
