---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 9a844515a4596064937762ac05b850463f1b5e14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819176"
---
# <a name="-filealign"></a>-filealign
Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Erforderlich. Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `-filealign` Option aus, um die Ausrichtung der Abschnitte in Ihrer Ausgabedatei angeben. Abschnitte sind zusammenhängende Speicherblöcke in einer PE (Portable Executable)-Datei, die entweder Code oder Daten enthält. Die `-filealign` Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren; die meisten Entwickler müssen sich nicht auf diese Option verwenden.  
  
 Jeder Abschnitt orientiert sich an einer Grenze, die ein Vielfaches von ist das `-filealign` Wert. Es gibt keinen festen Standardwert. Wenn `-filealign` nicht angegeben wird, wählt der Compiler einen Standardwert zum Zeitpunkt der Kompilierung.  
  
 Durch Angeben der Abschnittsgröße, können Sie die Größe der Ausgabedatei ändern. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
> [!NOTE]
>  Die `-filealign` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
