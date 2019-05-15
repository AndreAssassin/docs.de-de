---
title: Serialisierung in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 1f90a128ef6b29acbd315beae7aaaf1d1b78a62b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638843"
---
# <a name="serialization-in-net"></a><span data-ttu-id="eb4a1-102">Serialisierung in .NET</span><span class="sxs-lookup"><span data-stu-id="eb4a1-102">Serialization in .NET</span></span>
<span data-ttu-id="eb4a1-103">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="eb4a1-104">Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="eb4a1-105">Zusammen ermöglichen es diese Prozesse, dass Daten einfach gespeichert und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="eb4a1-106">Zwei Serialisierungstechnologien für .NET-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="eb4a1-106">.NET features two serialization technologies:</span></span>  
  
- <span data-ttu-id="eb4a1-107">Bei der binären Serialisierung wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="eb4a1-108">So können Sie z.&amp;#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="eb4a1-109">Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="eb4a1-110">Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="eb4a1-111">Bei der XML-Serialisierung werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="eb4a1-112">Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="eb4a1-113">Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="eb4a1-114">Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb4a1-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eb4a1-115">In This Section</span></span>  
[<span data-ttu-id="eb4a1-116">Vorgehensweise-Themen zur Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eb4a1-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="eb4a1-117">Enthält Links zu Gewusst-wie-Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="eb4a1-118">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eb4a1-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="eb4a1-119">Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="eb4a1-120">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eb4a1-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="eb4a1-121">Beschreibt den XML- und SOAP-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="eb4a1-122">Serialisierungstools</span><span class="sxs-lookup"><span data-stu-id="eb4a1-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="eb4a1-123">Diese Tools sind hilfreich bei der Entwicklung von Serialisierungscode.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="eb4a1-124">Serialisierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="eb4a1-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="eb4a1-125">In den Beispielen wird veranschaulicht, wie die Serialisierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="eb4a1-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="eb4a1-126">Reference</span></span>
<span data-ttu-id="eb4a1-127"><xref:System.Runtime.Serialization> Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="eb4a1-128">Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="eb4a1-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>
