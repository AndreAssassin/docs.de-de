---
title: Synchronisieren eines "DataSet "mit einem "XmlDataDocument"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fbc96fa9-b5d1-4f97-b099-c89b0e14ce2c
ms.openlocfilehash: b4682d60e213ad57308143b2c7ea06d123daf61d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133730"
---
# <a name="synchronizing-a-dataset-with-an-xmldatadocument"></a><span data-ttu-id="5f93b-102">Synchronisieren eines "DataSet "mit einem "XmlDataDocument"</span><span class="sxs-lookup"><span data-stu-id="5f93b-102">Synchronizing a DataSet with an XmlDataDocument</span></span>
<span data-ttu-id="5f93b-103">In diesem Abschnitt wird ein Schritt bei der Verarbeitung einer Bestellung mit einem <xref:System.Data.DataSet> mit strikter Typbindung beschrieben, das mit einem <xref:System.Xml.XmlDataDocument> synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5f93b-103">This section demonstrates one step in the processing of a purchase order, using a strongly typed <xref:System.Data.DataSet> synchronized with an <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="5f93b-104">Erstellen Sie die folgenden Beispielen ein **DataSet** mit einem minimalistischen Schema, der nur einen Teil des XML-Quelldokuments übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5f93b-104">The examples that follow create a **DataSet** with a minimized schema that matches only a portion of the source XML document.</span></span> <span data-ttu-id="5f93b-105">Die Beispiele verwenden eine **XmlDataDocument** um die Genauigkeit der XML-Quelldokument beizubehalten aktivieren die **DataSet** verwendet werden, um eine Teilmenge der XML-Dokument verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="5f93b-105">The examples use an **XmlDataDocument** to preserve the fidelity of the source XML document, enabling the **DataSet** to be used to expose a subset of the XML document.</span></span>  
  
 <span data-ttu-id="5f93b-106">Das folgende XML-Dokument enthält alle Informationen zu einer Bestellung: Kundeninformationen, bestellte Artikel, Versandinformationen usw.</span><span class="sxs-lookup"><span data-stu-id="5f93b-106">The following XML document contains all the information pertaining to a purchase order: customer information, items ordered, shipping information, and so on.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<PurchaseOrder>  
  <Customers>  
    <CustomerID>CHOPS</CustomerID>  
    <Orders>  
      <OrderID>10966</OrderID>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>37</ProductID>  
        <UnitPrice>26</UnitPrice>  
        <Quantity>8</Quantity>  
        <Discount>0</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>56</ProductID>  
        <UnitPrice>38</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>62</ProductID>  
        <UnitPrice>49.3</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <CustomerID>CHOPS</CustomerID>  
      <EmployeeID>4</EmployeeID>  
      <OrderDate>1998-03-20T00:00:00.0000000</OrderDate>  
      <RequiredDate>1998-04-17T00:00:00.0000000</RequiredDate>  
      <ShippedDate>1998-04-08T00:00:00.0000000</ShippedDate>  
      <ShipVia>1</ShipVia>  
      <Freight>27.19</Freight>  
      <ShipName>Chop-suey Chinese</ShipName>  
      <ShipAddress>Hauptstr. 31</ShipAddress>  
      <ShipCity>Bern</ShipCity>  
      <ShipPostalCode>3012</ShipPostalCode>  
      <ShipCountry>Switzerland</ShipCountry>  
    </Orders>  
    <CompanyName>Chop-suey Chinese</CompanyName>  
    <ContactName>Yang Wang</ContactName>  
    <ContactTitle>Owner</ContactTitle>  
    <Address>Hauptstr. 29</Address>  
    <City>Bern</City>  
    <PostalCode>3012</PostalCode>  
    <Country>Switzerland</Country>  
    <Phone>0452-076545</Phone>  
  </Customers>  
  <Shippers>  
    <ShipperID>1</ShipperID>  
    <CompanyName>Speedy Express</CompanyName>  
    <Phone>(503) 555-0100</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>2</ShipperID>  
    <CompanyName>United Package</CompanyName>  
    <Phone>(503) 555-0101</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>3</ShipperID>  
    <CompanyName>Federal Shipping</CompanyName>  
    <Phone>(503) 555-0102</Phone>  
  </Shippers>  
  <Products>  
    <ProductID>37</ProductID>  
    <ProductName>Gravad lax</ProductName>  
    <QuantityPerUnit>12 - 500 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>11</UnitsInStock>  
    <UnitsOnOrder>50</UnitsOnOrder>  
    <ReorderLevel>25</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>56</ProductID>  
    <ProductName>Gnocchi di nonna Alice</ProductName>  
    <QuantityPerUnit>24 - 250 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>21</UnitsInStock>  
    <UnitsOnOrder>10</UnitsOnOrder>  
    <ReorderLevel>30</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>62</ProductID>  
    <ProductName>Tarte au sucre</ProductName>  
    <QuantityPerUnit>48 pies</QuantityPerUnit>  
    <UnitsInStock>17</UnitsInStock>  
    <UnitsOnOrder>0</UnitsOnOrder>  
    <ReorderLevel>0</ReorderLevel>  
  </Products>  
</PurchaseOrder>  
```  
  
 <span data-ttu-id="5f93b-107">Ein Schritt bei der Verarbeitung der Bestellinformationen aus dem vorhergehenden XML-Dokument besteht darin, dass die Bestellung über den aktuellen Lagerbestand des Unternehmens ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f93b-107">One step in processing the purchase order information contained in the preceding XML document is for the order to be filled from the company's current inventory.</span></span> <span data-ttu-id="5f93b-108">Der Mitarbeiter, der die Bestellung über das Lager des Unternehmens bearbeitet, muss nicht den gesamten Inhalt der Bestellung kennen – es genügt, wenn die Produktinformationen für die Bestellung zu sehen sind.</span><span class="sxs-lookup"><span data-stu-id="5f93b-108">The employee responsible for filling the order from the company's warehouse does not need to see the entire contents of the purchase order; they only need to see the product information for the order.</span></span> <span data-ttu-id="5f93b-109">Um nur die Produktinformationen aus der XML-Dokument verfügbar zu machen, erstellen Sie eine stark typisierte **DataSet** mit einem Schema, die als XML-Schema (XSD Schema Definition Language), der Zuordnungen, die die Produkte und Kapazitäten Reihenfolge geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5f93b-109">To expose only the product information from the XML document, create a strongly typed **DataSet** with a schema, written as XML Schema definition language (XSD) schema, that maps to the products and quantities ordered.</span></span> <span data-ttu-id="5f93b-110">Weitere Informationen zu stark typisierte **DataSet** Objekten finden Sie [typisierter DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="5f93b-110">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="5f93b-111">Der folgende Code zeigt das Schema aus der die stark typisierte **DataSet** für dieses Beispiel generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5f93b-111">The following code shows the schema from which the strongly typed **DataSet** is generated for this sample.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<xs:schema id="OrderDetail" xmlns=""   
                            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
                            xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"   
                            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="OrderDetail" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetails" codegen:typedName="LineItem" codegen:typedPlural="LineItems">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" type="xs:int" minOccurs="0" codegen:typedName="OrderID"/>  
              <xs:element name="Quantity" type="xs:short" minOccurs="0" codegen:typedName="Quantity"/>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Products" codegen:typedName="Product" codegen:typedPlural="Products">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
              <xs:element name="ProductName" type="xs:string" minOccurs="0" codegen:typedName="ProductName"/>  
              <xs:element name="QuantityPerUnit" type="xs:string" minOccurs="0" codegen:typedName="QuantityPerUnit"/>  
              <xs:element name="UnitsInStock" type="xs:short" minOccurs="0" codegen:typedName="UnitsInStock"/>  
              <xs:element name="UnitsOnOrder" type="xs:short" minOccurs="0" codegen:typedName="UnitsOnOrder"/>  
              <xs:element name="ReorderLevel" type="xs:short" minOccurs="0" codegen:typedName="ReorderLevel"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Products" />  
      <xs:field xpath="ProductID" />  
    </xs:unique>  
    <xs:keyref name="Relation1" refer="Constraint1" codegen:typedChildren="GetLineItems" codegen:typedParent="Product">  
      <xs:selector xpath=".//OrderDetails" />  
      <xs:field xpath="ProductID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="5f93b-112">Beachten Sie, dass nur Informationen aus der **OrderDetails** und **Produkte** Elemente des ursprünglichen XML-Dokuments befinden sich im Schema für die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="5f93b-112">Notice that only information from the **OrderDetails** and **Products** elements of the original XML document are included in the schema for the **DataSet**.</span></span> <span data-ttu-id="5f93b-113">Synchronisieren der **DataSet** mit einer **XmlDataDocument** wird sichergestellt, dass die Elemente nicht in der **DataSet** das XML-Dokument erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="5f93b-113">Synchronizing the **DataSet** with an **XmlDataDocument** ensures that the elements not included in the **DataSet** will persist with the XML document.</span></span>  
  
 <span data-ttu-id="5f93b-114">Mit dem stark typisierten **DataSet** aus dem XML-Schema generiert (mit dem Namespace **Northwind.FillOrder**), ein Teil des ursprünglichen XML-Dokuments kann durch Synchronisierung verfügbar gemacht werden die  **DataSet** mit der **XmlDataDocument** aus dem XML-Quelldokument geladen.</span><span class="sxs-lookup"><span data-stu-id="5f93b-114">With the strongly typed **DataSet** generated from the XML Schema (with a namespace of **Northwind.FillOrder**), a portion of the original XML document can be exposed by synchronizing the **DataSet** with the **XmlDataDocument** loaded from the source XML document.</span></span> <span data-ttu-id="5f93b-115">Beachten Sie, dass die **DataSet** aus generiert das Schema enthält, Struktur, aber keine Daten.</span><span class="sxs-lookup"><span data-stu-id="5f93b-115">Notice that the **DataSet** generated from the schema contains structure but no data.</span></span> <span data-ttu-id="5f93b-116">Die Daten werden eingefügt, beim Laden der XML-Daten in die **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="5f93b-116">The data is filled in when you load the XML into the **XmlDataDocument**.</span></span> <span data-ttu-id="5f93b-117">Wenn Sie versuchen, Sie laden ein **XmlDataDocument** , die mit synchronisiert eine **DataSet** , die bereits Daten enthält, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5f93b-117">If you attempt to load an **XmlDataDocument** that has been synchronized with a **DataSet** that already contains data, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="5f93b-118">Nach der **DataSet** (und die **XmlDataDocument**) wurde aktualisiert, die **XmlDataDocument** können schreiben, das geänderte XML-Dokument mit den Elementen, die ignoriert werden, indem Sie die **DataSet** noch intakt ist, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5f93b-118">After the **DataSet** (and the **XmlDataDocument**) has been updated, the **XmlDataDocument** can then write out the modified XML document with the elements ignored by the **DataSet** still intact, as shown below.</span></span> <span data-ttu-id="5f93b-119">Im Bestellszenario kann das geänderte Dokument, nachdem die Posten der Bestellung angegeben wurden, an den nächsten Schritt im Bestellprozess übergeben werden; das kann z. B. die Versandabteilung des Unternehmens sein.</span><span class="sxs-lookup"><span data-stu-id="5f93b-119">In the purchase order scenario, after the order items have been filled, the modified XML document can then be passed on to the next step in the order process, perhaps to the company's shipping department.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Xml  
Imports Northwind.FillOrder  
  
Public class Sample  
  Public Shared Sub Main()  
  
    Dim orderDS As OrderDetail = New OrderDetail  
  
    Dim xmlDocument As XmlDataDocument = New XmlDataDocument(orderDS)   
  
    xmlDocument.Load("Order.xml")  
  
    Dim orderItem As OrderDetail.LineItem  
    Dim product As OrderDetail.Product  
  
    For Each orderItem In orderDS.LineItems  
      product = orderItem.Product  
  
      ' Remove quantity from the current stock.  
      product.UnitsInStock = CType(product.UnitsInStock - orderItem.Quantity, Short)  
  
      ' If the remaining stock is less than the reorder level, order more.  
      If ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel) Then  
        product.UnitsOnOrder = CType(product.UnitsOnOrder + product.ReorderLevel, Short)  
      End If  
    Next  
  
    xmlDocument.Save("Order_out.xml")  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Xml;  
using Northwind.FillOrder;  
  
public class Sample  
{  
  public static void Main()  
  {  
    OrderDetail orderDS = new OrderDetail();   
  
    XmlDataDocument xmlDocument = new XmlDataDocument(orderDS);   
  
    xmlDocument.Load("Order.xml");  
  
    foreach (OrderDetail.LineItem orderItem in orderDS.LineItems)  
    {  
      OrderDetail.Product product = orderItem.Product;  
  
      // Remove quantity from the current stock.  
      product.UnitsInStock = (short)(product.UnitsInStock - orderItem.Quantity);  
  
      // If the remaining stock is less than the reorder level, order more.  
      if ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel)  
        product.UnitsOnOrder = (short)(product.UnitsOnOrder + product.ReorderLevel);  
    }  
  
    xmlDocument.Save("Order_out.xml");  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f93b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f93b-120">See also</span></span>

- [<span data-ttu-id="5f93b-121">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="5f93b-121">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="5f93b-122">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="5f93b-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
