---
title: 'Entschärfung: WCF-Dienste und Zertifikatauthentifizierung'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f94cabb482a237395854fcdc91df476c567069c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599509"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="cec00-102">Entschärfung: WCF-Dienste und Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="cec00-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="cec00-103">.NET Framework 4.6 fügt der Standardliste des WCF-SSL-Protokolls TLS 1.1 und TLS 1.2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="cec00-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="cec00-104">Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="cec00-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="cec00-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="cec00-105">Impact</span></span>  
 <span data-ttu-id="cec00-106">TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht.</span><span class="sxs-lookup"><span data-stu-id="cec00-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="cec00-107">Wenn ein Kunde ein SSL-Zertifikat verwendet, das MD5 als Hashalgorithmus einsetzt, kann der WCF-Client daher keine Verbindung mit dem WCF-Dienst herstellen.</span><span class="sxs-lookup"><span data-stu-id="cec00-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="cec00-108">Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="cec00-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="cec00-109">Minderung</span><span class="sxs-lookup"><span data-stu-id="cec00-109">Mitigation</span></span>  
 <span data-ttu-id="cec00-110">Sie können dieses Problem umgehen, sodass ein WCF-Client eine Verbindung mit einem WCF-Server herstellen kann, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cec00-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
- <span data-ttu-id="cec00-111">Aktualisieren Sie das Zertifikat so, dass der MD5-Algorithmus nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cec00-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="cec00-112">Dies ist die empfohlene Lösung.</span><span class="sxs-lookup"><span data-stu-id="cec00-112">This is the recommended solution.</span></span>  
  
- <span data-ttu-id="cec00-113">Wenn die Bindung im Quellcode nicht dynamisch konfiguriert ist, aktualisieren Sie die Konfigurationsdatei der Anwendung für die Verwendung von TLS 1.1 oder einer früheren Version des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="cec00-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="cec00-114">Dadurch können Sie weiterhin ein Zertifikat mit MD5-Hashalgorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="cec00-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="cec00-115">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="cec00-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="cec00-116">In der folgenden Konfigurationsdatei wird so vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="cec00-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
- <span data-ttu-id="cec00-117">Wenn die Bindung im Quellcode dynamisch konfiguriert ist, aktualisieren Sie die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>-Eigenschaft für die Verwendung von TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) oder einer früheren Version des Protokolls im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="cec00-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="cec00-118">Diese Problemumgehung wird nicht empfohlen, da ein Zertifikat mit MD5-Hashalgorithmus als unsicher angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="cec00-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec00-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cec00-119">See also</span></span>

- [<span data-ttu-id="cec00-120">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cec00-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
