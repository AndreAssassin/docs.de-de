---
title: 'Problembehandlung: Lesen aus und Schreiben in Textdateien (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 90a04d9de2ac77c28a92d99e1fe118a1f8ecf448
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831786"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a>Problembehandlung: Lesen aus und Schreiben in Textdateien (Visual Basic)
Dieses Thema behandelt häufige Probleme beim Arbeiten mit Textdateien und bietet entsprechende Lösungsansätze an.  
  
## <a name="common-problems"></a>Häufige Probleme  
 Zu den häufigsten Probleme beim Arbeiten mit Textdateien zählen u.a. Sicherheitsausnahmen, Dateicodierungen oder ungültige Pfade.  
  
### <a name="security-exceptions"></a>Sicherheitsausnahmen  
 Eine <xref:System.Security.SecurityException> wird ausgelöst, wenn ein Sicherheitsfehler auftritt. Dies geschieht häufig, wenn dem Benutzer notwendige Berechtigungen fehlen; es kann möglicherweise durch das Hinzufügen von Berechtigungen oder die Arbeit mit Dateien in einem isolierten Speicher behoben werden.  
  
### <a name="file-encodings"></a>Dateicodierungen  
 Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden. Unerwartete Zeichen in einer Textdatei können aufgrund einer falschen Codierung auftreten. Für die meisten Dateien ist eine Codierung vielleicht einer anderen vorzuziehen, je nachdem, welche Sprachzeichen sie verarbeiten oder nicht verarbeiten kann. Unicode wird jedoch in der Regel empfohlen. Weitere Informationen finden Sie unter [Dateicodierungen](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) und <xref:System.Text.Encoding>.  
  
### <a name="incorrect-paths"></a>Falsche Pfade  
 Beim Analysieren von Dateipfaden, insbesondere bei relativen Pfaden, ist es einfach, die falschen Daten bereitzustellen. Viele Probleme können korrigiert werden, indem Sie sicherstellen, dass Sie den richtigen Pfad angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Schreiben in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
