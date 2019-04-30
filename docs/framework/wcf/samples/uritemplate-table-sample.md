---
title: Beispiel zur UriTemplate-Tabelle
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: 4543d4676344d10c3e380c3522a7ca5a6a8d6294
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006446"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="fbfa4-102">Beispiel zur UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="fbfa4-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="fbfa4-103">Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von `UriTemplate`-Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="fbfa4-104">Bestimmte URIs (Uniform Resource Identifiers) können effizient mit allen Vorlagen in der Tabelle verglichen und die zur gefundenen Vorlage gehörenden Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="fbfa4-105">Dieses Beispiel demonstriert die folgenden Grundbegriffe bezüglich der `UriTemplateTable`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="fbfa4-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="fbfa4-106">Die Syntax zum Instanziieren einer `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="fbfa4-107">Das Auffüllen einer `UriTemplateTable` mit einem Satz von Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="fbfa4-108">Das Vergleichen eines möglichen URI mit der Tabelle per <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fbfa4-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fbfa4-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="fbfa4-110">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="fbfa4-111">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fbfa4-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fbfa4-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fbfa4-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fbfa4-114">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fbfa4-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fbfa4-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="fbfa4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbfa4-116">See also</span></span>

- [<span data-ttu-id="fbfa4-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="fbfa4-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="fbfa4-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="fbfa4-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
