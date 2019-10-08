---
title: -Verweis (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 552fbcf920be609de83708a995a87761f6080220
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005273"
---
# <a name="-reference-visual-basic"></a>-Verweis (Visual Basic)
Bewirkt, dass der Compiler Typinformationen in den angegebenen Assemblys zur Verfügung stellt, die für das aktuell kompilierte Projekt verfügbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-reference:fileList  
```

oder

```console
-r:fileList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileList`|Erforderlich. Durch Trennzeichen getrennte Liste von Assemblydateinamen. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Dateien, die Sie importieren, müssen Assemblymetadaten enthalten. Nur öffentliche Typen sind außerhalb der Assembly sichtbar. Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) -Option importiert Metadaten aus einem Modul.  
  
 Wenn Sie auf eine Assembly (Assembly a) verweisen, die selbst auf eine andere Assembly (Assembly b) verweist, müssen Sie auf die Assembly b verweisen, wenn Folgendes gilt:  
  
- Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
- Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.  
  
 Verwenden Sie [-LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) , um das Verzeichnis anzugeben, in dem sich ein oder mehrere der Assemblyverweise befinden.  
  
 Damit der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennen kann, muss er gezwungen werden, den Typ aufzulösen. Ein Beispiel hierfür ist das Definieren einer Instanz des-Typs. Es stehen andere Möglichkeiten zum Auflösen von Typnamen in einer Assembly für den Compiler zur Verfügung. Wenn Sie z. b. von einem Typ in einer Assembly erben, wird der Typname dem Compiler bekannt.  
  
 Die Vbc. rsp-Antwortdatei, die auf häufig verwendete .NET Framework Assemblys verweist, wird standardmäßig verwendet. Verwenden Sie `-noconfig`, wenn Sie nicht möchten, dass der Compiler Vbc. rsp verwendet.  
  
 Die Kurzform von `-reference` ist `/r`.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Befehl werden Quelldatei `Input.vb` und Verweisassemblys aus `Metad1.dll` und `Metad2.dll` kompiliert, um `Out.exe` zu erstellen.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Öffentlich](../../../visual-basic/language-reference/modifiers/public.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
