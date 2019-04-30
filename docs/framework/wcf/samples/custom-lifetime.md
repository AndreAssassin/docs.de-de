---
title: Benutzerdefinierte Lebensdauer
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003158"
---
# <a name="custom-lifetime"></a><span data-ttu-id="0644b-102">Benutzerdefinierte Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="0644b-102">Custom lifetime</span></span>

<span data-ttu-id="0644b-103">In diesem Beispiel wird veranschaulicht, wie schreiben Sie eine Windows Communication Foundation (WCF)-Erweiterung, um die benutzerdefinierte Lebensdauerdienste für freigegebene Instanzen von WCF-Dienst bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="0644b-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="0644b-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="0644b-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="0644b-105">Freigegebene Instanziierung</span><span class="sxs-lookup"><span data-stu-id="0644b-105">Shared instancing</span></span>

<span data-ttu-id="0644b-106">WCF bietet mehrere instanziierungsmodi für Ihre Dienstinstanzen.</span><span class="sxs-lookup"><span data-stu-id="0644b-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="0644b-107">Der freigegebene Instanziierungsmodus, die in diesem Artikel behandelten bietet eine Möglichkeit, eine Dienstinstanz zwischen mehreren Kanälen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0644b-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="0644b-108">Clients können wenden Sie sich an eine Factorymethode im Dienst und erstellen einen neuen Kanal aus, um Kommunikation zu starten.</span><span class="sxs-lookup"><span data-stu-id="0644b-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="0644b-109">Der folgende Codeausschnitt zeigt, wie eine Clientanwendung einen neuen Kanal zu einer vorhandenen Dienstinstanz erstellt:</span><span class="sxs-lookup"><span data-stu-id="0644b-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="0644b-110">Der freigegebene Instanziierungsmodus unterscheidet sich von anderen Instanziierungsmodi in seiner einzigartigen Methode zum Freigeben von Dienstinstanzen.</span><span class="sxs-lookup"><span data-stu-id="0644b-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="0644b-111">Standardmäßig für alle Kanäle geschlossen werden ein <xref:System.ServiceModel.InstanceContext>, die WCF-Dienst-Laufzeit überprüft, ob der Dienst <xref:System.ServiceModel.InstanceContextMode> konfiguriert ist <xref:System.ServiceModel.InstanceContextMode.PerCall> oder <xref:System.ServiceModel.InstanceContextMode.PerSession>, und wenn also die Instanz frei, und die Ressourcen von Ansprüchen.</span><span class="sxs-lookup"><span data-stu-id="0644b-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="0644b-112">Wenn eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> ist WCF verwendet wird, aufgerufen werden. die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode der Implementierung des Anbieters, bevor die Instanz freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0644b-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="0644b-113">Wenn <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> gibt `true` die Instanz freigegeben wird, andernfalls die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung ist zuständig für die Benachrichtigung der `Dispatcher` von dem Leerlaufzustand durch Verwendung einer Rückrufmethode.</span><span class="sxs-lookup"><span data-stu-id="0644b-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="0644b-114">Dies erfolgt durch Aufrufen der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> -Methode des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="0644b-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="0644b-115">In diesem Beispiel wird veranschaulicht, wie Sie verzögern freigeben, können die <xref:System.ServiceModel.InstanceContext> mit einem Leerlauftimeout von 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="0644b-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="0644b-116">Erweitern von InstanceContext</span><span class="sxs-lookup"><span data-stu-id="0644b-116">Extending the InstanceContext</span></span>

<span data-ttu-id="0644b-117">In WCF <xref:System.ServiceModel.InstanceContext> ist der Link zwischen der Dienstinstanz und `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="0644b-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="0644b-118">WCF lässt sich durch Hinzufügen von neuen Zustand oder ein Verhalten mithilfe des erweiterbaren Objektmusters diese Laufzeitkomponente zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0644b-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="0644b-119">Das erweiterbare Objektmuster wird in WCF verwendet, um entweder vorhandene Laufzeitklassen neue Funktionen zu erweitern oder zu einem Objekt neue Zustandsfunktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0644b-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="0644b-120">Es gibt drei Schnittstellen im erweiterbaren Objektmuster: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> und <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="0644b-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="0644b-121">Die <xref:System.ServiceModel.IExtensibleObject%601> Schnittstelle wird implementiert von Objekten um Erweiterungen zuzulassen, die ihre Funktionalität anpassen.</span><span class="sxs-lookup"><span data-stu-id="0644b-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="0644b-122">Die <xref:System.ServiceModel.IExtension%601>-Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs `T` sein können.</span><span class="sxs-lookup"><span data-stu-id="0644b-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="0644b-123">Und schließlich die <xref:System.ServiceModel.IExtensionCollection%601> Schnittstelle ist eine Sammlung von <xref:System.ServiceModel.IExtension%601> Implementierungen, die es ermöglicht eine Implementierung der abrufen <xref:System.ServiceModel.IExtension%601> anhand ihres Typs.</span><span class="sxs-lookup"><span data-stu-id="0644b-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="0644b-124">Aus diesem Grund zum Erweitern der <xref:System.ServiceModel.InstanceContext>, müssen Sie implementieren die <xref:System.ServiceModel.IExtension%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0644b-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="0644b-125">In diesem Beispielprojekt das `CustomLeaseExtension` -Klasse enthält diese Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0644b-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="0644b-126">Die <xref:System.ServiceModel.IExtension%601>-Schnittstelle verfügt über zwei Methoden: <xref:System.ServiceModel.IExtension%601.Attach%2A> und <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="0644b-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="0644b-127">Wie ihre Namen vermuten lassen, werden diese beiden Methoden aufgerufen, wenn die Laufzeit die Erweiterung an eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse anfügt oder von der Instanz löst.</span><span class="sxs-lookup"><span data-stu-id="0644b-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="0644b-128">In diesem Beispiel wird die `Attach`-Methode für die Nachverfolgung des <xref:System.ServiceModel.InstanceContext>-Objekts verwendet, das zur aktuellen Instanz der Erweiterung gehört.</span><span class="sxs-lookup"><span data-stu-id="0644b-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="0644b-129">Darüber hinaus müssen Sie zur Bereitstellung der erweiterten Lebensdauerunterstützung die erforderliche Implementierung zur Erweiterung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0644b-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="0644b-130">Aus diesem Grund die `ICustomLease` Schnittstelle wird mit den gewünschten Methoden deklariert und implementiert wird, der `CustomLeaseExtension` Klasse.</span><span class="sxs-lookup"><span data-stu-id="0644b-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="0644b-131">Wenn WCF aufruft der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode in der die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung dieser Aufruf wird an weitergeleitet der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode der `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="0644b-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="0644b-132">Anschließend wird die `CustomLeaseExtension` überprüft den privaten Zustand, um festzustellen, ob die <xref:System.ServiceModel.InstanceContext> im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="0644b-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="0644b-133">Wenn er im Leerlauf ist, gibt es `true`.</span><span class="sxs-lookup"><span data-stu-id="0644b-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="0644b-134">Andernfalls wird ein Zeitgeber für eine bestimmte erweiterte Lebensdauerperiode gestartet.</span><span class="sxs-lookup"><span data-stu-id="0644b-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

<span data-ttu-id="0644b-135">In des Timers `Elapsed` Ereignis die Rückruffunktion im Verteiler wird aufgerufen, um eine andere Bereinigungszyklus zu starten.</span><span class="sxs-lookup"><span data-stu-id="0644b-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="0644b-136">Es gibt keine Möglichkeit, den ausgeführten Timer zu erneuern, wenn eine neue Nachricht eingeht, für die Instanz, die in den Leerlaufzustand verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0644b-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="0644b-137">Im Beispiel wird <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementiert, um die Aufrufe der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode abzufangen und diese zur `CustomLeaseExtension` weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="0644b-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="0644b-138">Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung ist in der `CustomLifetimeLease`-Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="0644b-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="0644b-139">Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode wird aufgerufen, wenn WCF Begriff ist, die Dienstinstanz freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0644b-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="0644b-140">Es gibt jedoch nur eine Instanz einer bestimmten `ISharedSessionInstance`-Implementierung in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Auflistung von ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="0644b-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="0644b-141">Dies bedeutet, dass es keine Möglichkeit wissen darüber zurück, wenn die <xref:System.ServiceModel.InstanceContext> wird geschlossen, die zum Zeitpunkt der WCF überprüft die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0644b-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="0644b-142">Dieses Beispiel verwendet aus diesem Grund Thread sperren, um Anforderungen zum Serialisieren der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0644b-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0644b-143">Die Verwendung der Threadsperre wird nicht empfohlen, da die Leistung der Anwendung durch die Serialisierung deutlich beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0644b-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="0644b-144">Ein privates Memberfeld werden in der `CustomLifetimeLease` Klasse zum Nachverfolgen von des Leerlaufzustand und wird zurückgegeben, indem die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0644b-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="0644b-145">Jedes Mal die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode aufgerufen wird, die `isIdle` Feld zurückgegeben wird, und zum Zurücksetzen `false`.</span><span class="sxs-lookup"><span data-stu-id="0644b-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="0644b-146">Dieser Wert muss auf `false` festgelegt werden, um sicherzustellen, dass der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="0644b-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="0644b-147">Wenn die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> Methodenrückgabe `false`, registriert der Verteiler eine Rückruffunktion mit der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0644b-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="0644b-148">Diese Methode empfängt einen Verweis darauf, dass <xref:System.ServiceModel.InstanceContext> freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0644b-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="0644b-149">Aus diesem Grund kann der Beispielcode Abfragen die `ICustomLease` "Erweiterung", und überprüfen Sie die `ICustomLease.IsIdle` Eigenschaft im erweiterten Zustand.</span><span class="sxs-lookup"><span data-stu-id="0644b-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

<span data-ttu-id="0644b-150">Bevor Sie die `ICustomLease.IsIdle` Eigenschaft aktiviert ist, wird die Callback-Eigenschaft muss festgelegt werden, da dies entscheidend für `CustomLeaseExtension` den Verteiler benachrichtigen, wenn es in den Leerlauf wechselt.</span><span class="sxs-lookup"><span data-stu-id="0644b-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="0644b-151">Wenn `ICustomLease.IsIdle``true` zurückgibt, wird der private `isIdle`-Member einfach in `CustomLifetimeLease` auf `true` festgelegt, und die Rückrufmethode wird vom Member aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0644b-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="0644b-152">Da der Code eine Sperre enthalten ist, können nicht andere Threads den Wert dieses privaten Members nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0644b-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="0644b-153">Das nächste Mal mit dem Verteiler ruft der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, gibt `true` und der Verteiler, die die Instanz freigeben kann.</span><span class="sxs-lookup"><span data-stu-id="0644b-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="0644b-154">Jetzt da die Vorarbeit für die benutzerdefinierte Erweiterung abgeschlossen ist, muss sie in das Dienstmodell eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="0644b-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="0644b-155">Zum Einbinden der `CustomLeaseExtension` Implementierung, die die <xref:System.ServiceModel.InstanceContext>, WCF bietet der <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> Schnittstelle, führen Sie das bootstrapping von <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="0644b-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="0644b-156">In diesem Beispiel implementiert die `CustomLeaseInitializer`-Klasse diese Schnittstelle und fügt eine `CustomLeaseExtension`-Instanz zur <xref:System.ServiceModel.InstanceContext.Extensions%2A>-Auflistung aus der einzigen Methodeninitialisierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="0644b-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="0644b-157">Diese Methode wird vom Verteiler aufgerufen, während <xref:System.ServiceModel.InstanceContext> initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0644b-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="0644b-158">Zum Schluss die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung ist eingebunden in das Dienstmodell mithilfe der <xref:System.ServiceModel.Description.IServiceBehavior> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0644b-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="0644b-159">Diese Implementierung wird in der `CustomLeaseTimeAttribute`-Klasse eingefügt, und sie wird außerdem von der <xref:System.Attribute>-Basisklasse abgeleitet, um dieses Verhalten als Attribut verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="0644b-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="0644b-160">Dieses Verhalten kann einer Beispieldienstklasse hinzugefügt werden, indem es mit dem `CustomLeaseTime`-Attribut kommentiert wird.</span><span class="sxs-lookup"><span data-stu-id="0644b-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="0644b-161">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0644b-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="0644b-162">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0644b-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0644b-163">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0644b-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="0644b-164">Stellen Sie sicher, dass Sie durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0644b-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="0644b-165">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="0644b-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="0644b-166">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0644b-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0644b-167">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0644b-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0644b-168">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0644b-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0644b-169">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0644b-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0644b-170">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0644b-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
