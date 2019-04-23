---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e88a85b96c1e5d33d748332991cb9480222a9c66
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612094"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="7dc59-103">Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="7dc59-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="7dc59-104">Dieses Beispieltutorial veranschaulicht das Verwenden von ML.NET zum Erstellen eines Standpunktklassifizierers zum Vorhersagen eines positiven oder negativen Standpunkts über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7dc59-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="7dc59-105">In der Welt von Machine Learning wird diese Art von Vorhersage als binäre Klassifizierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="7dc59-106">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="7dc59-107">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7dc59-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="7dc59-108">Dieses Tutorial und das zugehörige Beispiel verwenden zurzeit **ML.NET Version 0.11**.</span><span class="sxs-lookup"><span data-stu-id="7dc59-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="7dc59-109">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="7dc59-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="7dc59-110">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7dc59-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="7dc59-111">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="7dc59-111">Understand the problem</span></span>
> * <span data-ttu-id="7dc59-112">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7dc59-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="7dc59-113">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-113">Prepare your data</span></span>
> * <span data-ttu-id="7dc59-114">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-114">Transform the data</span></span>
> * <span data-ttu-id="7dc59-115">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-115">Train the model</span></span>
> * <span data-ttu-id="7dc59-116">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-116">Evaluate the model</span></span>
> * <span data-ttu-id="7dc59-117">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="7dc59-117">Predict with the trained model</span></span>
> * <span data-ttu-id="7dc59-118">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="7dc59-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="7dc59-119">Übersicht über das Standpunktanalyse-Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dc59-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="7dc59-120">Das Beispiel ist eine Konsolen-App, die ML.NET verwendet, um ein Modell zu trainieren, das den Standpunkt als positiv oder negativ klassifiziert und vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="7dc59-121">Das von der University of California, Irvine (UCI), stammende Yelp-Standpunktdataset ist in ein Trainingsdataset und ein Testdataset unterteilt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="7dc59-122">Das Beispiel wertet das Modell mit dem Testdataset für die Qualitätsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-122">The sample evaluates the model with the test dataset for quality analysis.</span></span>

<span data-ttu-id="7dc59-123">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="7dc59-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7dc59-124">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="7dc59-124">Prerequisites</span></span>

* <span data-ttu-id="7dc59-125">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="7dc59-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="7dc59-126">Die Dataset-ZIP-Datei „UCI Sentiment Labeled Sentences“</span><span class="sxs-lookup"><span data-stu-id="7dc59-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="7dc59-127">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="7dc59-127">Machine learning workflow</span></span>

<span data-ttu-id="7dc59-128">Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="7dc59-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="7dc59-129">Die Workflowphasen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7dc59-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="7dc59-130">**Verstehen des Problems**</span><span class="sxs-lookup"><span data-stu-id="7dc59-130">**Understand the problem**</span></span>
2. <span data-ttu-id="7dc59-131">**Vorbereiten Ihrer Daten**</span><span class="sxs-lookup"><span data-stu-id="7dc59-131">**Prepare your data**</span></span>
   * <span data-ttu-id="7dc59-132">**Laden der Daten**</span><span class="sxs-lookup"><span data-stu-id="7dc59-132">**Load the data**</span></span>
   * <span data-ttu-id="7dc59-133">**Extrahieren von Funktionen (Transformieren von Daten)**</span><span class="sxs-lookup"><span data-stu-id="7dc59-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="7dc59-134">**Erstellen und trainieren**</span><span class="sxs-lookup"><span data-stu-id="7dc59-134">**Build and train**</span></span>
   * <span data-ttu-id="7dc59-135">**Trainieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="7dc59-135">**Train the model**</span></span>
   * <span data-ttu-id="7dc59-136">**Evaluieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="7dc59-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="7dc59-137">**Bereitstellen des Modells**</span><span class="sxs-lookup"><span data-stu-id="7dc59-137">**Deploy Model**</span></span>
   * <span data-ttu-id="7dc59-138">**Vorhersagen treffen mit dem Modell**</span><span class="sxs-lookup"><span data-stu-id="7dc59-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="7dc59-139">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="7dc59-139">Understand the problem</span></span>

<span data-ttu-id="7dc59-140">Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern.</span><span class="sxs-lookup"><span data-stu-id="7dc59-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="7dc59-141">Das Aufschlüsseln des Problems ermöglicht es Ihnen, die Ergebnisse vorherzusagen und auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="7dc59-142">Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="7dc59-143">Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7dc59-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="7dc59-144">Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="7dc59-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="7dc59-145">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7dc59-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="7dc59-146">Von diesem Problem kennen Sie die folgenden Fakten:</span><span class="sxs-lookup"><span data-stu-id="7dc59-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="7dc59-147">Trainingsdaten: Websitekommentare können positiv (1) oder negativ (0) sein (**Standpunkt**).</span><span class="sxs-lookup"><span data-stu-id="7dc59-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="7dc59-148">Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, positiv oder negativ, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="7dc59-149">Ich liebe das Bedienpersonal hier.</span><span class="sxs-lookup"><span data-stu-id="7dc59-149">I love the wait staff here.</span></span> <span data-ttu-id="7dc59-150">Sie bringen‘s.</span><span class="sxs-lookup"><span data-stu-id="7dc59-150">They rock.</span></span>
* <span data-ttu-id="7dc59-151">Hier gibt‘s die schlechteste Suppe.</span><span class="sxs-lookup"><span data-stu-id="7dc59-151">This place has the worst soup.</span></span>

<span data-ttu-id="7dc59-152">Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="7dc59-153">Informationen zum Klassifizierungsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="7dc59-153">About the classification algorithm</span></span>

<span data-ttu-id="7dc59-154">Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="7dc59-155">Beispielsweise können Sie mit der Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="7dc59-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="7dc59-156">Einen Standpunkt als positiv oder negativ identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="7dc59-157">E-Mails als Spam, Junk oder gut klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="7dc59-158">Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.</span><span class="sxs-lookup"><span data-stu-id="7dc59-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="7dc59-159">Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="7dc59-160">Klassifizierungsalgorithmen zählen häufig zu einem der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="7dc59-161">Binär: entweder A oder B.</span><span class="sxs-lookup"><span data-stu-id="7dc59-161">Binary: either A or B.</span></span>
* <span data-ttu-id="7dc59-162">Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="7dc59-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="7dc59-163">Da die Websitekommentare als positiv oder negativ klassifiziert werden müssen, verwenden Sie den Algorithmus für die Binärklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="7dc59-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="7dc59-164">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7dc59-164">Create a console application</span></span>

1. <span data-ttu-id="7dc59-165">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7dc59-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="7dc59-166">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="7dc59-167">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="7dc59-168">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="7dc59-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="7dc59-169">Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="7dc59-170">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="7dc59-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="7dc59-171">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="7dc59-172">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="7dc59-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="7dc59-173">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="7dc59-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="7dc59-174">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="7dc59-175">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="7dc59-176">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="7dc59-177">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-177">Prepare your data</span></span>

1. <span data-ttu-id="7dc59-178">Laden Sie [die Dataset-ZIP-Datei „UCI Sentiment Labeled Sentences“ (siehe Zitate im folgenden Hinweis)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7dc59-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="7dc59-179">Kopieren Sie die `yelp_labelled.txt`-Datei in das Verzeichnis *Data*, das Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7dc59-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="7dc59-180">Die in diesem Tutorial verwendeten Datasets stammen aus „From Group to Individual Labels using Deep Features“, Kotzias et</span><span class="sxs-lookup"><span data-stu-id="7dc59-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="7dc59-181">al.,</span><span class="sxs-lookup"><span data-stu-id="7dc59-181">al,.</span></span> <span data-ttu-id="7dc59-182">KDD 2015, und werden im UCI Machine Learning Repository – Dua, D. und Karra Taniskidou, E. gehostet. (2017).</span><span class="sxs-lookup"><span data-stu-id="7dc59-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="7dc59-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="7dc59-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="7dc59-184">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="7dc59-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="7dc59-185">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Datei `yelp_labeled.txt`, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="7dc59-186">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="7dc59-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="7dc59-187">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="7dc59-187">Create classes and define paths</span></span>

<span data-ttu-id="7dc59-188">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="7dc59-189">Sie müssen zwei globale Felder zum Speichern des gerade heruntergeladenen Datasetdateipfads und des gespeicherten Modelldateipfads erstellen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="7dc59-190">`_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7dc59-190">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="7dc59-191">`_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7dc59-191">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="7dc59-192">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="7dc59-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="7dc59-193">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="7dc59-194">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="7dc59-195">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="7dc59-196">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="7dc59-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="7dc59-197">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7dc59-198">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="7dc59-199">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="7dc59-200">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="7dc59-201">Die Klasse des Eingabedatasets, `SentimentData`, hat eine `string`-Variable für den Kommentar (`SentimentText`) und eine `bool`-Variable (`Sentiment`), die entweder einen positiven oder negativen Wert für den Standpunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="7dc59-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="7dc59-202">Beiden Feldern sind <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>-Attribute angefügt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="7dc59-203">Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="7dc59-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="7dc59-204">Darüber hinaus hat die `Sentiment`-Eigenschaft ein <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>, um es als `Label`-Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> <span data-ttu-id="7dc59-205">Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7dc59-205">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="7dc59-206">Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dc59-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="7dc59-207">Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit dem Split out-Testdataset verwendet, um das Modell zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="7dc59-208">Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="7dc59-209">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="7dc59-210">Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst einen <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="7dc59-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="7dc59-211">`MLContext` ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="7dc59-211">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="7dc59-212">Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dc59-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="7dc59-213">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="7dc59-213">Initialize variables in Main</span></span>

<span data-ttu-id="7dc59-214">Erstellen Sie eine Variable namens `mlContext`, und initialisieren Sie sie mit einer neuen `MLContext`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="7dc59-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="7dc59-215">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="7dc59-216">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="7dc59-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="7dc59-217">Die `LoadData`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-218">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-218">Loads the data.</span></span>
* <span data-ttu-id="7dc59-219">Teilt das geladene Dataset in Trainings- und Testdatasets auf.</span><span class="sxs-lookup"><span data-stu-id="7dc59-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="7dc59-220">Gibt die aufgeteilten Trainings- und Testdatasets zurück.</span><span class="sxs-lookup"><span data-stu-id="7dc59-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="7dc59-221">Erstellen Sie die `LoadData`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```

## <a name="load-the-data"></a><span data-ttu-id="7dc59-222">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-222">Load the data</span></span>

<span data-ttu-id="7dc59-223">Da der zuvor von Ihnen erstellte `SentimentData`-Datenmodelltyp dem Schema des Datasets entspricht, können Sie das Initialisieren, Zuordnen und Laden des Datasets mit dem `MLContext.Data.LoadFromTextFile`-Wrapper für die [LoadFromTextFile-Methode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) in einer Codezeile zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="7dc59-224">Zurückgegeben wird ein <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="7dc59-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span>

<span data-ttu-id="7dc59-225">Als Ein- und Ausgabe von `Transforms` ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="7dc59-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="7dc59-226">In ML.NET ähneln die Daten einer SQL-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="7dc59-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="7dc59-227">Sie werden verzögert ausgewertet, sind schematisiert und heterogen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="7dc59-228">Das Objekt ist der erste Teil der Pipeline und lädt die Daten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="7dc59-229">Für dieses Tutorial lädt es ein Dataset mit Kommentaren und entsprechend schädlichen oder unschädlichen Standpunkten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="7dc59-230">Damit wird das Modell erstellt und trainiert.</span><span class="sxs-lookup"><span data-stu-id="7dc59-230">This is used to create the model, and train it.</span></span>

<span data-ttu-id="7dc59-231">Fügen Sie den folgenden Code am Ende der ersten Zeile der `LoadData`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dc59-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="7dc59-232">Aufteilen des Datasets für Modelltraining und -test</span><span class="sxs-lookup"><span data-stu-id="7dc59-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="7dc59-233">Als Nächstes benötigen Sie ein Trainingsdataset zum Trainieren des Modells und ein Testdataset zum Evaluieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="7dc59-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="7dc59-234">Verwenden Sie den `MLContext.BinaryClassification.TrainTestSplit`, der <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> umschließt, um das geladene Dataset in Trainings- und Testdatasets aufzuteilen und in <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="7dc59-235">Sie können den Anteil der Daten für das Testset mit dem `testFraction`-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="7dc59-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="7dc59-236">Der Standardwert ist 10%, aber Sie verwenden in diesem Fall 20%, um mehr Daten für die Auswertung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>

<span data-ttu-id="7dc59-237">Um die geladenen Daten in die erforderlichen Datasets aufzuteilen, fügen Sie den folgenden Code als nächste Zeile in die `LoadData`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="7dc59-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="7dc59-238">Geben Sie `splitDataView` am Ende der `LoadData`-Methode zurück:</span><span class="sxs-lookup"><span data-stu-id="7dc59-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="7dc59-239">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-239">Build and train the model</span></span>

<span data-ttu-id="7dc59-240">Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="7dc59-241">Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-242">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="7dc59-243">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="7dc59-243">Trains the model.</span></span>
* <span data-ttu-id="7dc59-244">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="7dc59-245">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="7dc59-245">Returns the model.</span></span>

<span data-ttu-id="7dc59-246">Erstellen Sie die `BuildAndTrainModel`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="7dc59-247">Beachten Sie, dass zwei Parameter an die Train-Methode übergeben werden; ein `MLContext` für den Kontext (`mlContext`) und eine `IDataView` für das Trainingsdatenset (`splitTrainSet`).</span><span class="sxs-lookup"><span data-stu-id="7dc59-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span>

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="7dc59-248">Extrahieren und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-248">Extract and transform the data</span></span>

<span data-ttu-id="7dc59-249">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7dc59-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="7dc59-250">Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="7dc59-251">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="7dc59-252">Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="7dc59-253">Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="7dc59-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="7dc59-254">Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="7dc59-255">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="7dc59-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="7dc59-256">Rufen Sie anschließend `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalte (`SentimentText`) in einen numerischen Vektor namens `Features` konvertiert wird, den der Machine Learning-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dc59-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="7dc59-257">Dies ist ein Wrapperaufruf, der <xref:Microsoft.ML.Data.EstimatorChain%601> zurückgibt, das effektiv eine Pipeline ist.</span><span class="sxs-lookup"><span data-stu-id="7dc59-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="7dc59-258">Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="7dc59-259">Fügen Sie das zur nächsten Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="7dc59-260">Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert.</span><span class="sxs-lookup"><span data-stu-id="7dc59-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="7dc59-261">Dies führt erst dann zu einem Fehler, wenn Sie die Anwendung ausführen und das Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="7dc59-262">Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="7dc59-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="7dc59-263">Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="7dc59-264">Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="7dc59-265">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="7dc59-265">Choose a learning algorithm</span></span>

<span data-ttu-id="7dc59-266">Um die Trainer hinzuzufügen, rufen Sie die `mlContext.BinaryClassification.Trainers.FastTree`-Wrappermethode auf, die ein <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="7dc59-267">Das ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="7dc59-268">Der `FastTreeBinaryClassificationTrainer` wird an die `pipeline` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="7dc59-269">Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="7dc59-270">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-270">Train the model</span></span>

<span data-ttu-id="7dc59-271">Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="7dc59-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="7dc59-272">Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit der <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>-Methode und stellen die bereits geladenen Trainingsdaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7dc59-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="7dc59-273">Damit wird ein Modell zurückgegeben, das für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dc59-273">This returns a model to use for predictions.</span></span> <span data-ttu-id="7dc59-274">`pipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück.</span><span class="sxs-lookup"><span data-stu-id="7dc59-274">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="7dc59-275">Das Experiment wird erst ausgeführt, wenn die `.Fit()`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7dc59-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="7dc59-276">Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="7dc59-277">Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung</span><span class="sxs-lookup"><span data-stu-id="7dc59-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="7dc59-278">An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dc59-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="7dc59-279">Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="7dc59-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="7dc59-280">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-280">Evaluate the model</span></span>

<span data-ttu-id="7dc59-281">Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="7dc59-282">In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="7dc59-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="7dc59-283">Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7dc59-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="7dc59-284">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-285">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="7dc59-285">Loads the test dataset.</span></span>
* <span data-ttu-id="7dc59-286">Erstellt den Auswerter der binären Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="7dc59-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="7dc59-287">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="7dc59-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="7dc59-288">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="7dc59-288">Displays the metrics.</span></span>

<span data-ttu-id="7dc59-289">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="7dc59-290">Als nächstes verwenden Sie den Machine Learning-Parameter `model` (einen Transformator) und den `splitTestSet`-Parameter, um die Features einzugeben und die Vorhersagen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7dc59-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="7dc59-291">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="7dc59-292">Die `mlContext.BinaryClassification.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset.</span><span class="sxs-lookup"><span data-stu-id="7dc59-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="7dc59-293">Das zurückgegebene <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics>-Objekt enthält alle von Auswertern der binären Klassifizierung berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="7dc59-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="7dc59-294">Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="7dc59-295">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="7dc59-296">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="7dc59-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="7dc59-297">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="7dc59-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="7dc59-298">Um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code als nächste Zeile in `Evaluate` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="7dc59-299">Speichern des Modells als ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="7dc59-299">Save the model as a.zip file</span></span>

<span data-ttu-id="7dc59-300">Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="7dc59-301">Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-302">Speichern Sie das Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="7dc59-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="7dc59-303">Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dc59-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="7dc59-304">Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="7dc59-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="7dc59-305">Um die als ZIP-Datei zu speichern, erstellen Sie den `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode.</span><span class="sxs-lookup"><span data-stu-id="7dc59-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="7dc59-306">Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

<span data-ttu-id="7dc59-307">Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:</span><span class="sxs-lookup"><span data-stu-id="7dc59-307">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="7dc59-308">Vorhersagen des Testdatenergebnisses mit dem gespeicherten Modell</span><span class="sxs-lookup"><span data-stu-id="7dc59-308">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="7dc59-309">Erstellen Sie die `UseModelWithSingleItem`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-309">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="7dc59-310">Die `UseModelWithSingleItem`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-310">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-311">Erstellen eines einzelnen Kommentars aus Testdaten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-311">Creates a single comment of test data.</span></span>
* <span data-ttu-id="7dc59-312">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-312">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="7dc59-313">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="7dc59-313">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="7dc59-314">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="7dc59-314">Displays the predicted results.</span></span>

<span data-ttu-id="7dc59-315">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-315">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="7dc59-316">Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, wohingegen ein sehr gängiges Produktionsszenario die Notwendigkeit von Vorhersagen für einzelne Beispiele ist.</span><span class="sxs-lookup"><span data-stu-id="7dc59-316">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="7dc59-317"><xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7dc59-317">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="7dc59-318">Fügen wir den folgenden Code hinzu, um die `PredictionEngine` als erste Zeile in der `Predict`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-318">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

<span data-ttu-id="7dc59-319">Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-319">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="7dc59-320">Damit können Sie den positiven oder negativen Standpunkt einer einzelnen Instanz der Kommentardaten vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-320">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="7dc59-321">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-321">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="7dc59-322">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="7dc59-322">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="7dc59-323">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="7dc59-323">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="7dc59-324">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-324">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="7dc59-325">Verwenden des Modells: Vorhersage</span><span class="sxs-lookup"><span data-stu-id="7dc59-325">Use the model: prediction</span></span>

<span data-ttu-id="7dc59-326">Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-326">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="7dc59-327">Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-327">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="7dc59-328">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="7dc59-328">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="7dc59-329">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="7dc59-329">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="7dc59-330">Erstellen Sie die `UseLoadedModelWithBatchItems`-Methode mit dem folgenden Code direkt vor der `SaveModelAsFile`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7dc59-330">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="7dc59-331">Die `UseLoadedModelWithBatchItems`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7dc59-331">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="7dc59-332">Erstellen von Batchtestdaten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-332">Creates batch test data.</span></span>
* <span data-ttu-id="7dc59-333">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-333">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="7dc59-334">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="7dc59-334">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="7dc59-335">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="7dc59-335">Displays the predicted results.</span></span>

<span data-ttu-id="7dc59-336">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `UseModelWithSingleItem`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-336">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="7dc59-337">Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `UseLoadedModelWithBatchItems`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-337">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="7dc59-338">Das des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-338">Load the model</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="7dc59-339">Nun besitzen Sie ein Modell, mit dem Sie den schädlichen oder nicht schädlichen Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.ITransformer.Transform%2A>-Methode vorhersagen können.</span><span class="sxs-lookup"><span data-stu-id="7dc59-339">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="7dc59-340">Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="7dc59-340">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="7dc59-341">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="7dc59-341">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="7dc59-342">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="7dc59-342">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="7dc59-343">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-343">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="7dc59-344">Fügen Sie für die Vorhersage den folgenden Code zur `UseLoadedModelWithBatchItems`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-344">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="7dc59-345">Verwenden des geladenen Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="7dc59-345">Use the loaded model for prediction</span></span>

<span data-ttu-id="7dc59-346">Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-346">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="7dc59-347">Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dc59-347">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="7dc59-348">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="7dc59-348">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="7dc59-349">Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-349">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="7dc59-350">Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:</span><span class="sxs-lookup"><span data-stu-id="7dc59-350">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="7dc59-351">Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:</span><span class="sxs-lookup"><span data-stu-id="7dc59-351">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="7dc59-352">Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="7dc59-352">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="7dc59-353">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-353">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="7dc59-354">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="7dc59-354">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="7dc59-355">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="7dc59-355">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="7dc59-356">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="7dc59-356">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="7dc59-357">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="7dc59-357">Results</span></span>

<span data-ttu-id="7dc59-358">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="7dc59-358">Your results should be similar to the following.</span></span> <span data-ttu-id="7dc59-359">Während der Pipelineverarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-359">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="7dc59-360">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-360">You may see warnings, or processing messages.</span></span> <span data-ttu-id="7dc59-361">Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-361">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="7dc59-362">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7dc59-362">Congratulations!</span></span> <span data-ttu-id="7dc59-363">Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="7dc59-363">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="7dc59-364">Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess.</span><span class="sxs-lookup"><span data-stu-id="7dc59-364">Building successful models is an iterative process.</span></span> <span data-ttu-id="7dc59-365">Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7dc59-365">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="7dc59-366">Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen Hyperparametern für jeden Algorithmus zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7dc59-366">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="7dc59-367">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="7dc59-367">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7dc59-368">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7dc59-368">Next steps</span></span>

<span data-ttu-id="7dc59-369">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7dc59-369">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7dc59-370">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="7dc59-370">Understand the problem</span></span>
> * <span data-ttu-id="7dc59-371">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7dc59-371">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="7dc59-372">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-372">Prepare your data</span></span>
> * <span data-ttu-id="7dc59-373">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="7dc59-373">Transform the data</span></span>
> * <span data-ttu-id="7dc59-374">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-374">Train the model</span></span>
> * <span data-ttu-id="7dc59-375">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7dc59-375">Evaluate the model</span></span>
> * <span data-ttu-id="7dc59-376">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="7dc59-376">Predict with the trained model</span></span>
> * <span data-ttu-id="7dc59-377">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="7dc59-377">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="7dc59-378">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="7dc59-378">Advance to the next tutorial to learn more</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7dc59-379">Klassifizierung von Issues</span><span class="sxs-lookup"><span data-stu-id="7dc59-379">Issue Classification</span></span>](github-issue-classification.md)
