---
title: 'Vorgehensweise: Asynchrones Laden eines Sounds in einem Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 1d710f1e6d3b208365d5b1eb2524fbeeaa673c2d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185756"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a>Vorgehensweise: Asynchrones Laden eines Sounds in einem Windows Forms
Im folgenden Codebeispiel wird ein Sound aus einer URL asynchron geladen und anschließend auf einem neuen Thread abgespielt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
-   Ersetzen Sie den Dateinamen `"http://www.tailspintoys.com/sounds/stop.wav"` durch einen gültigen Dateinamen.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Dateioperationen sollten in entsprechende Ausnahmebehandlungsblöcke eingeschlossen sein.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfadname ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).  
  
-   Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).  
  
-   Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>-Klasse).  
  
-   Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).  
  
-   Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>-Klasse).  
  
-   Der Pfad besteht nur aus einem Doppelpunkt ":" (<xref:System.NotSupportedException>-Klasse).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei `Form1.vb` handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei. Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [Vorgehensweise: Wiedergabe von Sound in Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
