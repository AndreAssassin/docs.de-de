---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 650cd6b8b8149529f115f22a11d19178fbd6d302
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108224"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="bc7a6-102">Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bc7a6-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="bc7a6-103">In einem XML-Schema Definition Language (XSD)-Schema der **eindeutige** Element gibt die eindeutigkeitseinschränkung für ein Element oder Attribut an.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="bc7a6-104">	Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="bc7a6-105">Der folgenden Tabelle werden die **Msdata** Attribute, die Sie, in angeben können der **eindeutige** Element.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="bc7a6-106">Attributname</span><span class="sxs-lookup"><span data-stu-id="bc7a6-106">Attribute name</span></span>|<span data-ttu-id="bc7a6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc7a6-107">Description</span></span>|  
|--------------------|-----------------|  
|**<span data-ttu-id="bc7a6-108">msdata:ConstraintName</span><span class="sxs-lookup"><span data-stu-id="bc7a6-108">msdata:ConstraintName</span></span>**|<span data-ttu-id="bc7a6-109">Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="bc7a6-110">Andernfalls die **Namen** -Attribut stellt den Wert, der den Namen der Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|**<span data-ttu-id="bc7a6-111">msdata:PrimaryKey</span><span class="sxs-lookup"><span data-stu-id="bc7a6-111">msdata:PrimaryKey</span></span>**|<span data-ttu-id="bc7a6-112">Wenn `PrimaryKey="true"` befindet sich in der **eindeutige** -Element, eine unique-Einschränkung wird erstellt, mit der **IsPrimaryKey** -Eigenschaft auf festgelegt **"true"**.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="bc7a6-113">Das folgende Beispiel zeigt eine XML-Schema, verwendet der **eindeutige** Element, um eine Unique-Einschränkung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="bc7a6-114">Die **eindeutige** Elements im Schema gibt an, dass für alle **Kunden** Elemente in einem Dokument-Instanz, den Wert des der **"CustomerID"** untergeordnetes Element muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="bc7a6-115">Bei Erstellung der **DataSet**, der Zuordnungsprozess dieses Schema liest und in der folgende Tabelle generiert:</span><span class="sxs-lookup"><span data-stu-id="bc7a6-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="bc7a6-116">Außerdem erstellt der Zuordnungsprozess eine unique-Einschränkung auf die **"CustomerID"** Spalte, wie im folgenden gezeigt **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="bc7a6-117">(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="bc7a6-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="bc7a6-118">In der **DataSet** ist die **IsPrimaryKey** -Eigenschaftensatz auf **"false"** für die unique-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="bc7a6-119">Die **eindeutige** -Eigenschaft in der Spalte gibt an, dass die **"CustomerID"** Spaltenwerte müssen eindeutig sein (aber sie können ein null-Verweis, laut der **AllowDBNull** -Eigenschaft der Spalte).</span><span class="sxs-lookup"><span data-stu-id="bc7a6-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="bc7a6-120">Wenn Sie das Schema ändern, und legen Sie den optionalen **msdata: PrimaryKey** -Attributwert auf **"true"**, die unique-Einschränkung für die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="bc7a6-121">Die **AllowDBNull** -Spalteneigenschaft ist auf **"false"**, und die **IsPrimaryKey** -Eigenschaft der Einschränkung ist auf **"true"**, daher machen die **"CustomerID"** Spalte eine Primärschlüsselspalte.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="bc7a6-122">Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="bc7a6-123">Im folgende Beispiel wird veranschaulicht, wie an, dass eine Kombination von **"CustomerID"** und **CompanyName** Werte müssen für alle eindeutig sein **Kunden** in jeder Instanz von Hinzufügen einer weiteren **xs: field** Elements im Schema.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="bc7a6-124">Dies ist die Einschränkung, die in der resultierenden erstellt wird **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bc7a6-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc7a6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc7a6-125">See also</span></span>

- [<span data-ttu-id="bc7a6-126">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bc7a6-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="bc7a6-127">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="bc7a6-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="bc7a6-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="bc7a6-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
