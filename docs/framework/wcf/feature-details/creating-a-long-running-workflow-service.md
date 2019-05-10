---
title: Erstellen eines Workflowdiensts mit langer Ausführungszeit
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 10a2c568f14c3f3c1818fd8b3240279b798777b8
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063796"
---
# <a name="creating-a-long-running-workflow-service"></a>Erstellen eines Workflowdiensts mit langer Ausführungszeit
In diesem Thema wird beschrieben, wie ein Workflowdienst mit langer Laufzeit erstellt wird. Workflowdienste mit langer Laufzeit können über einen sehr großen Zeitraum hinweg ausgeführt werden. Währenddessen kann der Workflow in den Leerlauf wechseln und auf weitere Informationen warten. In diesem Fall wird der Workflow in einer SQL-Datenbank beibehalten und aus dem Arbeitsspeicher entfernt. Wenn weitere Informationen für die Workflowinstanz verfügbar sind, wird diese wieder in den Arbeitsspeicher geladen, und die Ausführung wird fortgesetzt.  In diesem Szenario implementieren Sie ein stark vereinfachtes Bestellsystem.  Zunächst wird eine Nachricht vom Client an den Workflow gesendet, um die Bestellung zu beginnen. Die Bestell-ID wird an den Client zurückgegeben. Der Workflowdienst wartet nun auf eine weitere Nachricht vom Client, wechselt in den Leerlauf und wird in der SQL-Datenbank beibehalten.  Wenn die nächste Nachricht vom Client mit der Bestellung eines Artikels empfangen wird, wird der Workflowdienst wieder in den Arbeitsspeicher geladen, und die Bestellung wird abschließend bearbeitet. In diesem Codebeispiel wird eine Zeichenfolge zurückgegeben, die angibt, dass der Artikel der Bestellung hinzugefügt wurde. Das Codebeispiel ist nicht als reale Anwendung der Technologie gedacht. Es soll vielmehr auf einfache Weise einen Workflowdienst mit langer Laufzeit veranschaulichen. In diesem Thema wird davon ausgegangen, dass Sie wissen, wie Visual Studio 2012-Projekte und Projektmappen zu erstellen.

## <a name="prerequisites"></a>Vorraussetzungen
 Sie müssen folgende Software installiert haben, um diese exemplarische Vorgehensweise verwenden zu können:

1. Microsoft SQL Server 2008

2. Visual Studio 2012

3. Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4. Sie sind mit WCF und Visual Studio 2012 vertraut und wissen, wie Sie Projekte und Projektmappen erstellt.

### <a name="to-setup-the-sql-database"></a>So richten Sie die SQL-Datenbank ein

1. Damit Workflowdienstinstanzen beibehalten werden können, muss Microsoft SQL Server installiert sein, und Sie müssen eine Datenbank konfiguriert haben, in der die beibehaltenen Workflowinstanzen gespeichert werden können. Führen Microsoft SQL Management Studio, indem Sie auf die **starten** Schaltfläche auswählen **Programme**, **Microsoft SQL Server 2008**, und **Microsoft SQL Management Studio**.

2. Klicken Sie auf die **Connect** Schaltfläche zur Anmeldung beim SQL Server-Instanz

3. Klicken Sie mit der rechten Maustaste auf **Datenbanken** in der Strukturansicht und **neue Datenbank...** Erstellen Sie eine neue Datenbank namens `SQLPersistenceStore`.

4. Führen Sie die Skriptdatei SqlWorkflowInstanceStoreSchema.sql unter C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en in der SQLPersistenceStore-Datenbank aus, um die erforderlichen Datenbankschemas einzurichten.

5. Führen Sie die Skriptdatei SqlWorkflowInstanceStoreLogic.sql unter C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en in der SQLPersistenceStore-Datenbank aus, um die erforderliche Datenbanklogik einzurichten.

### <a name="to-create-the-web-hosted-workflow-service"></a>So erstellen Sie den im Internet gehosteten Workflowdienst

1. Erstellen Sie eine leere Projektmappe mit Visual Studio 2012, nennen Sie es `OrderProcessing`.

2. Fügen Sie der Projektmappe ein neues Projekt für eine WCF-Workflowdienstanwendung mit dem Namen `OrderService` hinzu.

3. Wählen Sie im Eigenschaftendialogfeld Projekts, das **Web** Registerkarte.

    1. Klicken Sie unter **Startaktion** wählen **bestimmte Seite** , und geben Sie `Service1.xamlx`.

         ![Workflow-Webeigenschaften](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "im Web gehosteten Workflow-Dienst - Option für bestimmte Seite erstellen")

    2. Klicken Sie unter **Server** wählen **lokalen IIS-Webserver verwenden**.

         ![Lokale Webservereinstellungen](./media/creating-a-long-running-workflow-service/use-local-web-server.png "erstellen Sie im Web gehosteten Workflow-Dienst - Option des lokalen IIS-Webserver verwenden")

        > [!WARNING]
        >  Sie müssen Visual Studio 2012 ausführen, im Administratormodus für diese Einstellung vorzunehmen.

         Mit diesen beiden Schritten wird das Workflowdienstprojekt konfiguriert, das von IIS gehostet werden soll.

4. Öffnen Sie `Service1.xamlx` ist dies nicht bereits geöffnet ist, und löschen Sie die vorhandenen **ReceiveRequest** und **SendResponse** Aktivitäten.

5. Wählen Sie die **sequenzieller Dienst** -Aktivität, und klicken Sie auf die **Variablen** verknüpfen, und fügen Sie die Variablen, die in der folgenden Abbildung dargestellt. Dadurch werden einige Variablen hinzugefügt, die im weiteren Verlauf in diesem Workflow verwendet werden.

    > [!NOTE]
    >  Wenn CorrelationHandle nicht in der Dropdown-Liste der Variablentyp ist, wählen Sie **nach Typen suchen** aus der Dropdownliste aus. Geben Sie CorrelationHandle im der **Typnamen** Feld, wählen Sie CorrelationHandle aus dem Listenfeld aus, und klicken Sie auf **OK**.

     ![Fügen Sie Variablen](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Variablen an die Aktivität sequenzieller Dienst hinzufügen.")

6. Drag & drop eine **ReceiveAndSendReply** Aktivitätsvorlage in der **sequenzieller Dienst** Aktivität. Diese Gruppe von Aktivitäten empfängt eine Nachricht von einem Client und sendet eine Antwort.

    1. Wählen Sie die **Receive** Aktivität, und legen die Eigenschaften, die in der folgenden Abbildung hervorgehoben.

         ![Legen Sie Eigenschaften der Aktivität](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "die Receive-Aktivitätseigenschaften festgelegt.")

         Mit der DisplayName-Eigenschaft wird der angezeigte Name für die Receive-Aktivität im Designer festgelegt. Mit der ServiceContractName-Eigenschaft und der OperationName-Eigenschaft wird der Name des Dienstvertrags und des Vorgangs angegeben, die von der Receive-Aktivität implementiert werden. Weitere Informationen zur Verwendung von Verträgen in Workflowdiensten finden Sie unter [mithilfe von Verträgen im Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).

    2. Klicken Sie auf die **definieren...**  -link in der **ReceiveStartOrder** Aktivität und Festlegen der Eigenschaften, die in der folgenden Abbildung dargestellt.  Beachten Sie, dass die **Parameter** Optionsfeld ausgewählt ist, einen Parameter namens `p_customerName` gebunden ist, um die `customerName` Variable. Konfiguriert die **Receive** Aktivität, um einige Daten empfangen und diese Daten auf lokale Variablen zu binden.

         ![Festlegen der Daten, die von der Receive-Aktivität empfangenen](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "legen die Eigenschaften für die von der Receive-Aktivität empfangenen Daten.")

    3. Wählen Sie die **SendReplyToReceive** Aktivität, und legen die hervorgehobene Eigenschaft, die in der folgenden Abbildung dargestellt.

         ![Festlegen der Eigenschaften der SendReply-Aktivität](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4. Klicken Sie auf die **definieren...**  -link in der **SendReplyToStartOrder** Aktivität und Festlegen der Eigenschaften, die in der folgenden Abbildung dargestellt. Beachten Sie, dass die **Parameter** Optionsfeld ausgewählt ist und der Parameter `p_orderId` gebunden ist, um die `orderId` Variable. Mit dieser Einstellung wird festgelegt, dass von der SendReplyToStartOrder-Aktivität ein Wert vom Typ Zeichenfolge an den Aufrufer zurückgegeben wird.

         ![Konfigurieren der SendReply-aktivitätsinhaltsdaten](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Konfigurieren der Einstellung für SetReplyToStartOrder-Aktivität.")

    5. Drag & drop eine zuweisungsaktivität zwischen der **Receive** und **"SendReply"** Aktivitäten und die Eigenschaften festlegen, wie in der folgenden Abbildung gezeigt:

         ![Hinzufügen einer zuweisungsaktivität](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "hinzufügen eine zuweisungsaktivität.")

         Dadurch wird eine neue Bestell-ID erstellt, und der Wert wird in der orderId-Variablen platziert.

    6. Wählen Sie die **ReplyToStartOrder** Aktivität. Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungspunkten, für die **CorrelationInitializers**. Wählen Sie die **Initialisierer hinzufügen** verknüpfen, geben Sie `orderIdHandle` im initialisierertextfeld ein, wählen Sie abfragekorrelationsinitialisierer für den Korrelationstyp, und wählen Sie im Dropdownfeld XPATH-Abfragen "P_orderId". Diese Einstellungen sind in der folgenden Abbildung dargestellt. Klicken Sie auf **OK**.  Dadurch wird eine Korrelation zwischen dem Client und dieser Instanz des Workflowdiensts initialisiert. Wenn eine Nachricht mit dieser Bestell-ID empfangen wird, wird sie an diese Instanz des Workflowdiensts weitergeleitet.

         ![Hinzufügen eines korrelationsinitialisierers](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "hinzufügen ein korrelationsinitialisierers.")

7. Drag & drop ein weiteres **ReceiveAndSendReply** Aktivität bis zum Ende des Workflows (außerhalb der **Sequenz** , enthält die erste **Receive** und  **"SendReply"** Aktivitäten). Dadurch wird die zweite Meldung empfangen, die vom Client gesendet wurde, und beantwortet.

    1. Wählen Sie die **Sequenz** , enthält die neu hinzugefügte **Receive** und **"SendReply"** Aktivitäten, und klicken Sie auf die **Variablen** Schaltfläche. Fügen Sie die in der folgenden Abbildung hervorgehobene Variable hinzu:

         ![Hinzufügen neuer Variablen](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "fügen Sie die Element-ID-Variable.")
         
         Fügen Sie auch `orderResult` als **Zeichenfolge** in die `Sequence` Bereich.

    2. Wählen Sie die **Receive** Aktivität und Festlegen der Eigenschaften, die in der folgenden Abbildung gezeigt:

         ![Legen Sie die Receive-Aktivitätseigenschaften](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "legen Sie die Eigenschaften der Receive-Aktivitäten.")
         
         > [!NOTE]
         >  Vergessen Sie nicht so ändern Sie **ServiceContractName** Feld `../IAddItem`.

    3. Klicken Sie auf die **definieren...**  -link in der **ReceiveAddItem** Aktivität und fügen Sie die Parameter in der folgenden Abbildung gezeigt: Dadurch wird die Receive-Aktivität akzeptiert zwei Parameter: die Bestell-ID und die ID des zu sortierenden Elements konfiguriert.

         ![Angeben von Parametern für den zweiten Empfang](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "konfigurieren Sie die Receive-Aktivität, um zwei Parameter erhalten.")

    4. Klicken Sie auf die **CorrelateOn** mit den Auslassungszeichen und geben Sie `orderIdHandle`. Klicken Sie unter **XPath-Abfragen**, klicken Sie auf den Dropdownpfeil, und wählen Sie `p_orderId`. Dadurch wird die Korrelation für die zweite Receive-Aktivität konfiguriert. Weitere Informationen zu Korrelationen finden Sie unter [Korrelation](../../../../docs/framework/wcf/feature-details/correlation.md).

         ![Festlegen der Eigenschaft "CorrelatesOn"](./media/creating-a-long-running-workflow-service/correlateson-setting.png "legen Sie die Eigenschaft \"CorrelatesOn\".")

    5. Drag & drop eine **Wenn** Aktivität unmittelbar nach der **ReceiveAddItem** Aktivität. Diese Aktivität verhält sich analog zu einer Anweisung.

        1. Legen Sie die **Bedingung** Eigenschaft `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2. Drag & drop eine **zuweisen** Aktivität in der **klicken Sie dann** und eine andere in der **Else** Abschnitt legen Sie die Eigenschaften von der **zuweisen** Aktivitäten, wie in der folgenden Abbildung dargestellt.

             ![Erneute Zuordnen des Ergebnisses des Dienstaufrufs](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "weisen Sie das Ergebnis des Dienstaufrufs.")

             Wenn die Bedingung `true` der **dann** Abschnitt ausgeführt wird. Wenn die Bedingung `false` der **Else** Abschnitt ausgeführt wird.

        3. Wählen Sie die **SendReplyToReceive** Aktivität, und legen die **"DisplayName"** Eigenschaft, die in der folgenden Abbildung dargestellt.

             ![Festlegen der SendReply-Aktivitätseigenschaften](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "legen Sie die Eigenschaft der SendReply-Aktivität.")

        4. Klicken Sie auf die **definieren...**  -link in der **SetReplyToAddItem** Aktivität und konfigurieren Sie es in der folgenden Abbildung dargestellt. Konfiguriert die **SendReplyToAddItem** Aktivität zum Zurückgeben des Werts in der `orderResult` Variable.

             ![Einrichten der Datenbindung für die SendReply-Aktivität](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "-Eigenschaft für SendReplyToAddItem Aktivität festgelegt.")

8. Öffnen Sie die Datei "Web.config", und fügen Sie die folgenden Elemente in der \<Verhalten > Abschnitt aus, um die Workflowpersistenz zu aktivieren.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  Ersetzen Sie den Namen des Hosts und der SQL Server-Instanz aus dem vorherigen Codeausschnitt.

9. Erstellen Sie die Projektmappe.

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>So erstellen Sie eine Clientanwendung zum Aufrufen des Workflowdiensts

1. Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `OrderClient` hinzu.

2. Fügen Sie dem `OrderClient`-Projekt Verweise auf die folgenden Assemblys hinzu:

    1. System.ServiceModel.dll

    2. System.ServiceModel.Activities.dll

3. Fügen Sie dem Workflowdienst einen Dienstverweis hinzu, und geben Sie `OrderService` als Namespace an.

4. Fügen Sie der `Main()`-Methode des Clientprojekts den folgenden Code hinzu:

    ```
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5. Erstellen Sie die Projektmappe, und führen Sie die `OrderClient`-Anwendung aus. Der folgende Text wird vom Client angezeigt:

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. Um sicherzustellen, dass der Workflowdienst beibehalten wurde, starten Sie SQL Server Management Studio, indem Sie die **starten** im Menü auswählen **Programme**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.

    1. Erweitern Sie im linken Bereich, **Datenbanken**, **SQLPersistenceStore**, **Ansichten** , und klicken Sie mit der rechten Maustaste auf **System.Activities.DurableInstancing.Instances**  , und wählen Sie **oberste 1000 Zeilen auswählen**. In der **Ergebnisse** Bereich sollte mindestens eine Instanz aufgeführt. Es kann sein, dass auch Instanzen früherer Ausführungen aufgelistet sind, wenn Fehler bei der Ausführung aufgetreten sind. Sie können vorhandene Zeilen löschen, mit der rechten Maustaste **System.Activities.DurableInstancing.Instances** und **oberste 200 Zeilen bearbeiten**, drücken die **Execute** Schaltfläche Wählen alle Zeilen im Ergebnisbereich, und wählen **löschen**.  Um zu überprüfen, ob in der Datenbank die Instanz angezeigt wird, die von Ihrer Anwendung erstellt wurde, können Sie überprüfen, ob die Ansicht für Instanzen vor Ausführung des Clients leer ist. Führen Sie die Abfrage (Oberste 1000 Zeilen auswählen) erneut aus, sobald der Client ausgeführt wird, und überprüfen Sie, ob eine neue Instanz hinzugefügt wurde.

7. Drücken Sie die EINGABETASTE, um die Nachricht zum Hinzufügen des Artikels an den Workflowdienst zu senden. Der folgende Text wird vom Client angezeigt:

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
