---
title: 'Vorgehensweise: Dynamisches Erstellen einer neuen Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: 92db9bdb209a542cc4fa269b35bfa98f8f20d2b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940084"
---
# <a name="how-to-dynamically-create-a-database"></a><span data-ttu-id="e64a5-102">Vorgehensweise: Dynamisches Erstellen einer neuen Datenbank</span><span class="sxs-lookup"><span data-stu-id="e64a5-102">How to: Dynamically Create a Database</span></span>
<span data-ttu-id="e64a5-103">In LINQ to SQL wird einer relationalen Datenbank ein Objektmodell zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e64a5-103">In LINQ to SQL, an object model is mapped to a relational database.</span></span> <span data-ttu-id="e64a5-104">Das Mapping wird durch attributbasiertes Mapping oder eine externe Mappingdatei zur Beschreibung der Struktur der relationalen Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e64a5-104">Mapping is enabled by using attribute-based mapping or an external mapping file to describe the structure of the relational database.</span></span> <span data-ttu-id="e64a5-105">In beiden Szenarien sind genügend Informationen über die relationale Datenbank vorhanden, dass mithilfe der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode eine neue Instanz der Datenbank erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e64a5-105">In both scenarios, there is enough information about the relational database that you can create a new instance of the database using the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e64a5-106">Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode erstellt nur in dem Umfang ein Replikat der Datenbank, in dem Informationen im Objektmodell codiert sind.</span><span class="sxs-lookup"><span data-stu-id="e64a5-106">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a replica of the database only to the extent of the information encoded in the object model.</span></span> <span data-ttu-id="e64a5-107">Mappingdateien und -attribute aus dem Objektmodell können möglicherweise nicht alle Informationen zur Struktur einer vorhandenen Datenbank codieren.</span><span class="sxs-lookup"><span data-stu-id="e64a5-107">Mapping files and attributes from your object model might not encode everything about the structure of an existing database.</span></span> <span data-ttu-id="e64a5-108">Mappinginformationen stellen nicht den Inhalt von benutzerdefinierten Funktionen, gespeicherten Prozeduren, Triggern und CHECK-Einschränkungen dar.</span><span class="sxs-lookup"><span data-stu-id="e64a5-108">Mapping information does not represent the contents of user-defined functions, stored procedures, triggers, or check constraints.</span></span> <span data-ttu-id="e64a5-109">Dieses Verhalten ist für eine Vielzahl von Datenbanken ausreichend.</span><span class="sxs-lookup"><span data-stu-id="e64a5-109">This behavior is sufficient for a variety of databases.</span></span>  
  
 <span data-ttu-id="e64a5-110">Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode kann in einer Vielzahl von Szenarien verwendet werden, insbesondere dann, wenn ein bekannter Datenanbieter wie Microsoft SQL Server 2008 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e64a5-110">You can use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method in any number of scenarios, especially if a known data provider like Microsoft SQL Server 2008 is available.</span></span> <span data-ttu-id="e64a5-111">Zu den typischen Szenarien zählen:</span><span class="sxs-lookup"><span data-stu-id="e64a5-111">Typical scenarios include the following:</span></span>  
  
- <span data-ttu-id="e64a5-112">Sie erstellen eine Anwendung, die sich automatisch auf einem Kundensystem installiert.</span><span class="sxs-lookup"><span data-stu-id="e64a5-112">You are building an application that automatically installs itself on a customer system.</span></span>  
  
- <span data-ttu-id="e64a5-113">Sie erstellen eine Clientanwendung, die eine lokale Datenbank benötigt, um den Offlinezustand zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e64a5-113">You are building a client application that needs a local database to save its offline state.</span></span>  
  
 <span data-ttu-id="e64a5-114">Sie können die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode auch in Verbindung mit SQL Server nutzen, indem Sie (je nach Verbindungszeichenfolge) eine MDF-Datei oder einen Katalognamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e64a5-114">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method with SQL Server by using an .mdf file or a catalog name, depending on your connection string.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e64a5-115">definiert mithilfe der Verbindungszeichenfolge die zu erstellende Datenbank und den zu verwendenden Server.</span><span class="sxs-lookup"><span data-stu-id="e64a5-115">uses the connection string to define the database to be created and on which server the database is to be created.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e64a5-116">Falls möglich, sollte die integrierte Sicherheit von Windows für die Verbindung mit der Datenbank verwendet werden, sodass in der Verbindungszeichenfolge keine Kennwörter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e64a5-116">Whenever possible, use Windows Integrated Security to connect to the database so that passwords are not required in the connection string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e64a5-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e64a5-117">Example</span></span>  
 <span data-ttu-id="e64a5-118">Der folgende Code bietet ein Beispiel für die Erstellung einer neuen Datenbank mit dem Namen "MyDVDs.mdf".</span><span class="sxs-lookup"><span data-stu-id="e64a5-118">The following code provides an example of how to create a new database named MyDVDs.mdf.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="e64a5-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e64a5-119">Example</span></span>  
 <span data-ttu-id="e64a5-120">Das Objektmodell kann verwendet werden, um wie folgt eine Datenbank zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e64a5-120">You can use the object model to create a database by doing the following:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="e64a5-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e64a5-121">Example</span></span>  
 <span data-ttu-id="e64a5-122">Beim Erstellen einer Anwendung, die auf einem Kundensystem automatisch installiert wird, sollte überprüft werden, ob die Datenbank bereits existiert. In diesem Fall sollte sie vor der Erstellung einer neuen Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e64a5-122">When building an application that automatically installs itself on a  customer system, see if the database already exists and drop it before creating a new one.</span></span> <span data-ttu-id="e64a5-123">Die <xref:System.Data.Linq.DataContext>-Klasse stellt die <xref:System.Data.Linq.DataContext.DatabaseExists%2A>-Methode und die <xref:System.Data.Linq.DataContext.DeleteDatabase%2A>-Methode bereit, um diesen Prozess zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="e64a5-123">The <xref:System.Data.Linq.DataContext> class provides the <xref:System.Data.Linq.DataContext.DatabaseExists%2A> and <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> methods to help you with this process.</span></span>  
  
 <span data-ttu-id="e64a5-124">Im folgenden Beispiel wird eine Möglichkeit dargestellt, wie diese Methoden verwendet werden können, um diesen Ansatz zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="e64a5-124">The following example shows one way these methods can be used to implement this approach:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="e64a5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e64a5-125">See also</span></span>

- [<span data-ttu-id="e64a5-126">Attributbasierte Zuordnung</span><span class="sxs-lookup"><span data-stu-id="e64a5-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [<span data-ttu-id="e64a5-127">External Mapping (Externe Zuordnung)</span><span class="sxs-lookup"><span data-stu-id="e64a5-127">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [<span data-ttu-id="e64a5-128">SQL-CLR-Typenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e64a5-128">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [<span data-ttu-id="e64a5-129">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="e64a5-129">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="e64a5-130">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="e64a5-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
