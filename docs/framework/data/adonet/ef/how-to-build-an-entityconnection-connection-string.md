---
title: 'Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 33a52b2542a2e312f7fbb8b7ca09a8b85662d2d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251551"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="da0b3-102">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="da0b3-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="da0b3-103">In diesem Thema wird anhand eines Beispiels gezeigt, wie eine <xref:System.Data.EntityClient.EntityConnection> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="da0b3-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="da0b3-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="da0b3-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="da0b3-105">Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]das Projekt für die Verwendung von.</span><span class="sxs-lookup"><span data-stu-id="da0b3-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="da0b3-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="da0b3-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="da0b3-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="da0b3-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="da0b3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da0b3-108">Example</span></span>  
 <span data-ttu-id="da0b3-109">Im folgenden Beispiel wird <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> für den zugrunde liegenden Anbieter initialisiert. Anschließend wird das <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>-Objekt initialisiert und an den Konstruktor der <xref:System.Data.EntityClient.EntityConnection> übergeben.</span><span class="sxs-lookup"><span data-stu-id="da0b3-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="da0b3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da0b3-110">See also</span></span>

- <span data-ttu-id="da0b3-111">[Vorgehensweise: Verwenden von EntityConnection mit einem Objekt Kontext](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="da0b3-111">[How to: Use EntityConnection with an Object Context](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="da0b3-112">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="da0b3-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
