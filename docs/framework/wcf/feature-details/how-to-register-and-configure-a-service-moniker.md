---
title: 'Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: 547e507b4a1115de81532263c34964cd20f15d4e
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972144"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="aff91-102">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="aff91-102">How to: Register and Configure a Service Moniker</span></span>
<span data-ttu-id="aff91-103">Vor der Verwendung des Windows Communication Foundation (WCF)-Dienstmonikers in einer COM-Anwendung mit einem typisierten Vertrag müssen Sie die erforderlichen attributierten Typen bei com registrieren und die COM-Anwendung und den Moniker mit der erforderlichen Bindung konfigurieren. konfiguri.</span><span class="sxs-lookup"><span data-stu-id="aff91-103">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
### <a name="to-register-the-required-attributed-types-with-com"></a><span data-ttu-id="aff91-104">So registrieren Sie die erforderlichen attributierten Typen bei COM</span><span class="sxs-lookup"><span data-stu-id="aff91-104">To register the required attributed types with COM</span></span>  
  
1. <span data-ttu-id="aff91-105">Verwenden Sie das Tool [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , um den Metadatenvertrag aus dem WCF-Dienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="aff91-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="aff91-106">Dadurch wird der Quellcode für eine WCF-Clientassembly und eine Client Anwendungs Konfigurationsdatei generiert.</span><span class="sxs-lookup"><span data-stu-id="aff91-106">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>  
  
2. <span data-ttu-id="aff91-107">Stellen Sie sicher, dass die Typen in der Assembly als `ComVisible` markiert sind.</span><span class="sxs-lookup"><span data-stu-id="aff91-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="aff91-108">Fügen Sie hierzu der Datei AssemblyInfo.cs in Ihrem Visual Studio-Projekt das folgende Attribut hinzu:</span><span class="sxs-lookup"><span data-stu-id="aff91-108">To do so, add the following attribute to the AssemblyInfo.cs file in your Visual Studio project.</span></span>  
  
    ```csharp
    [assembly: ComVisible(true)]  
    ```  
  
3. <span data-ttu-id="aff91-109">Kompilieren Sie den verwalteten WCF-Client als Assembly mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="aff91-109">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="aff91-110">Dies erfordert die Signierung mit einem kryptografischen Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="aff91-110">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="aff91-111">Weitere Informationen finden Sie unter [Signieren einer Assembly mit einem starken Namen](https://go.microsoft.com/fwlink/?LinkId=94874) im .NET Developer es Guide.</span><span class="sxs-lookup"><span data-stu-id="aff91-111">For more information, see [Signing an Assembly with a Strong Name](https://go.microsoft.com/fwlink/?LinkId=94874) in the .NET Developer's Guide.</span></span>  
  
4. <span data-ttu-id="aff91-112">Verwenden Sie das Assemblyregistrierungstool (Regasm.exe) mit der `/tlb`-Option, um die Typen in der Assembly bei COM zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="aff91-112">Use the Assembly Registration (Regasm.exe) tool with the `/tlb` option to register the types in the assembly with COM.</span></span>  
  
5. <span data-ttu-id="aff91-113">Fügen Sie die Assembly mithilfe des Tools für den globalen Assemblycache (Gacutil.exe) dem globalen Assemblycache hinzu.</span><span class="sxs-lookup"><span data-stu-id="aff91-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aff91-114">Das Signieren sowie das Hinzufügen der Assembly zum globalen Assemblycache sind optionale Schritte, sie dienen jedoch zum Vereinfachen des Prozesses zum Laden der Assembly aus dem korrekten Speicherort im Laufzeitmodus.</span><span class="sxs-lookup"><span data-stu-id="aff91-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="aff91-115">So konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="aff91-115">To configure the COM application and the moniker with the required binding configuration</span></span>  
  
- <span data-ttu-id="aff91-116">Platzieren Sie die Bindungs Definitionen (generiert durch das [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der generierten Client Anwendungs Konfigurationsdatei) in der Konfigurationsdatei der Client Anwendung.</span><span class="sxs-lookup"><span data-stu-id="aff91-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="aff91-117">Beispiel: Für eine ausführbare Visual Basic 6.0-Datei mit dem Namen CallCenterClient.exe muss die Konfiguration in eine Datei mit dem Namen CallCenterConfig.exe.config platziert werden, und diese Datei muss sich im gleichen Verzeichnis befinden wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="aff91-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="aff91-118">Der Moniker kann nun von der Clientanwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff91-118">The client application can now use the moniker.</span></span> <span data-ttu-id="aff91-119">Beachten Sie, dass die Bindungs Konfiguration nicht erforderlich ist, wenn Sie einen der Standard Bindungs Typen verwenden, die von WCF bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aff91-119">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>  
  
     <span data-ttu-id="aff91-120">Der folgende Typ wird registriert:</span><span class="sxs-lookup"><span data-stu-id="aff91-120">The following type is registered.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     <span data-ttu-id="aff91-121">Die Anwendung wird mit einer `wsHttpBinding`-Bindung verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="aff91-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="aff91-122">Für den angegebenen Typ und die Anwendungskonfiguration werden die folgenden Beispielmonikerzeichenfolgen verwendet:</span><span class="sxs-lookup"><span data-stu-id="aff91-122">For the given type and application configuration, the following example moniker strings are used.</span></span>  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     <span data-ttu-id="aff91-123">Nachdem ein Verweis auf die Assembly mit den `IMathService`-Typen hinzugefügt wurde (siehe folgendes Codebeispiel), kann jede dieser Monikerzeichenfolgen in einer Visual Basic 6.0-Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff91-123">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>  
  
    ```vb  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     <span data-ttu-id="aff91-124">In diesem Beispiel wird die Definition für die Bindungskonfiguration `Binding1` in einer Konfigurationsdatei für die Clientanwendung mit geeignetem Namen (wie vb6appname.exe.config) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aff91-124">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as vb6appname.exe.config.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aff91-125">Für C#-, C++- oder andere .NET-Anwendung kann ein ähnlicher Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff91-125">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aff91-126">: Wenn der Moniker falsch formatiert ist oder der Dienst nicht verfügbar ist, `GetObject` gibt der Aufruf von den Fehler "Ungültige Syntax" zurück.</span><span class="sxs-lookup"><span data-stu-id="aff91-126">: If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="aff91-127">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="aff91-127">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
     <span data-ttu-id="aff91-128">Obgleich in diesem Thema hauptsächlich die Verwendung des Dienstmonikers in VB 6.0-Code behandelt wird, können Dienstmoniker auch in anderen Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff91-128">Although this topic focuses on using the service moniker from VB 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="aff91-129">Bei Verwendung eines Monikers in C++-Code muss die von Svcutil.exe generierte Assembly gemäß dem folgenden Beispiel mit "no_namespace named_guids raw_interfaces_only" importiert werden:</span><span class="sxs-lookup"><span data-stu-id="aff91-129">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>  
  
    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     <span data-ttu-id="aff91-130">Dadurch wird die importierte Schnittstellendefinitionen geändert, sodass von allen Methoden `HResult` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aff91-130">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="aff91-131">Alle anderen Rückgabewerte werden zu out-Parametern umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="aff91-131">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="aff91-132">An der Ausführung der Methoden ändert das nichts.</span><span class="sxs-lookup"><span data-stu-id="aff91-132">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="aff91-133">Dies ermöglicht es Ihnen, beim Aufrufen einer Methode auf dem Proxy die Ursache einer Ausnahme zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="aff91-133">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="aff91-134">Diese Funktion ist ausschließlich in C++-Code verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aff91-134">This functionality is only available from C++ code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff91-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aff91-135">See also</span></span>

- [<span data-ttu-id="aff91-136">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="aff91-136">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
