---
title: 'Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: ebf96bc575ef68e1190c5b9be7111902c0f69fef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780988"
---
# <a name="walkthrough-querying-across-relationships-c"></a>Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)
Diese exemplarische Vorgehensweise veranschaulicht die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Verwendung von *Zuordnungen* , um Fremdschlüssel Beziehungen in der Datenbank darzustellen.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Sie müssen die exemplarische Vorgehensweise abgeschlossen [haben: Einfaches Objektmodell und Abfrage (C#)](walkthrough-simple-object-model-and-query-csharp.md). Diese exemplarische Vorgehensweise basiert auf jener und erfordert die Datei northwnd.mdf im Verzeichnis c:\linqtest5.  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst drei Hauptaufgaben:  
  
- Hinzufügen einer Entitätsklasse zur Darstellung der Orders-Tabelle in der Beispieldatenbank Northwind.  
  
- Ergänzen von Anmerkungen zur `Customer`-Klasse, um die Beziehung zwischen der `Customer`-Klasse und der `Order`-Klasse zu erweitern.  
  
- Erstellen und Ausführen einer Abfrage, um das Abrufen von `Order`-Informationen unter Verwendung der `Customer`-Klasse zu testen  
  
## <a name="mapping-relationships-across-tables"></a>Zuordnen von Beziehungen über Tabellen hinweg  
 Erstellen Sie nach der Definition der `Customer`-Klasse die Definition der `Order`-Entitätsklasse, die den folgenden Code enthält. Dieser gibt an, dass `Order.Customer` ein Fremdschlüssel zu `Customer.CustomerID` ist.  
  
### <a name="to-add-the-order-entity-class"></a>So fügen Sie die Order-Entitätsklasse hinzu  
  
- Geben Sie den folgenden Code nach der `Customer`-Klasse ein, oder fügen Sie ihn ein:  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a>Hinzufügen von Anmerkungen zu einer Customer-Klasse  
 In diesem Schritt fügen Sie der `Customer`-Klasse Anmerkungen hinzu, um deren Beziehung zur `Order`-Klasse anzugeben. (Diese Ergänzung ist nicht unbedingt erforderlich, da die Definition der Beziehungen in beide Richtungen zum Erstellen der Verbindung ausreicht. Mithilfe dieser Anmerkung können Sie jedoch leicht in allen Richtungen zwischen den Objekten navigieren.)  
  
### <a name="to-annotate-the-customer-class"></a>So fügen Sie der Customer-Klasse Anmerkungen hinzu  
  
- Geben Sie den folgenden Code in die `Customer`-Klasse ein, oder fügen Sie ihn ein:  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Erstellen und Ausführen einer Abfrage über die Customer-Order-Beziehung  
 Sie können nun direkt auf die `Order`-Objekte zugreifen, und zwar von den `Customer`-Objekten aus oder in umgekehrter Richtung. Sie benötigen keinen expliziten *Join* zwischen Kunden und Bestellungen.  
  
### <a name="to-access-order-objects-by-using-customer-objects"></a>So greifen Sie mithilfe von Customer-Objekten auf Order-Objekte zu  
  
1. Ändern Sie die `Main`-Methode durch das Eingeben oder Einfügen des folgenden Codes in die Methode:  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2. Drücken Sie F5, um die Anwendung zu debuggen.  
  
    > [!NOTE]
    > Sie können den SQL-Code im Konsolenfenster eliminieren, indem Sie `db.Log = Console.Out;` auskommentieren.  
  
3. Drücken Sie die EINGABETASTE im Konsolenfenster, um das Debuggen zu stoppen.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>Erstellen einer Datenbankansicht mit strikter Typbindung  
 Es ist viel leichter, mit einer Datenbankansicht mit strikter Typbindung zu beginnen. Bei strikter Typbindung des <xref:System.Data.Linq.DataContext>-Objekts benötigen Sie keine Aufrufe von <xref:System.Data.Linq.DataContext.GetTable%2A>. Sie können Tabellen mit strikter Typbindung in allen Abfragen verwenden, wenn Sie das <xref:System.Data.Linq.DataContext>-Objekt mit strikter Typbindung verwenden.  
  
 In den folgenden Schritten erstellen Sie `Customers` als Tabelle mit strikter Typbindung und Zuordnung zur Customers-Tabelle in der Datenbank.  
  
### <a name="to-strongly-type-the-datacontext-object"></a>So erstellen Sie die striktre Typbindung für das DataContext-Objekt  
  
1. Fügen Sie den folgenden Code oberhalb der Deklaration der `Customer`-Klasse hinzu.  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2. Ändern Sie die `Main`-Methode wie folgt, damit diese den <xref:System.Data.Linq.DataContext> mit strikter Typbindung verwendet:  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3. Drücken Sie F5, um die Anwendung zu debuggen.  
  
     Die Ausgabe im Konsolenfenster lautet:  
  
     `ID=WHITC`  
  
4. Drücken Sie die EINGABETASTE im Konsolenfenster, um das Debuggen zu stoppen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die nächste exemplarische Vorgehens[Weise (Exemplarische Vorgehensweise: Bearbeiten von DatenC#(](walkthrough-manipulating-data-csharp.md))) veranschaulicht, wie Daten geändert werden. Diese exemplarische Vorgehensweise setzt nicht voraus, dass Sie die beiden in dieser Serie abgeschlossenen exemplarischen Vorgehensweisen speichern.  
  
## <a name="see-also"></a>Siehe auch

- [Lernen durch exemplarische Vorgehensweisen](learning-by-walkthroughs.md)
