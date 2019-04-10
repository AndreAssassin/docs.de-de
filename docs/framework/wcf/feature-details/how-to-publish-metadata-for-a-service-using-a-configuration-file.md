---
title: 'Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei'
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: 367ebeee5c12d809a758f1bee73dfaadda85788d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295535"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="d8eb4-102">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d8eb4-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="d8eb4-103">Dies ist eines der beiden Gewusst-wie-Themen, die Veröffentlichung von Metadaten für einen Windows Communication Foundation (WCF)-Dienst zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-103">This is one of two how-to topics that demonstrate publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="d8eb4-104">Es gibt zwei Möglichkeiten, wie ein Dienst Metadaten veröffentlichen kann: mit einer Konfigurationsdatei und mit Code.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="d8eb4-105">In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d8eb4-106">In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="d8eb4-107">Jeder Client kann Metadaten vom Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="d8eb4-108">Wenn Sie den Dienst zum Veröffentlichen von Metadaten auf sichere Weise benötigen, finden Sie unter [benutzerdefinierte sicheren-Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="d8eb4-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="d8eb4-109">Weitere Informationen zum Veröffentlichen von Metadaten im Code finden Sie unter [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span><span class="sxs-lookup"><span data-stu-id="d8eb4-109">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="d8eb4-110">Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS-Transfer-GET-Anforderung oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="d8eb4-111">Um sicherzustellen, dass der Code funktioniert, erstellen Sie einen grundlegenden WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-111">To be sure that the code is working, create a basic WCF service.</span></span> <span data-ttu-id="d8eb4-112">Der Einfachheit halber wird im folgenden Code ein grundlegender, selbst gehosteter Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="d8eb4-113">Dieser Dienst ist ein selbst gehosteter Dienst, der mit einer Konfigurationsdatei konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="d8eb4-114">Die folgende Konfigurationsdatei dient als Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-114">The following configuration file serves as a starting point.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="d8eb4-115">So veröffentlichen Sie Metadaten für einen WCF-Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d8eb4-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1. <span data-ttu-id="d8eb4-116">Erstellen Sie in der App.config-Datei, nachdem Sie das `</services>`-Element geschlossen haben, ein `<behaviors>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  

2. <span data-ttu-id="d8eb4-117">Fügen Sie im `<behaviors>`-Element ein `<serviceBehaviors>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  

3. <span data-ttu-id="d8eb4-118">Fügen Sie ein `<behavior>`-Element zum `<serviceBehaviors>`-Element hinzu, und geben Sie einen Wert für das `name`-Attribut des `<behavior>`-Elements an.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  

4. <span data-ttu-id="d8eb4-119">Fügen Sie dem `<serviceMetadata>`-Element ein `<behavior>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="d8eb4-120">Legen Sie das `httpGetEnabled`-Attribut auf `true` und das `policyVersion`-Attribut auf Policy15 fest.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> `httpGetEnabled` <span data-ttu-id="d8eb4-121">ermöglicht dem Dienst, auf die Metadatenanforderungen einer HTTP GET-Anforderung zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-121">allows the service to respond to metadata requests made by an HTTP GET request.</span></span> `policyVersion` <span data-ttu-id="d8eb4-122">weist den Dienst, um WS-Richtlinie 1.5 zu entsprechen, bei der Erstellung von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-122">tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  

5. <span data-ttu-id="d8eb4-123">Fügen Sie dem `behaviorConfiguration`-Element ein `<service>`-Attribut hinzu, und geben Sie das `name`-Attribut des in Schritt&amp;#160;1 hinzugefügten `<behavior>`-Elements an, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6. <span data-ttu-id="d8eb4-124">Fügen Sie ein oder mehrere `<endpoint>`-Elemente hinzu, wobei der Vertrag auf `IMetadataExchange` festgelegt ist, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7. <span data-ttu-id="d8eb4-125">Legen Sie für die im vorherigen Schritt hinzugefügten Metadatenendpunkte das `binding`-Attribut auf einen der folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="d8eb4-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    -   `mexHttpBinding` <span data-ttu-id="d8eb4-126">für HTTP-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-126">for HTTP publication.</span></span>  
  
    -   `mexHttpsBinding` <span data-ttu-id="d8eb4-127">für HTTPS-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-127">for HTTPS publication.</span></span>  
  
    -   `mexNamedPipeBinding` <span data-ttu-id="d8eb4-128">für benannte pipeveröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-128">for named pipe publication.</span></span>  
  
    -   `mexTcpBinding` <span data-ttu-id="d8eb4-129">für TCP-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-129">for TCP publication.</span></span>  
  
8. <span data-ttu-id="d8eb4-130">Legen Sie die Adressen für die in einem vorherigen Schritt hinzugefügten Metadatenendpunkte auf Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="d8eb4-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    -   <span data-ttu-id="d8eb4-131">Eine leere Zeichenfolge, um die Basisadresse der Hostanwendung als Veröffentlichungspunkt zu verwenden, wenn die Basisadresse gleich der Metadatenbindung ist.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    -   <span data-ttu-id="d8eb4-132">Eine relative Adresse, wenn die Hostanwendung über eine Basisadresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-132">A relative address if the host application has a base address.</span></span>  
  
    -   <span data-ttu-id="d8eb4-133">Eine absolute Adresse.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="d8eb4-134">Erstellen Sie die Konsolenanwendung und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="d8eb4-135">Verwenden Sie Internet Explorer, um die Basisadresse des Diensts zu suchen (http://localhost:8001/MetadataSample in diesem Beispiel) und stellen Sie sicher, dass die Metadatenveröffentlichung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-135">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="d8eb4-136">Wenn dies nicht der Fall ist, wird eine Meldung am oberen Rand die entsprechende Seite angezeigt: "Veröffentlichen von Metadaten für diesen Dienst ist derzeit deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="d8eb4-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="d8eb4-137">So verwenden Sie Standardendpunkte</span><span class="sxs-lookup"><span data-stu-id="d8eb4-137">To use default endpoints</span></span>  
  
1. <span data-ttu-id="d8eb4-138">Um Metadaten für einen Dienst zu konfigurieren, der Standardendpunkte verwendet, geben Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in der Konfigurationsdatei fest, so wie im vorherigen Beispiel. Legen Sie jedoch keine Endpunkte fest.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="d8eb4-139">Die Konfigurationsdatei sieht dann wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-139">The configuration file would then look like this.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="d8eb4-140">Da für den Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> mit `httpGetEnabled` auf `true` festgelegt wurde, ist für den Dienst die Veröffentlichung von Metadaten aktiviert. Und da keine Endpunkte explizit hinzugefügt wurden, fügt die Runtime die Standardendpunkte hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="d8eb4-141">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8eb4-141">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8eb4-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8eb4-142">Example</span></span>  
 <span data-ttu-id="d8eb4-143">Das folgende Codebeispiel zeigt die Implementierung eines einfachen WCF-Diensts und die Konfigurationsdatei, die Metadaten für den Dienst veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-143">The following code example shows the implementation of a basic WCF service and the configuration file that publishes metadata for the service.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8eb4-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8eb4-144">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="d8eb4-145">Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="d8eb4-145">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="d8eb4-146">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="d8eb4-146">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="d8eb4-147">Übersicht über die Metadatenarchitektur</span><span class="sxs-lookup"><span data-stu-id="d8eb4-147">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="d8eb4-148">Verwenden von Metadaten</span><span class="sxs-lookup"><span data-stu-id="d8eb4-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="d8eb4-149">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code</span><span class="sxs-lookup"><span data-stu-id="d8eb4-149">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
