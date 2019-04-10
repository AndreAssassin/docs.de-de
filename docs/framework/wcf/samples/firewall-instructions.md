---
title: Firewall-Anweisungen
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: f1b576b4e413fa3bae70ef1eb8f8ed768e28e309
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295158"
---
# <a name="firewall-instructions"></a><span data-ttu-id="ef57d-102">Firewall-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ef57d-102">Firewall Instructions</span></span>
<span data-ttu-id="ef57d-103">Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die Beispiele für Windows Communication Foundation (WCF) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ef57d-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="ef57d-104">In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000-8003 und über Port 9000 statt.</span><span class="sxs-lookup"><span data-stu-id="ef57d-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="ef57d-105">Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports.</span><span class="sxs-lookup"><span data-stu-id="ef57d-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="ef57d-106">Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="ef57d-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
-   <span data-ttu-id="ef57d-107">Option 1: Aktivieren Sie interaktiv die Beispiele während der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ef57d-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="ef57d-108">Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ef57d-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="ef57d-109">Wenn ein Beispiel ausgeführt wird, eine **Windows-Sicherheitshinweis** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef57d-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="ef57d-110">Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef57d-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="ef57d-111">Möglicherweise müssen Sie das Beispiel neu starten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-111">With this procedure, you may have to then restart the sample.</span></span>  
  
-   <span data-ttu-id="ef57d-112">Option 2: Aktivieren Sie Beispielprogramme im voraus.</span><span class="sxs-lookup"><span data-stu-id="ef57d-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="ef57d-113">Starten Sie den **Windows-Firewall-Systemsteuerung** Applet, und aktivieren Sie die Beispielprogramme, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="ef57d-114">Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ef57d-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="ef57d-115">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-115">You can find more detailed instructions in the following procedure.</span></span>  
  
-   <span data-ttu-id="ef57d-116">Option 3: Können aktivieren Sie einen Portbereich im voraus.</span><span class="sxs-lookup"><span data-stu-id="ef57d-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="ef57d-117">Starten Sie den **Windows-Firewall** **Systemsteuerung** Applet, und aktivieren Sie Ports 80, 443, 8000-8003 und 9000, die von den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef57d-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="ef57d-118">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="ef57d-119">Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.</span><span class="sxs-lookup"><span data-stu-id="ef57d-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="ef57d-120">Wenn Sie nicht sicher sind, verwenden Sie die erste Option.</span><span class="sxs-lookup"><span data-stu-id="ef57d-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="ef57d-121">Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ef57d-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef57d-122">Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="ef57d-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="ef57d-123">Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="ef57d-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="ef57d-124">So aktivieren Sie Beispielprogramme im Voraus</span><span class="sxs-lookup"><span data-stu-id="ef57d-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="ef57d-125">Erstellen Sie das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ef57d-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="ef57d-126">Klicken Sie auf **starten**, klicken Sie auf **ausführen**, und geben `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="ef57d-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="ef57d-127">Daraufhin wird die **Windows-Firewall-Systemsteuerung** Applet.</span><span class="sxs-lookup"><span data-stu-id="ef57d-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef57d-128">Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows-Firewall erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ef57d-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="ef57d-129">Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.</span><span class="sxs-lookup"><span data-stu-id="ef57d-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="ef57d-130">Führen Sie eine der folgenden betriebssystemabhängigen Vorgehensweisen aus, um einem Programm den Zugriff durch die Windows-Firewall zu gewähren:</span><span class="sxs-lookup"><span data-stu-id="ef57d-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    -   <span data-ttu-id="ef57d-131">Klicken Sie auf Windows 7 oder Windows Server 2008 r2 auf **können Sie ein Programm oder Feature durch die Windows-Firewall**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="ef57d-132">Klicken Sie auf **Ändern der Einstellungen**, ermöglichen **ein anderes Programm...** .</span><span class="sxs-lookup"><span data-stu-id="ef57d-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    -   <span data-ttu-id="ef57d-133">Auf [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)], klicken Sie auf **Programm durch die Windows-Firewall lassen**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="ef57d-134">Auf der **Ausnahmen** auf **Programm hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="ef57d-135">Klicken Sie auf die **Durchsuchen** Schaltfläche, und wählen Sie die ausführbare Datei des Beispiels, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="ef57d-136">Wiederholen Sie die Schritte 4 und 5, bis Sie die ausführbaren Dateien alle gewünschten Beispiele hinzugefügt haben, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ef57d-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="ef57d-137">Klicken Sie auf **OK** um das Firewall-Applet zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ef57d-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="ef57d-138">So aktivieren Sie einen Portbereich im Voraus</span><span class="sxs-lookup"><span data-stu-id="ef57d-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="ef57d-139">Klicken Sie auf **starten**, klicken Sie auf **ausführen**, und geben `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="ef57d-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="ef57d-140">Daraufhin wird die **Windows-Firewall-Systemsteuerung** Applet.</span><span class="sxs-lookup"><span data-stu-id="ef57d-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="ef57d-141">Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ef57d-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="ef57d-142">Klicken Sie auf **Erweiterte Einstellungen** in der linken Spalte des Fensters Windows-Firewall.</span><span class="sxs-lookup"><span data-stu-id="ef57d-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2.  <span data-ttu-id="ef57d-143">Klicken Sie auf **Eingangsregeln** in der linken Spalte.</span><span class="sxs-lookup"><span data-stu-id="ef57d-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3.  <span data-ttu-id="ef57d-144">Klicken Sie auf **neue Regeln** in der rechten Spalte.</span><span class="sxs-lookup"><span data-stu-id="ef57d-144">Click **New Rules** in the right column.</span></span>  
  
    4.  <span data-ttu-id="ef57d-145">Wählen Sie **Port** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-145">Select **Port** and click **next**.</span></span>  
  
    5.  <span data-ttu-id="ef57d-146">Wählen Sie **TCP** , und geben Sie `8000, 8001, 8002, 8003, 9000, 80, 443` in die **bestimmte lokale Ports** Feld.</span><span class="sxs-lookup"><span data-stu-id="ef57d-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6.  <span data-ttu-id="ef57d-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-147">Click **Next**.</span></span>  
  
    7.  <span data-ttu-id="ef57d-148">Wählen Sie **Verbindung zulassen,**, und klicken Sie auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="ef57d-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8.  <span data-ttu-id="ef57d-149">Wählen Sie **Domäne** und **Private**, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="ef57d-150">Nennen Sie die Regel `WCF-WF 4.0 Samples`, und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="ef57d-151">Klicken Sie auf **Ausgangsregeln** , und wiederholen Sie die Schritte von c bis h.</span><span class="sxs-lookup"><span data-stu-id="ef57d-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="ef57d-152">Führen Sie bei [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ef57d-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1.  <span data-ttu-id="ef57d-153">Klicken Sie auf **Programm durch die Windows-Firewall lassen**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2.  <span data-ttu-id="ef57d-154">Auf der **Ausnahmen** auf **Port hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3.  <span data-ttu-id="ef57d-155">Geben Sie einen Namen, geben Sie als Portnummer 8000 ein, und wählen die **TCP** Option.</span><span class="sxs-lookup"><span data-stu-id="ef57d-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4.  <span data-ttu-id="ef57d-156">Klicken Sie auf die **Änderungsbereich** Klicken die **Mein Netzwerk** unumgänglich (Subnetz), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef57d-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="ef57d-157">Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.</span><span class="sxs-lookup"><span data-stu-id="ef57d-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="ef57d-158">Klicken Sie auf **OK** um das Firewall-Applet zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ef57d-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef57d-159">Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="ef57d-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="ef57d-160">Öffnen Sie hierzu die **Windows-Firewall-Systemsteuerung** Applet und entfernen Sie alle Programme bzw. Ports, die von den vorherigen Prozeduren hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef57d-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
