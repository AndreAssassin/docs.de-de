---
title: 'Vorgehensweise: Erstellen einer Aktivität'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 6d74af6af6cea0d65c33db67ecbfd71ac1d5c346
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636945"
---
# <a name="how-to-create-an-activity"></a>Vorgehensweise: Erstellen einer Aktivität

Aktivitäten sind die wichtigsten Einheiten für das Verhalten in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Die Ausführungslogik einer Aktivität kann in verwaltetem Code oder mithilfe anderer Aktivitäten implementiert werden. In diesem Thema wird veranschaulicht, wie zwei Aktivitäten erstellt werden. Die erste Aktivität ist eine einfache Aktivität, die die Ausführungslogik auf der Basis von Code implementiert. Die Implementierung der zweiten Aktivität wird mithilfe anderer Aktivitäten definiert. Diese Aktivitäten werden in den folgenden Schritten des Lernprogramms verwendet.

> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.

## <a name="create-the-activity-library-project"></a>Erstellen Sie die Workflow-aktivitätsbibliothekprojekt

1. Öffnen Sie Visual Studio, und wählen Sie **neu** > **Projekt** aus der **Datei** Menü.

2. In der **neues Projekt** Dialogfeld unter die **installiert** Kategorie **Visual C#-** > **Workflow** (oder **Visual Basic** > **Workflow**).

    > [!NOTE]
    > Wenn Sie nicht sehen die **Workflow** Vorlagenkategorie, müssen Sie möglicherweise installieren die **Windows Workflow Foundation** Komponente von Visual Studio. Wählen Sie die **Visual Studio-Installer öffnen** Link auf der linken Seite die **neues Projekt** Dialogfeld. Wählen Sie in Visual Studio-Installer die **Einzelkomponenten** Registerkarte. Klicken Sie unter den **Entwicklungsaktivitäten** Kategorie der **Windows Workflow Foundation** Komponente. Wählen Sie **ändern** die Komponente installieren.

3. Wählen Sie die **Aktivitätsbibliothek** Projektvorlage. Typ `NumberGuessWorkflowActivities` in die **Namen** ein, und klicken Sie dann auf **OK**.

4. Mit der rechten Maustaste **Activity1.xaml** in **Projektmappen-Explorer** , und wählen Sie **löschen**. Klicken Sie zur Bestätigung auf **OK** .

## <a name="create-the-readint-activity"></a>Erstellen Sie die ReadInt-Aktivität

1. Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.

2. In der **installiert** > **gemeinsame Elemente** Knoten **Workflow**. Wählen Sie **Codeaktivität** aus der **Workflow** Liste.

3. Typ `ReadInt` in die **Namen** ein, und klicken Sie dann auf **hinzufügen**.

4. Ersetzen Sie die vorhandene `ReadInt`-Definition durch die folgende Definition.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > Die `ReadInt`-Aktivität wird von <xref:System.Activities.NativeActivity%601> statt von <xref:System.Activities.CodeActivity> abgeleitet. Das entspricht dem Standard für die Vorlage "Codeaktivität". <xref:System.Activities.CodeActivity%601> kann verwendet werden, wenn die Aktivität ein einziges Ergebnis bereitstellt, das durch das <xref:System.Activities.Activity%601.Result%2A>-Argument verfügbar gemacht wird, da <xref:System.Activities.CodeActivity%601> jedoch nicht die Verwendung von Lesezeichen unterstützt, wird <xref:System.Activities.NativeActivity%601> verwendet.

## <a name="create-the-prompt-activity"></a>Erstellen Sie die Prompt-Aktivität

1. Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen des Projekts. Durch das Erstellen des Projekts wird die `ReadInt`-Aktivität in diesem Projekt erstellt, mit der die benutzerdefinierte Aktivität aus diesem Schritt erstellt werden soll.

2. Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.

3. In der **installiert** > **gemeinsame Elemente** Knoten **Workflow**. Wählen Sie **Aktivität** aus der **Workflow** Liste.

4. Typ `Prompt` in die **Namen** ein, und klicken Sie dann auf **hinzufügen**.

5. Doppelklicken Sie auf **Prompt.xaml** in **Projektmappen-Explorer** um es im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.

6. Klicken Sie auf **Argumente** in den links unten auf der der Aktivitäts-Designer zum Anzeigen der **Argumente** Bereich.

7. Klicken Sie auf **Argument erstellen**.

8. Typ `BookmarkName` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Zeichenfolge** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE** auf das Argument zu speichern.

9. Klicken Sie auf **Argument erstellen**.

10. Typ `Result` in die **Namen** Feld unter dem neu hinzugefügten `BookmarkName` Argument die Option **Out** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE**.

11. Klicken Sie auf **Argument erstellen**.

12. Typ `Text` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Zeichenfolge** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE** auf das Argument zu speichern.

     Diese drei Argumente werden an die entsprechenden Argumente der <xref:System.Activities.Statements.WriteLine>-Aktivität und `ReadInt`-Aktivität gebunden, die der `Prompt`-Aktivität in den folgenden Schritten hinzugefügt werden.

13. Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.

14. Ziehen Sie eine **Sequenz** Aktivität aus der **Ablaufsteuerung** im Abschnitt der **Toolbox** und legen ihn auf der **Aktivität hier ablegen** Bezeichnung der **Eingabeaufforderung** Aktivitäts-Designer.

    > [!TIP]
    > Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.

15. Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** im Abschnitt der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Bezeichnung der **Sequenz** Aktivität.

16. Binden der **Text** Argument der **WriteLine** Aktivität, um die **Text** Argument der **Eingabeaufforderung** Aktivität durch Eingabe `Text` in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** im Feld der **Eigenschaften** Fenster, und drücken Sie dann die **Registerkarte** -Taste zwei Mal. Dadurch wird das Fenster mit den IntelliSense-Listenmembern geschlossen und der Eigenschaftswert gespeichert, indem die Auswahl der Eigenschaft aufgehoben wird. Diese Eigenschaft kann auch festgelegt werden, indem Sie eingeben `Text` in die **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld in der Aktivität selbst.

    > [!TIP]
    > Wenn die **Fenster "Eigenschaften"** als nicht angezeigt, aktivieren **Fenster "Eigenschaften"** aus der **Ansicht** Menü.

17. Ziehen Sie eine **ReadInt** Aktivität aus der **NumberGuessWorkflowActivities** Teil der **Toolbox** und legen Sie sie in der **Sequenz** -Aktivität, folgt die **WriteLine** Aktivität.

18. Binden der **BookmarkName** Argument der **ReadInt** Aktivität, um die **BookmarkName** Argument der **Eingabeaufforderung** Aktivität durch Eingabe von `BookmarkName` in die **VB-Ausdruck eingeben** Feld rechts neben der **BookmarkName** -Argument in der **Fenster "Eigenschaften"**, und drücken Sie dann die **Registerkarte** Schlüssel doppelt so groß wie das IntelliSense-Liste-Member-Fenster zu schließen und speichern Sie die Eigenschaft.

19. Binden der **Ergebnis** Argument der **ReadInt** Aktivität, um die **Ergebnis** Argument der **Eingabeaufforderung** Aktivität durch Eingabe `Result` in der **VB-Ausdruck eingeben** Feld rechts neben der **Ergebnis** -Argument in der **Fenster "Eigenschaften"**, und drücken Sie dann die **Registerkarte** zweimal-Taste.

20. Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen der Projektmappe.

## <a name="next-steps"></a>Nächste Schritte

Anweisungen zum Erstellen eines Workflows mit den Aktivitäten besteht, finden Sie im nächsten Schritt im Tutorial [Vorgehensweise: Erstellen eines Workflows](how-to-create-a-workflow.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Entwerfen und Implementieren von benutzerdefinierten Aktivitäten](designing-and-implementing-custom-activities.md)
- [Tutorial mit ersten Schritten](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen eines Workflows](how-to-create-a-workflow.md)
- [Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
