---
title: Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit Polly
description: Erfahren Sie, wie Sie HTTP-Fehler mit Polly und HttpClientFactory verarbeiten können.
ms.date: 01/07/2019
ms.openlocfilehash: d5e0b6c830422990aaf1a5e3b6ae257eb3dae99c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696900"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a>Implementieren von Wiederholungen von HTTP-Aufrufen mit exponentiellem Backoff mit HttpClientFactory und Polly-Richtlinien

Für Wiederholungen mit exponentiellem Backoff wird empfohlen, fortgeschrittenere .NET-Bibliotheken wie die Open Source-Bibliothek [Polly](https://github.com/App-vNext/Polly) zu verwenden.

Polly ist eine .NET-Bibliothek, die Funktionen für die Flexibilität und die Behandlung von vorübergehenden Fehlern bereitstellt. Sie können diese Funktionen implementieren, indem Sie Polly-Richtlinien wie „Retry“, „Circuit Breaker“, „Bulkhead Isolation“, „Timeout“, und „Fallback“ anwenden. Polly ist auf .NET 4.x und die .NET Standard-Bibliothek 1.0 (die .NET Core unterstützt) ausgelegt.

Das Schreiben eines eigenen benutzerdefinierten Codes zur Verwendung der Polly-Bibliothek mit HttpClient kann jedoch sehr komplex sein. In der ursprünglichen Version von eShopOnContainers war der Baustein [ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) enthalten, der auf Polly basierte. Mit dem Release von [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md) wurde die Implementierung von robuster HTTP-Kommunikation mit Polly wesentlich einfacher, sodass dieser Baustein von eShopOnContainers nun als veraltet markiert wurde. 

Die folgenden Schritte veranschaulichen, wie Sie HTTP-Wiederholungen mit Polly in HttpClientFactory verwenden können. Die Integration von Polly wird im vorherigen Abschnitt erläutert.

**Verweisen auf die ASP.NET Core 2.2-Pakete**

`HttpClientFactory` ist seit .NET Core 2.1 verfügbar. Wir empfehlen jedoch die Verwendung der aktuellsten ASP.NET Core 2.2-Pakete von NuGet in Ihrem Projekt. Sie benötigen üblicherweise das Metapaket `AspNetCore` und das Erweiterungspaket `Microsoft.Extensions.Http.Polly`.

**Konfigurieren eines Clients mit der Polly-Wiederholungsrichtlinie in der Startup-Klasse**

Wie in den vorherigen Abschnitten beschrieben wurde, müssen Sie eine benannte oder typisierte HttpClient-Clientkonfiguration in Ihrer Startup.ConfigureServices(...)-Standardmethode definieren. Nun fügen Sie jedoch inkrementellen Code hinzu, der die Richtlinie für die HTTP-Wiederholungen mit exponentiellem Backoff angibt:

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

Durch die Methode **AddPolicyHandler()** werden Richtlinien zu `HttpClient`-Objekten hinzugefügt, die Sie verwenden werden. In diesem Fall wird eine Polly-Richtlinie für HTTP-Wiederholungen mit exponentiellem Backoff hinzugefügt.

Für einen modulareren Ansatz kann die HTTP-Wiederholungsrichtlinie in einer separaten Methode innerhalb der `Startup.cs`-Datei definiert werden. Dies wird im folgenden Code veranschaulicht:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

Mit Polly können Sie eine Wiederholungsrichtlinie definieren, die die Anzahl von Wiederholungen, die Konfiguration des exponentiellen Backoffs und die Aktionen enthält, die ausgeführt werden, wenn eine HTTP-Ausnahme ausgelöst wird, z.B. die Protokollierung des Fehlers. In diesem Fall ist die Richtlinie dafür konfiguriert, sechs Versuche mit einer exponentiellen Wiederholung durchzuführen, die bei zwei Sekunden beginnt. 

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>Hinzufügen einer Jitterstrategie zur Wiederholungsrichtlinie

Eine reguläre Wiederholungsrichtlinie kann ein System negativ beeinflussen, falls hohe Parallelität, hohe Skalierbarkeit und ein hohes Konfliktpotenzial vorhanden sind. Um mit Spitzenlasten umgehen zu können, die bei ähnlichen Wiederholungsanforderungen von vielen Clients bei einem Teilausfall auftreten, empfiehlt es sich als Notlösung, den Wiederholungsalgorithmus oder die Wiederholungsrichtlinie um eine Jitterstrategie zu ergänzen. Wenn für den exponentiellen Backoff der Jitter zufällig festgelegt wird, kann dies die Gesamtleistung des End-to-End-Systems verbessern. Dadurch lassen sich beim Auftreten von Problemen Lastspitzen verteilen. Wenn Sie eine einfache Polly-Richtlinie verwenden, könnte der Code zum Implementieren des Jitters wie folgt aussehen:

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Wiederholungsmuster**  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly und HttpClientFactory**  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- **Polly (.NET-Bibliothek zur Gewährleistung von Resilienz und zur Behandlung temporärer Fehler)**  
  <https://github.com/App-vNext/Polly>

- **Marc Brooker. Jitter: Making Things Better With Randomness** (Marc Brooker. Jitter: Dinge durch Zufall verbessern)  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
>[Zurück](explore-custom-http-call-retries-exponential-backoff.md)
>[Weiter](implement-circuit-breaker-pattern.md)
