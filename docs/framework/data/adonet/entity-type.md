---
title: Entitätstyp
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: dd1e8a7605c29b3dacaa7ccf9156af2a9b65d5b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599622"
---
# <a name="entity-type"></a><span data-ttu-id="58fc9-102">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="58fc9-102">entity type</span></span>
<span data-ttu-id="58fc9-103">Die *Entitätstyp* ist der wesentliche Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="58fc9-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="58fc9-104">In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="58fc9-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="58fc9-105">Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen.</span><span class="sxs-lookup"><span data-stu-id="58fc9-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="58fc9-106">Jede Vorlage enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="58fc9-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="58fc9-107">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="58fc9-107">A unique name.</span></span> <span data-ttu-id="58fc9-108">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="58fc9-108">(Required.)</span></span>  
  
- <span data-ttu-id="58fc9-109">Ein [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) durch eine oder mehrere Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="58fc9-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="58fc9-110">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="58fc9-110">(Required.)</span></span>  
  
- <span data-ttu-id="58fc9-111">Daten in Form von [Eigenschaften](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="58fc9-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="58fc9-112">(Optional)</span><span class="sxs-lookup"><span data-stu-id="58fc9-112">(Optional.)</span></span>  
  
- <span data-ttu-id="58fc9-113">[Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) , mit denen für die Navigation von einem [End](../../../../docs/framework/data/adonet/association-end.md) von einem [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zum anderen Ende.</span><span class="sxs-lookup"><span data-stu-id="58fc9-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="58fc9-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="58fc9-114">(Optional)</span></span>  
  
 <span data-ttu-id="58fc9-115">In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung.</span><span class="sxs-lookup"><span data-stu-id="58fc9-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="58fc9-116">Jede Instanz eines Entitätstyps muss eine eindeutige verfügen [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="58fc9-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="58fc9-117">Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="58fc9-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58fc9-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58fc9-118">Example</span></span>  
 <span data-ttu-id="58fc9-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:</span><span class="sxs-lookup"><span data-stu-id="58fc9-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Beispielmodell mit drei Entitätstypen](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="58fc9-121">Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "(Schlüssel)" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="58fc9-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="58fc9-122">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="58fc9-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="58fc9-123">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="58fc9-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="58fc9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58fc9-124">See also</span></span>

- [<span data-ttu-id="58fc9-125">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="58fc9-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="58fc9-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="58fc9-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="58fc9-127">facet</span><span class="sxs-lookup"><span data-stu-id="58fc9-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
