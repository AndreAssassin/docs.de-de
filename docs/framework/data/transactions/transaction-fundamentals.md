---
title: Transaktionsgrundlagen
ms.date: 03/30/2017
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
ms.openlocfilehash: 49e44ce1112a44c105f47560017331afe4454a0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076757"
---
# <a name="transaction-fundamentals"></a>Transaktionsgrundlagen
In Transaktionen werden mehrere Aufgaben zusammengefasst. Stellen Sie sich z.&amp;#160;B. vor, dass eine Anwendung zwei Aufgaben ausführt. Zuerst erstellt sie eine neue Tabelle in einer Datenbank. Danach ruft sie ein spezielles Objekt auf, um Daten zu sammeln, zu formatieren und in die neue Tabelle einzufügen. Diese beiden Aufgaben sind aufeinander bezogen und sogar voneinander abhängig, da nur dann eine neue Tabelle erstellt werden sollte, wenn diese mit Daten gefüllt werden kann. Wenn beide Aufgaben im Bereich einer Transaktion ausgeführt werden, wird die zwischen ihnen bestehende Beziehung verstärkt. Falls die zweite Aufgabe fehlschlägt, wird die erste Aufgabe bis zu einem Punkt rückgängig gemacht, der vor der Erstellung der Tabelle liegt.  
  
 Um ein vorhersagbares Verhalten sicherzustellen, müssen alle Transaktionen die vier grundlegenden Eigenschaften Unteilbarkeit, Konsistenz, Isolation und Dauerhaftigkeit besitzen. Diese Eigenschaften verstärken der Rolle termingebundener Transaktionen als Projekte, die entweder ganz oder gar nicht ausgeführt werden. Weitere Informationen zu den ACID finden Sie unter [ACID-Eigenschaften](https://go.microsoft.com/fwlink/?LinkId=98791). Durch diese vier Eigenschaften wird also garantiert, dass ein Satz verwandter Aufgaben entweder insgesamt erfolgreich ausgeführt wird oder fehlschlägt. In der Terminologie der Transaktionsverarbeitung heißt dies, dass für eine Transaktion entweder ein Commit oder ein Rollback durchgeführt wird. Damit für eine Transaktion ein Commit ausgeführt werden kann, müssen alle Teilnehmer garantieren, ausschließlich permanente Änderungen an Daten vorzunehmen. Änderungen müssen auch im Fall von Systemausfällen oder anderen unvorhergesehenen Ereignissen dauerhaft sein. Wenn auch nur ein einziger Teilnehmer dies nicht garantieren kann, schlägt die gesamte Transaktion fehl. Alle Änderungen an Daten, die im Bereich der Transaktion vorgenommen wurden, werden bis zu einem bestimmten definierten Punkt rückgängig gemacht.  
  
 Eine Transaktion kann auf eine einzelne Datenressource beschränkt werden, z.&amp;#160;B. eine Datenbank oder eine Meldungswarteschlange. In diesem Szenario wird die lokale Transaktion vom dem in <xref:System.Transactions> verfügbaren Transaktions-Manager verwaltet, Da sie von der Datenressource gesteuert werden, sind diese Transaktionen effizient und leicht zu verwalten.  
  
 Transaktionen können auch mehrere Datenressourcen umfassen. Verteilte Transaktionen versetzen Sie in die Lage, verschiedene Operationen, die in unterschiedlichen Systemen ausgeführt werden, in einer Alles-oder-Nichts-Aktion zusammenzufassen. In diesem Szenario werden die Transaktionen vom Microsoft Distributed Transaction Coordinator (MSDTC) koordiniert, der auf jedem System vorhanden ist.  
  
 Wenn Sie mithilfe der in <xref:System.Transactions> verfügbaren Klassen eine Transaktionsanwendung entwickeln, müssen Sie weder um den erforderlichen Typ von Transaktion noch um den benötigten Transaktions-Manager Gedanken machen. Die <xref:System.Transactions>-Infrastruktur verwaltet diese automatisch für Sie.  
  
 Beim Erstellen einer Transaktion können Sie die Isolationsstufe angeben, die für die Transaktion gelten soll. Die Isolationsstufe, definiert durch die <xref:System.Transactions.IsolationLevel> Enumeration bestimmt, welche Zugriffsebene andere Transaktionen auf die Daten sich von der Transaktion wirkt müssen.  
  
 Sie können Transaktionen, die mithilfe von ADO.NET erstellen <xref:System.EnterpriseServices>, oder das transaktionsprogrammierungsmodell durch die <xref:System.Transactions> Namespace. Die [von System.Transactions bereitgestellte Funktionen](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md) Thema wird erläutert, die Funktionen, die Sie, zum Schreiben einer transaktionsanwendung mithilfe verwenden können der <xref:System.Transactions> Namespace.  
  
## <a name="see-also"></a>Siehe auch

- [Von System.Transactions bereitgestellte Funktionen](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)
