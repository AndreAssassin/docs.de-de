---
title: Erweitern von WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 037182a3cb105f544e15a05f955c142ba57f62f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795538"
---
# <a name="extending-wcf"></a><span data-ttu-id="c3ba1-102">Erweitern von WCF</span><span class="sxs-lookup"><span data-stu-id="c3ba1-102">Extending WCF</span></span>
<span data-ttu-id="c3ba1-103">Mit Windows Communication Foundation (WCF) können Sie Laufzeitkomponenten ändern und erweitern, um Dienst basierte Anwendungen exakt zu steuern und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="c3ba1-104">Die Themen in diesem Abschnitt enthalten eingehende Informationen zur Erweiterbarkeitsarchitektur.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="c3ba1-105">Weitere Informationen zur grundlegenden Programmierung finden Sie unter [grundlegende WCF-Programmierung](../basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="c3ba1-105">For more information about basic programming, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3ba1-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c3ba1-106">In This Section</span></span>  
 [<span data-ttu-id="c3ba1-107">Erweitern von ServiceHost und der Dienstmodellebene</span><span class="sxs-lookup"><span data-stu-id="c3ba1-107">Extending ServiceHost and the Service Model Layer</span></span>](extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="c3ba1-108">Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="c3ba1-109">Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="c3ba1-110">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c3ba1-110">Extending Bindings</span></span>](extending-bindings.md)  
 <span data-ttu-id="c3ba1-111">Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="c3ba1-112">Bindungserweiterungen oder benutzerdefinierte Bindungen implementieren die benutzerdefinierte Kommunikationsfunktionalität, die erforderlich ist, um Anwendungsfunktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="c3ba1-113">Erweitern der Kanalschicht</span><span class="sxs-lookup"><span data-stu-id="c3ba1-113">Extending the Channel Layer</span></span>](extending-the-channel-layer.md)  
 <span data-ttu-id="c3ba1-114">Die Kanalebene liegt unterhalb der Dienstmodellebene und ist für den Austausch von Nachrichten zwischen Clients und Diensten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="c3ba1-115">Kanalerweiterungen können neue Protokollfunktionalität implementieren, zum Beispiel Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="c3ba1-116">Kanalerweiterungen transportieren außerdem Funktionalität, zum Beispiel das Implementieren eines neuen Netzwerktransports, um SOAP-Nachrichten zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="c3ba1-117">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c3ba1-117">Extending Security</span></span>](extending-security.md)  
 <span data-ttu-id="c3ba1-118">Die Sicherheit in WCF besteht aus Übertragungssicherheit (Integrität, Vertraulichkeit und Authentifizierung), Zugriffs Steuerung (Autorisierung) und Überwachung.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="c3ba1-119">Die im `IdentityModel` -Namespace gefundenen Klassen werden von WCF für die Zugriffs Steuerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="c3ba1-120">Wenn Sie die Sicherheitsarchitektur verinnerlichen, können Sie benutzerdefinierte Anspruchstypen für benutzerdefinierte Zugriffssteuerungssysteme erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="c3ba1-121">Erweitern des Metadatensystems</span><span class="sxs-lookup"><span data-stu-id="c3ba1-121">Extending the Metadata System</span></span>](extending-the-metadata-system.md)  
 <span data-ttu-id="c3ba1-122">Das WCF-Metadatensystem ist eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die für die Implementierung von Dienst basierten Anwendungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="c3ba1-123">Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="c3ba1-124">Erweitern von Encodern und Serialisierungsprogrammen</span><span class="sxs-lookup"><span data-stu-id="c3ba1-124">Extending Encoders and Serializers</span></span>](extending-encoders-and-serializers.md)  
 <span data-ttu-id="c3ba1-125">Encoder und Serialisierungsprogramme übersetzen Daten von einem Formular in ein anderes.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="c3ba1-126">In den Themen in diesem Abschnitt wird erläutert, wie Sie die angegebenen Klassen erweitern, um besondere Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c3ba1-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c3ba1-127">Referenz</span><span class="sxs-lookup"><span data-stu-id="c3ba1-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="c3ba1-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c3ba1-128">Related Sections</span></span>  
 [<span data-ttu-id="c3ba1-129">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3ba1-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="c3ba1-130">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="c3ba1-130">WCF Feature Details</span></span>](../feature-details/index.md)  
  
 [<span data-ttu-id="c3ba1-131">Richtlinien und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="c3ba1-131">Guidelines and Best Practices</span></span>](../guidelines-and-best-practices.md)
