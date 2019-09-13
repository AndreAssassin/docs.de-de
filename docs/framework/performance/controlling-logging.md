---
title: Steuern der Protokollierung in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1648af8c3dc407581714e8e863fe4972d6ffadbc
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894932"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="d612b-102">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d612b-102">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="d612b-103">Sie können mithilfe der Ereignisablaufverfolgung für Windows (ETW) Common Language Runtime (CLR)-Ereignisse aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d612b-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="d612b-104">Sie können Ablaufverfolgungen mit den folgenden Tools erstellen und anzeigen:</span><span class="sxs-lookup"><span data-stu-id="d612b-104">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="d612b-105">Die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) sind im Windows-Betriebssystem enthalten.</span><span class="sxs-lookup"><span data-stu-id="d612b-105">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="d612b-106">Die [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference)-Tools im [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="d612b-106">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="d612b-107">Weitere Informationen zu Xperf finden Sie im [Windows Performance-Blog](https://go.microsoft.com/fwlink/?LinkId=179509).</span><span class="sxs-lookup"><span data-stu-id="d612b-107">For more information about Xperf, see the [Windows Performance blog](https://go.microsoft.com/fwlink/?LinkId=179509).</span></span>

<span data-ttu-id="d612b-108">Wenn Sie CLR-Ereignisinformationen erfassen möchten, muss der CLR-Anbieter auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d612b-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="d612b-109">Geben Sie an der Eingabeaufforderung `logman query providers` ein, um festzustellen, ob der Anbieter installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d612b-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="d612b-110">Eine Anbieterliste wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d612b-110">A list of providers is displayed.</span></span> <span data-ttu-id="d612b-111">Diese Liste sollte wie folgt einen Eintrag für den CLR-Anbieter enthalten.</span><span class="sxs-lookup"><span data-stu-id="d612b-111">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="d612b-112">Wenn der CLR-Anbieter nicht aufgeführt ist, können Sie ihn unter Windows Vista und späteren Betriebssystemen mithilfe des Windows-Befehlszeilentools [Wevtutil](/windows-server/administration/windows-commands/wevtutil) installieren.</span><span class="sxs-lookup"><span data-stu-id="d612b-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="d612b-113">Öffnen Sie das Eingabeaufforderungsfenster als Administrator.</span><span class="sxs-lookup"><span data-stu-id="d612b-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="d612b-114">Ändern Sie das Eingabe Aufforderungs Verzeichnis in den Ordner .NET Framework 4 (%windir%\Microsoft.NET\Framework [64]\<\v4.). NET-Version > \).</span><span class="sxs-lookup"><span data-stu-id="d612b-114">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="d612b-115">Dieser Ordner enthält die Datei "CLR-ETW.man".</span><span class="sxs-lookup"><span data-stu-id="d612b-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="d612b-116">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um den CLR-Anbieter zu installieren:</span><span class="sxs-lookup"><span data-stu-id="d612b-116">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="d612b-117">Erfassen von CLR-ETW-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="d612b-117">Capturing CLR ETW Events</span></span>

<span data-ttu-id="d612b-118">Sie können die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) verwenden, um ETW-Ereignisse zu erfassen. Mit den Tools [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) können Sie die Ablaufverfolgungsereignisse dekodieren.</span><span class="sxs-lookup"><span data-stu-id="d612b-118">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="d612b-119">Zum Aktivieren der Protokollierung müssen Benutzer drei Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="d612b-119">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="d612b-120">Anbieter, mit dem kommuniziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d612b-120">The provider to communicate to.</span></span>

- <span data-ttu-id="d612b-121">Eine 64-Bit-Zahl, die einen Satz von Schlüsselwörtern darstellt.</span><span class="sxs-lookup"><span data-stu-id="d612b-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="d612b-122">Jedes Schlüsselwort stellt einen Satz von Ereignissen dar, den der Anbieter aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="d612b-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="d612b-123">Die Zahl stellt einen kombinierten Satz von Schlüsselwörtern dar, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d612b-123">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="d612b-124">Eine kleine Zahl, die die Ebene (den Ausführlichkeitsgrad) der Protokollierung darstellt.</span><span class="sxs-lookup"><span data-stu-id="d612b-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="d612b-125">Ebene 1 ist die am wenigsten ausführliche, Ebene 5 die ausführlichste.</span><span class="sxs-lookup"><span data-stu-id="d612b-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="d612b-126">Ebene 0 ist ein Standard mit anbieterspezifischer Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="d612b-126">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="d612b-127">So erfassen Sie CLR-ETW-Ereignisse mit Logman</span><span class="sxs-lookup"><span data-stu-id="d612b-127">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="d612b-128">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d612b-128">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="d612b-129">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="d612b-129">where:</span></span>

    - <span data-ttu-id="d612b-130">Durch den `-p`-Parameter wird die Anbieter-GUID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d612b-130">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="d612b-131">`0x1CCBD` gibt die Kategorien der Ereignisse an, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d612b-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="d612b-132">`0x5` legt die Ebene der Protokollierung fest (in diesem Fall "Ausführlich" (5)).</span><span class="sxs-lookup"><span data-stu-id="d612b-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="d612b-133">Mit dem `-ets`-Parameter wird Logman angewiesen, Befehle an Ereignisablaufverfolgungs-Sitzungen zu senden.</span><span class="sxs-lookup"><span data-stu-id="d612b-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="d612b-134">Der `-ct perf`-Parameter gibt an, dass mit der `QueryPerformanceCounter`-Funktion der Zeitstempel für jedes Ereignis protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="d612b-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="d612b-135">Geben Sie Folgendes ein, um die Protokollierung der Ereignisse zu beenden:</span><span class="sxs-lookup"><span data-stu-id="d612b-135">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="d612b-136">Mit diesem Befehl wird eine binäre Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.</span><span class="sxs-lookup"><span data-stu-id="d612b-136">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="d612b-137">So erfassen Sie CLR-ETW-Ereignisse mit XPerf</span><span class="sxs-lookup"><span data-stu-id="d612b-137">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="d612b-138">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d612b-138">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="d612b-139">Dabei ist die GUID die GUID des CLR-ETW-Anbieters, und `0x1CCBD:5` verfolgt sämtliche Vorgänge auf und unterhalb von Ebene 5 (Ausführlich).</span><span class="sxs-lookup"><span data-stu-id="d612b-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="d612b-140">Geben Sie Folgendes ein, um die Ablaufverfolgung zu beenden:</span><span class="sxs-lookup"><span data-stu-id="d612b-140">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="d612b-141">Mit diesem Befehl wird eine Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.</span><span class="sxs-lookup"><span data-stu-id="d612b-141">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="d612b-142">Anzeigen von CLR-ETW-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="d612b-142">Viewing CLR ETW Events</span></span>

<span data-ttu-id="d612b-143">Verwenden Sie die unten aufgeführten Befehle, um die CLR-ETW-Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d612b-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="d612b-144">Eine Beschreibung der Ereignisse finden Sie unter [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="d612b-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="d612b-145">So zeigen Sie CLR-ETW-Ereignisse mit Tracerpt an</span><span class="sxs-lookup"><span data-stu-id="d612b-145">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="d612b-146">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d612b-146">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="d612b-147">Mit diesem Befehl werden zwei Dateien erstellt: "dumpfile.xml" und "summary.txt".</span><span class="sxs-lookup"><span data-stu-id="d612b-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="d612b-148">In der Datei "dumpfile.xml" werden alle Ereignisse aufgeführt, wohingegen "summary.txt" eine Zusammenfassung der Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="d612b-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="d612b-149">So zeigen Sie CLR-ETW-Ereignisse mit Xperf an</span><span class="sxs-lookup"><span data-stu-id="d612b-149">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="d612b-150">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d612b-150">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="d612b-151">Mit diesem Befehl wird der ETL-Datei-Viewer von Xperf geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d612b-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="d612b-152">In diesem Viewer werden die CLR-Ereignisse in der Ansicht **Generische Ereignisse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d612b-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="d612b-153">Zum Anzeigen eines nach Typen kategorisierten Datenrasters von Ereignissen wählen Sie in der Ansicht einen Zeitraum aus, klicken Sie dann mit der rechten Maustaste, und wählen Sie **Zusammenfassung** aus.</span><span class="sxs-lookup"><span data-stu-id="d612b-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="d612b-154">So konvertieren Sie die ETL-Datei in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="d612b-154">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="d612b-155">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d612b-155">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="d612b-156">Dieser Befehl bewirkt, dass XPerf die Ereignisse als CSV-Datei (CSV) sichert, die Sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="d612b-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="d612b-157">Da für unterschiedliche Ereignisse auch unterschiedliche Felder verfügbar sind, enthält diese CSV-Datei vor den Daten mehrere Headerzeilen.</span><span class="sxs-lookup"><span data-stu-id="d612b-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="d612b-158">Das erste Feld jeder Zeile ist für den Ereignistyp vorgesehen, der den Header angibt, der zum Ermitteln der weiteren Felder verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d612b-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="d612b-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d612b-159">See also</span></span>

- [<span data-ttu-id="d612b-160">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="d612b-160">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="d612b-161">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d612b-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
