---
title: Eigenständige JSON-Serialisierung mit DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 312bd7b2-1300-4b12-801e-ebe742bd2287
ms.openlocfilehash: 614776a905ec319624f76876762c25bfca15a357
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249447"
---
# <a name="stand-alone-json-serialization-using-datacontractjsonserializer"></a>Eigenständige JSON-Serialisierung mit DataContractJsonSerializer

> [!NOTE]
> Dieser Artikel <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>behandelt . Für die meisten Szenarien, die die Serialisierung und Deserialisierung von JSON beinhalten, empfehlen wir die APIs im [Namespace System.Text.Json](../../../standard/serialization/system-text-json-overview.md).

JSON (JavaScript Object Notation) ist ein Datenformat, das speziell zur Verwendung von JavaScript-Code entworfen wurde, der auf Webseiten innerhalb des Browsers ausgeführt wird. Es ist das Standarddatenformat, das von ASP.NET AJAX-Diensten verwendet wird, die in Windows Communication Foundation (WCF) erstellt wurden.

Dieses Format kann auch für AJAX-Dienste verwendet werden, die nicht in ASP.NET integriert sind. In diesem Fall ist zwar XML der Standard, jedoch kann JSON gewählt werden.

Und wenn Sie schließlich JSON-Unterstützung benötigen, aber keinen AJAX-Dienst erstellen, ermöglicht Ihnen der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, .NET-Objekte direkt in JSON-Daten zu serialisieren und diese Daten wieder in Instanzen von .NET-Typen zu deserialisieren. Eine Beschreibung hierzu finden Sie unter [Gewusst wie: Serialisieren und Deserialisieren von JSON-Daten](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).

Bei der Arbeit mit JSON werden mit wenigen Ausnahmen dieselben .NET-Typen unterstützt, die auch vom <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt werden. Eine Liste der unterstützten Typen finden Sie unter [Typen, die vom Data Contract Serializer unterstützt werden.](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md) Dazu gehören die meisten primitiven Typen, die meisten Array- und Auflistungstypen sowie die komplexen Typen, die das <xref:System.Runtime.Serialization.DataContractAttribute> und das <xref:System.Runtime.Serialization.DataMemberAttribute> verwenden.

## <a name="mapping-net-types-to-json-types"></a>Zuordnung von .NET-Typen zu JSON-Typen

Die folgende Tabelle zeigt die Entsprechungen zwischen .NET-Typen und JSON/JavaScript-Typen, die für die Zuordnung während der Serialisierung und Deserialisierung gelten.

|.NET-Typen|JSON/JavaScript|Notizen|
|----------------|----------------------|-----------|
|Alle numerischen Typen, z.&#160;B. <xref:System.Int32>, <xref:System.Decimal> oder <xref:System.Double>|Number|Spezielle Werte, z.&#160;B. `Double.NaN`, `Double.PositiveInfinity` und `Double.NegativeInfinity` werden nicht unterstützt und führen zu ungültigen JSON-Daten.|
|<xref:System.Enum>|Number|Siehe "Enumerationen und JSON" weiter unten in diesem Thema.|
|<xref:System.Boolean>|Boolean|--|
|<xref:System.String>, <xref:System.Char>|String|--|
|<xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>|String|Das Format dieser Typen in JSON ist das gleiche wie in XML (im Wesentlichen TimeSpan im ISO 8601 Duration-Format, GUID im "12345678-ABCD-ABCD-ABCD-1234567890AB" Format und URI in seiner natürlichen Zeichenfolgenform wie "http://www.example.com"). Genaue Informationen finden Sie unter [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).|
|<xref:System.Xml.XmlQualifiedName>|String|Das Format ist "name:namespace" (sämtliche Zeichen vor dem ersten Doppelpunkt bilden den Namen). Der Name oder der Namespace kann fehlen. Wenn kein Namespace angegeben wird, kann auch der Doppelpunkt weggelassen werden.|
|<xref:System.Array> vom Typ <xref:System.Byte>|Array von Zahlen|Jede Zahl stellt den Wert eines Bytes dar.|
|<xref:System.DateTime>|DateTime oder Zeichenfolge|Siehe "Datums-/Uhrzeitangaben und JSON" weiter unten in diesem Thema.|
|<xref:System.DateTimeOffset>|Komplexer Typ|Siehe "Datums-/Uhrzeitangaben und JSON" weiter unten in diesem Thema.|
|XML- und ADO.NET-Typen (<xref:System.Xml.XmlElement>,<br /><br /> <xref:System.Xml.Linq.XElement>. Arrays von <xref:System.Xml.XmlNode>,<br /><br /> <xref:System.Runtime.Serialization.ISerializable>,<br /><br /> <xref:System.Data.DataSet>).|String|Siehe den Abschnitt "XML-Typen und JSON" in diesem Thema.|
|<xref:System.DBNull>|Leerer komplexer Typ|--|
|Auflistungen, Wörterbücher und Arrays|Array|Siehe den Abschnitt "Auflistungen, Wörterbücher und Arrays" in diesem Thema.|
|Komplexe Typen (mit angewendetem <xref:System.Runtime.Serialization.DataContractAttribute> oder <xref:System.SerializableAttribute>)|Komplexer Typ|Datenmember werden Member des komplexen JavaScript-Typs.|
|Komplexe Typen (die die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren)|Komplexer Typ|Entspricht anderen komplexen Typen, jedoch werden einige <xref:System.Runtime.Serialization.ISerializable>-Typen nicht unterstützt. Weitere Informationen finden Sie in den Hinweisen zur ISerializable-Unterstützung im Abschnitt "Weitere Informationen" in diesem Thema.|
|`Null`-Wert für jeden Typ|Null|Nullable Werttypen werden ebenfalls unterstützt und JSON auf die gleiche Weise zugeordnet wie nicht NULL-Werttypen.|

### <a name="enumerations-and-json"></a>Enumerationen und JSON

Enumerationsmemberwerte werden in JSON als Zahlen behandelt. Dies unterscheidet sich von ihrer Behandlung in Datenverträgen, in die sie als Membernamen eingefügt werden. Weitere Informationen zur Verarbeitung von Datenverträgen finden Sie unter [Enumerationstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).

- Wenn beispielsweise `public enum Color {red, green, blue, yellow, pink}` gegeben ist, ergibt die Serialisierung von `yellow` die Zahl&#160;3 und nicht die Zeichenfolge "yellow".

- Alle `enum`-Member sind serialisierbar. Die <xref:System.Runtime.Serialization.EnumMemberAttribute>-Klasse und die <xref:System.NonSerializedAttribute>-Attribute werden ignoriert, wenn sie verwendet werden.

- Es ist möglich, einen nicht vorhandenen `enum`-Wert zu deserialisieren. Der Wert 87 kann z.&#160;B. in den vorherigen Farbenumerationswert deserialisiert werden, auch wenn kein entsprechender Farbname definiert ist.

- Eine `enum` aus Flags stellt keinen Sonderfall dar und wird wie jede andere `enum` behandelt.

### <a name="datestimes-and-json"></a>Datums-/Uhrzeitangaben und JSON

Das JSON-Format unterstützt Datums- und Zeitangaben nicht direkt. Jedoch werden sie sehr häufig verwendet, und ASP.NET AJAX bietet eine spezielle Unterstützung dieser Typen. Werden ASP.NET AJAX-Proxys verwendet, entspricht der <xref:System.DateTime>-Typ in .NET vollständig dem `DateTime`-Typ in JavaScript.

- Wird ASP.NET nicht verwendet, wird ein <xref:System.DateTime>-Typ in JSON durch ein spezielles Zeichenfolgenformat dargestellt, das im Abschnitt "Weitere Informationen" in diesem Thema beschrieben wird.

- <xref:System.DateTimeOffset> wird in JSON als komplexer Typ dargestellt: {"DateTime":dateTime,"OffsetMinutes":offsetMinutes}. Der `offsetMinutes`-Member gibt den mit der Position des Ereignisses von Interesse verbundenen Ortszeitoffset zur GMT (Greenwich Mean Time) an. GMT wird jetzt auch als UTC (Coordinated Universal Time) bezeichnet. Der `dateTime`-Member gibt den Zeitpunkt an, zu dem das betreffende Ereignis eingetreten ist (er wird wieder in einen `DateTime`-Typ in JavaScript umgewandelt, wenn ASP.NET AJAX verwendet wird; andernfalls wird er in eine Zeichenfolge umgewandelt). Bei der Serialisierung wird der `dateTime`-Member immer in GMT serialisiert. Wenn beispielsweise die Uhrzeit 3:00&#160;AM in der Zeitzone von New York beschrieben wird, dann enthält `dateTime` die Zeitangabe "8:00&#160;AM" und `offsetMinutes` den Wert "300" (minus 300&#160;Minuten oder 5&#160;Stunden gegenüber GMT).

  > [!NOTE]
  > Werden die Objekte <xref:System.DateTime> und <xref:System.DateTimeOffset> zu JSON serialisiert, behalten sie die Informationen nur mit Millisekundengenauigkeit bei. Werte, die kleiner als Millisekunden (Mikro-/Nanosekunden) sind, gehen bei der Serialisierung verloren.

### <a name="xml-types-and-json"></a>XML-Typen und JSON

XML-Typen werden zu JSON-Zeichenfolgen.

- Wenn z. B. ein Datenelement "q" vom Typ XElement abc/> enthält, \<lautet die JSON "q":"\<abc/>".

- Es gibt einige spezielle Regeln, die festlegen, wie XML eingebunden wird. Nähere Informationen dazu finden Sie im Abschnitt "Weitere Informationen" weiter unten in diesem Thema.

- Wenn Sie mit ASP.NET AJAX arbeiten und in JavaScript keine Zeichenfolgen, sondern XML DOM verwenden möchten, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft für <xref:System.ServiceModel.Web.WebGetAttribute> oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft für <xref:System.ServiceModel.Web.WebInvokeAttribute> auf XML fest.

### <a name="collections-dictionaries-and-arrays"></a>Auflistungen, Wörterbücher und Arrays

Alle Auflistungen, Wörterbücher und Arrays werden in JSON als Arrays dargestellt.

- Jede Anpassung, in der das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> verwendet wird, wird in der JSON-Darstellung ignoriert.

- Wörterbücher stellen keine Möglichkeit dar, JSON-Daten direkt zu bearbeiten. Wörterbuchzeichenfolge,\<Objekt> werden in WCF möglicherweise nicht auf die gleiche Weise unterstützt, wie von der Arbeit mit anderen JSON-Technologien erwartet. Wird beispielsweise in einem Wörterbuch "abc" dem Wert "xyz" und "def" dem Wert 42 zugeordnet, dann lautet die JSON-Darstellung nicht {"abc":"xyz","def":42}, sondern [{"Key":"abc","Value":"xyz"},{"Key":"def","Value":42}].

- Wenn Sie direkt mit JSON arbeiten möchten (also ohne vorher definierten strengen Vertrag auf Schlüssel und Werte dynamisch zugreifen möchten), stehen Ihnen mehrere Optionen zur Verfügung:

  - Erwägen Sie die Verwendung des [Beispiels für die schwache Typisierung von JSON Serialization (AJAX).](../../../../docs/framework/wcf/samples/weakly-typed-json-serialization-sample.md)

  - Verwenden Sie die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle und Deserialisierungskonstruktoren. Diese beiden Mechanismen ermöglichen es Ihnen, bei der Serialisierung und der Deserialisierung auf JSON-Schlüssel/Wert-Paare zuzugreifen, was jedoch in teilweise vertrauenswürdigen Szenarien nicht möglich ist.

  - Erwägen Sie, mit dem [Mapping Between JSON und XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md) zu arbeiten, anstatt einen Serialisierungsmodul zu verwenden.

  - *Polymorphismus* im Kontext der Serialisierung bezieht sich auf die Fähigkeit, einen abgeleiteten Typ zu serialisieren, bei dem sein Basistyp erwartet wird. Es gelten spezielle JSON-spezifische Regeln für die polymorphe Verwendung von Auflistungen (beispielsweise die Zuweisung einer Auflistung zu einem <xref:System.Object>. Dieser Punkt wird ausführlicher im Abschnitt "Weitere Informationen" weiter unten in diesem Thema erläutert.

## <a name="additional-details"></a>Weitere Details

### <a name="order-of-data-members"></a>Reihenfolge der Datenmember

Die Reihenfolge der Datenmember ist bei Verwendung von JSON nicht von Bedeutung. Insbesondere gilt: Auch wenn <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> festgelegt wird, können die JSON-Daten immer noch in jeder beliebigen Reihenfolge deserialisiert werden.

### <a name="json-types"></a>JSON-Typen

Der JSON-Typ muss bei der Deserialisierung nicht mit der vorangehenden Tabelle übereinstimmen. Beispielsweise wird ein Wert vom Typ `Int` normalerweise einer JSON-Zahl zugeordnet, aber er kann auch aus einer JSON-Zeichenfolge deserialisiert werden, sofern diese Zeichenfolge eine gültige Zahl enthält. Daher ist sowohl {"q":42} als auch {"q":"42"} zulässig, wenn ein `Int`-Datenmember namens "q" vorhanden ist.

### <a name="polymorphism"></a>Polymorphie

Polymorphe Serialisierung besteht aus der Fähigkeit, einen abgeleiteten Typ zu serialisieren, wo sein Basistyp erwartet wird. Dies wird für die JSON-Serialisierung durch WCF unterstützt, vergleichbar mit der Art und Weise, wie XML-Serialisierung unterstützt wird. Sie können z. `MyDerivedType` B. serialisieren, wo `MyBaseType` erwartet wird, oder serialisieren, `Int` wo `Object` erwartet wird.

Typinformationen gehen möglicherweise verloren, wenn ein abgeleiteter Typ deserialisiert wird, wo der Basistyp erwartet wird, es sei denn, Sie deserialisieren einen komplexen Typ. Wenn z.&#160;B. ein <xref:System.Uri> serialisiert wird, wo ein <xref:System.Object> erwartet wird, ergibt sich daraus eine JSON-Zeichenfolge. Wenn diese Zeichenfolge dann wieder in <xref:System.Object> zurück deserialisiert wird, wird ein .NET <xref:System.String> zurückgegeben. Das Deserialisierungsprogramm weiß nicht, dass die Zeichenfolge ursprünglich den Typ <xref:System.Uri> hatte. Allgemein gilt: Wird ein <xref:System.Object> erwartet, werden alle JSON-Zeichenfolgen als .NET-Zeichenfolgen und alle JSON-Arrays, die zur Serialisierung von .NET-Auflistungen, -Wörterbüchern und -Arrays verwendet wurden, als .NET <xref:System.Array> des Typs <xref:System.Object> deserialisiert, unabhängig davon, welchen ursprünglichen Typ sie hatten. Der JSON-Typ boolean wird dem .NET-Typ <xref:System.Boolean> zugeordnet. Wenn jedoch ein <xref:System.Object> erwartet wird, dann werden JSON-Zahlen in einen der .NET-Typen <xref:System.Int32>, <xref:System.Decimal> oder <xref:System.Double> serialisiert, wobei automatisch der am besten geeignete Typ ausgewählt wird.

Beim Deserialisieren in einen Schnittstellentyp, deserialisiert der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> die Daten so, als wäre ein Objekt als Typ deklariert.

Wenn Sie mit Ihren eigenen Basistyp und abgeleiteten Typen arbeiten, ist normalerweise die Verwendung von <xref:System.Runtime.Serialization.KnownTypeAttribute>, <xref:System.ServiceModel.ServiceKnownTypeAttribute> oder eines äquivalenten Mechanismus erforderlich. Wenn Sie z. B. über `Animal` einen Vorgang mit einem `Cat` Rückgabewert `Animal`verfügen und tatsächlich <xref:System.Runtime.Serialization.KnownTypeAttribute>eine Instanz `Animal` von <xref:System.ServiceModel.ServiceKnownTypeAttribute> (abgeleitet von ) `Cat` zurückgeben, sollten Sie entweder die , auf den Typ oder die auf den Vorgang anwenden und den Typ in diesen Attributen angeben. Weitere Informationen finden Sie unter [Bekannte Datenvertragstypen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).

Weitere Informationen zur polymorphen Serialisierung und der Einschränkungen, die Sie bei der Verwendung beachten müssen, finden Sie im Abschnitt "Weitere Informationen" weiter unten in diesem Thema.

### <a name="versioning"></a>Versionskontrolle

Die Datenvertragsversionsfunktionen werden einschließlich der <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle in JSON vollständig unterstützt. Darüber hinaus ist es in den meisten Fällen möglich, einen Typ in ein Format (beispielsweise XML) zu deserialisieren, es dann in ein anderes Format (beispielsweise JSON) zu serialisieren und die Daten in <xref:System.Runtime.Serialization.IExtensibleDataObject> beizubehalten. Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md). Denken Sie daran, dass JSON ungeordnet ist und daher alle Reihenfolgeninformationen verloren gehen. .JSON unterstützt auch keine mehrfachen Schlüssel/Wert-Paare mit dem gleichen Schlüsselnamen. Und schließlich sind alle Vorgänge mit <xref:System.Runtime.Serialization.IExtensibleDataObject> grundsätzlich polymorph. Das bedeutet, dass ihr abgeleiteter Typ <xref:System.Object> zugewiesen ist, dem Basistyp aller Typen.

## <a name="json-in-urls"></a>JSON in URLs

Bei Verwendung von ASP.NET AJAX-Endpunkten mit dem HTTP-GET-Verb (wobei das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut verwendet wird) werden eingehende Parameter in der Anforderungs-URL statt im Nachrichtentext angegeben. JSON wird auch in der Anforderungs-URL unterstützt, `Int` wenn Sie also `Person` einen Vorgang haben, der eine aufgerufene "Nummer" und einen komplexen Typ namens "p" verwendet, kann die URL der folgenden URL ähneln.

```html
http://example.com/myservice.svc/MyOperation?number=7&p={"name":"John","age":42}
```

Wenn Sie ein ASP.NET AJAX Script-Manager-Steuerelement und einen Proxy für den Aufruf des Diensts verwenden, wird diese URL automatisch vom Proxy erstellt und nicht erkannt. JSON kann nicht in URLs auf Nicht-ASP.NET AJAX-Endpunkten verwendet werden.

## <a name="advanced-information"></a>Weitere Informationen

### <a name="iserializable-support"></a>ISerializable-Unterstützung

#### <a name="supported-and-unsupported-iserializable-types"></a>Unterstützte und nicht unterstützte ISerializable-Typen

Im Allgemeinen werden Typen, die die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren, bei der Serialisierung oder Deserialisierung von JSON vollständig unterstützt. Jedoch sind manche dieser Typen (einschließlich einiger .NET&#160;Framework-Typen) so implementiert, dass die JSON-spezifischen Serialisierungseigenheiten dazu führen, dass diese Typen nicht korrekt deserialisiert werden:

- Mit <xref:System.Runtime.Serialization.ISerializable> ist der Typ einzelner Datenmember nicht im Voraus bekannt. Dies führt zu einer polymorphen Situation ähnlich der Deserialisierung von Typen in ein Objekt. Wie bereits erwähnt, führt dies in JSON möglicherweise zum Verlust der Typinformationen. Ein Typ z.&#160;B., der eine `enum` in seiner <xref:System.Runtime.Serialization.ISerializable>-Implementierung serialisiert und versucht, den erhaltenen Wert direkt wieder zurück in eine `enum` zu deserialisieren, wird ohne die korrekten Umwandlungen fehlschlagen, weil eine `enum` in JSON als Zahl serialisiert wird und JSON-Zahlen in die integrierten numerischen .NET-Typen (Int32, Decimal oder Double) deserialisiert werden. Deshalb geht die Tatsache, dass die verwendete Zahl ein `enum`-Wert war, verloren.

- Ein <xref:System.Runtime.Serialization.ISerializable>-Typ, der in seinem Deserialisierungskonstruktor von einer bestimmten Reihenfolge der Deserialisierung abhängt, wird bei der Deserialisierung mancher JSON-Daten möglicherweise ebenfalls fehlschlagen, weil die meisten JSON-Serialisierungsprogramme keine bestimmte Reihenfolge gewährleisten.

#### <a name="factory-types"></a>Factorytypen

Während die <xref:System.Runtime.Serialization.IObjectReference>-Schnittstelle allgemein in JSON unterstützt wird, werden Typen, die die Funktion „Factorytyp“ benötigen (die Rückgabe eines anderen Typs von <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%28System.Runtime.Serialization.StreamingContext%29> als den Typ, der die Schnittstelle implementiert) nicht unterstützt.

### <a name="datetime-wire-format"></a>DateTime-Übertragungsformat

<xref:System.DateTime>-Werte werden als JSON-Zeichenfolgen im Format "/Date(700000+0500)/" dargestellt, wobei die erste Zahl (700000 in dem angeführten Beispiel) die Anzahl der seit Mitternacht des 1. Januar 1970 in der GMT-Zeitzone verstrichenen Millisekunden (ohne Berücksichtigung der Sommerzeit) angibt. Die Zahl kann negativ sein und gibt dann einen früheren Zeitpunkt an. Der im Beispiel als „+0500“ angegebene Teil ist optional und legt fest, dass die Zeitangabe als <xref:System.DateTimeKind.Local> zu verstehen ist, also bei der Deserialisierung in eine lokale Zeitzone konvertiert werden muss. Fehlt dieser Teil, wird die Zeitangabe als <xref:System.DateTimeKind.Utc> deserialisiert. Die tatsächliche Zahl ("0500" in diesem Beispiel) und ihr Vorzeichen (+ oder -) werden ignoriert.

Bei der Serialisierung werden <xref:System.DateTime>-, <xref:System.DateTimeKind.Local>- und <xref:System.DateTimeKind.Unspecified>-Zeitangaben mit einem Offset und <xref:System.DateTimeKind.Utc>-Zeitangaben ohne Offset geschrieben.

Im JavaScript-Code eines ASP.NET AJAX-Clients werden solche Zeichenfolgen automatisch in `DateTime`-Instanzen für JavaScript konvertiert. Andere Zeichenfolgen ähnlicher Form, die aber nicht vom .NET-Typ <xref:System.DateTime> sind, werden ebenfalls konvertiert.

Die Konvertierung erfolgt nur, wenn die "/"-Zeichen escapeiert werden\\(d. h. die JSON sieht\\aus wie " /Date(700000+0500) /"), und aus diesem Grund entgeht wCfs JSON-Encoder (aktiviert durch die <xref:System.ServiceModel.WebHttpBinding>) immer dem "/"-Zeichen.

### <a name="xml-in-json-strings"></a>XML in JSON-Zeichenfolgen

#### <a name="xmlelement"></a>XmlElement

Der Typ <xref:System.Xml.XmlElement> wird ohne Einbindung serialisiert wie er ist. Beispielsweise wird das Datenelement "x" des Typs, <xref:System.Xml.XmlElement> der abc/> enthält, \<wie folgt dargestellt:

```json
{"x":"<abc/>"}
```

#### <a name="arrays-of-xmlnode"></a>XmlNode-Arrays

<xref:System.Array>-Objekte des Typs <xref:System.Xml.XmlNode> werden in ein Element namens ArrayOfXmlNode im Standardnamespace des Datenvertrags für den Typ eingebunden. Ist "x" ein Array, das den Attributknoten "N" im Namespace "ns" enthält, der seinerseits "value" und den leeren Elementknoten "M" enthält, dann ergibt sich folgende Darstellung.

```json
{"x":"<ArrayOfXmlNode xmlns=\"http://schemas.datacontract.org/2004/07/System.Xml\" a:N=\"value\" xmlns:a=\"ns\"><M/></ArrayOfXmlNode>"}
```

 Attribute in einem leeren Namespace werden am Anfang von XmlNode-Arrays (vor anderen Elementen) nicht unterstützt.

#### <a name="ixmlserializable-types-including-xelement-and-dataset"></a>IXmlSerializable-Typen, einschließlich XElement- und DataSet-Typen

<xref:System.Runtime.Serialization.ISerializable>-Typen teilen sich in "Inhaltstypen", "DataSet-Typen" und "Elementtypen". Definitionen dieser Typen finden Sie unter [XML und ADO.NET Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).

"Inhalts-" und "DataSet-Typen" werden ähnlich den <xref:System.Array>-Objekten von <xref:System.Xml.XmlNode>serialisiert, die im vorherigen Abschnitt erläutert wurden. Sie werden in ein Element eingebunden, dessen Name und Namespace dem Datenvertragsnamen und dem Namespace des jeweiligen Typs entsprechen.

"Elementtypen", wie das <xref:System.Xml.Linq.XElement>, werden serialisiert wie sie sind, ähnlich wie das bereits in diesem Thema erläuterte <xref:System.Xml.XmlElement>.

### <a name="polymorphism"></a>Polymorphie

#### <a name="preserving-type-information"></a>Bewahren von Typinformationen

Wie schon vorher festgestellt, wird Polymorphie in JSON mit einigen Einschränkungen unterstützt. JavaScript ist eine schwach typisierte Sprache, und Typidentität stellt normalerweise kein Problem dar. Wird jedoch JSON verwendet, um zwischen einem stark typisierten System (.NET) und einem schwach typisierten System (JavaScript) zu kommunizieren, ist es sinnvoll, die Typidentität zu bewahren. Die Typen mit den Datenvertragsnamen "Square" und "Circle" sind beispielsweise von einem Typ mit dem Datenvertragsnamen "Shape" abgeleitet. Wenn "Circle" von .NET zu JavaScript gesendet und später wieder an eine .NET-Methode übergeben wird, die "Shape" erwartet, ist es für .NET sinnvoll zu wissen, dass das fragliche Objekt ursprünglich ein "Circle" war. Andernfalls gehen eventuell alle für den abgeleiteten Typ spezifischen Informationen (z. B. der Datenmember "radius" von "Circle") verloren.

Um bei der Serialisierung komplexer Typen zu JSON die Typidentität zu bewahren, kann ein "Typhinweis" hinzugefügt werden, den das Deserialisierungsprogramm erkennen und auf den es entsprechend reagieren kann. Der "Typ-Hinweis" ist ein JSON-Schlüssel-Wert-Paar mit dem Schlüsselnamen "typ"\_\_(zwei Unterstriche gefolgt vom Wort "type"). Der Wert ist eine JSON-Zeichenfolge der Form "DataContractName:DataContractNamespace" (alles vor dem ersten Doppelpunkt bildet den Namen). Bei dem schon früher verwendeten Beispiel kann "Circle" wie folgt serialisiert werden.

```json
{"__type":"Circle:http://example.com/myNamespace","x":50,"y":70,"radius":10}
```

Der Typhinweis ist dem von der standardmäßigen XML-Schemainstanz definierten und bei der Serialisierung oder Deserialisierung verwendeten `xsi:type`-Attribut sehr ähnlich.

Datenmember,\_\_die als "Typ" bezeichnet werden, sind aufgrund eines potenziellen Konflikts mit dem Typhinweis verboten.

#### <a name="reducing-the-size-of-type-hints"></a>Reduzieren der Größe von Typhinweisen

Um die Größe von JSON-Nachrichten zu reduzieren,`http://schemas.datacontract.org/2004/07/`wird das standardmäßige Namespacepräfix des Datenvertrags ( ) durch das Zeichen "A" ersetzt. (Um diesen Ersatz umkehrbar zu machen, wird eine Fluchtregel verwendet: Wenn\\der Namespace mit den Zeichen\\"A" oder """ beginnt, werden sie mit einem zusätzlichen " " Zeichen angehängt). Wenn also "Circle" ein Typ im .NET-Namespace "MyApp.Shapes" ist, lautet `http://schemas.datacontract.org/2004/07/MyApp`der Standardmäßige Datenvertragsnamespace . Shapes und die JSON-Darstellung lautet wie folgt.

```json
{"__type":"Circle:#MyApp.Shapes","x":50,"y":70,"radius":10}
```

Sowohl die abgeschnittenen (#MyApp.Shapes) alshttp://schemas.datacontract.org/2004/07/MyApp.Shapes) auch die vollständigen (Namen werden bei der Deserialisierung verstanden).

#### <a name="type-hint-position-in-json-objects"></a>Position des Typhinweises in JSON-Objekten

Beachten Sie, dass in der JSON-Darstellung der Typhinweis das erste Element sein muss. Dies ist der einzige Fall, wo die Reihenfolge von Schlüssel/Wert-Paaren bei der JSON-Verarbeitung wichtig ist. Folgendes ist beispielsweise keine gültige Angabe des Typhinweises.

```json
{"x":50,"y":70,"radius":10,"__type":"Circle:#MyApp.Shapes"}
```

Sowohl <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> die von WCF als auch von ASP.NET AJAX-Clientseiten verwendeten AJAX-Clientseiten geben immer zuerst den Typhinweis aus.

#### <a name="type-hints-apply-only-to-complex-types"></a>Typhinweise gelten nur für komplexe Typen

Es gibt keine Möglichkeit, einen Typhinweis für nicht-komplexe Typen auszugeben. Hat z.&#160;B. ein Vorgang einen <xref:System.Object>-Rückgabetyp, gibt aber einen Circle-Typ zurück, entspricht die JSON-Darstellung wahrscheinlich der vorher gezeigten, und die Typinformationen werden beibehalten. Wird jedoch ein URI-Typ zurückgegeben, ist die JSON-Darstellung eine Zeichenfolge, und die Tatsache, dass diese Zeichenfolge einen URI-Typ darstellt, geht verloren. Dies gilt nicht nur für primitive Typen, sondern auch für Auflistungen und Arrays.

#### <a name="when-are-type-hints-emitted"></a>Wann Typhinweise ausgegeben werden

Typhinweise können die Nachrichtengröße beträchtlich erhöhen. Dieses Problem kann durch die Verwendung kürzerer Datenvertragsnamespaces (wenn möglich) vermieden werden. Deshalb bestimmen die folgenden Regeln, ob Typhinweise ausgegeben werden:

- Bei Verwendung von ASP.NET AJAX werden Typhinweise nach Möglichkeit ausgegeben, auch wenn keine Zuweisung von Basistypen zu abgeleiteten Typen besteht. Dies gilt auch, wenn beispielsweise ein Circle einem Circle zugewiesen ist. (Dies ist erforderlich, um den Aufruf aus der schwach typisierten JSON-Umgebung in die stark typisierte .NET-Umgebung vollständig zu unterstützen und den versehentlichen Verlust von Informationen zu vermeiden.)

- Bei Verwendung von AJAX-Diensten ohne ASP.NET-Integration werden Typhinweise nur dann ausgegeben, wenn es eine Zuweisung von Basistypen zu abgeleiteten Typen gibt &#8211; also wenn Circle einem Shape-Typ oder einem <xref:System.Object> zugewiesen ist, nicht aber, wenn Circle einem Circle zugewiesen ist. Dies stellt die zur korrekten Implementierung eines JavaScript-Clients notwendigen Mindestinformationen bereit und verbessert so die Leistung, schützt jedoch nicht vor dem Verlust von Typinformationen in nicht ordnungsgemäß implementierten Clients. Vermeiden Sie Zuweisungen von Basistypen zu abgeleiteten Typen auf dem Server, damit Sie diese Probleme nicht beim Client behandeln müssen.

- Wenn Sie den <xref:System.Runtime.Serialization.DataContractSerializer>-Typ verwenden, ermöglicht Ihnen der `alwaysEmitTypeInformation`-Parameter des Konstruktors, zwischen den beiden genannten Möglichkeiten zu wählen, wobei der Standard auf "`false`" festgelegt ist (Typhinweise nur wenn erforderlich ausgeben).

#### <a name="duplicate-data-member-names"></a>Doppelte Datenelementnamen

Im JSON-Objekt sind Informationen des abgeleiteten Typs zusammen mit denen des Basistyps in beliebiger Reihenfolge vorhanden. `Shape` Kann z. B. wie folgt dargestellt werden.

```json
{"__type":"Shape:#MyApp.Shapes","x":50,"y":70}
```

Circle wird dagegen möglicherweise wie folgt dargestellt wird.

```json
{"__type":"Circle:#MyApp.Shapes","x":50, "radius":10,"y":70}
```

Wenn der `Shape` Basistyp auch einen`radius`Datenmember mit dem Namen " enthielt, führt dies zu einer Kollision sowohl bei der Serialisierung (da `Shape.radius` `Circle.radius`JSON-Objekte keine wiederholten Schlüsselnamen haben können) als auch bei der Deserialisierung (da unklar ist, ob sich "radius" auf oder bezieht). Daher ist das Konzept des "Verbergens von Eigenschaften" (Datenmember mit gleichen Namen in der Basisklassen und in abgeleiteten Klassen), das in Datenvertragsklassen generell nicht empfohlen wird, im Fall von JSON sogar unzulässig.

#### <a name="polymorphism-and-ixmlserializable-types"></a>Polymorphie und IXmlSerializable-Typen

<xref:System.Xml.Serialization.IXmlSerializable>-Typen können polymorph einander zugewiesen werden, solange die Anforderungen für bekannte Typen entsprechend den üblichen Datenvertragsregeln eingehalten werden. Die Serialisierung eines <xref:System.Xml.Serialization.IXmlSerializable>-Typs statt eines <xref:System.Object>-Typs führt zu einem Verlust von Typinformationen, da das Ergebnis eine JSON-Zeichenfolge ist.

#### <a name="polymorphism-and-certain-interface-types"></a>Polymorphie und bestimmte Schnittstellentypen

Es ist nicht zulässig, einen Auflistungstyp oder einen Typ, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert, zu serialisieren, wenn ein Nicht-Auflistungstyp erwartet wird, der nicht <xref:System.Xml.Serialization.IXmlSerializable> ist (ausgenommen <xref:System.Object>). Beispielsweise eine benutzerdefinierte `IMyInterface` Schnittstelle, `MyType` die aufgerufen <xref:System.Collections.Generic.IEnumerable%601> wird, und ein Typ, der sowohl vom Typ `int` als auch von implementiert `IMyInterface`wird. Es ist verboten, von einem Vorgang zurückzukehren, `MyType` dessen Rückgabetyp . `IMyInterface` Dies `MyType` liegt daran, dass als JSON-Array serialisiert werden muss und ein Typhinweis erforderlich ist, und wie angegeben, bevor Sie einen Typhinweis nicht mit Arrays, sondern nur mit komplexen Typen einschließen können.

#### <a name="known-types-and-configuration"></a>Bekannte Typen und Konfiguration

Der gesamte vom <xref:System.Runtime.Serialization.DataContractSerializer> verwendete Mechanismus bekannter Typen wird auf gleiche Weise auch vom <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt. Beide Serialisierer lesen dasselbe Konfigurationselement, [ \<dataContractSerializer>](../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md) in [ \<system.runtime.serialization>](../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md), um bekannte Typen zu ermitteln, die über eine Konfigurationsdatei hinzugefügt wurden.

#### <a name="collections-assigned-to-object"></a>Objekten zugewiesene Auflistungen

Objekten zugewiesene Auflistungen werden so serialisiert als handele es sich um Auflistungen, die <xref:System.Collections.Generic.IEnumerable%601> implementieren: als JSON-Array, bei dem jeder Eintrag einen Typhinweis besitzt, als wäre er ein komplexer Typ. Beispielsweise sieht <xref:System.Collections.Generic.List%601> ein `Shape` Typ, <xref:System.Object> dem zugewiesen ist, wie folgt aus.

```json
[{"__type":"Shape:#MyApp.Shapes","x":50,"y":70},
{"__type":"Shape:#MyApp.Shapes","x":58,"y":73},
{"__type":"Shape:#MyApp.Shapes","x":41,"y":32}]
```

Wenn es wieder in ein <xref:System.Object> deserialisiert wird:

- `Shape`muss sich in der Liste Bekannte Typen befinden. Das <xref:System.Collections.Generic.List%601> Einhaben des Typs `Shape` in bekannten Typen hat keine Auswirkungen. Beachten Sie, dass Sie `Shape` in diesem Fall bei der Serialisierung keine bekannten Typen hinzufügen müssen - dies geschieht automatisch.

- Die Auflistung wird als <xref:System.Array> typisiert, <xref:System.Object> `Shape` der Instanzen enthält.

#### <a name="derived-collections-assigned-to-base-collections"></a>Abgeleitete Auflistungen, die Basisauflistungen zugewiesen sind

Wenn eine abgeleitete Auflistung einer Basisauflistung zugewiesen ist, wird die Auflistung normalerweise so serialisiert, als wäre sie eine Auflistung des Basistyps. Kann jedoch der Elementtyp der abgeleiteten Auflistung nicht dem Elementtyp der Basisauflistung zugewiesen werden, wird eine Ausnahme ausgelöst.

#### <a name="type-hints-and-dictionaries"></a>Typhinweise und Wörterbücher

Wenn ein Wörterbuch einem <xref:System.Object> zugewiesen ist, wird jeder Schlüssel- und Werteintrag des Wörterbuchs so behandelt, als wäre er <xref:System.Object> zugewiesen, und erhält einen Typhinweis.

Bei der Serialisierung von Wörterbuchtypen, wird das JSON-Objekt, das die Member "Key" und "Value" enthält, von der `alwaysEmitTypeInformation`-Einstellung nicht betroffen und erhält nur dann einen Typhinweis, wenn die oben genannten Auflistungsregeln dies erfordern.

### <a name="valid-json-key-names"></a>Gültige JSON-Schlüsselnamen

Das Serialisierungsprogramm codiert Schlüsselnamen in XML, die keine gültigen XML-Namen sind. Beispielsweise hätte ein Datenmember mit dem Namen "123" einen codierten\_Namen wie\_\_" x0031 x0032\_\_x0033 ",\_da "123" ein ungültiger XML-Elementname ist (beginnt mit einer Ziffer). Eine ähnliche Situation tritt möglicherweise bei einigen internationalen Zeichensätzen auf, deren Verwendung ungültige XML-Namen ergibt. Eine Erläuterung dieses Xml-Effekts auf die JSON-Verarbeitung finden Sie unter [Zwischenführen zwischen JSON und XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).

## <a name="see-also"></a>Siehe auch

- [Unterstützung für JSON und andere Datenübertragungsformate](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
