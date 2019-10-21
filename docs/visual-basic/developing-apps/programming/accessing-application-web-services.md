---
title: Zugreifen auf Anwendungswebdienste (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: faefb49e252445216bdce2e5606b1eb3fbcd430d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582012"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="9d382-102">Zugreifen auf Anwendungswebdienste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d382-102">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="9d382-103">Das `My.WebServices`-Objekt bietet eine Instanz jedes Webdienstes, auf den vom aktuellen Projekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9d382-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="9d382-104">Jede Instanz wird bei Bedarf instanziiert.</span><span class="sxs-lookup"><span data-stu-id="9d382-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="9d382-105">Sie können über die Eigenschaften des `My.WebServices`-Objekts auf diese Webdienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d382-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="9d382-106">Der Name der Eigenschaft stimmt mit dem des Webdienstes überein, auf den die Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="9d382-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="9d382-107">Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst.</span><span class="sxs-lookup"><span data-stu-id="9d382-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="9d382-108">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9d382-108">Tasks</span></span>

<span data-ttu-id="9d382-109">In der folgenden Tabelle werden Möglichkeiten zum Zugriff auf Webdienste aufgelistet, auf die eine Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="9d382-109">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="9d382-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d382-110">To</span></span>|<span data-ttu-id="9d382-111">Siehe</span><span class="sxs-lookup"><span data-stu-id="9d382-111">See</span></span>|
|---|---|
|<span data-ttu-id="9d382-112">Aufrufen eines Webdienstes</span><span class="sxs-lookup"><span data-stu-id="9d382-112">Call a Web service</span></span>|[<span data-ttu-id="9d382-113">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="9d382-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="9d382-114">Asynchrones Aufrufen eines Webdienstes und Behandeln eines Ereignisses beim Abschluss</span><span class="sxs-lookup"><span data-stu-id="9d382-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="9d382-115">Vorgehensweise: Asynchrones Aufrufen eines Webdiensts</span><span class="sxs-lookup"><span data-stu-id="9d382-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="9d382-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d382-116">See also</span></span>

- [<span data-ttu-id="9d382-117">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="9d382-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
