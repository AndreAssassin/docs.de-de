---
title: 'Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: f4c34252f7d92985dac94663c85d3cca0dc58ab3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655130"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a>Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit. Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Für die Zwecke dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die von gespeicherten Prozeduren in der Northwind-Beispieldatenbank zugeordnet wurden: CustOrdersDetail und CustOrderHist. Die Zuordnung tritt auf, wenn Sie das SQLMetal-Befehlszeilentool ausführen, um eine C#-Datei zu generieren. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.  
  
 Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Entwickler, die mit Visual Studio können auch die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] Funktionalität einer gespeicherten Prozedur zu implementieren. Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
- Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest7") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
- Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest7.  
  
- Eine von der Datenbank Northwind generierte C#-Codedatei.  
  
     Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
- Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.  
  
- Hinzufügen der System.Data.Linq-Assembly zum Projekt  
  
- Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
- Erstellen einer Verbindung mit der Datenbank  
  
- Einrichten der Benutzeroberfläche.  
  
- Ausführen und Testen der Anwendung.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1. Visual Studio **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.  
  
2. In der **Projekttypen** im Bereich der **neues Projekt** Dialogfeld klicken Sie auf **Visual C#** .  
  
3. Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
4. In der **Namen** geben **SprocOnlyApp**.  
  
5. In der **Speicherort** Vergewissern Sie sich, in der Sie die Projektdateien speichern möchten.  
  
6. Klicken Sie auf **OK**.  
  
     Der Windows Forms Designer wird geöffnet.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Hinzufügen des LINQ to SQL-Assemblyverweises  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten. Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:  
  
#### <a name="to-add-systemdatalinqdll"></a>So fügen Sie die Datei System.Data.Linq.dll hinzu  
  
1. In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2. In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1. Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
2. In der **vorhandenes Element hinzufügen** Dialogfeld zu c:\linqtest7\northwind.cs verschieben, und klicken Sie dann auf **hinzufügen**.  
  
     Die Datei northwind.cs wird dem Projekt hinzugefügt.  
  
## <a name="creating-a-database-connection"></a>Erstellen von Datenbankverbindungen  
 In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind. Diese exemplarische Vorgehensweise verwendet "c:\linqtest7\northwnd.mdf" als Pfad.  
  
#### <a name="to-create-the-database-connection"></a>So erstellen Sie die Datenbankverbindung  
  
1. In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.cs"**, und klicken Sie dann auf **Ansichtscode**.  
  
2. Geben Sie den folgenden Code in die `Form1`-Klasse ein:  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a>Einrichten der Benutzeroberfläche  
 In dieser Aufgabe richten Sie eine Benutzeroberfläche ein, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können. In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.  
  
#### <a name="to-set-up-the-user-interface"></a>So richten Sie die Benutzeroberfläche ein  
  
1. Wechseln Sie zurück zur der Windows Forms-Designer (**Form1.cs]**).  
  
2. Klicken Sie im Menü **Ansicht** auf **Toolbox**.  
  
     Die Toolbox wird geöffnet.  
  
    > [!NOTE]
    >  Klicken Sie auf die **automatisch im Hintergrund** PIN, die Toolbox geöffnet zu lassen, während der folgenden Schritte in diesem Abschnitt.  
  
3. Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen aus der Toolbox auf **Form1**.  
  
     Ordnen Sie die Steuerelemente wie in der Abbildung an. Erweitern Sie **Form1** , damit die Steuerelemente platziert.  
  
4. Mit der rechten Maustaste **label1**, und klicken Sie dann auf **Eigenschaften**.  
  
5. Ändern der **Text** Eigenschaft **label1** zu **Enter OrderID:**.  
  
6. Für die gleiche Weise **label2**, ändern Sie die **Text** Eigenschaft aus **label2** zu **Enter CustomerID:**.  
  
7. Ändern Sie in die gleiche Weise die **Text** -Eigenschaft für **"Button1"** zu **Bestelldetails**.  
  
8. Ändern der **Text** -Eigenschaft für **button2** zu **Bestellverlauf**.  
  
     Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.  
  
#### <a name="to-handle-button-clicks"></a>Verarbeitung von Mausklicks auf die Schaltflächen  
  
1. Doppelklicken Sie auf **Bestelldetails** auf **Form1** um den button1-Ereignishandler im Code-Editor zu öffnen.  
  
2. Geben Sie den folgenden Code in den `button1`-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3. Doppelklicken Sie jetzt auf **button2** auf **Form1** zum Öffnen der `button2` Handler  
  
4. Geben Sie den folgenden Code in den `button2`-Ereignishandler ein.  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Nun können Sie die Anwendung testen. Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist. Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.  
  
#### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1. Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.  
  
     Form1 wird angezeigt.  
  
2. In der **Enter OrderID** geben `10249`, und klicken Sie dann auf **Bestelldetails**.  
  
     Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
3. In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.  
  
     Ein Meldungsfeld mit der Bestellhistorie für den Kunden ALFKI wird angezeigt.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
4. In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.  
  
     Die Meldung "Keine Ergebnisse" erscheint.  
  
     Klicken Sie auf **OK** um das Meldungsfeld zu schließen.  
  
5. Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.  
  
     Die Debugsitzung schließt.  
  
6. Wenn Sie mit dem Experimentieren fertig sind, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie können dieses Projekt mit einigen Änderungen erweitern. Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann. Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.  
  
## <a name="see-also"></a>Siehe auch

- [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
