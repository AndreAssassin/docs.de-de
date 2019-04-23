---
title: Integrieren von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 51626da6e97e346f43cfe606a5164024580a2ac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155323"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="df938-102">Integrieren von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="df938-102">Integrating with COM Applications</span></span>
<span data-ttu-id="df938-103">Windows Communication Foundation (WCF)-Dienste können direkt in den vorhandenen Code integriert werden, mithilfe des WCF-dienstmonikers.</span><span class="sxs-lookup"><span data-stu-id="df938-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="df938-104">Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df938-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df938-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="df938-105">In This Section</span></span>  
 [<span data-ttu-id="df938-106">Übersicht über die Integration von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="df938-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="df938-107">Bietet eine Übersicht über die Hauptbestandteile des Integrationsprozesses.</span><span class="sxs-lookup"><span data-stu-id="df938-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="df938-108">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="df938-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="df938-109">Um den WCF-Dienstmoniker in eine COM-Anwendung verwenden zu können, die erforderlichen attributierten Typen bei COM registriert werden, und die COM-Anwendung sowie der Moniker mit der erforderlichen Bindungskonfiguration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="df938-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="df938-110">Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="df938-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="df938-111">Erläutert, wie Sie die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments oder aus einem WS-MetadataExchange-Endpunkt abrufen.</span><span class="sxs-lookup"><span data-stu-id="df938-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="df938-112">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="df938-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="df938-113">Beschreibt, wie ein WCF-Beispiel, das mit einem WCF-WSDL-Monikers aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="df938-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="df938-114">Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen</span><span class="sxs-lookup"><span data-stu-id="df938-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="df938-115">Beschreibt das Aufrufen von WCF-Beispiel verwenden einen WCF-Moniker, der einen Mex-Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="df938-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="df938-116">Vorgehensweise: Geben Sie Anmeldeinformationen für Kanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="df938-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="df938-117">Der WCF-Dienstmoniker unterstützt die `IChannelCredentials` Schnittstelle, die eine Reihe von alternativen Methoden für die Angabe von kanalanmeldeinformationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="df938-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="df938-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="df938-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="df938-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df938-119">See also</span></span>

- [<span data-ttu-id="df938-120">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="df938-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
