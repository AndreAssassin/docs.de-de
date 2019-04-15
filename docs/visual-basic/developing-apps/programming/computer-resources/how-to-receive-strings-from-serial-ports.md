---
title: 'Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 6c832cd9ef5df904850261f4de2d769bfc28c3cb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296718"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic
Dieses Thema beschreibt, wie `My.Computer.Ports` zum Empfangen von Zeichenfolgen von seriellen Ports des Computers in Visual Basic verwendet wird.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>So werden Zeichenfolgen von seriellen Anschlüssen empfangen  
  
1. Initialisieren Sie die zurückgegebene Zeichenfolge.  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. Bestimmen Sie, welcher serielle Anschluss die Zeichenfolgen bereitstellen soll. In diesem Beispiel wird vorausgesetzt, dass es `COM1` ist.  
  
3. Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Der `Try...Catch...Finally`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird. Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block angezeigt werden.  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. Erstellen Sie eine `Do`-Schleife für das Lesen von Textzeilen, bis keine weiteren Zeilen verfügbar sind.  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. Verwenden Sie die <xref:System.IO.Ports.SerialPort.ReadLine>-Methode, um die nächste verfügbare Textzeile aus dem seriellen Anschluss auszulesen.  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. Verwenden Sie eine `If`-Anweisung, um zu ermitteln, ob die <xref:System.IO.Ports.SerialPort.ReadLine>-Methode `Nothing` zurückgibt (was bedeutet, dass kein weiterer Text mehr verfügbar ist). Wenn sie `Nothing` zurückgibt, beenden Sie die `Do`-Schleife.  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. Fügen Sie einen `Else`-Block zur `If`-Anweisung hinzu, um den Fall so zu behandeln, als würde die Zeichenfolge tatsächlich gelesen. Der Block fügt die Zeichenfolge vom seriellen Anschluss an die Rückgabezeichenfolge an.  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. Gibt die Zeichenfolge zurück.  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet. Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen, um mehr Flexibilität zu gewährleisten. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Dieses Beispiel verwendet einen `Try...Catch...Finally`-Block, um sicherzustellen, dass die Anwendung den Anschluss schließt, und um Zeitüberschreitungen zu erfassen. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
