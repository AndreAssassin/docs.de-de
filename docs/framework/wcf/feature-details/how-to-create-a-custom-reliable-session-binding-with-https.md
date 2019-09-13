---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 7f22eeaae39b4d9a83c77c7f3e9db1d7d3f04e8e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895198"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="fbcc6-102">Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="fbcc6-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="fbcc6-103">Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer (SSL)-Transportsicherheit mit zuverlässigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="fbcc6-104">Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="fbcc6-105">Sie aktivieren die zuverlässige Sitzung entweder Imperativ mithilfe von Code oder deklarativ in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="fbcc6-106">In dieser Prozedur werden die Client-und Dienst Konfigurationsdateien verwendet, um die zuverlässige Sitzung und das [ **\<httpsTransport->** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) Element zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="fbcc6-107">Der wesentliche Teil dieser Prozedur ist, dass das  **\<Endpunkt >** -Konfigurationselement ein `bindingConfiguration` -Attribut enthält, das auf eine Benutzer `reliableSessionOverHttps`definierte Bindungs Konfiguration mit dem Namen verweist.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="fbcc6-108">[ **Das\<Bindungs >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um anzugeben, dass eine zuverlässige Sitzung und der HTTPS-Transport verwendet  **\<werden, indem ReliableSession >** und **\<httpsTransport verwendet werden >** -Elemente.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="fbcc6-109">Die Quell Kopie dieses Beispiels finden Sie unter [benutzerdefinierte Bindung für zuverlässige Sitzung über HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="fbcc6-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="fbcc6-110">Konfigurieren des Dienstanbieter mit einer CustomBinding zur Verwendung einer zuverlässigen Sitzung mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="fbcc6-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="fbcc6-111">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="fbcc6-112">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="fbcc6-113">Beachten Sie, dass die Adresse oder die Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fbcc6-114">Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="fbcc6-115">Erstellen Sie eine *Web. config* -Datei, um einen Endpunkt `CalculatorService` für mit einer benutzerdefinierten `reliableSessionOverHttps` Bindung mit dem Namen zu konfigurieren, die eine zuverlässige Sitzung und den HTTPS-Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="fbcc6-116">Erstellen Sie eine *Service. svc* -Datei, die die folgende Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="fbcc6-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="fbcc6-117">Platzieren Sie die Datei " *Service. svc* " in Ihrem virtuellen Verzeichnis für Internetinformationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="fbcc6-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="fbcc6-118">Konfigurieren des Clients mit einer CustomBinding zur Verwendung einer zuverlässigen Sitzung mit HTTPS</span><span class="sxs-lookup"><span data-stu-id="fbcc6-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="fbcc6-119">Verwenden Sie das [Service Model Metadata Utility-Tool (*Svcutil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Befehlszeile, um Code aus Dienst Metadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="fbcc6-120">Der generierte Client enthält die `ICalculator` -Schnittstelle, die den Dienstvertrag definiert, den die Client Implementierung erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="fbcc6-121">Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="fbcc6-122">Beachten Sie, dass die Adress-und Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fbcc6-123">Sie müssen keinen Code schreiben, um die Adresse und die Bindungs Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="fbcc6-124">Konfigurieren Sie eine benutzerdefinierte `reliableSessionOverHttps` Bindung mit dem Namen, um HTTPS-Transport und zuverlässige Sitzungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="fbcc6-125">Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="fbcc6-126">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="fbcc6-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fbcc6-127">.NET Framework security</span></span>

<span data-ttu-id="fbcc6-128">Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Test Zertifikat handelt, das mit *Makecert. exe*erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie `https://localhost/servicemodelsamples/service.svc`versuchen, auf eine HTTPS-Adresse (z. b.) in Ihrem Browser zuzugreifen</span><span class="sxs-lookup"><span data-stu-id="fbcc6-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbcc6-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbcc6-129">See also</span></span>

- [<span data-ttu-id="fbcc6-130">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="fbcc6-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
