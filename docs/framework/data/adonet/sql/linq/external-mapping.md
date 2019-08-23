---
title: Externe Zuordnung
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 70372473eb2de5d3c4751e237e7beb66315b690e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950330"
---
# <a name="external-mapping"></a><span data-ttu-id="62c9d-102">Externe Zuordnung</span><span class="sxs-lookup"><span data-stu-id="62c9d-102">External Mapping</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="62c9d-103">unterstützt *externe Zuordnung*, einen Prozess, mit dem Sie eine separate XML-Datei verwenden, um die Zuordnung zwischen dem Datenmodell der Datenbank und dem Objektmodell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="62c9d-103">supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="62c9d-104">Die Verwendung einer externen Zuordnungsdatei bietet u. a. folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="62c9d-104">Advantages of using an external mapping file include the following:</span></span>  
  
- <span data-ttu-id="62c9d-105">Sie können den Zuordnungscode vom Anwendungscode trennen.</span><span class="sxs-lookup"><span data-stu-id="62c9d-105">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="62c9d-106">Hierdurch wird die Übersichtlichkeit des Anwendungscodes verbessert.</span><span class="sxs-lookup"><span data-stu-id="62c9d-106">This approach reduces clutter in your application code.</span></span>  
  
- <span data-ttu-id="62c9d-107">Eine externe Zuordnungsdatei kann in etwa wie eine Konfigurationsdatei behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="62c9d-107">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="62c9d-108">Beispielsweise können Sie das Anwendungsverhalten aktualisieren, nachdem die Binärdateien bereits ausgeliefert wurden, indem Sie einfach die externe Zuordnungsdatei austauschen.</span><span class="sxs-lookup"><span data-stu-id="62c9d-108">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c9d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62c9d-109">Requirements</span></span>  
 <span data-ttu-id="62c9d-110">Die Zuordnungsdatei muss eine XML-Datei sein, und die Datei muss [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] anhand einer Schema Definitionsdatei (. xsd) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="62c9d-110">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="62c9d-111">Dabei gelten folgende Regeln:</span><span class="sxs-lookup"><span data-stu-id="62c9d-111">The following rules apply:</span></span>  
  
- <span data-ttu-id="62c9d-112">Die Zuordnungsdatei muss eine XML-Datei sein.</span><span class="sxs-lookup"><span data-stu-id="62c9d-112">The mapping file must be an XML file.</span></span>  
  
- <span data-ttu-id="62c9d-113">Die XML-Zuordnungsdatei muss gegenüber der XML-Schemadefinitionsdatei gültig sein.</span><span class="sxs-lookup"><span data-stu-id="62c9d-113">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="62c9d-114">Weitere Informationen finden Sie unter [Vorgehensweise: Validieren von DBML-und](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)externen Mapping-Dateien.</span><span class="sxs-lookup"><span data-stu-id="62c9d-114">For more information, see [How to: Validate DBML and External Mapping Files](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
- <span data-ttu-id="62c9d-115">Externe Zuordnungen überschreiben attributbasierte Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="62c9d-115">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="62c9d-116">Dies bedeutet, dass alle für Klassen erstellten Zuordnungsattribute von <xref:System.Data.Linq.DataContext> ignoriert werden, wenn Sie <xref:System.Data.Linq.DataContext> unter Verwendung einer externen Zuordnungsquelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="62c9d-116">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="62c9d-117">Dieses Verhalten gilt unabhängig davon, ob die Klasse in der externen Zuordnungsdatei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="62c9d-117">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="62c9d-118">bietet keine Unterstützung für die kombinierte Verwendung beider Zuordnungsarten (attributbasiert und extern).</span><span class="sxs-lookup"><span data-stu-id="62c9d-118">does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="62c9d-119">XML-Schemadefinitionsdatei</span><span class="sxs-lookup"><span data-stu-id="62c9d-119">XML Schema Definition File</span></span>  
 <span data-ttu-id="62c9d-120">Die externe Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] muss gegenüber der folgenden XML-Schemadefinition gültig sein.</span><span class="sxs-lookup"><span data-stu-id="62c9d-120">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="62c9d-121">Beachten Sie den Unterschied zwischen dieser Schemadefinitionsdatei und der Schemadefinitionsdatei, die zum Überprüfen einer DBML-Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62c9d-121">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="62c9d-122">Weitere Informationen finden Sie unter [Code Generierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="62c9d-122">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62c9d-123">Visual Studio-Benutzer finden diese XSD-Datei auch im Dialogfeld XML-Schemas als "linqdesqlmapping. xsd".</span><span class="sxs-lookup"><span data-stu-id="62c9d-123">Visual Studio users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="62c9d-124">Informationen dazu, wie Sie diese Datei ordnungsgemäß für die Validierung einer externen [Datei verwenden, finden Sie unter Gewusst wie: Validieren von DBML-und](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)externen Mapping-Dateien.</span><span class="sxs-lookup"><span data-stu-id="62c9d-124">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
```  
?<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62c9d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62c9d-125">See also</span></span>

- [<span data-ttu-id="62c9d-126">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="62c9d-126">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="62c9d-127">Verweis</span><span class="sxs-lookup"><span data-stu-id="62c9d-127">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="62c9d-128">Vorgehensweise: Generieren des Objektmodells als externe Datei</span><span class="sxs-lookup"><span data-stu-id="62c9d-128">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)
