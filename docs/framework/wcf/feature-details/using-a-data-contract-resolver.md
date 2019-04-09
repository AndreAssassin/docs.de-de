---
title: Verwenden eines Datenvertragsresolvers
ms.date: 03/30/2017
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
ms.openlocfilehash: b1c545d84db68f4b13925dd9088cc9d81050b5e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222444"
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="188df-102">Verwenden eines Datenvertragsresolvers</span><span class="sxs-lookup"><span data-stu-id="188df-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="188df-103">Mithilfe eines Datenvertragsresolver können Sie bekannte Typen dynamisch konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="188df-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="188df-104">Bekannte Typen sind erforderlich, wenn ein Typ serialisiert oder deserialisiert wird, der von einem Datenvertrag nicht erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="188df-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> <span data-ttu-id="188df-105">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="188df-105">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="188df-106">Bekannte Typen werden in der Regel statisch angegeben.</span><span class="sxs-lookup"><span data-stu-id="188df-106">Known types are normally specified statically.</span></span> <span data-ttu-id="188df-107">Das bedeutet, dass Sie beim Implementieren eines Vorgangs alle möglichen Typen kennen müssen, die der Vorgang erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="188df-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="188df-108">In einigen Szenarios trifft dies nicht zu, und es ist wichtig, bekannte Typen dynamisch angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="188df-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="188df-109">Erstellen eines Datenvertragsresolvers</span><span class="sxs-lookup"><span data-stu-id="188df-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="188df-110">Das Erstellen eines Datenvertragsresolvers umfasst die Implementierung von zwei Methoden: <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> und <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span><span class="sxs-lookup"><span data-stu-id="188df-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="188df-111">Diese beiden Methoden implementieren Rückrufe, die jeweils während der Serialisierung und der Deserialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="188df-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="188df-112">Die <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A>-Methode wird während der Serialisierung aufgerufen. Sie verwendet einen Datenvertragstyp und ordnet diesen einem `xsi:type`-Namen und einem Namespace zu.</span><span class="sxs-lookup"><span data-stu-id="188df-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="188df-113">Die <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>-Methode wird während der Deserialisierung aufgerufen. Sie verwendet einen `xsi:type`-Namen und einen Namespace und löst diesen zu einem Datenvertragstyp auf.</span><span class="sxs-lookup"><span data-stu-id="188df-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="188df-114">Beide Methoden verfügen über einen `knownTypeResolver`-Parameter, der verwendet werden kann, um den standardmäßigen bekannten Typresolver in der Implementierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="188df-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="188df-115">Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.Runtime.Serialization.DataContractResolver> implementieren, um die Zuordnung zu und von einem Datenvertragstyp mit dem Namen `Customer` vorzunehmen, der vom einem Datenvertragstyp `Person` abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="188df-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="188df-116">Nachdem Sie einen <xref:System.Runtime.Serialization.DataContractResolver> definiert haben, können Sie diesen verwenden, indem Sie ihn an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben. Dies ist im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="188df-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```  
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="188df-117">Sie können einen <xref:System.Runtime.Serialization.DataContractResolver> in einem Aufruf der Methoden <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> oder <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="188df-117">You can specify a <xref:System.Runtime.Serialization.DataContractResolver> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> methods, as shown in the following example.</span></span>  
  
```  
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="188df-118">Sie können ihn jedoch auch unter <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> festlegen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="188df-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```  
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 <span data-ttu-id="188df-119">Sie können einen Datenvertragsresolver deklarativ angeben, indem Sie ein Attribut implementieren, das auf einen Dienst angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="188df-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  <span data-ttu-id="188df-120">Weitere Informationen finden Sie unter den [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="188df-120">For more information, see the [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="188df-121">Diesem Beispiel wird ein Attribut namens "KnownAssembly" implementiert, das Verhalten des Diensts einen benutzerdefinierten datenvertragsresolver hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="188df-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188df-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="188df-122">See also</span></span>

- [<span data-ttu-id="188df-123">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="188df-123">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="188df-124">DataContractSerializer-Beispiel</span><span class="sxs-lookup"><span data-stu-id="188df-124">DataContractSerializer Sample</span></span>](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)
- [<span data-ttu-id="188df-125">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="188df-125">KnownAssemblyAttribute</span></span>](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
