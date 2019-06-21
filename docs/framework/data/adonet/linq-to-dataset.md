---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306233"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="9f5df-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9f5df-102">LINQ to DataSet</span></span>
<span data-ttu-id="9f5df-103">Mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] können Daten, die in einem <xref:System.Data.DataSet>-Objekt zwischengespeichert sind, leichter und schneller abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="9f5df-103">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="9f5df-104">Insbesondere [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] vereinfacht das Entwickler Schreiben von Abfragen von der Programmiersprache selbst, anstatt eine separate Abfragesprache mit Abfragen.</span><span class="sxs-lookup"><span data-stu-id="9f5df-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="9f5df-105">Dies ist besonders nützlich für Visual Studio-Entwickler, die nun die syntaxüberprüfung für während der Kompilierung, statische Typisierung und IntelliSense-Unterstützung, die von der Visual Studio in ihren Abfragen bereitgestellten nutzen können.</span><span class="sxs-lookup"><span data-stu-id="9f5df-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="9f5df-106">kann auch für das Abfragen von Daten verwendet werden, die aus einer oder mehreren Datenquellen konsolidiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9f5df-106">can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="9f5df-107">Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="9f5df-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="9f5df-108">Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="9f5df-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="9f5df-109">Die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Funktionen werden verfügbar gemacht, in erster Linie durch die Erweiterungsmethoden in den <xref:System.Data.DataRowExtensions> und <xref:System.Data.DataTableExtensions> Klassen.</span><span class="sxs-lookup"><span data-stu-id="9f5df-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="9f5df-110">baut auf die vorhandene ADO.NET-Architektur verwendet und ist nicht zum Ersetzen von ADO.NET in Anwendungscode vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9f5df-110">builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="9f5df-111">Vorhandener ADO.NET-Code funktioniert weiterhin in einem [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9f5df-111">Existing ADO.NET code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="9f5df-112">Die Beziehung zwischen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ADO.NET und der Store ist in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f5df-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Das Diagramm zeigt, dass LINQ to DataSet auf dem ADO.NET-Anbieter basiert.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="9f5df-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9f5df-114">In This Section</span></span>  
 [<span data-ttu-id="9f5df-115">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="9f5df-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="9f5df-116">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9f5df-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="9f5df-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="9f5df-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="9f5df-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f5df-118">See also</span></span>

- [<span data-ttu-id="9f5df-119">Language Integrated Query (LINQ) – C#</span><span class="sxs-lookup"><span data-stu-id="9f5df-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="9f5df-120">Language Integrated Query (LINQ) – Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f5df-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="9f5df-121">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9f5df-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="9f5df-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9f5df-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
