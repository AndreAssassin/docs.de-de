---
title: UriTemplate-Beispiel
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 5f8a969a9ddea633d12ebe2d922c152dbb0d7241
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322614"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="d0bff-102">UriTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0bff-102">UriTemplate Sample</span></span>
<span data-ttu-id="d0bff-103">Die <xref:System.UriTemplate>-Klasse stellt Methoden zum Arbeiten mit Sätzen von URIs bereit, die eine gemeinsame Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0bff-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="d0bff-104">In diesem Beispiel werden die folgenden Schlüsselkonzepte für die `UriTemplate`-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="d0bff-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="d0bff-105">Syntax zum Erstellen von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="d0bff-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="d0bff-106">Instanziieren von URIs aus einer `UriTemplate` mit <xref:System.UriTemplate.BindByName%2A> und <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0bff-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <xref:System.UriTemplateTable.Match%2A><span data-ttu-id="d0bff-107">, dies ist die Umkehroperation `BindByName` und `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="d0bff-107">, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d0bff-108">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d0bff-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d0bff-109">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d0bff-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="d0bff-110">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d0bff-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0bff-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d0bff-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d0bff-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d0bff-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d0bff-113">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d0bff-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d0bff-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d0bff-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="d0bff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0bff-115">See also</span></span>

- [<span data-ttu-id="d0bff-116">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0bff-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="d0bff-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="d0bff-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
