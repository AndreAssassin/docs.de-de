---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode'
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: 5b905b6943127d483e001749c263242550ab28ea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329387"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="48ebb-102">Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode</span><span class="sxs-lookup"><span data-stu-id="48ebb-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="48ebb-103">"Svcutil.exe" kann Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys wie folgt exportieren:</span><span class="sxs-lookup"><span data-stu-id="48ebb-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
-   <span data-ttu-id="48ebb-104">Zum Exportieren von Metadaten für alle kompilierten Dienstverträge für eine Assemblygruppe mithilfe von "Svcutil.exe" geben Sie die Assemblys als Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="48ebb-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="48ebb-105">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="48ebb-105">This is the default behavior.</span></span>  
  
-   <span data-ttu-id="48ebb-106">Zum Exportieren von Metadaten für einen kompilierten Dienst mithilfe von "Svcutil.exe" geben Sie die Dienstassembly bzw. -assemblys als Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="48ebb-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="48ebb-107">Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Diensts anzugeben, den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="48ebb-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="48ebb-108">"Svcutil.exe" lädt die Konfigurationsdatei für die angegebene ausführbare Assembly automatisch.</span><span class="sxs-lookup"><span data-stu-id="48ebb-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
-   <span data-ttu-id="48ebb-109">Um alle Datenvertragstypen innerhalb einer Assemblygruppe zu exportieren, verwenden Sie die `/dataContractOnly`-Option.</span><span class="sxs-lookup"><span data-stu-id="48ebb-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ebb-110">Zum Angeben von Dateipfaden zu abhängigen Assemblys verwenden Sie die `/reference`-Option.</span><span class="sxs-lookup"><span data-stu-id="48ebb-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="48ebb-111">So exportieren Sie Metadaten für kompilierte Dienstverträge</span><span class="sxs-lookup"><span data-stu-id="48ebb-111">To export metadata for compiled service contracts</span></span>  
  
1. <span data-ttu-id="48ebb-112">Kompilieren Sie die Dienstvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="48ebb-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2. <span data-ttu-id="48ebb-113">Führen Sie "Svcutil.exe" auf den kompilierten Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="48ebb-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48ebb-114">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ebb-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="48ebb-115">So exportieren Sie Metadaten füreinen kompilierten Dienst</span><span class="sxs-lookup"><span data-stu-id="48ebb-115">To export metadata for a compiled service</span></span>  
  
1. <span data-ttu-id="48ebb-116">Kompilieren Sie die Dienstimplementierung in eine ausführbare Assembly.</span><span class="sxs-lookup"><span data-stu-id="48ebb-116">Compile your service implementation into an executable assembly.</span></span>  
  
2. <span data-ttu-id="48ebb-117">Erstellen Sie eine Konfigurationsdatei für die ausführbare Dienstdatei, und fügen Sie eine Dienstkonfiguration hinzu.</span><span class="sxs-lookup"><span data-stu-id="48ebb-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3. <span data-ttu-id="48ebb-118">Zum Angeben des Konfigurationsnamen des Diensts führen Sie "Svcutil.exe" für die kompilierte ausführbare Dienstdatei mithilfe des `/serviceName`-Schalters aus.</span><span class="sxs-lookup"><span data-stu-id="48ebb-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48ebb-119">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ebb-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="48ebb-120">So exportieren Sie Metadaten für kompilierte Datenverträge</span><span class="sxs-lookup"><span data-stu-id="48ebb-120">To export metadata for compiled data contracts</span></span>  
  
1. <span data-ttu-id="48ebb-121">Kompilieren Sie die Datenvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="48ebb-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2. <span data-ttu-id="48ebb-122">Führen Sie "Svcutil.exe" für die kompilierten Assemblys mithilfe des `/dataContract`-Schalters aus, um anzugeben, dass nur Metadaten für Datenverträge generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48ebb-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48ebb-123">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ebb-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="48ebb-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48ebb-124">Example</span></span>  
 <span data-ttu-id="48ebb-125">Im folgenden Beispiel wird veranschaulicht, wie Metadaten für eine einfache Dienstimplementierung und -konfiguration generiert werden.</span><span class="sxs-lookup"><span data-stu-id="48ebb-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="48ebb-126">So exportieren Sie Metadaten für den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="48ebb-126">To export metadata for the service contract.</span></span>  
  
```  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="48ebb-127">So exportieren Sie Metadaten für Datenverträge</span><span class="sxs-lookup"><span data-stu-id="48ebb-127">To export metadata for the data contracts.</span></span>  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="48ebb-128">So exportieren Sie Metadaten für die Dienstimplementierung</span><span class="sxs-lookup"><span data-stu-id="48ebb-128">To export metadata for the service implementation.</span></span>  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="48ebb-129">Der `<path>` entspricht dem Pfad zu "Contracts.dll".</span><span class="sxs-lookup"><span data-stu-id="48ebb-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```  
// The following service contract and data contracts are compiled into   
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
  
// The following service implementation is compiled into Service.exe.     
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48ebb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ebb-130">See also</span></span>

- [<span data-ttu-id="48ebb-131">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="48ebb-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="48ebb-132">Exportieren und Importieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="48ebb-132">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
