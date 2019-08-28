---
title: Firewall-Anweisungen
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 2c07d17ebb6bbefa78d12bb128e354112311891a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044951"
---
# <a name="firewall-instructions"></a><span data-ttu-id="1bbd0-102">Firewall-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="1bbd0-102">Firewall Instructions</span></span>
<span data-ttu-id="1bbd0-103">Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die Windows Communication Foundation (WCF)-Beispiele funktionieren können.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="1bbd0-104">In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000-8003 und über Port 9000 statt.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="1bbd0-105">Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="1bbd0-106">Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1bbd0-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
- <span data-ttu-id="1bbd0-107">Option 1: Interaktive Aktivierung von Beispielen bei der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="1bbd0-108">Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="1bbd0-109">Wenn ein Beispiel ausgeführt wird, wird das Dialogfeld **Windows-Sicherheitswarnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="1bbd0-110">Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="1bbd0-111">Möglicherweise müssen Sie das Beispiel neu starten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-111">With this procedure, you may have to then restart the sample.</span></span>  
  
- <span data-ttu-id="1bbd0-112">Option 2: Aktivieren Sie Beispiel Programme im voraus.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="1bbd0-113">Starten Sie das Applet **Windows-Firewall-Systemsteuerung** , und aktivieren Sie die Beispiel Programme, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="1bbd0-114">Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="1bbd0-115">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-115">You can find more detailed instructions in the following procedure.</span></span>  
  
- <span data-ttu-id="1bbd0-116">Option 3: Aktivieren Sie einen Port Bereich im voraus.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="1bbd0-117">Starten Sie das Applet **Windows-Firewall** - **Systemsteuerung** , und aktivieren Sie die Ports 80, 443, 8000-8003 und 9000, die von den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="1bbd0-118">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="1bbd0-119">Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="1bbd0-120">Wenn Sie nicht sicher sind, verwenden Sie die erste Option.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="1bbd0-121">Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1bbd0-122">Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="1bbd0-123">Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="1bbd0-124">So aktivieren Sie Beispielprogramme im Voraus</span><span class="sxs-lookup"><span data-stu-id="1bbd0-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="1bbd0-125">Erstellen Sie das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="1bbd0-126">Klicken Sie auf **Start**und dann auf **Ausführen**, und geben `firewall.cpl`Sie ein.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="1bbd0-127">Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1bbd0-128">Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows-Firewall erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="1bbd0-129">Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="1bbd0-130">Führen Sie eine der folgenden betriebssystemabhängigen Vorgehensweisen aus, um einem Programm den Zugriff durch die Windows-Firewall zu gewähren:</span><span class="sxs-lookup"><span data-stu-id="1bbd0-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    - <span data-ttu-id="1bbd0-131">Klicken Sie unter Windows 7 oder Windows Server 2008 R2 auf **Programm oder Feature durch Windows-Firewall zulassen**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="1bbd0-132">Klicken Sie auf **Einstellungen ändern**, **anderes Programm**zulassen....</span><span class="sxs-lookup"><span data-stu-id="1bbd0-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    - <span data-ttu-id="1bbd0-133">Klicken [!INCLUDE[wv](../../../../includes/wv-md.md)] Sie [!INCLUDE[lserver](../../../../includes/lserver-md.md)]unter oder auf **Programm durch die Windows-Firewall zulassen**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="1bbd0-134">Klicken Sie auf der Registerkarte **Ausnahmen** auf **Programm hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="1bbd0-135">Klicken Sie auf die Schaltfläche **Durchsuchen** , und wählen Sie die ausführbare Datei des Beispiels, das Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="1bbd0-136">Wiederholen Sie die Schritte 4 und 5, bis Sie die ausführbaren Dateien aller Beispiele hinzugefügt haben, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="1bbd0-137">Klicken Sie auf **OK** , um das Applet Firewall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="1bbd0-138">So aktivieren Sie einen Portbereich im Voraus</span><span class="sxs-lookup"><span data-stu-id="1bbd0-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="1bbd0-139">Klicken Sie auf **Start**und dann auf **Ausführen**, und geben `firewall.cpl`Sie ein.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="1bbd0-140">Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="1bbd0-141">Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1. <span data-ttu-id="1bbd0-142">Klicken Sie in der linken Spalte des Fensters Windows-Firewall auf **Erweiterte Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="1bbd0-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2. <span data-ttu-id="1bbd0-143">Klicken Sie in der linken Spalte auf **Eingehende Regeln** .</span><span class="sxs-lookup"><span data-stu-id="1bbd0-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3. <span data-ttu-id="1bbd0-144">Klicken Sie in der rechten Spalte auf **neue Regeln** .</span><span class="sxs-lookup"><span data-stu-id="1bbd0-144">Click **New Rules** in the right column.</span></span>  
  
    4. <span data-ttu-id="1bbd0-145">Wählen Sie **Port** , und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-145">Select **Port** and click **next**.</span></span>  
  
    5. <span data-ttu-id="1bbd0-146">Wählen Sie **TCP** aus `8000, 8001, 8002, 8003, 9000, 80, 443` , und geben Sie im Feld **bestimmte lokale Ports** ein.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6. <span data-ttu-id="1bbd0-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-147">Click **Next**.</span></span>  
  
    7. <span data-ttu-id="1bbd0-148">Wählen Sie **Verbindung zulassen**aus, und klicken Sie auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="1bbd0-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8. <span data-ttu-id="1bbd0-149">Wählen Sie **Domäne** und **Privat**aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="1bbd0-150">Benennen Sie diese `WCF-WF 4.0 Samples`Regel, und klicken Sie auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="1bbd0-151">Klicken Sie auf **ausgehende Regeln** und wiederholen Sie die Schritte c bis h.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="1bbd0-152">Führen Sie bei [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1. <span data-ttu-id="1bbd0-153">Klicken Sie auf **Programm durch die Windows-Firewall zulassen**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2. <span data-ttu-id="1bbd0-154">Klicken Sie auf der Registerkarte **Ausnahmen** auf **Port hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3. <span data-ttu-id="1bbd0-155">Geben Sie einen Namen ein, geben Sie 8000 als Portnummer ein, und wählen Sie die Option **TCP** aus.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4. <span data-ttu-id="1bbd0-156">Klicken Sie auf die Schaltfläche **Bereich ändern** , wählen Sie die Option **mein Netzwerk** (Subnetz) nur aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5. <span data-ttu-id="1bbd0-157">Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="1bbd0-158">Klicken Sie auf **OK** , um das Applet Firewall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bbd0-159">Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="1bbd0-160">Öffnen Sie hierzu das Applet **Windows-Firewall-Systemsteuerung** , und entfernen Sie alle Programme oder Port Einträge, die von den vorherigen Prozeduren hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
