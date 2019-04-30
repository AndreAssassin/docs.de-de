---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034228"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="fecb6-102">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fecb6-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="fecb6-103">In einem Schema können Sie angeben eine schlüsseleinschränkung für ein Element oder-Attribut mit dem **Schlüssel** Element.</span><span class="sxs-lookup"><span data-stu-id="fecb6-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="fecb6-104">Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL-Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="fecb6-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="fecb6-105">Die Schlüsseleinschränkung ist der unique-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL-Werte enthalten darf.</span><span class="sxs-lookup"><span data-stu-id="fecb6-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="fecb6-106">Der folgenden Tabelle werden die **Msdata** Attribute, die Sie, in angeben können der **Schlüssel** Element.</span><span class="sxs-lookup"><span data-stu-id="fecb6-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="fecb6-107">Attributname</span><span class="sxs-lookup"><span data-stu-id="fecb6-107">Attribute name</span></span>|<span data-ttu-id="fecb6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fecb6-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fecb6-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="fecb6-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="fecb6-110">Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.</span><span class="sxs-lookup"><span data-stu-id="fecb6-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="fecb6-111">Andernfalls die **Namen** -Attribut stellt den Wert, der den Namen der Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="fecb6-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="fecb6-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="fecb6-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="fecb6-113">Wenn `PrimaryKey="true"` vorhanden ist, die **IsPrimaryKey** -Einschränkungseigenschaft nastaven NA hodnotu **"true"**, wodurch es einen Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="fecb6-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="fecb6-114">Die **AllowDBNull** -Spalteneigenschaft ist auf **"false"**, da Primärschlüssel keine null-Werte enthalten darf nicht.</span><span class="sxs-lookup"><span data-stu-id="fecb6-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="fecb6-115">Beim Konvertieren eines Schemas, in denen eine schlüsseleinschränkung angegeben wird, erstellt der Zuordnungsprozess eine unique-Einschränkung in der Tabelle mit den **AllowDBNull** Spalteneigenschaft, die auf **"false"** für jede Spalte in der Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="fecb6-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="fecb6-116">Die **IsPrimaryKey** der unique-Einschränkung auch-Eigenschaftensatz auf **"false"** , wenn Sie angegeben haben `msdata:PrimaryKey="true"` auf die **Schlüssel** Element.</span><span class="sxs-lookup"><span data-stu-id="fecb6-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="fecb6-117">Dies ist mit einer unique-Einschränkung im Schema mit `PrimaryKey="true"` identisch.</span><span class="sxs-lookup"><span data-stu-id="fecb6-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="fecb6-118">Im folgenden Schemabeispiel die **Schlüssel** Element gibt die Key-Einschränkung für die **"CustomerID"** Element.</span><span class="sxs-lookup"><span data-stu-id="fecb6-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="fecb6-119">Die **Schlüssel** Element gibt an, dass die Werte von der **"CustomerID"** untergeordnetes Element von der **Kunden** Element muss eindeutige Werte aufweisen und darf nicht null-Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fecb6-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="fecb6-120">Beim Übertragen des XSD-Schemas (XML Schema Definition Language) wird vom Zuordnungsprozess die folgende Tabelle erstellt:</span><span class="sxs-lookup"><span data-stu-id="fecb6-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="fecb6-121">Die XML-schemazuordnung erstellt außerdem eine **UniqueConstraint** auf die **"CustomerID"** Spalte, wie im folgenden gezeigt <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fecb6-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fecb6-122">(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="fecb6-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="fecb6-123">In der **DataSet** ist die **IsPrimaryKey** Eigenschaft der **UniqueConstraint** nastaven NA hodnotu **"true"** da das Schema Gibt an, `msdata:PrimaryKey="true"` in die **Schlüssel** Element.</span><span class="sxs-lookup"><span data-stu-id="fecb6-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="fecb6-124">Der Wert des der **ConstraintName** Eigenschaft der **UniqueConstraint** in die **DataSet** ist der Wert des der **ConstraintName** angegebene Attribut der **Schlüssel** Elements im Schema.</span><span class="sxs-lookup"><span data-stu-id="fecb6-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fecb6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fecb6-125">See also</span></span>

- [<span data-ttu-id="fecb6-126">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fecb6-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="fecb6-127">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="fecb6-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="fecb6-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fecb6-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
