---
title: Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von RabbitMQ zum Implementieren eines Ereignisbusmessagings für Integrationsereignisse für die Entwicklung oder für Testumgebungen
ms.date: 10/02/2018
ms.openlocfilehash: af02208bb9e680403a04377ccb740a8b15be29bc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644437"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen

Wenn Sie den benutzerdefinierten Ereignisbus basierend auf RabbitMQ erstellen, das in einem Container ausgeführt wird, so wie bei der eShopOnContainers-Anwendung, sollte er nur für Entwicklungszwecke und Testumgebungen verwendet werden. Sie sollten ihn nicht für Ihre Produktionsumgebung verwenden, es sei denn, Sie erstellen ihn als Teil eines produktionsbereiten Service Busses. Einem einfachen benutzerdefinierten Ereignisbus fehlen ggf. viele produktionsbereite wichtige Features, über die ein kommerzieller Service Bus verfügt.

Eine der benutzerdefinierten Implementierungen des Ereignisbusses in eShopOnContainers ist eine Bibliothek, die die RabbitMQ-API verwendet. Es gibt jedoch noch eine weitere, die auf Azure Service Bus basiert.

Aufgrund der Implementierung von Ereignisbussen mit RabbitMQ können Microservices, wie in Abbildung 6-21 dargestellt, Ereignisse abonnieren, veröffentlichen und empfangen.

![RabbitMQ fungiert als Mittler zwischen dem Nachrichtenverleger und den Abonnenten, um die Verteilung zu verarbeiten.](./media/image22.png)

**Abbildung 6-21**. RabbitMQ-Implementierung eines Ereignisbusses

Die EventBusRabbitMQ-Klasse implementiert im Code die generische IEventBus-Schnittstelle. Dies basiert auf Abhängigkeitsinjektion, damit Sie von dieser Dev/Test-Version auf eine Produktionsversion umstellen können.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

Die RabbitMQ-Implementierung eines Beispiel-Dev/Test-Ereignisbusses ist Standardcode. Er muss die Verbindung mit dem RabbitMQ-Server verwalten und Code für die Veröffentlichung von eines Nachrichtenereignisses in den Warteschlangen bereitstellen. Darüber hinaus muss er ein Wörterbuch von Sammlungen der Integrationsereignishandler für jeden Ereignistyp implementieren. Diese Ereignistypen können, wie in Abbildung 6-21 dargestellt, eine unterschiedliche Instanziierung haben und verschiedene Abonnements für jeden Empfängermicroservice.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementieren einer einfachen Publish-Methode mit RabbitMQ

Der folgende Code ist eine ***vereinfachte*** Version einer Ereignisbusimplementierung für RabbitMQ, um das gesamte Szenario vorzustellen. Die Verbindung wird nicht wirklich so hergestellt. Eine vollständige Implementierung finden Sie im tatsächlichen Code im Repository [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs). 

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

Der [tatsächliche Code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) der Publish-Methode in der Anwendung „eShopOnContainers“ wird mithilfe der [Polly](https://github.com/App-vNext/Polly)-Wiederholungsrichtlinie verbessert, die die Aufgabe eine bestimmte Anzahl von Malen wiederholt, falls der RabbitMQ-Container noch nicht bereit ist. Dies kann auftreten, wenn die Container mithilfe von „docker-compose“ gestartet werden. Ein RabbitMQ-Container startet z.B. möglicherweise langsamer als die anderen Container.

Wie bereits erwähnt, gibt es viele mögliche Konfigurationen in RabbitMQ. Daher sollte dieser Code nur für Entwicklungs- und Testumgebungen verwendet werden.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Implementieren des Abonnementcodes mit der RabbitMQ-API

So wie bei dem Publish-Code ist der folgende eine Vereinfachung eines Teils der Ereignisbusimplementierung für RabbitMQ. Wie gesagt müssen Sie ihn normalerweise nicht ändern, es sei denn, Sie nehmen Verbesserungen vor.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();
        
        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

Jeder Ereignistyp hat einen zugehörigen Kanal, über den Ereignisse von RabbitMQ abgerufen werden. In jedem Kanal und Ereignistyp können so viele Ereignishandler vorhanden sein wie nötig.

Die Subscribe-Methode akzeptiert ein IIntegrationEventHandler-Objekt, das einer Rückrufmethode im aktuellen Microservice ähnelt, sowie ein zugehöriges IntegrationEvent-Objekt. Der Code fügt diesen Ereignishandler dann zur Liste der Ereignishandler hinzu, über die jeder Integrationsereignistyp pro Clientmicroservice verfügen kann. Wenn der Clientcode noch nicht von dem Ereignis abonniert wurde, erstellt er einen Kanal für den Ereignistyp, um Ereignisse im Push-Format von RabbitMQ empfangen zu können, wenn das Ereignis in einem anderen Dienst veröffentlicht wird.

>[!div class="step-by-step"]
>[Zurück](integration-event-based-microservice-communications.md)
>[Weiter](subscribe-events.md)
