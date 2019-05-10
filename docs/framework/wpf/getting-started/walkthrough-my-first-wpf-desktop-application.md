---
title: Erstellen einer WPF-Anwendung in Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: 9d0abd18b2242ab21e8a915caac1ff9e3216acd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617273"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="d8254-102">Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung</span><span class="sxs-lookup"><span data-stu-id="d8254-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="d8254-103">In diesem Artikel erfahren Sie, wie Sie eine Windows Presentation Foundation (WPF) desktop-Anwendung entwickeln, die die Elemente enthält, die für die meisten WPF-Anwendungen gelten: Extensible Application Markup Language (XAML) Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile.</span><span class="sxs-lookup"><span data-stu-id="d8254-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="d8254-104">Um die Anwendung zu entwickeln, verwenden Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8254-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="d8254-105">Diese exemplarische Vorgehensweise umfasst die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d8254-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="d8254-106">Verwenden Sie XAML zum Entwerfen der Darstellung der Benutzeroberfläche (UI) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d8254-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="d8254-107">Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8254-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="d8254-108">Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8254-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="d8254-109">Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout der Benutzeroberfläche die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8254-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="d8254-110">Stile für ein konsistentes Erscheinungsbild in der Benutzeroberfläche der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8254-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="d8254-111">Binden Sie die Benutzeroberfläche mit Daten füllen Sie die Benutzeroberfläche von Daten und die Daten und die Benutzeroberfläche, die synchronisiert zu halten.</span><span class="sxs-lookup"><span data-stu-id="d8254-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="d8254-112">Am Ende dieser exemplarischen Vorgehensweise werden Sie eine eigenständigen Windows-Anwendung erstellt haben, die Benutzer spesenabrechnungen für bestimmte Personen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="d8254-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="d8254-113">Die Anwendung besteht aus der WPF-Seiten, die in einem Fenster im Browserstil gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="d8254-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="d8254-114">Der Beispielcode, der verwendet wird, in dieser exemplarischen Vorgehensweise ist für Visual Basic verfügbar und C# am [Exemplarische Vorgehensweise WPF-App-Beispielcodes](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="d8254-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="d8254-115">Sie können die Codesprache des Beispielcodes zwischen umschalten C# und Visual Basic mithilfe der **\< />** Dropdownliste oben rechts auf der in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="d8254-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8254-116">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8254-116">Prerequisites</span></span>

- <span data-ttu-id="d8254-117">Visual Studio 2017 oder höher</span><span class="sxs-lookup"><span data-stu-id="d8254-117">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="d8254-118">Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d8254-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="d8254-119">In diesem Artikel wird Visual Studio-2019 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8254-119">This article uses Visual Studio 2019.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="d8254-120">Erstellen des Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="d8254-120">Create the application project</span></span>

<span data-ttu-id="d8254-121">Der erste Schritt ist die Erstellung von Infrastruktur der Anwendung, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="d8254-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="d8254-122">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="d8254-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="d8254-123">Öffnen Sie Visual Studio, und wählen Sie **Datei** > **neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d8254-123">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="d8254-124">Die **Erstellen eines neuen Projekts** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8254-124">The **Create a new project** dialog opens.</span></span>

      ![Erstellen Sie ein Dialogfeld "Neues Projekt"](./media/gettingstartedfigure0a.png)

   2. <span data-ttu-id="d8254-126">In der **Sprache** Dropdownliste, wählen Sie entweder **C#** oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="d8254-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="d8254-127">Wählen Sie die **WPF-App ((.NET Framework)** Vorlage, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d8254-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
    
   4. <span data-ttu-id="d8254-128">Wählen Sie **Erstellen eines neuen Projekts**.</span><span class="sxs-lookup"><span data-stu-id="d8254-128">Select **Create a new project**.</span></span>

      <span data-ttu-id="d8254-129">Die **Konfigurieren eines neues Projekts** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8254-129">The **Configure a new project** dialog opens.</span></span>

      ![Konfigurieren Sie ein Dialogfeld "Neues Projekt"](./media/gettingstartedfigure0c.png)

   5. <span data-ttu-id="d8254-131">Geben Sie den Namen des Projekts **`ExpenseIt`** und wählen Sie dann **erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d8254-131">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      <span data-ttu-id="d8254-132">Visual Studio erstellt das Projekt und öffnet den Designer für das standardanwendungsfenster namens **"MainWindow.xaml"**.</span><span class="sxs-lookup"><span data-stu-id="d8254-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="d8254-133">Open *"Application.xaml"* (Visual Basic) oder *"App.xaml"* (c#).</span><span class="sxs-lookup"><span data-stu-id="d8254-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="d8254-134">Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungsressourcen.</span><span class="sxs-lookup"><span data-stu-id="d8254-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="d8254-135">Sie verwenden diese Datei auch in diesem Fall an der Benutzeroberfläche *"MainWindow.xaml"*, das automatisch wird angezeigt, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d8254-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="d8254-136">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="d8254-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="d8254-137">Und wie der folgende in C#:</span><span class="sxs-lookup"><span data-stu-id="d8254-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="d8254-138">Open *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="d8254-139">Dieser XAML-Datei ist das Hauptfenster der Anwendung und zeigt erstellten Inhalt auf Seiten.</span><span class="sxs-lookup"><span data-stu-id="d8254-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="d8254-140">Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters wie Titel, Größe oder Symbol, und behandelt Ereignisse wie schließen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="d8254-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="d8254-141">Ändern der <xref:System.Windows.Window> Element eine <xref:System.Windows.Navigation.NavigationWindow>, wie in den folgenden XAML dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d8254-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="d8254-142">Diese app navigiert zu anderem Inhalt, abhängig von der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="d8254-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="d8254-143">Deshalb ist die Main <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d8254-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="d8254-144"><xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften des <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="d8254-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="d8254-145">Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d8254-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="d8254-146">Weitere Informationen finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="d8254-147">Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.</span><span class="sxs-lookup"><span data-stu-id="d8254-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="d8254-148">Ändern Sie die folgenden Eigenschaften in der XAML-Code für die <xref:System.Windows.Navigation.NavigationWindow> Element:</span><span class="sxs-lookup"><span data-stu-id="d8254-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="d8254-149">Legen Sie die <xref:System.Windows.Window.Title%2A> Eigenschaft "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="d8254-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="d8254-150">Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft auf 350 Pixel.</span><span class="sxs-lookup"><span data-stu-id="d8254-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="d8254-151">Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel.</span><span class="sxs-lookup"><span data-stu-id="d8254-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="d8254-152">Ihre XAML sieht wie folgt für Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d8254-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="d8254-153">Und wie folgt für C#:</span><span class="sxs-lookup"><span data-stu-id="d8254-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="d8254-154">Open *"MainWindow.Xaml.vb"* oder *"MainWindow.Xaml.cs"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="d8254-155">Diese Datei ist eine Code-Behind-Datei Code zum Behandeln der Ereignisse, die im deklarierten mit *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="d8254-156">Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.</span><span class="sxs-lookup"><span data-stu-id="d8254-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="d8254-157">Bei Verwendung von C#, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d8254-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="d8254-158">(In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.) Ihre C# Code sollte jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="d8254-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="d8254-159">Hinzufügen von Dateien zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="d8254-159">Add files to the application</span></span>

<span data-ttu-id="d8254-160">In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8254-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="d8254-161">Fügen Sie dem Projekt eine neue Seite, und nennen Sie sie *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="d8254-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="d8254-162">In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.</span><span class="sxs-lookup"><span data-stu-id="d8254-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="d8254-163">In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="d8254-164">Geben Sie den Namen **`ExpenseItHome`**, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d8254-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="d8254-165">Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d8254-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="d8254-166">Es zeigt eine Liste der Personen an, wählen aus, um eine Spesenabrechnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8254-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="d8254-167">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="d8254-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="d8254-168">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="d8254-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="d8254-169">Legen Sie die `DesignHeight` und `DesignWidth` Elementwerte auf 300 Pixel.</span><span class="sxs-lookup"><span data-stu-id="d8254-169">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="d8254-170">Die XAML sieht nun folgendermaßen für Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d8254-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="d8254-171">Und wie folgt für C#:</span><span class="sxs-lookup"><span data-stu-id="d8254-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="d8254-172">Open *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="d8254-173">Hinzufügen einer <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft, um die <xref:System.Windows.Navigation.NavigationWindow> Element, und legen Sie sie auf "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="d8254-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="d8254-174">Hiermit *`ExpenseItHome.xaml`* werden von der ersten Seite geöffnet werden soll, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d8254-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="d8254-175">Beispiel für XAML in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d8254-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="d8254-176">Und in C#:</span><span class="sxs-lookup"><span data-stu-id="d8254-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="d8254-177">Sie können auch Festlegen der **Quelle** -Eigenschaft in der **Sonstiges** Kategorie der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="d8254-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Source-Eigenschaft im Fenster "Eigenschaften"](./media/properties-source.png)

1. <span data-ttu-id="d8254-179">Hinzufügen einer anderen neuen WPF-Seite auf das Projekt, und nennen Sie sie *"ExpenseReportPage.xaml"*::</span><span class="sxs-lookup"><span data-stu-id="d8254-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="d8254-180">In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.</span><span class="sxs-lookup"><span data-stu-id="d8254-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="d8254-181">In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Seite (WPF)** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8254-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="d8254-182">Geben Sie den Namen **ExpenseReportPage**, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d8254-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="d8254-183">Auf dieser Seite zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite.</span><span class="sxs-lookup"><span data-stu-id="d8254-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="d8254-184">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d8254-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="d8254-185">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="d8254-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="d8254-186">Legen Sie die `DesignHeight` und `DesignWidth` Elementwerte auf 300 Pixel.</span><span class="sxs-lookup"><span data-stu-id="d8254-186">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="d8254-187">*"ExpenseReportPage.xaml"* jetzt sieht wie in Visual Basic die folgenden:</span><span class="sxs-lookup"><span data-stu-id="d8254-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="d8254-188">Und wie der folgende in C#:</span><span class="sxs-lookup"><span data-stu-id="d8254-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="d8254-189">Open *"ExpenseItHome.Xaml.vb"* und *ExpenseReportPage.xaml.vb*, oder *"ExpenseItHome.Xaml.cs"* und *"ExpenseReportPage.Xaml.cs"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="d8254-190">Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch die *CodeBehind* Datei.</span><span class="sxs-lookup"><span data-stu-id="d8254-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="d8254-191">Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="d8254-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="d8254-192">Der Code sollte aussehen wie folgt für **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="d8254-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="d8254-193">Und wie folgt für **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="d8254-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="d8254-194">Fügen Sie ein Bild mit dem Namen *watermark.png* zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8254-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="d8254-195">Sie können Ihr eigenes Image erstellen, kopieren Sie die Datei aus dem Beispielcode oder erhalten sie [hier](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="d8254-195">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="d8254-196">Mit der rechten Maustaste auf den Projektknoten, und wählen Sie **hinzufügen** > **vorhandenes Element**, oder drücken Sie **UMSCHALT**+**Alt** + **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d8254-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="d8254-197">In der **vorhandenes Element hinzufügen** Dialogfeld legen Sie den Dateifilter entweder **alle Dateien** oder **Bilddateien**, navigieren Sie zu dem Image-Datei, die Sie verwenden möchten, und wählen Sie dann **hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="d8254-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="d8254-198">Erstellen eines Builds und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="d8254-198">Build and run the application</span></span>

1. <span data-ttu-id="d8254-199">Zum Erstellen und die Anwendung auszuführen, drücken Sie die **F5** oder wählen Sie **Debuggen starten** aus der **Debuggen** Menü.</span><span class="sxs-lookup"><span data-stu-id="d8254-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="d8254-200">Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:</span><span class="sxs-lookup"><span data-stu-id="d8254-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Bildschirmabbildung für ExpenseIt-Beispiel](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="d8254-202">Schließen Sie die Anwendung zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d8254-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="d8254-203">Erstellen Sie das layout</span><span class="sxs-lookup"><span data-stu-id="d8254-203">Create the layout</span></span>

<span data-ttu-id="d8254-204">Layout bietet die Möglichkeit, Elemente der Benutzeroberfläche zu platzieren und verwaltet auch die Größe und Position dieser Elemente beim Ändern der Größe einer Benutzeroberflächenautomatisierungs.</span><span class="sxs-lookup"><span data-stu-id="d8254-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="d8254-205">In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:</span><span class="sxs-lookup"><span data-stu-id="d8254-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="d8254-206"><xref:System.Windows.Controls.Canvas> : Definiert einen Bereich, in dem Sie explizit untergeordnete Elemente positionieren können mithilfe von Koordinaten, die relativ zur Canvas sind.</span><span class="sxs-lookup"><span data-stu-id="d8254-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="d8254-207"><xref:System.Windows.Controls.DockPanel> : Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.</span><span class="sxs-lookup"><span data-stu-id="d8254-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="d8254-208"><xref:System.Windows.Controls.Grid> : Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.</span><span class="sxs-lookup"><span data-stu-id="d8254-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="d8254-209"><xref:System.Windows.Controls.StackPanel> : Ordnet untergeordnete Elemente in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8254-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="d8254-210"><xref:System.Windows.Controls.VirtualizingStackPanel> -Ordnet die und virtualisiert Inhalt in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="d8254-211"><xref:System.Windows.Controls.WrapPanel> -Positionen untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds.</span><span class="sxs-lookup"><span data-stu-id="d8254-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="d8254-212">Die nachfolgende Sortierung erfolgt sequenziell von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d8254-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="d8254-213">Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Typ von Layout für die untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="d8254-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="d8254-214">`ExpenseIt` Seiten geändert werden können, und jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d8254-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="d8254-215">In diesem Beispiel die <xref:System.Windows.Controls.Grid> als Layoutelement für die Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8254-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="d8254-216">Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Übersicht über Panel](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="d8254-217">Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="d8254-218">In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Zeilendefinitionen zu den <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="d8254-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="d8254-219">In *`ExpenseItHome.xaml`* legen die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft für die <xref:System.Windows.Controls.Grid> Element auf "10,0,10,10", auf der linken, oberen, rechten und unteren Ränder entspricht:</span><span class="sxs-lookup"><span data-stu-id="d8254-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="d8254-220">Sie können auch Festlegen der **Rand** Werte in der **Eigenschaften** Fenster unter dem **Layout** Kategorie:</span><span class="sxs-lookup"><span data-stu-id="d8254-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Randwerte in Fenster "Eigenschaften"](./media/properties-margin.png)

2. <span data-ttu-id="d8254-222">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d8254-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="d8254-223">Die <xref:System.Windows.Controls.RowDefinition.Height%2A> zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A>, was bedeutet, dass die Größe der Zeilen basierend auf dem Inhalt in den Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d8254-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="d8254-224">Der Standardwert <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> größenanpassung, was bedeutet, dass die Zeilenhöhe eine gewichtete Proportion des verfügbaren Platzes ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="d8254-225">Wenn z. B. zwei Zeilen jeweils eine <xref:System.Windows.Controls.RowDefinition.Height%2A> von "\*", sie verfügen jeweils über eine Höhe von der Hälfte des verfügbaren Platzes ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="d8254-226">Ihre <xref:System.Windows.Controls.Grid> sollte nun dem folgenden XAML enthalten:</span><span class="sxs-lookup"><span data-stu-id="d8254-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="d8254-227">Hinzufügen von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d8254-227">Add controls</span></span>

<span data-ttu-id="d8254-228">In diesem Abschnitt Aktualisieren Sie die Homepage Benutzeroberfläche, um eine Liste der Personen, anzuzeigen, wählen Sie, in dem eine Person, die die Spesenabrechnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8254-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="d8254-229">Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d8254-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="d8254-230">Weitere Informationen finden Sie unter [Steuerelemente](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="d8254-231">Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente zu *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="d8254-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="d8254-232">Ein <xref:System.Windows.Controls.ListBox> (für die Liste der Personen).</span><span class="sxs-lookup"><span data-stu-id="d8254-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="d8254-233">Ein <xref:System.Windows.Controls.Label> (für den Listenheader).</span><span class="sxs-lookup"><span data-stu-id="d8254-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="d8254-234">Ein <xref:System.Windows.Controls.Button> (zum klicken, um die Spesenabrechnung für die Person anzuzeigen, die in der Liste ausgewählt ist).</span><span class="sxs-lookup"><span data-stu-id="d8254-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="d8254-235">Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> angefügte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d8254-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="d8254-236">Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="d8254-237">In *`ExpenseItHome.xaml`*, fügen Sie den folgenden XAML an einer beliebigen Stelle zwischen den <xref:System.Windows.Controls.Grid> Tags:</span><span class="sxs-lookup"><span data-stu-id="d8254-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="d8254-238">Sie können die Steuerelemente auch erstellen, ziehen sie aus der **Toolbox** Fenster in das Entwurfsfenster, und klicken Sie dann ihre Einstellungen der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="d8254-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="d8254-239">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8254-239">Build and run the application.</span></span>

    <span data-ttu-id="d8254-240">Die folgende Abbildung zeigt die Steuerelemente, die Sie erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="d8254-240">The following illustration shows the controls you created:</span></span>

    ![Bildschirmabbildung für ExpenseIt-Beispiel](./media/gettingstartedfigure2.png)

3. <span data-ttu-id="d8254-242">Schließen Sie die Anwendung zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d8254-242">Close the application to return to Visual Studio.</span></span>

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="d8254-243">Fügen Sie ein Image und einen Titel hinzu</span><span class="sxs-lookup"><span data-stu-id="d8254-243">Add an image and a title</span></span>

<span data-ttu-id="d8254-244">In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche der Homepage mit einem Bild und einem Seitentitel.</span><span class="sxs-lookup"><span data-stu-id="d8254-244">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="d8254-245">In *`ExpenseItHome.xaml`*, fügen Sie eine andere Spalte als die <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixel:</span><span class="sxs-lookup"><span data-stu-id="d8254-245">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="d8254-246">Hinzufügen zu einer anderen Zeile der <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, also insgesamt vier Zeilen:</span><span class="sxs-lookup"><span data-stu-id="d8254-246">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="d8254-247">Verschieben Sie die Steuerelemente in die zweite Spalte, durch Festlegen der <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> -Eigenschaft auf 1 in jedem der drei Steuerelemente (Rahmen, ListBox und Schaltfläche ").</span><span class="sxs-lookup"><span data-stu-id="d8254-247">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="d8254-248">Verschieben Sie jedes Steuerelement eine Zeile nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> Wert 1 für jedes der drei Steuerelemente (Rahmen, ListBox und Schaltfläche ") und Border-Elements.</span><span class="sxs-lookup"><span data-stu-id="d8254-248">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="d8254-249">Der XAML für die drei Steuerelemente sieht nun folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="d8254-249">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="d8254-250">Legen Sie die <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Eigenschaft, um die *watermark.png* Image-Datei, indem Sie den folgenden XAML an einer beliebigen Stelle zwischen Hinzufügen der `<Grid>` und `</Grid>` Tags:</span><span class="sxs-lookup"><span data-stu-id="d8254-250">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="d8254-251">Vor der <xref:System.Windows.Controls.Border> -Element, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="d8254-251">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="d8254-252">Diese Bezeichnung wird der Titel der Seite.</span><span class="sxs-lookup"><span data-stu-id="d8254-252">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="d8254-253">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8254-253">Build and run the application.</span></span>

<span data-ttu-id="d8254-254">Die folgende Abbildung zeigt die Ergebnisse von was Sie gerade hinzugefügt haben:</span><span class="sxs-lookup"><span data-stu-id="d8254-254">The following illustration shows the results of what you just added:</span></span>

![Bildschirmabbildung für ExpenseIt-Beispiel](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="d8254-256">Fügen Sie Code zum Verarbeiten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="d8254-256">Add code to handle events</span></span>

1. <span data-ttu-id="d8254-257">In *`ExpenseItHome.xaml`*, Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der <xref:System.Windows.Controls.Button> Element.</span><span class="sxs-lookup"><span data-stu-id="d8254-257">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="d8254-258">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines einfachen ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d8254-258">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="d8254-259">Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="d8254-259">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="d8254-260">Fügen Sie den folgenden Code der `ExpenseItHome` Klasse, um eine Schaltfläche hinzufügen-click-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="d8254-260">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="d8254-261">Der Ereignishandler öffnet die **ExpenseReportPage** Seite.</span><span class="sxs-lookup"><span data-stu-id="d8254-261">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="d8254-262">Erstellen der Benutzeroberfläche für ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="d8254-262">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="d8254-263">*"ExpenseReportPage.xaml"* zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite.</span><span class="sxs-lookup"><span data-stu-id="d8254-263">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="d8254-264">In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="d8254-264">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="d8254-265">Außerdem fügen Hintergrund und Füllfarben zwischen den verschiedenen UI-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d8254-265">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="d8254-266">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d8254-266">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="d8254-267">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags:</span><span class="sxs-lookup"><span data-stu-id="d8254-267">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="d8254-268">Diese Benutzeroberfläche ähnelt *`ExpenseItHome.xaml`*, außer dass die Daten des Berichts, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="d8254-268">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="d8254-269">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8254-269">Build and run the application.</span></span>

4. <span data-ttu-id="d8254-270">Wählen Sie die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d8254-270">Select the **View** button.</span></span>

    <span data-ttu-id="d8254-271">Die Spesenabrechnungsseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8254-271">The expense report page appears.</span></span> <span data-ttu-id="d8254-272">Beachten Sie außerdem, dass die Navigationsschaltfläche "zurück" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-272">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="d8254-273">Die folgende Abbildung zeigt die Elemente der Benutzeroberfläche hinzugefügt *"ExpenseReportPage.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-273">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Bildschirmabbildung für ExpenseIt-Beispiel](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="d8254-275">Formatieren von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d8254-275">Style controls</span></span>

<span data-ttu-id="d8254-276">Die Darstellung verschiedener Elemente ist häufig für alle Elemente des gleichen Typs in einer Benutzeroberfläche identisch.</span><span class="sxs-lookup"><span data-stu-id="d8254-276">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="d8254-277">Benutzeroberfläche verwendet [Stile](../controls/styling-and-templating.md) Darstellungen in mehreren Elementen wieder verwendbaren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d8254-277">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="d8254-278">Die wiederverwendbarkeit von Stilen können Sie die um XAML-Erstellung und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d8254-278">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="d8254-279">Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d8254-279">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="d8254-280">Open *"Application.xaml"* oder *"App.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="d8254-280">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="d8254-281">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:</span><span class="sxs-lookup"><span data-stu-id="d8254-281">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="d8254-282">Durch diese XAML werden folgende Stile hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="d8254-282">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="d8254-283">`headerTextStyle`: Zum Formatieren des Seitentitels <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="d8254-283">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="d8254-284">`labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="d8254-284">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="d8254-285">`columnHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="d8254-285">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="d8254-286">`listHeaderStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Border> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="d8254-286">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="d8254-287">`listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="d8254-287">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="d8254-288">`buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="d8254-288">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="d8254-289">Beachten Sie, dass die Ressourcen und die untergeordneten Elemente werden der <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element.</span><span class="sxs-lookup"><span data-stu-id="d8254-289">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="d8254-290">An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.</span><span class="sxs-lookup"><span data-stu-id="d8254-290">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="d8254-291">Ein Beispiel für die Verwendung von Ressourcen in einer .NET-App, finden Sie unter [Verwenden von Anwendungsressourcen](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-291">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="d8254-292">In *`ExpenseItHome.xaml`*, ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="d8254-292">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="d8254-293">Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8254-293">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="d8254-294">Z. B. die `headerTextStyle` gilt für die "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="d8254-294">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="d8254-295">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d8254-295">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="d8254-296">Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="d8254-296">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="d8254-297">Dieses XAML Stile hinzugefügt. die <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Border> Elemente.</span><span class="sxs-lookup"><span data-stu-id="d8254-297">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="d8254-298">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8254-298">Build and run the application.</span></span> <span data-ttu-id="d8254-299">Die Darstellung des Fensters ist der gleiche wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="d8254-299">The window appearance is the same as previously.</span></span>

    ![Bildschirmabbildung für ExpenseIt-Beispiel](./media/gettingstartedfigure4.png)

7. <span data-ttu-id="d8254-301">Schließen Sie die Anwendung zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d8254-301">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="d8254-302">Binden von Daten an ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8254-302">Bind data to a control</span></span>

<span data-ttu-id="d8254-303">In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d8254-303">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="d8254-304">In *`ExpenseItHome.xaml`*, nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie den folgenden XAML zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält:</span><span class="sxs-lookup"><span data-stu-id="d8254-304">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="d8254-305">Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource.</span><span class="sxs-lookup"><span data-stu-id="d8254-305">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="d8254-306">Normalerweise würde diese Daten als Datei geladen, aber die Daten werden aus Gründen der Einfachheit Inline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d8254-306">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="d8254-307">In der `<Grid.Resources>` -Element, fügen Sie die folgenden `<xref:System.Windows.DataTemplate>` -Element, das definiert, wie Sie die Anzeige der Daten in die <xref:System.Windows.Controls.ListBox>, nachdem die `<XmlDataProvider>` Element:</span><span class="sxs-lookup"><span data-stu-id="d8254-307">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="d8254-308">Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-308">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="d8254-309">Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="d8254-309">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="d8254-310">Dieses XAML bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> an die Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8254-310">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="d8254-311">Verbinden Sie Daten an Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d8254-311">Connect data to controls</span></span>

<span data-ttu-id="d8254-312">Anschließend fügen Sie Code zum Abrufen des Namens, der ausgewählt wird die **`ExpenseItHome`** Seite, und übergeben Sie es an den Konstruktor der **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="d8254-312">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="d8254-313">**ExpenseReportPage** legt den Datenkontext mithilfe des übergebenen Elements, die die Steuerelemente definierten in *"ExpenseReportPage.xaml"* Binden an.</span><span class="sxs-lookup"><span data-stu-id="d8254-313">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="d8254-314">Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="d8254-314">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="d8254-315">Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.</span><span class="sxs-lookup"><span data-stu-id="d8254-315">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="d8254-316">Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="d8254-316">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="d8254-317">Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler aufrufen, den neuen Konstruktor, der die Spesenabrechnungsdaten der ausgewählten Person übergeben.</span><span class="sxs-lookup"><span data-stu-id="d8254-317">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="d8254-318">Style-Daten mit Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="d8254-318">Style data with data templates</span></span>

<span data-ttu-id="d8254-319">In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen.</span><span class="sxs-lookup"><span data-stu-id="d8254-319">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="d8254-320">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d8254-320">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="d8254-321">Binden Sie den Inhalt der "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente an die entsprechende Datenquelleneigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d8254-321">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="d8254-322">Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8254-322">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="d8254-323">Nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="d8254-323">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="d8254-324">Ersetzen Sie die <xref:System.Windows.Controls.DataGridTextColumn> Elemente mit <xref:System.Windows.Controls.DataGridTemplateColumn> unter der <xref:System.Windows.Controls.DataGrid> Element und die Vorlagen auf sie angewendet.</span><span class="sxs-lookup"><span data-stu-id="d8254-324">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="d8254-325">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8254-325">Build and run the application.</span></span>

6. <span data-ttu-id="d8254-326">Wählen Sie eine Person ein, und wählen Sie dann die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d8254-326">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="d8254-327">Die folgende Abbildung zeigt die beiden Seiten von der `ExpenseIt` Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen angewendet:</span><span class="sxs-lookup"><span data-stu-id="d8254-327">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Bildschirmabbildungen für ExpenseIt-Beispiel](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="d8254-329">In diesem Beispiel wird veranschaulicht, eine bestimmte Funktion von WPF und nicht alle bewährte Methoden für Aspekte wie Sicherheit, Lokalisierung und Eingabehilfen.</span><span class="sxs-lookup"><span data-stu-id="d8254-329">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="d8254-330">Von WPF und die bewährten Methoden für .NET-app-Entwicklung und umfassend behandelt finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d8254-330">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="d8254-331">Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="d8254-331">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="d8254-332">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d8254-332">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="d8254-333">Übersicht über WPF-Globalisierung und -Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="d8254-333">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="d8254-334">Von WPF</span><span class="sxs-lookup"><span data-stu-id="d8254-334">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="d8254-335">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d8254-335">Next steps</span></span>

<span data-ttu-id="d8254-336">In dieser exemplarischen Vorgehensweise haben Sie gelernt, eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d8254-336">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="d8254-337">Sie verfügen nun über einen grundlegenden Überblick über die Bausteine einer datengebundenen .NET-App.</span><span class="sxs-lookup"><span data-stu-id="d8254-337">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="d8254-338">Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d8254-338">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="d8254-339">WPF-Architektur</span><span class="sxs-lookup"><span data-stu-id="d8254-339">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="d8254-340">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d8254-340">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="d8254-341">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="d8254-341">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="d8254-342">Layout</span><span class="sxs-lookup"><span data-stu-id="d8254-342">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="d8254-343">Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d8254-343">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="d8254-344">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="d8254-344">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="d8254-345">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d8254-345">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="d8254-346">Übersicht über Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d8254-346">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="d8254-347">Grafiken und multimedia</span><span class="sxs-lookup"><span data-stu-id="d8254-347">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="d8254-348">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="d8254-348">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="d8254-349">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8254-349">See also</span></span>

- [<span data-ttu-id="d8254-350">Übersicht über Panel</span><span class="sxs-lookup"><span data-stu-id="d8254-350">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="d8254-351">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="d8254-351">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="d8254-352">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d8254-352">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="d8254-353">Stile und-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d8254-353">Styles and templates</span></span>](../controls/styles-and-templates.md)
