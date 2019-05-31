---
title: Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über neue Optionen zum Implementieren von Hintergrundtasks in Microservices in .NET Core mit IHostedService und BackgroundService
ms.date: 01/07/2019
ms.openlocfilehash: 9203404c0b623570c2b089087b7ce5d676bba376
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062975"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="c2bcc-103">Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse</span><span class="sxs-lookup"><span data-stu-id="c2bcc-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="c2bcc-104">Ab einem bestimmten Zeitpunkt müssen möglicherweise in auf Microservices basierende Anwendungen oder auch in anderen Anwendungen Hintergrundtasks und geplante Aufträge implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="c2bcc-105">Die Besonderheit bei der Verwendung einer Microservicesarchitektur ist, dass Sie einen einzelnen Microserviceprozess oder -container implementieren können, um diese Hintergrundtasks zu hosten. Dadurch kann bei Bedarf eine vertikale Skalierung vorgenommen und zusätzlich sichergestellt werden, dass nur eine Instanz des Microserviceprozesses oder -containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="c2bcc-106">In .NET Core werden diese Tasks als *gehostete Dienste* bezeichnet, da sie Dienste oder Logiken darstellen, die in einem Host, einer Anwendung oder einem Microservice gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-106">From a generic point of view, in .NET Core we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="c2bcc-107">Beachten Sie, dass in diesem Fall der gehostete Dienst einfach einer Klasse mit der Logik des Hintergrundtasks entspricht.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="c2bcc-108">Seit .NET Core 2.0 stellt das Framework die neue Schnittstelle <xref:Microsoft.Extensions.Hosting.IHostedService> bereit, mit der Sie gehostete Dienste einfach implementieren können.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="c2bcc-109">Die Grundidee besteht darin, mehrere Hintergrundtasks (gehostete Dienste) zu registrieren, die neben dem Host oder Webhost im Hintergrund ausgeführt werden (s. Abbildung 6-26).</span><span class="sxs-lookup"><span data-stu-id="c2bcc-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![ASP.NET Core 1.x und 2.x unterstützen IWebHost für Hintergrundprozesse in Web-Apps. .NET Core 2.1 unterstützt IHost für Hintergrundprozesse mit einfachen Konsolenanwendungen.](./media/image26.png)

<span data-ttu-id="c2bcc-111">**Abbildung 6-26**.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-111">**Figure 6-26**.</span></span> <span data-ttu-id="c2bcc-112">Verwenden von IHostedService mit Host und WebHost</span><span class="sxs-lookup"><span data-stu-id="c2bcc-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="c2bcc-113">Beachten Sie den Unterschied zwischen `WebHost` und `Host`.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-113">Note the difference made between `WebHost` and `Host`.</span></span>

<span data-ttu-id="c2bcc-114">`WebHost` (eine Basisklasse, die `IWebHost` implementiert) ist in ASP.NET Core 2.0 das Infrastrukturartefakt, mit dem Sie HTTP-Serverfunktionen für Ihren Prozess (z.B. das Implementieren einer MVC-Webanwendung oder eines Web-API-Diensts) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-114">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="c2bcc-115">Diese Klasse enthält in ASP.NET Core alle neuen Infrastrukturfunktionen, sodass Sie unter anderem die Abhängigkeitsinjektion verwenden, in Anforderungspipelines Middleware einfügen und `IHostedServices` für Hintergrundtasks nutzen können.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-115">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="c2bcc-116">`Host` (Basisklasse, die `IHost` implementiert) wurde in .NET Core 2.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-116">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="c2bcc-117">Mit `Host` können Sie eine ähnliche Infrastruktur wie mit `WebHost` (Dependency Injection, gehostete Dienste usw.) verwenden. Der Unterschied besteht darin, dass Sie einen einfacheren und schlankeren Prozess für den Host verwenden und auf Verknüpfungen mit MVC, einer Web-API oder HTTP-Serverfunktionen verzichten.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-117">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="c2bcc-118">Sie können daher entweder einen spezialisierten Hostprozess mit IHost erstellen, um ausschließlich gehostete Dienste (beispielsweise einen Microservice zum Hosten von `IHostedServices`) zu verarbeiten, oder aber einen vorhandenen ASP.NET Core-`WebHost` wie eine ASP.NET Core-Web-API oder eine MVC-Anwendung erweitern.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-118">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span>

<span data-ttu-id="c2bcc-119">Je nach Geschäfts- und Skalierbarkeitsanforderungen hat jeder Ansatz seine Vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-119">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="c2bcc-120">Zusammengefasst heißt das: Falls Ihre Hintergrundtasks nichts mit HTTP (IWebHost) zu tun haben, sollten Sie IHost verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-120">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use IHost.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="c2bcc-121">Registrieren von gehosteten Diensten in WebHost oder Host</span><span class="sxs-lookup"><span data-stu-id="c2bcc-121">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="c2bcc-122">Im Folgenden wird die `IHostedService`-Schnittstelle genauer beschrieben, da sie in `WebHost` und `Host` ähnlich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-122">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span>

<span data-ttu-id="c2bcc-123">SignalR ist ein Beispiel für ein Artefakt, das gehostete Dienste verwendet. Sie können den Dienst aber auch für einfachere Aufgaben verwenden. Hierzu zählt etwa Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c2bcc-123">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

- <span data-ttu-id="c2bcc-124">ein Hintergrundtask, der eine Datenbank abruft und nach Änderungen sucht</span><span class="sxs-lookup"><span data-stu-id="c2bcc-124">A background task polling a database looking for changes.</span></span>
- <span data-ttu-id="c2bcc-125">ein geplanter Task, der einen Cache regelmäßig aktualisiert</span><span class="sxs-lookup"><span data-stu-id="c2bcc-125">A scheduled task updating some cache periodically.</span></span>
- <span data-ttu-id="c2bcc-126">eine Implementierung von QueueBackgroundWorkItem, durch die ein Task in einem Hintergrundthread ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="c2bcc-126">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
- <span data-ttu-id="c2bcc-127">das Verarbeiten von Nachrichten aus einer Nachrichtenwarteschlange im Hintergrund einer Webanwendung, während allgemeine Dienste wie `ILogger` gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-127">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
- <span data-ttu-id="c2bcc-128">ein Hintergrundtask, der mit `Task.Run()` gestartet wird</span><span class="sxs-lookup"><span data-stu-id="c2bcc-128">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="c2bcc-129">Alle Aktionen lassen sich in einen Hintergrundtask auslagern, der auf IHostedService basiert.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-129">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="c2bcc-130">Sie können einem `WebHost` oder `Host` ein oder mehrere `IHostedServices` hinzufügen, indem Sie sie über den standardmäßigen Dependency Injection-Vorgang in einem ASP.NET Core-`WebHost` (oder in einem `Host` in .NET Core 2.1 oder höher) registrieren.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-130">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="c2bcc-131">Dabei müssen Sie die gehosteten Dienste in der bekannten `ConfigureServices()`-Methode der `Startup`-Klasse registrieren, was im folgenden Codeausschnitt einer typischen ASP.NET-WebHost-Klasse demonstriert wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-131">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="c2bcc-132">Der Code für den gehosteten Dienst `GracePeriodManagerService` entspricht dem Code aus dem Microservice für Bestellungen in eShopOnContainers. Bei den anderen beiden Diensten handelt es sich hingegen nur um zwei zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-132">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="c2bcc-133">Die Ausführung des `IHostedService`-Hintergrundtasks wird mit der Lebensdauer der Anwendung (also des Hosts oder des Microservices) koordiniert.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-133">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="c2bcc-134">Die Tasks werden registriert, wenn die Anwendung gestartet und eine ordnungsgemäße Aktion ausgeführt oder wenn die Anwendung beendet wird und dabei Ressourcen bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-134">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="c2bcc-135">Ohne die Nutzung von `IHostedService` ließe sich ein Hintergrundthread erstellen, in dem ein beliebiger Task ausgeführt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-135">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="c2bcc-136">Zum Beendigungszeitpunkt der Anwendung würde der Thread dann einfach beendet werden, und ordnungsgemäße Aktionen zur Bereinigung von Ressourcen könnten nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-136">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="c2bcc-137">Die IHostedService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2bcc-137">The IHostedService interface</span></span>

<span data-ttu-id="c2bcc-138">Beim Registrieren von `IHostedService` ruft .NET Core die Methoden `StartAsync()` und `StopAsync()` des Typs `IHostedService` während des Anwendungsstarts und -stopps auf.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-138">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="c2bcc-139">Nach dem Serverstart wird die Startmethode aufgerufen, und `IApplicationLifetime.ApplicationStarted` wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-139">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="c2bcc-140">Die `IHostedService`-Schnittstelle sieht in .NET Core wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c2bcc-140">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```

<span data-ttu-id="c2bcc-141">Sie können mehrere Implementierungen von IHostedService erstellen und wie zuvor gezeigt in der `ConfigureService()`-Methode des Dependency Injection-Containers registrieren.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-141">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="c2bcc-142">Alle gehosteten Dienste werden zusammen mit der Anwendung und dem Microservice gestartet und beendet.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-142">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="c2bcc-143">Als Entwickler sind Sie dafür verantwortlich, die Beendigungsaktion Ihrer Dienste zu verarbeiten, wenn die `StopAsync()`-Methode vom Host ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-143">As a developer, you are responsible for handling the stopping action of your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="c2bcc-144">Implementieren von IHostedService mit einer eigenen Klasse für gehostete Dienste, die von der Basisklasse BackgroundService abgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="c2bcc-144">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="c2bcc-145">Sie haben die Möglichkeit, eine eigene Klasse für gehostete Dienste neu zu erstellen und `IHostedService` zu implementieren, was im Fall von .NET Core 2.0 sogar unumgänglich ist.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-145">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span>

<span data-ttu-id="c2bcc-146">Da allerdings die meisten Hintergrundtasks ähnliche Anforderungen an die Verwaltung von Abbruchtoken und an weitere typische Vorgänge stellen, gibt es hierfür die praktische abstrakte Basisklasse `BackgroundService` (verfügbar ab NET Core 2.1), von der eigene Klassen abgeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-146">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="c2bcc-147">Diese Klasse fasst die wesentlichen Aufgaben zusammen, die zum Einrichten der Hintergrundtasks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-147">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="c2bcc-148">Im folgenden Codeausschnitt ist die in .NET Core implementierte abstrakte Basisklasse BackgroundService zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-148">The next code is the abstract BackgroundService base class as implemented in .NET Core.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="c2bcc-149">Wenn Sie eine Klasse aus der oben gezeigten abstrakten Basisklasse ableiten, müssen Sie dank der vererbten Implementierung nur die `ExecuteAsync()`-Methode in Ihrer eigenen Klasse für gehostete Dienste implementieren. Dies wird im folgenden vereinfachten Codeausschnitt aus eShopOnContainers demonstriert, in dem eine Datenbank abgerufen und Integrationsereignisse bei Bedarf im Ereignisbus veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-149">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMS / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

<span data-ttu-id="c2bcc-150">Im Fall von eShopOnContainers wird eine Anwendungsmethode ausgeführt, durch die eine Datenbanktabelle abgefragt wird. Diese sucht nach Bestellungen mit einem bestimmten Zustand. Beim Übernehmen von Änderungen werden Integrationsereignisse über den Ereignisbus veröffentlicht (im Hintergrund kann RabbitMQ oder Azure Service Bus verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="c2bcc-150">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="c2bcc-151">Sie könnten allerdings auch andere Geschäftshintergrundtasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-151">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="c2bcc-152">Standardmäßig wird für das Abbruchtoken ein Zeitlimit von 5 Sekunden festgelegt, obwohl der Wert beim Erstellen von `WebHost` mithilfe der `UseShutdownTimeout`-Erweiterung von `IWebHostBuilder` geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-152">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="c2bcc-153">Der Dienst muss also innerhalb von fünf Sekunden beendet werden, da er ansonsten sofort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-153">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="c2bcc-154">Im Folgenden Codeausschnitt wird dieses Zeitlimit geändert und auf 10 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-154">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="c2bcc-155">Zusammenfassendes Klassendiagramm</span><span class="sxs-lookup"><span data-stu-id="c2bcc-155">Summary class diagram</span></span>

<span data-ttu-id="c2bcc-156">In der folgenden Abbildung werden zusammenfassend die Klassen und Schnittstellen dargestellt, die an der Implementierung von IHostedService beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-156">The following image shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>

![Klassendiagramm: IWebHost und IHost können viele Dienste hosten, die von BackgroundService erben, der IHostedService implementiert.](./media/image27.png)

<span data-ttu-id="c2bcc-158">**Abbildung 6-27**.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-158">**Figure 6-27**.</span></span> <span data-ttu-id="c2bcc-159">Klassendiagramm mit mehreren Klassen und Schnittstellen, die mit IHostedService in Verbindung stehen</span><span class="sxs-lookup"><span data-stu-id="c2bcc-159">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="c2bcc-160">Überlegungen zur Bereitstellung und wesentliche Erkenntnisse</span><span class="sxs-lookup"><span data-stu-id="c2bcc-160">Deployment considerations and takeaways</span></span>

<span data-ttu-id="c2bcc-161">Sie sollten beachten, dass die konkrete Bereitstellung von ASP.NET Core-`WebHost` oder .NET Core-`Host` Ihre finale Lösung beeinflussen kann.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-161">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="c2bcc-162">Wenn Sie `WebHost` beispielsweise auf IIS oder in der regulären Azure App Service-Lösung bereitstellen, kann der Host durch den Neustart eines Anwendungspools heruntergefahren werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-162">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="c2bcc-163">Wenn Sie den Host jedoch als Container in einem Orchestrator wie Kubernetes oder Service Fabric bereitstellen, können Sie die zugesicherte Anzahl der aktiven Hostinstanzen anpassen.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-163">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="c2bcc-164">Darüber hinaus ist es empfehlenswert, sich mit anderen cloudbasierten Lösungen wie Azure Functions zu befassen, die speziell für derartige Szenarios entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-164">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="c2bcc-165">Wenn Sie möchten, dass der Dienst permanent ausgeführt und auf einer Windows Server-Instanz bereitgestellt wird, verwenden Sie einen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-165">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="c2bcc-166">Auch wenn `WebHost` in einem Anwendungspool bereitgestellt würde, müssten andere Szenarios wie das Leeren oder erneute Auffüllen des speicherinternen Anwendungscaches berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-166">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="c2bcc-167">Die `IHostedService`-Schnittstelle bietet eine einfache Möglichkeit, Hintergrundtasks in einer ASP.NET Core-Webanwendung (.NET 2.0 Core) oder in einem Prozess oder Host zu starten (ab .NET Core 2.1 mit `IHost`).</span><span class="sxs-lookup"><span data-stu-id="c2bcc-167">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="c2bcc-168">Der Hauptvorteil besteht darin, dass Sie durch einen ordnungsgemäßen Abbruch Bereinigungscode in Ihren Hintergrundtasks ausführen können, wenn der Host heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="c2bcc-168">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c2bcc-169">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c2bcc-169">Additional resources</span></span>

- <span data-ttu-id="c2bcc-170">**Building a scheduled task in ASP.NET Core/Standard 2.0 (Erstellen eines geplanten Tasks in ASP.NET Core/Standard 2.0)**</span><span class="sxs-lookup"><span data-stu-id="c2bcc-170">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> <br/>
    <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- <span data-ttu-id="c2bcc-171">**Implementing IHostedService in ASP.NET Core 2.0 (Implementieren von IHostedService in ASP.NET Core 2.0)**</span><span class="sxs-lookup"><span data-stu-id="c2bcc-171">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> <br/>
    <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- <span data-ttu-id="c2bcc-172">**GenericHost Sample using ASP.NET Core 2.1 (GenericHost-Beispiel mithilfe von ASP.NET Core 2.1)**</span><span class="sxs-lookup"><span data-stu-id="c2bcc-172">**GenericHost Sample using ASP.NET Core 2.1**</span></span> <br/>
    <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

>[!div class="step-by-step"]
><span data-ttu-id="c2bcc-173">[Zurück](test-aspnet-core-services-web-apps.md)
>[Weiter](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="c2bcc-173">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>
