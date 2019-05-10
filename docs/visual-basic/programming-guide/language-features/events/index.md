---
title: Ereignisse (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
ms.openlocfilehash: 5986923b10700b1795886c24343a4b45e6bff46e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616703"
---
# <a name="events-visual-basic"></a>Ereignisse (Visual Basic)
Sie sich Visual Studio-Projekt als eine Reihe von Prozeduren vorstellen, in einer Sequenz, in der Praxis ausgeführt, sind die meisten Programme ereignisgesteuerte – d. h. den Ausführungsablauf richtet sich nach externen Vorkommnissen aufgerufen *Ereignisse*.  
  
 Ein Ereignis ist ein Signal, das eine Anwendung darüber informiert, dass etwas Wichtiges geschehen ist. Wenn ein Benutzer beispielsweise auf ein Steuerelement in einem Formular klickt, löst das Formular ein `Click`-Ereignis aus und ruft eine Prozedur auf, die das Ereignis behandelt. Ereignisse ermöglichen zudem die Kommunikation zwischen separaten Tasks. Beispiel: Die Anwendung führt separat von der Hauptanwendung einen Sortiertask aus. Wenn ein Benutzer den Sortiervorgang abbricht, kann die Anwendung ein Cancel-Ereignis senden, das den Abbruch des Sortiervorgangs veranlasst.  
  
## <a name="event-terms-and-concepts"></a>Ereignisse – Begriffe und Konzepte  
 Dieser Abschnitt beschreibt die Begriffe und Konzepte, die mit Ereignissen in Visual Basic verwendet.  
  
### <a name="declaring-events"></a>Deklarieren von Ereignissen  
 Ereignisse werden innerhalb von Klassen, Strukturen, Modulen und Schnittstellen mithilfe des `Event`-Schlüsselworts deklariert, wie im folgenden Beispiel dargestellt:  
  
 [!code-vb[VbVbalrEvents#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#24)]  
  
### <a name="raising-events"></a>Auslösen von Ereignissen  
 Ein Ereignis ist mit einer Nachricht vergleichbar, die bekannt gibt, dass etwas Wichtiges geschehen ist. Das Senden der Nachricht wird als *Auslösen* des Ereignisses bezeichnet. In Visual Basic lösen Sie Ereignisse mit der `RaiseEvent` -Anweisung wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbalrEvents#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#25)]  
  
 Ereignisse müssen im Geltungsbereich der Klasse, des Moduls oder der Struktur ausgelöst werden, in der bzw. dem sie deklariert wurden. So kann beispielsweise eine abgeleitete Klasse keine Ereignisse auslösen, die von einer Basisklasse geerbt wurden.  
  
### <a name="event-senders"></a>Ereignissender  
 Jedes Objekt, das in der Lage ist, ein Ereignis auszulösen, ist ein *Ereignissender* (auch *Ereignisquelle* genannt). Formulare, Steuerelemente und benutzerdefinierte Objekte sind Beispiele für Ereignissender.  
  
### <a name="event-handlers"></a>Ereignishandler  
 *Ereignishandler* sind Prozeduren, die aufgerufen werden, wenn ein entsprechendes Ereignis eintritt. Jede gültige Unterroutine mit einer übereinstimmenden Signatur kann als Ereignishandler verwendet werden. Funktionen können jedoch nicht als Ereignishandler verwendet werden, da sie keinen Wert an die Ereignisquelle zurückgeben können.  
  
 Visual Basic verwendet eine standardmäßige Benennungskonvention für Ereignishandler, der den Namen des Ereignissenders, einen Unterstrich und der Name des Ereignisses kombiniert. Das `Click`-Ereignis einer Schaltfläche mit dem Namen `button1` heißt beispielsweise `Sub button1_Click`.  
  
> [!NOTE]
>  Beim Definieren von Ereignishandlern für Ihre Ereignisse empfiehlt sich die Verwendung dieser Benennungskonvention, sie ist jedoch nicht erforderlich. Sie können stattdessen auch jeden gültigen Unterroutinennamen verwenden.  
  
## <a name="associating-events-with-event-handlers"></a>Verknüpfen von Ereignissen mit Ereignishandlern  
 Bevor ein Ereignishandler verwendet werden kann, müssen Sie ihn über die `Handles`- oder die `AddHandler`-Anweisung mit einem Ereignis verknüpfen.  
  
### <a name="withevents-and-the-handles-clause"></a>WithEvents und die Handles-Klausel  
 Die `WithEvents`-Anweisung und die `Handles`-Klausel bieten die Möglichkeit, Ereignishandler per Deklaration festzulegen. Ein Ereignis, das durch ein mit dem `WithEvents`-Schlüsselwort deklariertes Objekt ausgelöst wird, kann von einer beliebigen Prozedur mit einer `Handles`-Anweisung für dieses Ereignis behandelt werden (siehe folgendes Beispiel):  
  
 [!code-vb[VbVbalrEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#1)]  
  
 Die `WithEvents`-Anweisung und die `Handles`-Klausel sind häufig die beste Wahl für Ereignishandler, da die hier verwendete Deklarationssyntax das Programmieren, Lesen und Debuggen der Ereignisbehandlung vereinfacht. Beachten Sie jedoch die folgenden Einschränkungen bei der Verwendung von `WithEvents`-Variablen:  
  
- Sie können eine `WithEvents`-Variable nicht als Objektvariable verwenden. Dies bedeutet, dass Sie die Variable nicht als `Object` deklarieren können, sondern den Klassennamen angeben müssen, wenn Sie die Variable deklarieren.  
  
- Da freigegebene Ereignisse nicht an Klasseninstanzen gebunden sind, können keine `WithEvents` auf deklarative Behandlung freigegebener Ereignisse. Ebenso können Sie `WithEvents` oder `Handles` nicht zum Behandeln von Ereignissen aus einer `Structure` verwenden. In beiden Fällen können Sie diese Ereignisse mit der `AddHandler`-Anweisung behandeln.  
  
- Sie können keine Arrays aus `WithEvents`-Variablen erstellen.  
  
 Mit `WithEvents`-Variablen kann ein einziger Ereignishandler eine oder mehrere Ereignisarten bzw. einen oder mehrere Ereignishandler zur Behandlung derselben Art von Ereignissen verarbeiten.  
  
 Die `Handles`-Klausel ist zwar das Standardverfahren zum Verknüpfen eines Ereignisses mit einem Ereignishandler, ist aber auf das Verknüpfen von Ereignissen mit Ereignishandlern zur Kompilierzeit beschränkt.  
  
 In einigen Fällen z. B. mit Ereignisse im Zusammenhang mit Formularen oder Steuerelementen erstellt Visual Basic automatisch einen Stub für einen leeren Ereignishandler und ordnet ihn einem Ereignis zu. Wenn Sie eine Befehlsschaltfläche in einem Formular im Entwurfsmodus doppelklicken, erstellt Visual Basic z. B. einen leeren Ereignishandler und eine `WithEvents` -Variable für die Befehlsschaltfläche, wie im folgenden Code:  
  
 [!code-vb[VbVbalrEvents#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#26)]  
  
### <a name="addhandler-and-removehandler"></a>AddHandler und RemoveHandler  
 Die `AddHandler`-Anweisung ähnelt der `Handles`-Klausel insofern, als Sie mit beiden einen Ereignishandler angeben können. `AddHandler` bietet Ihnen jedoch zusammen mit `RemoveHandler` mehr Flexibilität als die `Handles`-Klausel, da es ein dynamisches Hinzufügen, Entfernen und Ändern des einem Ereignis zugeordneten Ereignishandlers ermöglicht. Wenn Sie freigegebene Ereignisse oder Ereignisse aus einer Struktur behandeln möchten, müssen Sie `AddHandler` verwenden.  
  
 `AddHandler` benötigt zwei Argumente: den Namen eines Ereignisses von einem Ereignissender (z.B. einem Steuerelement) und einen Ausdruck, der einen Delegaten ergibt. Wenn Sie `AddHandler` verwenden, müssen Sie die Delegatklasse nicht explizit angeben, da die `AddressOf`-Anweisung stets einen Verweis auf den Delegaten zurückgibt. Im folgenden Beispiel wird ein Ereignishandler mit einem Ereignis verknüpft, das durch ein Objekt ausgelöst wird:  
  
 [!code-vb[VbVbalrEvents#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#28)]  
  
 Für `RemoveHandler`, wodurch ein Ereignis von einem Ereignishandler getrennt wird, wird die gleiche Syntax verwendet wie für `AddHandler`. Zum Beispiel:  
  
 [!code-vb[VbVbalrEvents#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#29)]  
  
 Im folgenden Beispiel ist einem Ereignis ein Ereignishandler zugeordnet, und das Ereignis wird ausgelöst. Der Ereignishandler fängt das Ereignis ab und zeigt eine Meldung an.  
  
 Anschließend wird der erste Ereignishandler entfernt, und dem Ereignis wird ein anderer Ereignishandler zugeordnet. Beim erneuten Auslösen des Ereignisses wird eine andere Meldung angezeigt.  
  
 Schließlich wird der zweite Ereignishandler entfernt, und das Ereignis wird zum dritten Mal ausgelöst. Da dem Ereignis kein Ereignishandler mehr zugeordnet ist, wird keine Aktion ausgeführt.  
  
 [!code-vb[VbVbalrEvents#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class2.vb#38)]  
  
## <a name="handling-events-inherited-from-a-base-class"></a>Behandeln von Ereignissen, die von einer Basisklasse geerbt wurden  
 *Abgeleitete Klassen* sind Klassen, die Merkmale von einer Basisklasse erben. Sie können mithilfe der `Handles MyBase`-Anweisung Ereignisse behandeln, die von ihrer Basisklasse ausgelöst wurden.  
  
### <a name="to-handle-events-from-a-base-class"></a>So behandeln Sie Ereignisse aus einer Basisklasse  
  
- Deklarieren Sie einen Ereignishandler in der abgeleiteten Klasse, indem Sie der Deklarationszeile der Prozedur für den Ereignishandler eine `Handles MyBase.`*Ereignisname*-Anweisung hinzufügen. Dabei ist *Ereignisname* der Name des zu behandelnden Ereignisses in der Basisklasse. Zum Beispiel:  
  
     [!code-vb[VbVbalrEvents#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#12)]  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|Stellt eine Schritt-für-Schritt-Beschreibung des Deklarierens und Auslösens von Ereignissen für eine Klasse bereit.|  
|[Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|Veranschaulicht das Schreiben einer Ereignishandlerprozedur.|  
|[Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um die Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|Veranschaulicht die Definition eines benutzerdefinierten Ereignisses, das einen asynchronen Aufruf seiner Ereignishandler zulässt.|  
|[Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|Veranschaulicht die Definition eines benutzerdefinierten Ereignisses, das nur bei der Behandlung des Ereignisses Arbeitsspeicher nutzt.|  
|[Problembehandlung für geerbte Ereignishandler in Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|Führt häufige Probleme auf, die bei Ereignishandlern in geerbten Komponenten auftreten können.|  
|[Ereignisse](../../../../standard/events/index.md)|Bietet eine Übersicht über das Ereignismodell in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].|  
|[Erstellen von Ereignishandlern in Windows Forms](../../../../framework/winforms/creating-event-handlers-in-windows-forms.md)|Beschreibt die Verwendung von Ereignissen, die Windows Forms-Objekten zugeordnet sind.|  
|[Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|Stellt eine Übersicht über Delegaten in Visual Basic bereit.|
