---
title: Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von RabbitMQ zum Implementieren eines Ereignisbusmessagings für Integrationsereignisse für die Entwicklung oder für Testumgebungen
ms.date: 10/02/2018
ms.openlocfilehash: af02208bb9e680403a04377ccb740a8b15be29bc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675887"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="ef633-103">Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen</span><span class="sxs-lookup"><span data-stu-id="ef633-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="ef633-104">Wenn Sie den benutzerdefinierten Ereignisbus basierend auf RabbitMQ erstellen, das in einem Container ausgeführt wird, so wie bei der eShopOnContainers-Anwendung, sollte er nur für Entwicklungszwecke und Testumgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef633-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="ef633-105">Sie sollten ihn nicht für Ihre Produktionsumgebung verwenden, es sei denn, Sie erstellen ihn als Teil eines produktionsbereiten Service Busses.</span><span class="sxs-lookup"><span data-stu-id="ef633-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="ef633-106">Einem einfachen benutzerdefinierten Ereignisbus fehlen ggf. viele produktionsbereite wichtige Features, über die ein kommerzieller Service Bus verfügt.</span><span class="sxs-lookup"><span data-stu-id="ef633-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="ef633-107">Eine der benutzerdefinierten Implementierungen des Ereignisbusses in eShopOnContainers ist eine Bibliothek, die die RabbitMQ-API verwendet. Es gibt jedoch noch eine weitere, die auf Azure Service Bus basiert.</span><span class="sxs-lookup"><span data-stu-id="ef633-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span>

<span data-ttu-id="ef633-108">Aufgrund der Implementierung von Ereignisbussen mit RabbitMQ können Microservices, wie in Abbildung 6-21 dargestellt, Ereignisse abonnieren, veröffentlichen und empfangen.</span><span class="sxs-lookup"><span data-stu-id="ef633-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![RabbitMQ fungiert als Mittler zwischen dem Nachrichtenverleger und den Abonnenten, um die Verteilung zu verarbeiten.](./media/image22.png)

<span data-ttu-id="ef633-110">**Abbildung 6-21**.</span><span class="sxs-lookup"><span data-stu-id="ef633-110">**Figure 6-21.**</span></span> <span data-ttu-id="ef633-111">RabbitMQ-Implementierung eines Ereignisbusses</span><span class="sxs-lookup"><span data-stu-id="ef633-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="ef633-112">Die EventBusRabbitMQ-Klasse implementiert im Code die generische IEventBus-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ef633-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="ef633-113">Dies basiert auf Abhängigkeitsinjektion, damit Sie von dieser Dev/Test-Version auf eine Produktionsversion umstellen können.</span><span class="sxs-lookup"><span data-stu-id="ef633-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="ef633-114">Die RabbitMQ-Implementierung eines Beispiel-Dev/Test-Ereignisbusses ist Standardcode.</span><span class="sxs-lookup"><span data-stu-id="ef633-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="ef633-115">Er muss die Verbindung mit dem RabbitMQ-Server verwalten und Code für die Veröffentlichung von eines Nachrichtenereignisses in den Warteschlangen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef633-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="ef633-116">Darüber hinaus muss er ein Wörterbuch von Sammlungen der Integrationsereignishandler für jeden Ereignistyp implementieren. Diese Ereignistypen können, wie in Abbildung 6-21 dargestellt, eine unterschiedliche Instanziierung haben und verschiedene Abonnements für jeden Empfängermicroservice.</span><span class="sxs-lookup"><span data-stu-id="ef633-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="ef633-117">Implementieren einer einfachen Publish-Methode mit RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="ef633-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="ef633-118">Der folgende Code ist eine ***vereinfachte*** Version einer Ereignisbusimplementierung für RabbitMQ, um das gesamte Szenario vorzustellen.</span><span class="sxs-lookup"><span data-stu-id="ef633-118">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="ef633-119">Die Verbindung wird nicht wirklich so hergestellt.</span><span class="sxs-lookup"><span data-stu-id="ef633-119">You don't really handle the connection this way.</span></span> <span data-ttu-id="ef633-120">Eine vollständige Implementierung finden Sie im tatsächlichen Code im Repository [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).</span><span class="sxs-lookup"><span data-stu-id="ef633-120">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span> 

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

<span data-ttu-id="ef633-121">Der [tatsächliche Code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) der Publish-Methode in der Anwendung „eShopOnContainers“ wird mithilfe der [Polly](https://github.com/App-vNext/Polly)-Wiederholungsrichtlinie verbessert, die die Aufgabe eine bestimmte Anzahl von Malen wiederholt, falls der RabbitMQ-Container noch nicht bereit ist.</span><span class="sxs-lookup"><span data-stu-id="ef633-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="ef633-122">Dies kann auftreten, wenn die Container mithilfe von „docker-compose“ gestartet werden. Ein RabbitMQ-Container startet z.B. möglicherweise langsamer als die anderen Container.</span><span class="sxs-lookup"><span data-stu-id="ef633-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="ef633-123">Wie bereits erwähnt, gibt es viele mögliche Konfigurationen in RabbitMQ. Daher sollte dieser Code nur für Entwicklungs- und Testumgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef633-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="ef633-124">Implementieren des Abonnementcodes mit der RabbitMQ-API</span><span class="sxs-lookup"><span data-stu-id="ef633-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="ef633-125">So wie bei dem Publish-Code ist der folgende eine Vereinfachung eines Teils der Ereignisbusimplementierung für RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="ef633-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="ef633-126">Wie gesagt müssen Sie ihn normalerweise nicht ändern, es sei denn, Sie nehmen Verbesserungen vor.</span><span class="sxs-lookup"><span data-stu-id="ef633-126">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="ef633-127">Jeder Ereignistyp hat einen zugehörigen Kanal, über den Ereignisse von RabbitMQ abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ef633-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="ef633-128">In jedem Kanal und Ereignistyp können so viele Ereignishandler vorhanden sein wie nötig.</span><span class="sxs-lookup"><span data-stu-id="ef633-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="ef633-129">Die Subscribe-Methode akzeptiert ein IIntegrationEventHandler-Objekt, das einer Rückrufmethode im aktuellen Microservice ähnelt, sowie ein zugehöriges IntegrationEvent-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ef633-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="ef633-130">Der Code fügt diesen Ereignishandler dann zur Liste der Ereignishandler hinzu, über die jeder Integrationsereignistyp pro Clientmicroservice verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="ef633-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="ef633-131">Wenn der Clientcode noch nicht von dem Ereignis abonniert wurde, erstellt er einen Kanal für den Ereignistyp, um Ereignisse im Push-Format von RabbitMQ empfangen zu können, wenn das Ereignis in einem anderen Dienst veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="ef633-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ef633-132">[Zurück](integration-event-based-microservice-communications.md)
>[Weiter](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="ef633-132">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>