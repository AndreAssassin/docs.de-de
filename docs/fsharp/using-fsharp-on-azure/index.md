---
title: Verwenden von F# in Azure
description: Anleitung zur Verwendung von Azure-Diensten mit F#
author: sylvanc
ms.date: 09/22/2016
ms.openlocfilehash: 92b453b680a5f8c55f35458e9020f15444e90035
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211737"
---
# <a name="using-f-on-azure"></a>Verwenden von F# in Azure

F# ist eine hervorragende Sprache für die Cloudprogrammierung und wird häufig zum Schreiben von ASP.NET-Webanwendungen, Clouddiensten, in der Cloud gehosteten Microservices und für die skalierbare Datenverarbeitung verwendet.

In den folgenden Abschnitten finden Sie Ressourcen zur Verwendung einer Reihe von Azure-Diensten mit F#.

> [!NOTE]
> Wenn ein bestimmter Azure-Dienst in dieser Dokumentation nicht erläutert wird, wenden Sie sich entweder an die Azure Functions- oder die .NET-Dokumentation für diesen Dienst. Einige Azure-Dienste sind sprachunabhängig und erfordern keine sprachspezifische Dokumentation und sind hier nicht aufgeführt.

## <a name="using-azure-virtual-machines-with-f"></a>Verwenden von virtuellen Azure-Computern mit F#\#

Azure unterstützt eine Vielzahl von Konfigurationen von virtuellen Computern. Informationen dazu finden Sie unter [Linux und Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).

Um F# auf einem virtuellen Computer zum Ausführen, für die Kompilierung und/oder zum Erstellen von Skripts zu installieren, gehen Sie unter [Use F# on Linux (Verwenden von F# unter Linux)](https://fsharp.org/use/linux) und [Use F# on Windows (Verwenden von F# unter Windows)](https://fsharp.org/use/windows).

## <a name="using-azure-functions-with-f"></a>Verwenden von Azure Functions mit F#\#

[Azure Functions](https://azure.microsoft.com/services/functions/) ist eine Lösung zum einfachen Ausführen kleiner Codestücke oder „Funktionen“ in der Cloud. Sie können nur den Code schreiben, den Sie für Ihr vorliegendes Problem benötigen, und müssen sich keine Sorgen über die Ausführung der gesamten Anwendung oder der Infrastruktur machen. Ihre Funktionen sind mit Ereignissen in Azure Storage und anderen in der Cloud gehosteten Ressourcen verbunden. Daten fließen über Funktionsargumente in Ihre F#-Funktionen. Sie können die Entwicklungssprache Ihrer Wahl verwenden und auf Azure vertrauen, dass skaliert wird, wenn dies erforderlich ist.

Azure Functions unterstützt F# als Hauptprogrammiersprache mit effizienter, reaktiver, skalierbare Ausführung von F#-Code. Referenzdokumentationen zur Verwendung von F# mit Azure Functions finden Sie unter [F#-Entwicklerreferenz zu Azure Functions](/azure/azure-functions/functions-reference-fsharp).

Weitere Ressourcen für die Verwendung von Azure Functions und F#:

* [Skalieren von Azure Functions in F# mit Suave](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [Vorgehensweise: Erstellen von Azure-Funktion inF#](https://mnie.github.io/2016-09-08-AzureFunctions/)
* [Mithilfe des Azure-Typanbieters mit Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a>Verwenden von Azure Storage mit F#\#

Azure Storage ist eine Ebene von Speicherlösung für moderne Anwendungen, die auf Dauerhaftigkeit., Verfügbarkeit und Skalierbarkeit für die Bedürfnisse ihrer Kunden beruhen. F#Programme können direkt mit Azure Storage-Dienste, die mit den in den folgenden Artikeln beschriebenen Methoden interagieren.

* [Erste Schritte mit Azure Blob Storage mit F#](blob-storage.md)
* [Erste Schritte mit Azure File Storage mit F#](file-storage.md)
* [Erste Schritte mit Azure Queue Storage mit F#](queue-storage.md)
* [Erste Schritte mit Azure Table Storage mit F#](table-storage.md)

Azure Storage kann auch in Verbindung mit Azure Functions über die deklarative Konfiguration anstatt mit expliziten API-Aufrufen verwendet werden. Beispiele für F# finden Sie unter [Azure Functions – Storage-Blobbindungen](/azure/azure-functions/functions-bindings-storage).

## <a name="using-azure-app-service-with-f"></a>Verwenden von Azure App Service mit F#\#

[Azure App Service](https://azure.microsoft.com/services/app-service/) ist eine Cloudplattform zum Erstellen leistungsstarker Web- und mobilen Apps, die sich überall mit Daten verbinden, ob in der Cloud oder lokal.

* [F#Azure-Web-API-Beispiel](https://github.com/fsprojects/azure-webapi-example)
* [Hosten von F# in einer Webanwendung in Azure](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a>Verwenden von Apache Spark mit F# mit Azure HDInsight

[Apache Spark für Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) ist ein Open-Source-Verarbeitungsframework, das umfangreiche Anwendungen zur Datenanalyse ausführt. Durch Azure kann Apache Spark einfach und kosteneffektiv bereitgestellt werden. Entwickeln Sie Ihre Spark-Anwendung in F# mithilfe von [Mobius](https://github.com/Microsoft/Mobius), einer .NET-API für Spark.

* [Implementieren von Spark-Apps in F# mithilfe von Mobius](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)
* [Beispiel F# Spark-Apps, die mithilfe von Mobius](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-cosmos-db-with-f"></a>Verwenden von Azure Cosmos DB mit F#\#

[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) ist ein NoSQL-Dienst für hoch verfügbare, Global verteilten apps.

Azure Cosmos DB kann mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions mit F# die reagieren oder dazu führen, dass Änderungen an Azure Cosmos DB-Sammlungen. Finden Sie unter [Azure Cosmos DB-Bindungen für Azure Functions](/azure/azure-functions/functions-bindings-cosmosdb), oder
2. Mithilfe der [Azure Cosmos DB .NET SDK für SQL-API](/azure/cosmos-db/sql-api-sdk-dotnet). Die Beispiele sind in C# geschrieben.

## <a name="using-azure-event-hubs-with-f"></a>Mithilfe von Azure Event Hubs mit F#\#

[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) stellt Telemetrieerfassung im Cloudmaßstab von Websites, Apps und Geräten bereit.

Azure Event Hubs kann mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions mit F#, was durch Ereignisse ausgelöst wird. (Weitere Informationen finden Sie unter [Event Hub-Bindungen für Azure Functions](/azure/azure-functions/functions-bindings-event-hubs)) oder
2. Mithilfe der [.NET SDK für Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="using-azure-notification-hubs-with-f"></a>Verwenden von Azure Notification Hubs mit F#\#

[Azure Notification Hubs](/azure/notification-hubs/) ist eine plattformübergreifende, erweiterbare Pushinfrastruktur, die Ihnen ermöglicht, Pushbenachrichtigungen von Mobilgeräten von jedem Backend (in der Cloud oder lokal) zu jeder mobilen Plattform zu senden.

Azure Notification Hubs können mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions in F#, wodurch Ergebnisse an Notification Hub gesendet werden. (Weitere Informationen finden Sie unter [Azure Functions Notification Hub-Ausgabebindung](/azure/azure-functions/functions-bindings-notification-hubs) oder
2. Mithilfe der [.NET SDK für Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="implementing-webhooks-on-azure-with-f"></a>Implementieren von WebHooks in Azure mit F#\#

Ein [Webhook](https://en.wikipedia.org/wiki/Webhook) ist ein Rückruf, der durch eine Webanfrage ausgelöst wird. Webhooks werden von Websites wie GitHub verwendet, um Ereignisse zu signalisieren.

Webhooks können in F# implementiert und in Azure durch [HTTP- und Webhookbindungen in Azure Functions](/azure/azure-functions/functions-bindings-http-webhook) gehostet werden.

## <a name="using-webjobs-with-f"></a>Verwenden von Webjobs mit F\#

[WebJobs](/azure/app-service-web/web-sites-create-web-jobs) sind Programme, die Sie in Ihrer App Service-Web-App auf drei Arten ausführen können: bedarfsgesteuert, kontinuierlich oder zeitplanmäßig.

[Beispiel F# Webjob](https://github.com/jrr/webjob-project-examples)

## <a name="implementing-timers-on-azure-with-f"></a>Implementieren von Timern in Azure mit F\#

Timer lösen Aufruffunktionen auf Grundlage eines Zeitplans, einmal oder wiederkehrend aus.

Timer können in F# implementiert und in Azure durch einen [Timerauslöser in Azure Functions in F#](/azure/azure-functions/functions-bindings-timer) gehostet werden.

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a>Bereitstellen und Verwalten von Azure-Ressourcen mit F#-Skripts

Azure-VMs können programmgesteuert bereitgestellt und von F#-Skripts mithilfe der Microsoft.Azure.Management-Pakete und APIs verwaltet werden. Bespiele finden Sie unter [Erste Schritte mit den Verwaltungsbibliotheken für .NET](https://msdn.microsoft.com/library/dn722415.aspx) und [Azure Resource Manager-Bereitstellung im Vergleich zur klassischen Bereitstellung: Grundlegendes zu Bereitstellungsmodellen und zum Status von Ressourcen](/azure/azure-resource-manager/resource-manager-deployment-model).

Auch andere Azure-Ressourcen können möglicherweise auch von F#-Skripts bereitgestellt und verwaltet werden, die über die gleichen Komponenten verfügen. Beispielsweise können Sie Speicherkonten erstellen, Bereitstellen von Azure Cloud Services, Azure Cosmos DB-Instanzen erstellen und Verwalten von Azure Notification Hubs programmgesteuert von F#-Skripts.

Die Verwendung von F#-Skripts zum Bereitstellen und Verwalten von Ressourcen ist normalerweise nicht notwendig. Azure-Ressourcen können z. B. auch direkt über eine Beschreibung der JSON-Vorlage bereitgestellt werden, die parametrisiert werden können. Informationen, einschließlich Beispiele wie die [Azure-Schnellstartvorlagen](https://azure.microsoft.com/resources/templates/), finden Sie unter [Bewährte Methoden für das Erstellen von Azure Resource Manager-Vorlagen](/azure/azure-resource-manager/resource-manager-template-best-practices).

## <a name="other-resources"></a>Weitere Ressourcen

* [Die vollständige Dokumentation für alle Azure-Dienste](/azure/)
