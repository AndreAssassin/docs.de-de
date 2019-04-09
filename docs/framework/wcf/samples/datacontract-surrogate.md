---
title: DataContract-Ersatzzeichen
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 663f168ebbba2238be814791fd0d75e211a469ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196423"
---
# <a name="datacontract-surrogate"></a><span data-ttu-id="c4adb-102">DataContract-Ersatzzeichen</span><span class="sxs-lookup"><span data-stu-id="c4adb-102">DataContract Surrogate</span></span>
<span data-ttu-id="c4adb-103">In diesem Beispiel wird beschrieben, wie Vorgänge wie Serialisierung, Deserialisierung, Schemaexport und Schemaimport mithilfe einer Datenvertrag-Ersatzzeichenklasse angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="c4adb-103">This sample demonstrates how processes like serialization, deserialization, schema export, and schema import can be customized using a data contract surrogate class.</span></span> <span data-ttu-id="c4adb-104">Dieses Beispiel zeigt, wie verwenden Sie ein Ersatzzeichen in einem Client und Server-Szenario, in dem Daten serialisiert und zwischen Windows Communication Foundation (WCF)-Client und Dienst übertragen.</span><span class="sxs-lookup"><span data-stu-id="c4adb-104">This sample shows how to use a surrogate in a client and server scenario where data is serialized and transmitted between a Windows Communication Foundation (WCF) client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4adb-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c4adb-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c4adb-106">Im Beispiel wird der folgende Dienstvertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4adb-106">The sample uses the following service contract:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 <span data-ttu-id="c4adb-107">Mit dem `AddEmployee`-Vorgang können Benutzer Daten zu neuen Mitarbeitern hinzufügen. Der `GetEmployee`-Vorgang unterstützt das Suchen von Mitarbeitern nach Namen.</span><span class="sxs-lookup"><span data-stu-id="c4adb-107">The `AddEmployee` operation allows users to add data about new employees and the `GetEmployee` operation supports search for employees based on name.</span></span>  
  
 <span data-ttu-id="c4adb-108">In diesen Vorgängen wird der folgende Datentyp verwendet:</span><span class="sxs-lookup"><span data-stu-id="c4adb-108">These operations use the following data type:</span></span>  
  
```  
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 <span data-ttu-id="c4adb-109">Im `Employee`-Typ kann die `Person`-Klasse (im folgenden Beispielcode dargestellt) nicht von <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert werden, da es sich nicht um eine gültige Datenvertragsklasse handelt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-109">In the `Employee` type, the `Person` class (shown in the following sample code) cannot be serialized by the <xref:System.Runtime.Serialization.DataContractSerializer> because it is not a valid data contract class.</span></span>  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <span data-ttu-id="c4adb-110">Sie können das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die `Person`-Klasse anwenden, dies ist jedoch nicht immer möglich.</span><span class="sxs-lookup"><span data-stu-id="c4adb-110">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the `Person` class, but this is not always possible.</span></span> <span data-ttu-id="c4adb-111">Die `Person`-Klasse kann beispielsweise in einer separaten Assembly definiert sein, auf die Sie keinen Einfluss haben.</span><span class="sxs-lookup"><span data-stu-id="c4adb-111">For example, the `Person` class can be defined in a separate assembly over which you have no control.</span></span>  
  
 <span data-ttu-id="c4adb-112">Wenn diese Einschränkung vorliegt, besteht eine Möglichkeit zum Serialisieren der `Person`-Klasse darin, sie durch eine andere Klasse zu ersetzen, die mit <xref:System.Runtime.Serialization.DataContractAttribute> markiert ist, und erforderliche Daten in die neue Klasse zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="c4adb-112">Given this restriction, one way to serialize the `Person` class is to substitute it with another class that is marked with <xref:System.Runtime.Serialization.DataContractAttribute> and copy over necessary data to the new class.</span></span> <span data-ttu-id="c4adb-113">Das Ziel ist dabei, die `Person`-Klasse für <xref:System.Runtime.Serialization.DataContractSerializer> als DataContract erscheinen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="c4adb-113">The objective is to make the `Person` class appear as a DataContract to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="c4adb-114">Beachten Sie, dass dies eine Möglichkeit zum Serialisieren von Klassen ist, bei denen es sich nicht um Datenvertragsklassen handelt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-114">Note that this is one way to serialize non-data contract classes.</span></span>  
  
 <span data-ttu-id="c4adb-115">Im Beispiel wird die `Person`-Klasse logisch durch eine andere Klasse namens `PersonSurrogated` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-115">The sample logically replaces the `Person` class with a different class named `PersonSurrogated`.</span></span>  
  
```  
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 <span data-ttu-id="c4adb-116">Zum Durchführen dieser Ersetzung wird das Datenvertrag-Ersatzzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4adb-116">The data contract surrogate is used to achieve this replacement.</span></span> <span data-ttu-id="c4adb-117">Ein Datenvertrag-Ersatzzeichen ist eine Klasse, die <xref:System.Runtime.Serialization.IDataContractSurrogate> implementiert.</span><span class="sxs-lookup"><span data-stu-id="c4adb-117">A data contract surrogate is a class that implements <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span></span> <span data-ttu-id="c4adb-118">In diesem Beispiel implementiert die `AllowNonSerializableTypesSurrogate`-Klasse diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c4adb-118">In this sample, the `AllowNonSerializableTypesSurrogate` class implements this interface.</span></span>  
  
 <span data-ttu-id="c4adb-119">In der Schnittstellenimplementierung ist die erste Aufgabe das Einrichten einer Typzuordnung von `Person` zu `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="c4adb-119">In the interface implementation, the first task is to establish a type mapping from `Person` to `PersonSurrogated`.</span></span> <span data-ttu-id="c4adb-120">Dies wird bei der Serialisierung sowie beim Schemaexport verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4adb-120">This is used both at serialization time as well as at schema export time.</span></span> <span data-ttu-id="c4adb-121">Diese Zuordnung erfolgt durch das Implementieren der <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c4adb-121">This mapping is achieved by implementing the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> method.</span></span>  
  
```  
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 <span data-ttu-id="c4adb-122">Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29>-Methode ordnet bei der Serialisierung eine `Person`-Instanz einer `PersonSurrogated`-Instanz zu, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-122">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> method maps a `Person` instance to a `PersonSurrogated` instance during serialization, as shown in the following sample code.</span></span>  
  
```  
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="c4adb-123">Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29>-Methode stellt die umgekehrte Zuordnung für die Deserialisierung bereit, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-123">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> method provides the reverse mapping for deserialization, as shown in the following sample code.</span></span>  
  
```  
public object GetDeserializedObject(object obj,   
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="c4adb-124">Zum Zuordnen des `PersonSurrogated`-Datenvertrags zu der vorhandenen `Person`-Klasse beim Schemaimport wird im Beispiel die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>-Methode implementiert, wie im folgenden Beispielcode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c4adb-124">To map the `PersonSurrogated` data contract to the existing `Person` class during schema import, the sample implements the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> method, as shown in the following sample code.</span></span>  
  
```  
public Type GetReferencedTypeOnImport(string typeName,   
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 <span data-ttu-id="c4adb-125">Im folgenden Beispielcode wird die Implementierung der <xref:System.Runtime.Serialization.IDataContractSurrogate>-Schnittstelle abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c4adb-125">The following sample code completes the implementation of the <xref:System.Runtime.Serialization.IDataContractSurrogate> interface.</span></span>  
  
```  
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,   
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,   
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 <span data-ttu-id="c4adb-126">In diesem Beispiel wird das Ersatzzeichen in ServiceModel von dem Attribut `AllowNonSerializableTypesAttribute` aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c4adb-126">In this sample, the surrogate is enabled in ServiceModel by an attribute called `AllowNonSerializableTypesAttribute`.</span></span> <span data-ttu-id="c4adb-127">Entwickler müssten dieses Attribut auf ihren Dienstvertrag anwenden, wie oben im `IPersonnelDataService`-Dienstvertrag dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-127">Developers would need to apply this attribute on their service contract as shown on the `IPersonnelDataService` service contract above.</span></span> <span data-ttu-id="c4adb-128">Dieses Attribut implementiert `IContractBehavior` und richtet das Ersatzzeichen bei Vorgängen in der `ApplyClientBehavior`-Methode und der `ApplyDispatchBehavior`-Methode ein.</span><span class="sxs-lookup"><span data-stu-id="c4adb-128">This attribute implements `IContractBehavior` and sets up the surrogate on operations in its `ApplyClientBehavior` and `ApplyDispatchBehavior` methods.</span></span>  
  
 <span data-ttu-id="c4adb-129">Das Attribut ist in diesem Fall nicht erforderlich. Es wird in diesem Beispiel nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4adb-129">The attribute is not necessary in this case - it is used for demonstration purposes in this sample.</span></span> <span data-ttu-id="c4adb-130">Die Benutzer können ein Ersatzzeichen auch aktivieren, indem sie mithilfe von Code oder Konfiguration ein ähnliches `IContractBehavior`, `IEndpointBehavior` oder `IOperationBehavior` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4adb-130">Users can alternatively enable a surrogate by manually adding a similar `IContractBehavior`, `IEndpointBehavior` or `IOperationBehavior` using code or using configuration.</span></span>  
  
 <span data-ttu-id="c4adb-131">Die `IContractBehavior`-Implementierung sucht nach Vorgängen, die DataContract verwenden, indem überprüft wird, ob `DataContractSerializerOperationBehavior` registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c4adb-131">The `IContractBehavior` implementation looks for operations that use DataContract by checking if they have a `DataContractSerializerOperationBehavior` registered.</span></span> <span data-ttu-id="c4adb-132">Wenn dies der Fall ist, wird die `DataContractSurrogate`-Eigenschaft auf dieses Verhalten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-132">If they do, it sets the `DataContractSurrogate` property on that behavior.</span></span> <span data-ttu-id="c4adb-133">Der folgende Beispielcode zeigt die Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="c4adb-133">The following sample code shows how this is done.</span></span> <span data-ttu-id="c4adb-134">Durch das Festlegen des Ersatzzeichens auf dieses Vorgangsverhalten wird es für die Serialisierung und die Deserialisierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c4adb-134">Setting the surrogate on this operation behavior enables it for serialization and deserialization.</span></span>  
  
```  
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 <span data-ttu-id="c4adb-135">Damit das Ersatzzeichen für die Verwendung bei der Metadaten-Generierung eingebunden werden kann, sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4adb-135">Additional steps need to be taken to plug in the surrogate for use during metadata generation.</span></span> <span data-ttu-id="c4adb-136">Ein Mechanismus hierfür ist das Bereitstellen einer `IWsdlExportExtension`. Dies wird in diesem Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c4adb-136">One mechanism to do this is to provide an `IWsdlExportExtension` which is what this sample demonstrates.</span></span> <span data-ttu-id="c4adb-137">Eine andere Möglichkeit ist das direkte Ändern von `WsdlExporter`.</span><span class="sxs-lookup"><span data-stu-id="c4adb-137">Another way is to modify the `WsdlExporter` directly.</span></span>  
  
 <span data-ttu-id="c4adb-138">Die `AllowNonSerializableTypesAttribute` -Attribut implementiert `IWsdlExportExtension` und `IContractBehavior`.</span><span class="sxs-lookup"><span data-stu-id="c4adb-138">The `AllowNonSerializableTypesAttribute` attribute implements `IWsdlExportExtension` and `IContractBehavior`.</span></span> <span data-ttu-id="c4adb-139">Die Erweiterung kann es sich um entweder eine `IContractBehavior` oder `IEndpointBehavior` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="c4adb-139">The extension can be either an `IContractBehavior` or `IEndpointBehavior` in this case.</span></span> <span data-ttu-id="c4adb-140">Die Implementierung der `IWsdlExportExtension.ExportContract`-Methode aktiviert das Ersatzzeichen, indem es dem bei der Schemagenerierung für DataContract verwendeten `XsdDataContractExporter` hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c4adb-140">Its `IWsdlExportExtension.ExportContract` method implementation enables the surrogate by adding it to the `XsdDataContractExporter` used during schema generation for DataContract.</span></span> <span data-ttu-id="c4adb-141">Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="c4adb-141">The following code snippet shows how to do this.</span></span>  
  
```  
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 <span data-ttu-id="c4adb-142">Wenn Sie das Beispiel ausführen, ruft der Client AddEmployee auf. Danach folgt ein Aufruf von GetEmployee, um zu überprüfen, ob der erste Aufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c4adb-142">When you run the sample, the client calls AddEmployee followed by a GetEmployee call to check if the first call was successful.</span></span> <span data-ttu-id="c4adb-143">Das Ergebnis der GetEmployee-Vorgangsanforderung wird im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-143">The result of the GetEmployee operation request is displayed in the client console window.</span></span> <span data-ttu-id="c4adb-144">Der GetEmployee-Vorgang muss erfolgreich ausgeführt werden, bei der Suche nach der Mitarbeiter und "found" ausgeben.</span><span class="sxs-lookup"><span data-stu-id="c4adb-144">The GetEmployee operation must succeed in finding the employee and print "found".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4adb-145">In diesem Beispiel wird das Einbinden eines Ersatzzeichens zum Serialisieren, Deserialisieren und für die Metadatengenerierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c4adb-145">This sample shows how to plug in a surrogate for serialize, deserialize and metadata generation.</span></span> <span data-ttu-id="c4adb-146">Das Einbinden eines Ersatzzeichens für die Codegenerierung aus Metadaten wird nicht dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4adb-146">It does not show how to plug in a surrogate for code generation from metadata.</span></span> <span data-ttu-id="c4adb-147">Ein Beispiel wie ein Ersatzzeichens zum Einbinden in die Generierung von Clientcode verwendet werden kann, finden Sie unter den [benutzerdefinierte WSDL-Veröffentlichung](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c4adb-147">To see a sample of how a surrogate can be used to plug into client code generation, see the [Custom WSDL Publication](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) sample.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c4adb-148">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c4adb-148">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c4adb-149">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c4adb-149">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c4adb-150">Um die C#-.NET-Edition der Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c4adb-150">To build the C# edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c4adb-151">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c4adb-151">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4adb-152">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c4adb-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c4adb-153">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c4adb-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c4adb-154">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c4adb-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c4adb-155">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c4adb-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
