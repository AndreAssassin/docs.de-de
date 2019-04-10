---
title: Lokaler Kanal
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 1711909ada4756dd2723f62160eef0ad12c03174
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333222"
---
# <a name="local-channel"></a><span data-ttu-id="2934f-102">Lokaler Kanal</span><span class="sxs-lookup"><span data-stu-id="2934f-102">Local Channel</span></span>
<span data-ttu-id="2934f-103">Lokale Kanal ist ein Windows Communication Foundation (WCF)-Transportkanal, der für die Kommunikation innerhalb derselben Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2934f-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="2934f-104">Dies ist nützlich bei Szenarien, in denen der Client und der Dienst in der gleichen Anwendungsdomäne ausgeführt werden und der Mehraufwand eines normalen WCF-Kanalstapels (Serialisierung und Deserialisierung von Meldungen) vermieden werden muss.</span><span class="sxs-lookup"><span data-stu-id="2934f-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2934f-105">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="2934f-105">Demonstrates</span></span>  
 <span data-ttu-id="2934f-106">Lokaler Kanal</span><span class="sxs-lookup"><span data-stu-id="2934f-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2934f-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="2934f-107">Discussion</span></span>  
 <span data-ttu-id="2934f-108">Das Beispiel umfasst zwei Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="2934f-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="2934f-109">**LocalChannel**: Die programmgesteuerte Darstellung des lokalen Kanals in der aktuellen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2934f-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="2934f-110">In diesem Projekt fügt die sendende Komponente die Nachricht einer Warteschlange im Arbeitsspeicher hinzu. Die empfangende Komponente ruft die Nachricht aus der Warteschlange ab, um sie zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="2934f-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="2934f-111">**ClientAndService**: Dieses Projekt hostet einen Dienst in einer Konsolenanwendung und führt dann einen Client, um den Dienst von innerhalb der gleichen Anwendungsdomäne aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2934f-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="2934f-112">Aufgrund des Entwurfs des lokalen Kanals werden Kanalstapel und Serialisierungsvorgang ausgelassen, um die Geschwindigkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="2934f-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="2934f-113">Der lokale Transportkanal wird mit einer Warteschlange implementiert, mit der Dienstaufrufe vom Client zum Dienst transportiert und der Wert zum Client zurückgesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2934f-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="2934f-114">Im Beispiel werden die Objekte kopiert, statt Parameter und Rückgabewerte zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="2934f-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2934f-115">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="2934f-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2934f-116">Erstellen Sie die Projektmappe LocalChannel, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="2934f-116">Build and run the LocalChannel solution.</span></span>  
  
2. <span data-ttu-id="2934f-117">Der Diensthost wird gestartet, und der Client ruft den Dienst mithilfe des lokalen Kanals auf.</span><span class="sxs-lookup"><span data-stu-id="2934f-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="2934f-118">Ein Konsolenfenster mit den Ergebnissen des Dienstaufrufs wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2934f-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2934f-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2934f-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2934f-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2934f-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2934f-121">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="2934f-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2934f-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2934f-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
