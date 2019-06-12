---
title: Verwenden von ML.NET in einem Szenario für die Erkennung von Vertriebsanomalien
description: Erfahren Sie, wie Sie ML.NET in einem Szenario zur Erkennung von Vertriebsanomalien einsetzen können, um zu verstehen, wie Sie die Daten im Hinblick auf Anomaliespitzen und Änderungspunkte analysieren können, um die entsprechenden Maßnahmen zu ergreifen.
ms.date: 05/29/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e092aea66ca9f439cf97c1ebee83097def0f520b
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758798"
---
# <a name="tutorial-use-mlnet-for-product-sales-anomaly-detection"></a>Tutorial: Verwenden von ML.NET für die Erkennung von Vertriebsanomalien 

Dieses Beispieltutorial veranschaulicht die Verwendung von ML.NET zur Erkennung von Anomalien in Produktvertriebsdaten, um über eine .NET Core-Konsolenanwendung mit C# in Visual Studio 2019 die entsprechenden Maßnahmen zu ergreifen. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Laden der Daten
> * Trainieren des Modells zur Erkennung von Anomaliespitzen
> * Erkennen von Anomaliespitzen mit dem trainierten Modell
> * Trainieren des Modells zur Erkennung einer Änderungspunktanomalie
> * Erkennen von Änderungspunktanomalien mit dem trainierten Modell

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* [Das Dataset „product-sales.csv“](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> Das Datenformat in `product-sales.csv` basiert auf dem Dataset „Shampoo Sales Over a Three Year Period“ von Rob Hyndman, ursprünglich aus dem DataMarket und von der Time Series Data Library (TSDL) bereitgestellt. Das Dataset „Shampoo Sales Over a Three Year Period“ ist im Rahmen der DataMarket Default Open License lizenziert.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „ProductSalesAnomalyDetection“.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte Durchsuchen aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das **v1.0.0**-Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.TimeSeries v0.12.0**.

4. Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Herunterladen der Daten

1. Laden Sie die das Dataset herunter, und speichern Sie es im Ordner *Data*, den Sie vorher erstellt haben:

   * Klicken Sie mit der rechten Maustaste auf [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) und anschließend auf „Link speichern unter“ oder „Ziel speichern unter“.

     Achten Sie darauf, die \*CSV-Datei entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie die \*CSV-Datei an anderer Stelle gespeichert haben.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*CSV Datei, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Die folgende Tabelle enthält eine Datenvorschau aus Ihrem \*CSV-Datei:

|Monat  |ProductSales |
|-------|-------------|
|1-Jan  |    271      |
|2-Jan  |    150,9    |
|.....  |    .....    |
|1-Feb  |    199,3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Als nächstes definieren Sie Ihre Datenstruktur der Eingabeklasse.

Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in*ProductSalesData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

Die Datei *ProductSalesData.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der *ProductSalesData.cs*-Datei hinzu:

```csharp
using Microsoft.ML.Data;
```

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ProductSalesData.cs* den folgenden Code mit den beiden Klassen `ProductSalesData` und `ProductSalesPrediction` hinzu:

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

`ProductSalesData` ist eine Klasse für Eingabedaten. Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen. 

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

Sie müssen zwei globale Felder zum Speichern des gerade heruntergeladenen Datasetdateipfads und des gespeicherten Modelldateipfads erstellen:

* `_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_docsize` enthält die Anzahl der Datensätze in der Datendatei. Sie verwenden diese Informationen zum Berechnen von `pvalueHistoryLength`.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a>Laden der Daten

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden. Fügen Sie der `Main()`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.

## <a name="ml-task---time-series-anomaly-detection"></a>ML-Aufgabe – Anomalieerkennung in einer Zeitreihe 

Die Anomalieerkennung zeigt unerwartete oder ungewöhnliche Ereignisse oder Verhaltensweisen an. Sie erhalten Hinweise darauf, wo Sie nach Problemen schauen müssen, und können die Frage beantworten, ob das Ereignis oder Verhalten ungewöhnlich ist.

![Ist das ungewöhnlich](./media/sales-anomaly-detection/anomalydetection.png)

Die Anomalieerkennung ist ein Prozess, bei dem Ausreißer in Zeitreihendaten ermittelt. Damit wird auf Eingabezeitreihen hingewiesen, bei denen nicht das erwartete oder ein ungewöhnliches Verhalten aufgetreten ist.

Dies kann in vielerlei Hinsicht hilfreich sein. Zum Beispiel:

Wenn Sie ein Auto besitzen, möchten Sie vielleicht wissen: Ist diese Ölstandsanzeige normal oder habe ich ein Leck?
Wenn Sie den Energieverbrauch überwachen, möchten Sie vielleicht wissen: Gibt es einen Stromausfall?

Es können zwei Arten von Zeitreihenanomalien erkannt werden: 

* **Spitzen** zeigen temporäre Häufungen von anomalem Verhalten im System an. 

* **Änderungspunkte** zeigen den Beginn anhaltender Änderungen im Zeitverlauf im System an. 

In ML.NET eignen sich die Algorithmen „IID Spike Detection“ oder „IID Change point Detection“ für [unabhängige und identisch verteilte Datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables). 

Sie analysieren die gleichen Produktvertriebsdaten, um Spitzen und Änderungspunkte zu erkennen. Der Prozess zum Erstellen und Trainieren eines Modells ist für die Erkennung von Spitzen und Änderungspunkten gleich; der Hauptunterschied besteht in dem verwendeten spezifischen Erkennungsalgorithmus.

## <a name="spike-detection"></a>Spitzenerkennung 

Das Ziel der Spitzenerkennung ist es, plötzliche, aber temporäre Häufungen zu identifizieren, die sich signifikant von der Mehrzahl der Zeitreihen-Datenwerte unterscheiden. Es ist wichtig, diese verdächtigen seltenen Elemente, Ereignisse oder Beobachtungen rechtzeitig zu erkennen, um sie zu minimieren. Der folgende Ansatz kann zur Erkennung einer Vielzahl von Anomalien verwendet werden: z.B. Ausfälle, Cyberangriffe oder virale Webinhalte. Das folgende Bild zeigt ein Beispiel für Spitzen in einem Zeitreihen-Dataset:

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a>Erstellen der DetectSpike()-Methode

Fügen Sie der `DetectSpike()`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

Die `DetectSpike()`-Methode führt die folgenden Aufgaben aus:

* Trainieren des Modells.
* Erkennen von Spitzen basierend auf historischen Vertriebsdaten.
* Anzeigen der Ergebnisse.

Erstellen Sie die `DetectSpike()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

Verwenden Sie [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator), um das Modell zum Erkennen von Spitzen zu trainieren. Fügen Sie ihn mit dem folgenden Code zur `DetectChangepoint()`-Methode hinzu:

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

Fügen Sie den folgenden Code als nächste Codezeile in die Methode `DetectSpike()` ein, um das Modell auf die `productSales`-Daten abzustimmen:

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

Mit der [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A)-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.

Fügen Sie die folgende Codezeile hinzu, um die `productSales`-Daten als nächste Zeile in der `DetectSpike()`-Methode zu transformieren:

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

Der vorherige Code verwendet die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.

Konvertieren Sie Ihre `transformedData` mit der [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable` zur einfacheren Anzeige:

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Kopfzeile:

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

In den Ergebnissen der Spitzenerkennung werden folgende Informationen angezeigt:

* `Alert` gibt eine Spitzenwarnung für einen bestimmten Datenpunkt an.

* `Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.

* `P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit). Damit wird angegeben, wie wahrscheinlich es ist, dass dieser Datenpunkt eine Anomalie ist. 

Verwenden Sie den folgenden Code, um `predictions` `IEnumerable` zu durchlaufen und die Ergebnisse anzuzeigen:

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a>Ergebnisse der Spitzenerkennung

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>Erkennen von Änderungspunkten

`Change points` sind anhaltende Änderungen in der Verteilung der Werte in einem Zeitreihen-Ereignisstrom, wie Niveauänderungen und Trends. Diese anhaltenden Änderungen dauern wesentlich länger als `spikes` und könnten auf katastrophale Ereignisse hinweisen. `Change points` sind in der Regel nicht mit bloßem Auge erkennbar, können aber mit Ansätzen wie beispielsweise der folgenden Methode in Ihren Daten festgestellt werden.  Das folgende Bild ist ein Beispiel für eine Änderungspunkterkennung:

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a>Erstellen der DetectChangepoint()-Methode

Fügen Sie der `DetectChangepoint()`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

Die `DetectChangepoint()`-Methode führt die folgenden Aufgaben aus:

* Trainieren des Modells.
* Erkennen von Änderungspunkten basierend auf historischen Vertriebsdaten.
* Anzeigen der Ergebnisse.

Erstellen Sie die `DetectChangepoint()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) wird zum Trainieren des Modells für die Erkennung von Änderungspunkten verwendet. Fügen Sie ihn mit dem folgenden Code zur `DetectChangepoint()`-Methode hinzu:

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

Fügen Sie wie zuvor den folgenden Code als nächste Codezeile in die Methode `DetectChangePoint()` ein, um das Modell auf die `productSales`-Daten abzustimmen:

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

Verwenden Sie die `Transform()`-Methode, um die `Training`-Daten zu transformieren, indem Sie den folgenden Code zu `DetectChangePoint()` hinzufügen:

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

Konvertieren Sie wie bereits zuvor Ihre `transformedData` mit der `CreateEnumerable()`-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable` zur einfacheren Anzeige:

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

Erstellen Sie mit dem folgenden Code als nächste Zeile in der `DetectChangePoint()`-Methode einen Anzeigeheader:

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

In den Ergebnissen der Änderungspunkterkennung werden folgende Informationen angezeigt:

* `Alert` gibt eine Änderungspunktwarnung für einen bestimmten Datenpunkt an.
* `Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.
* `P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit). Damit wird angegeben, wie wahrscheinlich es ist, dass dieser Datenpunkt eine Anomalie ist. 
* `Martingale value` wird verwendet, um basierend auf der Reihenfolge der P-Werte zu bestimmen, wie „ungewöhnlich ein Datenpunkt ist.  

Mit dem folgenden Code können Sie `predictions` `IEnumerable` durchlaufen und die Ergebnisse anzeigen:

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a>Ergebnisse der Änderungspunkterkennung

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich Machine Learning-Modelle zur Erkennung von Spitzen und Änderungspunktanomalien in Vertriebsdaten erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Laden der Daten
> * Trainieren des Modells zur Erkennung von Anomaliespitzen
> * Erkennen von Anomaliespitzen mit dem trainierten Modell
> * Trainieren des Modells zur Erkennung einer Änderungspunktanomalie
> * Erkennen von Änderungspunktanomalien mit dem trainierten Modell

## <a name="next-steps"></a>Nächste Schritte

Durchsuchen Sie das GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für die Erkennung von Stromverbrauchsanomalien, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
