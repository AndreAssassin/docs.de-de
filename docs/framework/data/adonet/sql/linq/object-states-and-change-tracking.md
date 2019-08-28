---
title: Objektzustände und Änderungsverfolgung
ms.date: 03/30/2017
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
ms.openlocfilehash: a60afab5158d0d5f66d12d6913ee890abc8ca730
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043520"
---
# <a name="object-states-and-change-tracking"></a>Objektzustände und Änderungsverfolgung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Objekte nehmen immer an einem *Zustand*Teil. Wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] z. B. ein neues Objekt erstellt, befindet sich dieses im `Unchanged`-Zustand. Ein neues-Objekt, das Sie selbst erstellen, ist <xref:System.Data.Linq.DataContext> dem unbekannt und `Untracked` befindet sich im-Zustand. Nach der erfolgreichen Ausführung von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> befinden sich alle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bekannten Objekte im `Unchanged`-Zustand. (Die einzige Ausnahme besteht in Objekten, die erfolgreich aus der Datenbank gelöscht wurden und sich im `Deleted`-Zustand befinden, weshalb sie für die <xref:System.Data.Linq.DataContext>-Instanz nicht nutzbar sind.)

## <a name="object-states"></a>Objektzustände

In der folgenden Tabelle werden die möglichen Zustände für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objekte aufgelistet.

|Status|Beschreibung|
|-----------|-----------------|
|`Untracked`|Ein Objekt, das nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verfolgt wird. Die Beispiele umfassen:<br /><br /> -Ein Objekt, das nicht durch den aktuellen <xref:System.Data.Linq.DataContext> abgefragt wurde (z. b. ein neu erstelltes Objekt).<br />-Ein durch Deserialisierung erstelltes Objekt<br />-Ein Objekt, das durch einen anderen <xref:System.Data.Linq.DataContext>abgefragt wird.|
|`Unchanged`|Ein Objekt, das mit dem aktuellen <xref:System.Data.Linq.DataContext> abgefragt wurde und von dem nicht bekannt ist, ob es seit der Erstellung verändert wurde.|
|`PossiblyModified`|Ein-Objekt, das an einen <xref:System.Data.Linq.DataContext>angefügt wird. Weitere Informationen finden Sie unter [Datenabruf-und CUD-Vorgänge in N-Tier-Anwendungen (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|
|`ToBeInserted`|Ein Objekt, das nicht vom aktuellen <xref:System.Data.Linq.DataContext> abgerufen wurde. Dies führt zu einem Datenbank-`INSERT` während <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeUpdated`|Ein Objekt, von dem bekannt ist, dass es seit dem Abruf verändert wurde. Dies führt zu einem Datenbank-`UPDATE` während <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeDeleted`|Ein zum Löschen markiertes Objekt, das zu einem Datenbank-`DELETE` während <xref:System.Data.Linq.DataContext.SubmitChanges%2A> führt.|
|`Deleted`|Ein Objekt, das in der Datenbank gelöscht wurde. Dieser Zustand ist endgültig und ermöglicht keine zusätzlichen Übergänge.|

## <a name="inserting-objects"></a>Einfügen von Objekten

Sie können `Inserts` mithilfe von <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> explizit anfordern. Alternativ kann [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Inserts` von abgeleitet werden, indem Objekte gefunden werden, die mit einem der bekannten Objekte verbunden sind, die aktualisiert werden müssen. Wenn Sie z. b. ein `Untracked` Objekt zu einem <xref:System.Data.Linq.EntitySet%601> hinzufügen oder <xref:System.Data.Linq.EntityRef%601> ein auf `Untracked` ein Objekt festlegen, machen `Untracked` Sie das Objekt mithilfe von überwachten Objekten im Diagramm erreichbar. Während der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>Verarbeitung [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden die überwachten Objekte durchlaufen und alle erreichbaren permanenten Objekte ermittelt, die nicht nachverfolgt werden. Solche Objekte sind Kandidaten für das Einfügen in die Datenbank.

Für Klassen in einer Vererbungs Hierarchie`o`legt () auch den Wert des als *Diskriminator* bezeichneten Members fest `o`, damit er mit dem Objekttyp identisch ist <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>. Entspricht ein Typ dem standardmäßigen Diskriminatorwert, wird durch diese Aktion der Diskriminatorwert mit dem Standardwert überschrieben. Weitere Informationen finden Sie [unter Vererbungs Unterstützung](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).

> [!IMPORTANT]
> Ein der `Table` hinzugefügtes Objekt befindet sich nicht im Identitäts-Cache. Der Identitäts-Cache enthält nur die Elemente, die aus der Datenbank abgerufen werden. Nach einem Aufruf von <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> erscheint die hinzugefügte Entität erst dann in den Abfragen für die Datenbank, wenn <xref:System.Data.Linq.DataContext.SubmitChanges%2A> erfolgreich abgeschlossen wurde.

## <a name="deleting-objects"></a>Löschen von Objekten

Sie markieren ein verfolgtes Objekt `o` zum Löschen, indem Sie <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>(o) in der entsprechenden <xref:System.Data.Linq.Table%601> aufrufen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]berücksichtigt das Entfernen eines Objekts aus einem <xref:System.Data.Linq.EntitySet%601> als Update Vorgang, und der entsprechende Fremdschlüssel Wert wird auf NULL festgelegt. Das Ziel der Operation (`o`) wird nicht aus seiner Tabelle gelöscht. `cust.Orders.DeleteOnSubmit(ord)` weist beispielsweise auf ein Update hin, wenn die Beziehung zwischen `cust` und `ord` durch Festlegen des Fremdschlüssels `ord.CustomerID` auf NULL getrennt wurde. Hierbei wird die entsprechende Zeile für `ord` nicht gelöscht.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]führt die folgende Verarbeitung aus, wenn ein Objekt aus<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>der Tabelle gelöscht wird:

- Wenn <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird, wird eine `DELETE`-Operation für dieses Objekt ausgeführt.

- Die Löschung wird unabhängig davon, ob diese geladen sind, nicht an verwandte Objekte weitergeleitet. Verwandte Objekte werden vor allem nicht geladen, um die Beziehungseigenschaft zu aktualisieren.

- Nach erfolgreicher Ausführung von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> werden die Objekte auf den `Deleted`-Zustand festgelegt. Daher können Sie das Objekt oder seine `id` nicht in diesem <xref:System.Data.Linq.DataContext> verwenden. Der interne Cache einer <xref:System.Data.Linq.DataContext>-Instanz eliminiert keine Objekte, die abgerufen oder neu hinzugefügt wurden, auch wenn diese in der Datenbank gelöscht wurden.

Sie können <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> nur für ein Objekt aufrufen, das vom <xref:System.Data.Linq.DataContext> verfolgt wird. Bei einem `Untracked`-Objekt müssen Sie <xref:System.Data.Linq.Table%601.Attach%2A> vor <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> aufrufen. Der Aufruf von <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> für ein `Untracked`-Objekt löst eine Ausnahme aus.

> [!NOTE]
> Durch das Entfernen eines Objekts aus einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Tabelle wird angegeben, dass `DELETE` zum Zeitpunkt von <xref:System.Data.Linq.DataContext.SubmitChanges%2A>ein entsprechender SQL-Befehl generiert wird. Diese Aktion entfernt das Objekt nicht aus dem Cache und gibt das Löschen auch nicht an verwandte Objekte weiter.
>
> Um die `id` eines gelöschten Objekts freizugeben, verwenden Sie eine neue <xref:System.Data.Linq.DataContext>-Instanz. Zum Bereinigen verwandter Objekte können Sie die Funktion zum *Löschen von Lösch* vorschnitten der Datenbank verwenden oder die verknüpften Objekte manuell löschen.
>
> Die verwandten Objekte müssen in keiner besonderen Reihenfolge gelöscht werden (im Gegensatz zur Datenbank).

## <a name="updating-objects"></a>Aktualisieren von Objekten

Sie können `Updates` durch Überwachen der Änderungsmitteilungen erkennen. Benachrichtigungen werden durch das <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging>-Ereignis in Eigenschaften-Settern bereitgestellt. Wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] über die erste Änderung an einem Objekt benachrichtigt, wird eine Kopie dieses Objekts erstellt, und das Objekt gilt als Kandidat zur Erzeugung einer `Update`-Anweisung.

Bei Objekten, die nicht implementieren <xref:System.ComponentModel.INotifyPropertyChanging>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] behält eine Kopie der Werte bei, die Objekte beim ersten materialisieren hatten. Beim Abrufen <xref:System.Data.Linq.DataContext.SubmitChanges%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] von vergleicht die aktuellen und ursprünglichen Werte, um zu entscheiden, ob das Objekt geändert wurde.

Bei Updates von Beziehungen gilt der Verweis vom unter- zum übergeordneten Element (der Verweis, der dem Fremdschlüssel entspricht) als Autorität. Der Verweis in die umgekehrte Richtung (d. h. vom übergeordneten zum untergeordneten Element) ist optional. Beziehungsklassen (<xref:System.Data.Linq.EntitySet%601> und <xref:System.Data.Linq.EntityRef%601>) stellen die Konsistenz bidirektionaler Verweise für 1:n-Beziehungen und 1:1-Beziehungen sicher. Verwendet das Objektmodel <xref:System.Data.Linq.EntitySet%601> oder <xref:System.Data.Linq.EntityRef%601> nicht und ist ein umgekehrter Verweis vorhanden, ist es Ihre Aufgabe, diesen beim Update der Beziehung mit dem vorwärts gerichteten Verweis konsistent zu halten.

Wenn Sie den erforderlichen Verweis und den entsprechenden Fremdschlüssel aktualisieren, müssen Sie deren Übereinstimmung sicherstellen. Eine <xref:System.InvalidOperationException>-Ausnahme wird ausgelöst, wenn die beiden Elemente zum Zeitpunkt des Aufrufs von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> nicht synchron sind. Obwohl die Werte von Fremdschlüsseln für ein Update der zugrunde liegenden Zeile ausreichen, müssen Sie die Referenz ändern, um die Konnektivität des Objektgraphen und die bidirektionale Konsistenz von Beziehungen zu erhalten.

## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)
