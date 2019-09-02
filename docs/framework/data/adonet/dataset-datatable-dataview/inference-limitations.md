---
title: Rückschlusseinschränkungen
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 4e0f63776162b60c9333ba47be58ea78a9b6805d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204835"
---
# <a name="inference-limitations"></a><span data-ttu-id="1d383-102">Rückschlusseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d383-102">Inference Limitations</span></span>
<span data-ttu-id="1d383-103">Beim Herleiten eines <xref:System.Data.DataSet>-Schemas aus XML können sich in Abhängigkeit von den XML-Elementen jedes Dokuments verschiedene Schemata ergeben.</span><span class="sxs-lookup"><span data-stu-id="1d383-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="1d383-104">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d383-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="1d383-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="1d383-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d383-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="1d383-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d383-107">Bei "Document1" erzeugt der Rückschluss Prozess ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.</span><span class="sxs-lookup"><span data-stu-id="1d383-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="1d383-108">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d383-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1d383-109">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="1d383-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1d383-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="1d383-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="1d383-111">Text1</span><span class="sxs-lookup"><span data-stu-id="1d383-111">Text1</span></span>|  
|<span data-ttu-id="1d383-112">Text2</span><span class="sxs-lookup"><span data-stu-id="1d383-112">Text2</span></span>|  
  
 <span data-ttu-id="1d383-113">Bei "Document2" erzeugt der Rückschluss Prozess jedoch ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="1d383-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="1d383-114">"Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.</span><span class="sxs-lookup"><span data-stu-id="1d383-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="1d383-115">**DataSet** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="1d383-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="1d383-116">**Glaub** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d383-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="1d383-117">Element1</span><span class="sxs-lookup"><span data-stu-id="1d383-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="1d383-118">Text1</span><span class="sxs-lookup"><span data-stu-id="1d383-118">Text1</span></span>|  
  
 <span data-ttu-id="1d383-119">Es war möglicherweise beabsichtigt, dass sich für beide XML-Dokumente dasselbe XML-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="1d383-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="1d383-120">Um Abweichungen zu vermeiden, die beim Erstellen eines Schemas aus einem XML-Dokument auftreten können, empfiehlt es sich, beim Laden eines **DataSets** aus XML explizit ein Schema mit XSD (XML Schema Definition Language) oder XDR (XML-Data Reduced) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1d383-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="1d383-121">Weitere Informationen zum expliziten Angeben eines **Datasetschemas** mit XML-Schema finden Sie unter [ableiten von relationalen DataSet-Strukturen aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="1d383-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d383-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d383-122">See also</span></span>

- [<span data-ttu-id="1d383-123">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="1d383-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="1d383-124">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="1d383-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="1d383-125">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="1d383-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="1d383-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="1d383-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="1d383-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="1d383-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="1d383-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1d383-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
