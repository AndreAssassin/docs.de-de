---
title: Einführung in LINQ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 2900cade8bc4166cccb62baf4381cb926cdff5f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614540"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="780dc-102">Einführung in LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="780dc-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="780dc-103">Language Integrated Query (LINQ) ist eine in .NET Framework-Version 3.5 eingeführte Innovation, die die Lücke zwischen der Welt der Objekte und der Welt der Daten überbrückt.</span><span class="sxs-lookup"><span data-stu-id="780dc-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="780dc-104">Abfragen von Daten werden gewöhnlich als einfache Zeichenfolgen ohne Typüberprüfung zur Kompilierzeit und ohne IntelliSense-Unterstützung ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="780dc-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="780dc-105">Außerdem müssen Sie für jeden Datenquellentyp eine andere Abfragesprache lernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw.</span><span class="sxs-lookup"><span data-stu-id="780dc-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="780dc-106">LINQ stellt eine *Abfrage* ein erstklassiges Sprachkonstrukt in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="780dc-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="780dc-107">Sie schreiben Abfragen für stark typisierte Auflistungen von Objekten mithilfe von Sprachschlüsselwörtern und bekannten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="780dc-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="780dc-108">Sie können LINQ-Abfragen in Visual Basic schreiben, für die SQL Server-Datenbanken, XML-Dokumente, ADO.NET-Datasets und jede Auflistung von Objekten, die unterstützt <xref:System.Collections.IEnumerable> oder die generische <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="780dc-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="780dc-109">LINQ-Unterstützung wird auch von Drittanbietern für viele Webdienste und andere Datenbankimplementierungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="780dc-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="780dc-110">Sie können LINQ-Abfragen in neuen Projekten oder zusammen mit nicht-LINQ-Abfragen in vorhandenen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="780dc-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="780dc-111">Die einzige Voraussetzung ist, dass sich das Projekt auf .NET Framework 3.5 oder höher bezieht.</span><span class="sxs-lookup"><span data-stu-id="780dc-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="780dc-112">Die folgende Abbildung aus Visual Studio zeigt eine teilweise abgeschlossene LINQ-Abfrage für eine SQL Server-Datenbank in C# und Visual Basic mit vollständiger Typüberprüfung und IntelliSense-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="780dc-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagramm, Shwos eine LINQ-Abfrage mit IntelliSense-Unterstützung.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="780dc-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="780dc-114">Next Steps</span></span>  
 <span data-ttu-id="780dc-115">Finden Sie weitere Informationen über LINQ vertraut machen mit einigen grundlegenden Konzepten im Abschnitt Erste Schritte zunächst [erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), und klicken Sie dann die Dokumentation für die LINQ-Technologie, die Sie zu lesen Möchten Sie:</span><span class="sxs-lookup"><span data-stu-id="780dc-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="780dc-116">SQL Server-Datenbanken: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="780dc-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="780dc-117">XML-Dokumente: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="780dc-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="780dc-118">ADO.NET-Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="780dc-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="780dc-119">.NET-Collections, -Dateien, -Zeichenfolgen usw.: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="780dc-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780dc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="780dc-120">See also</span></span>

- [<span data-ttu-id="780dc-121">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="780dc-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
