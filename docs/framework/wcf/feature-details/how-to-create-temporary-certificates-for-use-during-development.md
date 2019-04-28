---
title: 'Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: d45f18b0b8fe4e0cc9667091e166c80691faa2d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773294"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="c2257-102">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="c2257-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="c2257-103">Wenn Sie einen sicheren Dienst oder Client mit Windows Communication Foundation (WCF) zu entwickeln, ist es oft notwendig, geben Sie ein x. 509-Zertifikat als Anmeldeinformationen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2257-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="c2257-104">Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c2257-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="c2257-105">Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt.</span><span class="sxs-lookup"><span data-stu-id="c2257-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="c2257-106">Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c2257-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="c2257-107">Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c2257-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="c2257-108">Dieses Thema führt durch die Schritte zum Erstellen dieser beiden Zertifikate mithilfe von Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c2257-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2257-109">Die Zertifikate, die das Cmdlet "New-SelfSignedCertificate" generiert werden nur für Testzwecke bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c2257-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="c2257-110">Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2257-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="c2257-111">Dies kann entweder von einem Zertifikatserver für Windows Server in Ihrer Organisation werden oder einem Drittanbieter.</span><span class="sxs-lookup"><span data-stu-id="c2257-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="c2257-112">In der Standardeinstellung die [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) -Cmdlet erstellt die Zertifikate, die Zertifikate selbstsigniert sind, und diese Zertifikate sind unsicher.</span><span class="sxs-lookup"><span data-stu-id="c2257-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="c2257-113">Platzieren die selbstsignierten Zertifikate in der vertrauenswürdigen Stammzertifizierungsstellen ermöglicht Store Ihnen die Erstellung eine Entwicklungsumgebung, die Ihre bereitstellungsumgebung besser simuliert.</span><span class="sxs-lookup"><span data-stu-id="c2257-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="c2257-114">Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [arbeiten mit Zertifikaten](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c2257-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="c2257-115">Weitere Informationen zur Verwendung von einem Zertifikat als Anmeldeinformationen finden Sie unter [Sichern von Diensten und Clients](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c2257-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="c2257-116">Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="c2257-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="c2257-117">So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c2257-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="c2257-118">Der folgende Befehl erstellt ein selbstsigniertes Zertifikat mit dem Antragstellernamen "Stammzertifizierungsstelle" im Aktueller Benutzer persönlich Speicher.</span><span class="sxs-lookup"><span data-stu-id="c2257-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```

<span data-ttu-id="c2257-119">Wir müssen das Zertifikat in eine PFX-Datei exportieren, sodass es importiert werden kann, wo sie in einem späteren Schritt benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c2257-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="c2257-120">Wenn Sie ein Zertifikat mit dem privaten Schlüssel exportieren, ist ein Kennwort erforderlich, für den Schutz aus.</span><span class="sxs-lookup"><span data-stu-id="c2257-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="c2257-121">Wir speichern das Kennwort in einer `SecureString` und verwenden Sie die [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) Cmdlet, um das Zertifikat mit dem zugehörigen privaten Schlüssel in eine PFX-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="c2257-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="c2257-122">Wir speichern auch nur das öffentliche Zertifikat in einer CRT-Datei mithilfe der [Export-Certificate](/powershell/module/pkiclient/export-certificate) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c2257-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="c2257-123">So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat</span><span class="sxs-lookup"><span data-stu-id="c2257-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="c2257-124">Der folgende Befehl erstellt ein Testzertifikat signiertes Zertifikat der `RootCA` mit dem Antragstellernamen "SignedByRootCA" mit dem privaten Schlüssel des Ausstellers.</span><span class="sxs-lookup"><span data-stu-id="c2257-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="c2257-125">Auf ähnliche Weise speichern wir das Zertifikat mit privatem Schlüssel in eine PFX-Datei und nur den öffentlichen Schlüssel in einer CRT-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="c2257-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="c2257-126">Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="c2257-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="c2257-127">Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren.</span><span class="sxs-lookup"><span data-stu-id="c2257-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="c2257-128">Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="c2257-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="c2257-129">Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="c2257-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="c2257-130">Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung.</span><span class="sxs-lookup"><span data-stu-id="c2257-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="c2257-131">Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2257-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="c2257-132">Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.</span><span class="sxs-lookup"><span data-stu-id="c2257-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="c2257-133">So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="c2257-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="c2257-134">Öffnen Sie das Zertifikat-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="c2257-134">Open the certificate snap-in.</span></span> <span data-ttu-id="c2257-135">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="c2257-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="c2257-136">Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="c2257-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="c2257-137">Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .</span><span class="sxs-lookup"><span data-stu-id="c2257-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="c2257-138">Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="c2257-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="c2257-139">Führen Sie den Assistenten auf dem Bildschirm Anweisungen, um die RootCA.pfx in den Speicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c2257-139">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="c2257-140">Verwenden von Zertifikaten mit WCF</span><span class="sxs-lookup"><span data-stu-id="c2257-140">Using certificates With WCF</span></span>

<span data-ttu-id="c2257-141">Nach dem Einrichten der temporären Zertifikate können diese verwendet werden, um WCF-Lösungen zu entwickeln, mit denen Zertifikate als Clientanmeldeinformationstyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c2257-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="c2257-142">So gibt beispielsweise die folgende XML-Konfiguration Nachrichtensicherheit und ein Zertifikat als Clientanmeldeinformationstyp an.</span><span class="sxs-lookup"><span data-stu-id="c2257-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="c2257-143">So geben Sie ein Zertifikat als Clientanmeldeinformationstyp an</span><span class="sxs-lookup"><span data-stu-id="c2257-143">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="c2257-144">Verwenden Sie in der Konfigurationsdatei für einen Dienst die folgende XML, um den Sicherheitsmodus auf die Nachrichtenebene und den Clientanmeldeinformationstyp auf Zertifikate festzulegen:</span><span class="sxs-lookup"><span data-stu-id="c2257-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

    ```xml
    <bindings>
      <wsHttpBinding>
        <binding name="CertificateForClient">
          <security>
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

2. <span data-ttu-id="c2257-145">Verwenden Sie in der Konfigurationsdatei für einen Client das folgende XML, um anzugeben, dass das Zertifikat im Speicher des Benutzers gefunden wird, und kann durch Durchsuchen des SubjectName-Felds für den Wert "CohoWinery" gefunden werden</span><span class="sxs-lookup"><span data-stu-id="c2257-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="CertForClient">
          <clientCredentials>
            <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

<span data-ttu-id="c2257-146">Weitere Informationen zum Verwenden von Zertifikaten in WCF finden Sie unter [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c2257-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="c2257-147">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c2257-147">.NET Framework security</span></span>

<span data-ttu-id="c2257-148">Achten Sie darauf, alle temporären Stammzertifizierungsstellen-Zertifikate aus den Ordnern **Vertrauenswürdige Stammzertifizierungsstellen** und **Persönlich** zu löschen, indem Sie mit der rechten Maustaste auf das Zertifikat klicken und anschließend auf **Löschen**klicken.</span><span class="sxs-lookup"><span data-stu-id="c2257-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2257-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2257-149">See also</span></span>

- [<span data-ttu-id="c2257-150">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="c2257-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="c2257-151">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in</span><span class="sxs-lookup"><span data-stu-id="c2257-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="c2257-152">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c2257-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)
