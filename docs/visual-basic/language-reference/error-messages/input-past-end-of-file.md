---
title: Eingabe nach dem Dateiende.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342777"
---
# <a name="input-past-end-of-file"></a>Eingabe nach dem Dateiende.
Entweder ein `Input` Anweisung liest aus einer Datei, die leer ist oder eine der in dem alle Daten verwendet wird, oder Sie verwendet die `EOF` -Funktion mit einer Datei für den binären Zugriff geöffnet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Verwenden der `EOF` Funktion unmittelbar vor der `Input` Anweisung, um das Ende der Datei zu erkennen.  
  
2. Wenn die Datei für den binären Zugriff geöffnet wird, verwenden Sie `Seek` und `Loc`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
