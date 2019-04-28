---
title: 'Vorgehensweise: Hinzufügen eines Datendienstverweises (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765530"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="6a2c7-102">Vorgehensweise: Hinzufügen eines Datendienstverweises (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="6a2c7-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="6a2c7-103">Sie können die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio zum Hinzufügen eines Verweises auf WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="6a2c7-104">Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="6a2c7-105">Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="6a2c7-106">Weitere Informationen finden Sie unter [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6a2c7-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="6a2c7-107">Hinzufügen eines Datendienstverweises</span><span class="sxs-lookup"><span data-stu-id="6a2c7-107">Add a data service reference</span></span>

1. <span data-ttu-id="6a2c7-108">(Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="6a2c7-109">In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Clientprojekt, und wählen Sie dann **hinzufügen** > **Dienstverweis**.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="6a2c7-110">Wenn der Datendienst Teil der aktuellen Projektmappe ist, klicken Sie auf **Discover**.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="6a2c7-111">- oder - </span><span class="sxs-lookup"><span data-stu-id="6a2c7-111">-or-</span></span>

     <span data-ttu-id="6a2c7-112">In der **Adresse** Textfeld die base-URL des Datendiensts, z. B. `http://localhost:1234/Northwind.svc`, und klicken Sie dann auf **wechseln**.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="6a2c7-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-113">Select **OK**.</span></span>

     <span data-ttu-id="6a2c7-114">Eine neue Codedatei, die die Datenklassen enthält, die Zugriff auf und Interaktion mit datendienstressourcen können wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a2c7-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a2c7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a2c7-115">See also</span></span>

- [<span data-ttu-id="6a2c7-116">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="6a2c7-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)