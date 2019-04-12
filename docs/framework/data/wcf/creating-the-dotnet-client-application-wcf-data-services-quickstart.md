---
title: Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: dfc08d4623f124a41412907f5a118e8d9ee7833d
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517771"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="f3c8c-102">Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)</span><span class="sxs-lookup"><span data-stu-id="f3c8c-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="f3c8c-103">Dies ist die letzte Aufgabe des Schnellstarts WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="f3c8c-104">In dieser Aufgabe wird eine Konsolenanwendung mit der Lösung hinzufügen, fügen Sie einen Verweis auf die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in dieser neuen Clientanwendung und Zugriff auf den OData-feed von der Clientanwendung mit den generierten clientdatendienstklassen und Clientbibliotheken .</span><span class="sxs-lookup"><span data-stu-id="f3c8c-104">In this task, you will add a console application to the solution, add a reference to the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c8c-105">Eine .NET Framework-basierte Clientanwendung ist für den Zugriff auf einen Datenfeed nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="f3c8c-106">Der Datendienst kann jede Anwendungskomponente zugegriffen werden, die einen OData-feed nutzt.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="f3c8c-107">Weitere Informationen finden Sie unter [Verwenden eines Datendiensts in einer Clientanwendung](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f3c8c-107">For more information, see [Using a Data Service in a Client Application](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="f3c8c-108">So erstellen Sie die Clientanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3c8c-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="f3c8c-109">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, klicken Sie auf **hinzufügen**, und klicken Sie dann auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="f3c8c-110">Wählen Sie im linken Bereich **installiert** > [**Visual C#**  oder **Visual Basic**] > **Windows Desktop**, und wählen Sie dann die  **WPF-App** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="f3c8c-111">Geben Sie `NorthwindClient` für den Projektnamen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="f3c8c-112">Öffnen Sie die Datei MainWindow.xaml, und ersetzen Sie den XAML-Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f3c8c-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="f3c8c-113">So fügen Sie dem Projekt einen Datendienstverweis hinzu</span><span class="sxs-lookup"><span data-stu-id="f3c8c-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="f3c8c-114">In **Projektmappen-Explorer**mit der rechten Maustaste auf das NorthwindClient-Projekt, klicken Sie auf **hinzufügen** > **Dienstverweis**, und klicken Sie dann auf **ermitteln** .</span><span class="sxs-lookup"><span data-stu-id="f3c8c-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="f3c8c-115">Dadurch wird der Northwind-Datendienst angezeigt, den Sie in der ersten Aufgabe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="f3c8c-116">In der **Namespace** Textfeld `Northwind`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="f3c8c-117">Dadurch wird dem Projekt, das die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte verwendeten Datenklassen enthält, eine neue Codedatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="f3c8c-118">Die Datenklassen werden im Namespace `NorthwindClient.Northwind` erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="f3c8c-119">So greifen Sie auf Datendienstdaten in der WPF-Anwendung zu</span><span class="sxs-lookup"><span data-stu-id="f3c8c-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="f3c8c-120">In **Projektmappen-Explorer** unter **NorthwindClient**mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="f3c8c-121">In der **Verweis hinzufügen** Dialogfeld klicken Sie auf die **.NET** , wählen Sie die System.Data.Services.Client.dll-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="f3c8c-122">In **Projektmappen-Explorer** unter **NorthwindClient**, öffnen Sie die Codepage für die Datei "MainWindow.xaml", und fügen Sie die folgenden `using` Anweisung (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f3c8c-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

3. <span data-ttu-id="f3c8c-123">Fügen Sie den folgenden Code ein, der diesen Datendienst abfragt und das Ergebnis an eine <xref:System.Data.Services.Client.DataServiceCollection%601> in der `MainWindow`-Klasse bindet:</span><span class="sxs-lookup"><span data-stu-id="f3c8c-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3c8c-124">Sie müssen den Hostnamen `localhost:12345` durch den Server und den Anschluss ersetzen, der die Instanz des Northwind-Datendiensts hostet.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

4. <span data-ttu-id="f3c8c-125">Fügen Sie den folgenden Code zum Speichern von Änderungen in der `MainWindow`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="f3c8c-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="f3c8c-126">So erstellen Sie die NorthwindClient-Anwendung und führen sie aus</span><span class="sxs-lookup"><span data-stu-id="f3c8c-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="f3c8c-127">In **Projektmappen-Explorer**mit der rechten Maustaste auf das NorthwindClient-Projekt, und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="f3c8c-128">Drücken Sie **F5** zum Starten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="f3c8c-129">Die Projektmappe wird erstellt und die Clientanwendung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="f3c8c-130">Daten werden vom Dienst angefordert und in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="f3c8c-131">Bearbeiten eines Werts in der **Menge** Spalte das Datenraster, und klicken Sie dann auf **speichern**.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="f3c8c-132">Die Änderungen werden im Datendienst gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3c8c-133">In dieser Version der Anwendung NorthwindClient wird das Hinzufügen und Löschen von Entitäten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3c8c-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f3c8c-134">Next Steps</span></span>

<span data-ttu-id="f3c8c-135">Sie haben erfolgreich die Clientanwendung erstellt, die im Beispiel greift auf die, das Northwind-OData-feed.</span><span class="sxs-lookup"><span data-stu-id="f3c8c-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="f3c8c-136">Sie haben auch die WCF Data Services-Schnellstart abgeschlossen!</span><span class="sxs-lookup"><span data-stu-id="f3c8c-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="f3c8c-137">Für Weitere Informationen zum Zugreifen auf einen OData-von Feed einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Anwendung finden Sie unter [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span><span class="sxs-lookup"><span data-stu-id="f3c8c-137">For more information about accessing an OData feed from a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, see [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3c8c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3c8c-138">See also</span></span>

- [<span data-ttu-id="f3c8c-139">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="f3c8c-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="f3c8c-140">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f3c8c-140">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
