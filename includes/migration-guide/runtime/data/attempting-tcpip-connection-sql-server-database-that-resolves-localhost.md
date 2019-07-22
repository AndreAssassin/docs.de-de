---
ms.openlocfilehash: e36dac19beb6251debef100656670a6623344eea
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237841"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Der Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird, schlägt fehl

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 und 4.6.1 tritt bei dem Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird, folgender Fehler auf: &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server. Der Server wurde nicht gefunden oder es konnte nicht auf ihn zugegriffen werden. Stellen Sie sicher, dass der Instanzname richtig ist und dass SQL Server für Remoteverbindungen konfiguriert ist. (Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Auffinden des angegebenen Servers/der angegebenen Instanz)&quot;|
|Vorschlag|Dieses Problem wurde behoben und das vorherige Verhalten in .NET Framework 4.6.2 wiederhergestellt. Führen Sie ein Upgrade auf .NET Framework 4.6.2 durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird.|
|Bereich|Gering|
|Version|4.6|
|Typ|Laufzeit|
