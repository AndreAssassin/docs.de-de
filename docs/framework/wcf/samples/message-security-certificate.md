---
title: Nachrichtensicherheitszertifikat
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: b5a36d39e6e38f121bf3155c822681fb198f0850
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306273"
---
# <a name="message-security-certificate"></a><span data-ttu-id="33df8-102">Nachrichtensicherheitszertifikat</span><span class="sxs-lookup"><span data-stu-id="33df8-102">Message Security Certificate</span></span>
<span data-ttu-id="33df8-103">Dieses Beispiel zeigt, wie eine Anwendung implementiert wird, die WS-Sicherheit mit X.509 v3-Zertifikatauthentifizierung für den Client verwendet und eine Serverauthentifizierung über das X.509 v3-Zertifikat des Servers erfordert.</span><span class="sxs-lookup"><span data-stu-id="33df8-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="33df8-104">Es werden Standardeinstellungen so verwendet, dass alle Anwendungsnachrichten zwischen dem Client und dem Server signiert und verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="33df8-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="33df8-105">Dieses Beispiel basiert auf der [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) und besteht aus einem clientkonsolenprogramm und einer von IIS (Internetinformationsdienste) gehosteten Dienstbibliothek.</span><span class="sxs-lookup"><span data-stu-id="33df8-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="33df8-106">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33df8-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="33df8-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="33df8-108">Das Beispiel zeigt, wie die Authentifizierung mithilfe der Konfiguration gesteuert und wie die Identität des Aufrufers aus dem Sicherheitskontext ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="33df8-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="33df8-109">Der Dienst macht einen Endpunkt für die Kommunikation mit dem Dienst und einen Endpunkt für das Verfügbarmachen des WSDL-Dokuments des Diensts mithilfe des WS-MetadataExchange-Protokolls verfügbar, das in der Konfigurationsdatei (Web.config) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="33df8-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="33df8-110">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="33df8-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="33df8-111">Die Bindung konfiguriert ist, mit einer normalen [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) -Element, das standardmäßig nachrichtensicherheit.</span><span class="sxs-lookup"><span data-stu-id="33df8-111">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="33df8-112">In diesem Beispiel wird das `clientCredentialType`-Attribut auf "Certificate" festgelegt, um die Clientauthentifizierung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="33df8-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="33df8-113">Das Verhalten gibt die Anmeldeinformationen des Diensts an, die verwendet werden, wenn der Client den Dienst authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="33df8-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="33df8-114">Der Serverzertifikat-Antragstellername wird angegeben, der `findValue` -Attribut in der [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) Element.</span><span class="sxs-lookup"><span data-stu-id="33df8-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="33df8-115">Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="33df8-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="33df8-116">Die Clientbindung wird mit dem entsprechenden Sicherheitsmodus und Authentifizierungsmodus konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="33df8-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="33df8-117">Stellen Sie beim Ausführen in einem computerübergreifenden Szenario sicher, dass die Dienstendpunktadresse entsprechend geändert wird.</span><span class="sxs-lookup"><span data-stu-id="33df8-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="33df8-118">Die Clientimplementierung kann das zu verwendende Zertifikat entweder durch die Konfigurationsdatei oder durch Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="33df8-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="33df8-119">Im folgenden Beispiel wird gezeigt, wie das zu verwendende Zertifikat in der Konfigurationsdatei festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="33df8-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="33df8-120">Im folgenden Beispiel wird gezeigt, wie der Dienst im Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="33df8-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="33df8-121">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33df8-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="33df8-122">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="33df8-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="33df8-123">Mit der in den Beispielen für Nachrichtensicherheit enthaltenen Batchdatei Setup.bat können Sie den Client und den Server mit relevanten Zertifikaten zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="33df8-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="33df8-124">Die Batchdatei kann in drei Modi ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33df8-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="33df8-125">In den Typ für die einzelnen Computer ausführen **"Setup.bat"** im Developer-Eingabeaufforderung für Visual Studio; für den Dienstmodus **setup.bat Service**; und für den clientmodustyp **setup.bat Client**.</span><span class="sxs-lookup"><span data-stu-id="33df8-125">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="33df8-126">Verwenden Sie den Client- und den Dienstmodus, wenn Sie das Beispiel computerübergreifend ausführen.</span><span class="sxs-lookup"><span data-stu-id="33df8-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="33df8-127">Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="33df8-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="33df8-128">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="33df8-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
-   <span data-ttu-id="33df8-129">Erstellen des Clientzertifikats.</span><span class="sxs-lookup"><span data-stu-id="33df8-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="33df8-130">Die folgende Zeile in der Batchdatei erstellt das Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="33df8-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="33df8-131">Der angegebene Clientname wird im Antragstellernamen des erstellten Zertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="33df8-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="33df8-132">Das Zertifikat wird im `My`-Speicher am Speicherort `CurrentUser` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33df8-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="33df8-133">Installieren Sie das Clientzertifikat im Speicher für vertrauenswürdige Zertifikate des Servers.</span><span class="sxs-lookup"><span data-stu-id="33df8-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="33df8-134">Die folgende Zeile in der Batchdatei kopiert das Clientzertifikat in den Speicher TrustedPeople des Servers, damit der Server selbst entscheiden kann, was vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="33df8-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="33df8-135">In der Reihenfolge im Speicher TrustedPeople installiertes Zertifikat für einen von einem Windows Communication Foundation (WCF)-Dienst als vertrauenswürdig eingestuft werden, muss der Clientzertifikat-Validierungsmodus auf festgelegt werden `PeerOrChainTrust` oder `PeerTrust`.</span><span class="sxs-lookup"><span data-stu-id="33df8-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="33df8-136">Wie dies mithilfe einer Konfigurationsdatei durchgeführt werden kann, wurde im vorherigen Dienstkonfigurationsbeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="33df8-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
-   <span data-ttu-id="33df8-137">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="33df8-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="33df8-138">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="33df8-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="33df8-139">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="33df8-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="33df8-140">Das Zertifikat wird im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33df8-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="33df8-141">Wenn die Batchdatei "Setup.bat" mit einem dienstargument ausgeführt wird (z. B. **setup.bat Service**) enthält die %server_name% den vollqualifizierten Domänennamen des Computers.</span><span class="sxs-lookup"><span data-stu-id="33df8-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="33df8-142">Andernfalls wird standardmäßig localhost verwendet.</span><span class="sxs-lookup"><span data-stu-id="33df8-142">Otherwise it defaults to localhost.</span></span>  
  
-   <span data-ttu-id="33df8-143">Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.</span><span class="sxs-lookup"><span data-stu-id="33df8-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="33df8-144">Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="33df8-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="33df8-145">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="33df8-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="33df8-146">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="33df8-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="33df8-147">Gewähren von Berechtigungen auf dem privaten Schlüssel des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="33df8-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="33df8-148">Die folgenden Zeilen in der Datei Setup.bat sorgen dafür, dass das Serverzertifikat, das im Speicher LocalMachine gespeichert ist, für das [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Arbeitsprozesskonto verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="33df8-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="33df8-149">Bei Verwendung einer anderen als der englischsprachigen US-Version von Windows müssen Sie in der Datei Setup.bat den Kontonamen "NT AUTHORITY\NETWORK SERVICE" durch den äquivalenten Kontonamen in der entsprechenden Sprache ersetzen.</span><span class="sxs-lookup"><span data-stu-id="33df8-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33df8-150">In dieser Batchdatei verwendete Tools befinden sich entweder unter C:\Programme\Microsoft Visual Studio 8\Common7\tools oder unter C:\Programme\Microsoft SDKs\Windows\v6.0\bin.</span><span class="sxs-lookup"><span data-stu-id="33df8-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="33df8-151">Eines dieser Verzeichnisse muss im Systempfad enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="33df8-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="33df8-152">Wenn Sie Visual Studio installiert haben, ist die einfachste Möglichkeit zum Abrufen dieses Verzeichnis in Ihrem Pfad, um Developer-Eingabeaufforderung für Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="33df8-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="33df8-153">Klicken Sie auf **starten**, und wählen Sie dann **Programme**, **Visual Studio 2012**, **Tools**.</span><span class="sxs-lookup"><span data-stu-id="33df8-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="33df8-154">Innerhalb dieser Eingabeaufforderung sind die entsprechenden Pfade bereits konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="33df8-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="33df8-155">Andernfalls müssen Sie dem Pfad das entsprechende Verzeichnis manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="33df8-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33df8-156">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="33df8-157">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="33df8-157">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33df8-158">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="33df8-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33df8-159">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="33df8-159">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="33df8-160">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="33df8-160">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="33df8-161">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="33df8-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="33df8-162">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="33df8-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="33df8-163">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="33df8-163">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="33df8-164">Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie Setup.bat aus dem beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="33df8-164">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="33df8-165">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="33df8-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33df8-166">Die Batchdatei "Setup.bat" wird einer Developer-Eingabeaufforderung für Visual Studio ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="33df8-166">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="33df8-167">Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="33df8-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="33df8-168">Diese Umgebungsvariable wird automatisch innerhalb einer Developer-Eingabeaufforderung für Visual Studio (2010) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="33df8-168">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="33df8-169">Überprüfen des Zugriffs auf den Dienst über einen Browser unter Eingabe der Adresse `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="33df8-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="33df8-170">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="33df8-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="33df8-171">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33df8-171">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="33df8-172">Wenn der Client und Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="33df8-172">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="33df8-173">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="33df8-173">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="33df8-174">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="33df8-174">Create a directory on the service computer.</span></span> <span data-ttu-id="33df8-175">Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="33df8-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="33df8-176">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="33df8-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="33df8-177">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="33df8-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="33df8-178">Kopieren Sie auch die Dateien Setup.bat, Cleanup.bat und ImportClientCert.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="33df8-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="33df8-179">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="33df8-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="33df8-180">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="33df8-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="33df8-181">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="33df8-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="33df8-182">Führen Sie auf dem Server **setup.bat Service** in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="33df8-182">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="33df8-183">Ausführung **"Setup.bat"** mit der **Service** Argument wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und das Dienstzertifikat in die Datei Service.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="33df8-184">Bearbeiten Sie die Datei "Web.config", um den neuen Zertifikatnamen (im der `findValue` -Attribut in der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) die ist identisch mit den vollständig qualifizierten Domänennamen des Computers.</span><span class="sxs-lookup"><span data-stu-id="33df8-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="33df8-185">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="33df8-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="33df8-186">Führen Sie auf dem Client **setup.bat Client** in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="33df8-186">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="33df8-187">Ausführung **"Setup.bat"** mit der **Client** Argument wird ein Clientzertifikat mit dem Namen Client.com erstellt und das Clientzertifikat in der Datei Client.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="33df8-188">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="33df8-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="33df8-189">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="33df8-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="33df8-190">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="33df8-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="33df8-191">Auf dem Client importservicecert.bat aus in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="33df8-191">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="33df8-192">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="33df8-193">Auf dem Server "importclientcert.bat" im Developer-Eingabeaufforderung für Visual Studio mit Administratorberechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="33df8-193">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="33df8-194">Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="33df8-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="33df8-195">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="33df8-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="33df8-196">Wenn der Client und Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="33df8-196">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="33df8-197">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="33df8-197">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="33df8-198">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="33df8-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33df8-199">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="33df8-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="33df8-200">Wenn Sie Windows Communication Foundation (WCF)-Beispiele, die Zertifikate computerübergreifend verwenden ausgeführt haben, achten Sie darauf, dass Sie die Dienstzertifikate entfernen, die in den Speicher CurrentUser – trustedpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33df8-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="33df8-201">Zu diesem Zweck verwenden Sie den folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Zum Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="33df8-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
