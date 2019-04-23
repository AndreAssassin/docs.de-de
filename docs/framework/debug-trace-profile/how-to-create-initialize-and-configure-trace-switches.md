---
title: 'Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87170035df47e7605d25531df4b0759bf121ad80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325708"
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a><span data-ttu-id="0223f-102">Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="0223f-102">How to: Create, Initialize and Configure Trace Switches</span></span>
<span data-ttu-id="0223f-103">Mit Ablaufverfolgungsschaltern können Sie die Ablaufverfolgungsausgabe aktivieren, deaktivieren und filtern.</span><span class="sxs-lookup"><span data-stu-id="0223f-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span>  
  
<a name="create"></a>   
## <a name="creating-and-initializing-a-trace-switch"></a><span data-ttu-id="0223f-104">Erstellen und Initialisieren eines Ablaufverfolgungsschalters</span><span class="sxs-lookup"><span data-stu-id="0223f-104">Creating and initializing a trace switch</span></span>  
 <span data-ttu-id="0223f-105">Damit Sie Ablaufverfolgungsschalter verwenden können, müssen Sie diese zunächst erstellen und in Ihrem Code platzieren.</span><span class="sxs-lookup"><span data-stu-id="0223f-105">In order to use trace switches, you must first create them and place them in your code.</span></span> <span data-ttu-id="0223f-106">Es gibt zwei vordefinierte Klassen, aus denen Sie Schalterobjekte erstellen können: die <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType>-Klasse und die <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0223f-106">There are two predefined classes from which you can create switch objects: the <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> class and the <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0223f-107">Sie verwenden die <xref:System.Diagnostics.BooleanSwitch>-Klasse, wenn Sie nur wissen möchten, ob eine Ablaufverfolgungsmeldung angezeigt oder wird oder nicht. <xref:System.Diagnostics.TraceSwitch> verwenden Sie, wenn Sie zwischen Ebenen für die Ablaufverfolgung unterscheiden möchten.</span><span class="sxs-lookup"><span data-stu-id="0223f-107">You would use <xref:System.Diagnostics.BooleanSwitch> if you care only about whether or not a tracing message appears; you would use <xref:System.Diagnostics.TraceSwitch> if you want to discriminate between levels of tracing.</span></span> <span data-ttu-id="0223f-108">Wenn Sie eine <xref:System.Diagnostics.TraceSwitch>-Instanz verwenden, können Sie eigene Debugmeldungen definieren und diese verschiedenen Ablaufverfolgungsebenen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0223f-108">If you use a <xref:System.Diagnostics.TraceSwitch>, you can define your own debugging messages and associate them with different trace levels.</span></span> <span data-ttu-id="0223f-109">Sie können beide Typen von Schaltern mit Ablaufverfolgung oder Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0223f-109">You can use both types of switches with either tracing or debugging.</span></span> <span data-ttu-id="0223f-110">In der Standardeinstellung ist ein <xref:System.Diagnostics.BooleanSwitch> deaktiviert und ein <xref:System.Diagnostics.TraceSwitch> auf die Ebene <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0223f-110">By default, a <xref:System.Diagnostics.BooleanSwitch> is disabled and a <xref:System.Diagnostics.TraceSwitch> is set to level <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0223f-111">Ablaufverfolgungsschalter können in jedem beliebigen Teil Ihres Codes erstellt und platziert werden, in dem sie möglicherweise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0223f-111">Trace switches can be created and placed in any part of your code that might use them.</span></span>  
  
 <span data-ttu-id="0223f-112">Obwohl Sie Ablaufverfolgungsebenen und weitere Konfigurationsoptionen in Code festlegen können, empfiehlt es sich, dass Sie die Konfigurationsdatei verwenden, um den Zustand Ihrer Schalter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0223f-112">Although you can set trace levels and other configuration options in code, we recommend that you use the configuration file to manage the state of your switches.</span></span> <span data-ttu-id="0223f-113">Grund hierfür ist, dass Sie flexibler sind, wenn Sie die Konfiguration Ihrer Schalter im Konfigurationssystem verwalten, denn Sie können verschiedene Schalter und Änderungsebenen ein-und ausschalten, ohne Ihre Anwendung erneut zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="0223f-113">This is because managing the configuration of your switches in the configuration system gives you greater flexibility — you can turn on and off various switches and change levels without recompiling your application.</span></span>  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a><span data-ttu-id="0223f-114">So erstellen und initialisieren Sie einen Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="0223f-114">To create and initialize a trace switch</span></span>  
  
1. <span data-ttu-id="0223f-115">Definieren Sie einen Schalter entweder mit dem Typ <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> oder mit dem Typ <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>, und legen Sie den Namen und die Beschreibung des Schalters fest.</span><span class="sxs-lookup"><span data-stu-id="0223f-115">Define a switch as either type <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> or type <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> and set the name and description of the switch.</span></span>  
  
2. <span data-ttu-id="0223f-116">Konfigurieren Sie Ihren Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="0223f-116">Configure your trace switch.</span></span> <span data-ttu-id="0223f-117">Weitere Informationen finden Sie unter [Konfigurieren von Ablaufverfolgungsschaltern](#configure).</span><span class="sxs-lookup"><span data-stu-id="0223f-117">For more information, see [Configuring trace switches](#configure).</span></span>  
  
     <span data-ttu-id="0223f-118">Im folgenden Code werden zwei Schalter erstellt, jeweils ein Schalter jedes Typs:</span><span class="sxs-lookup"><span data-stu-id="0223f-118">The following code creates two switches, one of each type:</span></span>  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =   
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =   
       new System.Diagnostics.TraceSwitch("General",   
       "Entire application");  
    ```  
  
<a name="configure"></a>   
## <a name="configuring-trace-switches"></a><span data-ttu-id="0223f-119">Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="0223f-119">Configuring trace switches</span></span>  
 <span data-ttu-id="0223f-120">Nachdem Ihre Anwendung bereitgestellt wurde, können weiterhin Ablaufverfolgungsausgabe aktivieren oder deaktivieren, indem Sie die Ablaufverfolgungsschalter in der Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0223f-120">After your application has been distributed, you can still enable or disable trace output by configuring the trace switches in your application.</span></span> <span data-ttu-id="0223f-121">Konfigurieren eines Schalters bedeutet, dass sein Wert aus einer externen Quelle geändert wird, nachdem er initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0223f-121">Configuring a switch means changing its value from an external source after it has been initialized.</span></span> <span data-ttu-id="0223f-122">Sie können die Werte der Schalterobjekte mithilfe der Konfigurationsdatei ändern.</span><span class="sxs-lookup"><span data-stu-id="0223f-122">You can change the values of the switch objects using the configuration file.</span></span> <span data-ttu-id="0223f-123">Sie konfigurieren einen Ablaufverfolgungsschalter so, dass er aktiviert oder deaktiviert oder dass seine Ebene festgelegt wird. Dabei bestimmen Sie den Umfang und die Art der Meldungen, die der Schalter an Listener weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="0223f-123">You configure a trace switch to turn it on and off, or to set its level, determining the amount and type of messages it passes along to listeners.</span></span>  
  
 <span data-ttu-id="0223f-124">Ihre Schalter werden über die .config-Datei konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0223f-124">Your switches are configured using the .config file.</span></span> <span data-ttu-id="0223f-125">Für eine Webanwendung ist dies die "Web.config"-Datei, die dem Projekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0223f-125">For a Web application, this is the Web.config file associated with the project.</span></span> <span data-ttu-id="0223f-126">In einer Windows-Anwendung hat diese Datei den Namen "Anwendungsname.exe.config". In einer bereitgestellten Anwendung muss sich diese Datei im selben Ordner befinden wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="0223f-126">In a Windows application, this file is named (application name).exe.config. In a deployed application, this file must reside in the same folder as the executable.</span></span>  
  
 <span data-ttu-id="0223f-127">Wenn die Anwendung den Code, der eine Instanz eines Schalters erstellt, zum ersten Mal ausführt, prüft sie die Konfigurationsdatei auf Ablaufverfolgungsebenen-Informationen zu dem angegebenen Schalter.</span><span class="sxs-lookup"><span data-stu-id="0223f-127">When your application executes the code that creates an instance of a switch for the first time, it checks the configuration file for trace-level information about the named switch.</span></span> <span data-ttu-id="0223f-128">Das Ablaufverfolgungssystem durchsucht die Konfigurationsdatei für jeden Schalter nur ein Mal – wenn die Anwendung den Schalter erstmalig erstellt.</span><span class="sxs-lookup"><span data-stu-id="0223f-128">The tracing system examines the configuration file only once for any particular switch — the first time your application creates the switch.</span></span>  
  
 <span data-ttu-id="0223f-129">In einer bereitgestellten Anwendung aktivieren Sie Ablaufverfolgungscode, indem Sie Schalterobjekte neu konfigurieren, wenn die Anwendung nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0223f-129">In a deployed application, you enable trace code by reconfiguring switch objects when your application is not running.</span></span> <span data-ttu-id="0223f-130">Üblicherweise gehört hierzu Aktivieren oder Deaktivieren der Schalterobjekte oder Ändern der Ablaufverfolgungsebenen und dann Neustarten Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0223f-130">Typically this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
 <span data-ttu-id="0223f-131">Wenn Sie eine Instanz eines Schalters erstellen, initialisieren Sie diesen auch, indem Sie zwei Argumente angeben: ein *displayName*-Argument und ein *description*-Argument.</span><span class="sxs-lookup"><span data-stu-id="0223f-131">When you create an instance of a switch, you also initialize it by specifying two arguments: a *displayName* argument and a *description* argument.</span></span> <span data-ttu-id="0223f-132">Das *displayName*-Argument des Konstruktors legt die <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType>-Eigenschaft der <xref:System.Diagnostics.Switch>-Klasseninstanz fest.</span><span class="sxs-lookup"><span data-stu-id="0223f-132">The *displayName* argument of the constructor sets the <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> property of the <xref:System.Diagnostics.Switch> class instance.</span></span> <span data-ttu-id="0223f-133">Der *displayName* ist der Name, der verwendet wird, um den Schalter in der CONFIG-Datei zu konfigurieren, und das *description*-Argument sollte eine kurze Beschreibung des Schalters sowie die Information zurückgeben, welche Meldungen er steuert.</span><span class="sxs-lookup"><span data-stu-id="0223f-133">The *displayName* is the name that is used to configure the switch in the .config file, and the *description* argument should return a brief description of the switch and what messages it controls.</span></span>  
  
 <span data-ttu-id="0223f-134">Zusätzlich zum Angeben des Namens eines Schalters, der konfiguriert werden soll, müssen Sie auch einen Wert für den Schalter angeben.</span><span class="sxs-lookup"><span data-stu-id="0223f-134">In addition to specifying the name of a switch to configure, you must also specify a value for the switch.</span></span> <span data-ttu-id="0223f-135">Dieser Wert ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="0223f-135">This value is an Integer.</span></span> <span data-ttu-id="0223f-136">Für <xref:System.Diagnostics.BooleanSwitch> entspricht der Wert 0 **Deaktiviert**, und ein Wert ungleich 0 entspricht **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="0223f-136">For <xref:System.Diagnostics.BooleanSwitch>, a value of 0 corresponds to **Off**, and any nonzero value corresponds to **On**.</span></span> <span data-ttu-id="0223f-137">Für <xref:System.Diagnostics.TraceSwitch> entsprechen 0,1,2,3 bzw. 4 **Deaktiviert**, **Fehler**, **Warnung**, **Info** bzw. **Ausführlich**.</span><span class="sxs-lookup"><span data-stu-id="0223f-137">For <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3, and 4 correspond **Off**, **Error**, **Warning**, **Info**, and **Verbose**, respectively.</span></span> <span data-ttu-id="0223f-138">Jede Zahl, die größer als 4 ist, wird als **Ausführlich**, und jede Anzahl, die kleiner als 0 ist, wird als **Deaktiviert** angesehen.</span><span class="sxs-lookup"><span data-stu-id="0223f-138">Any number greater than 4 is treated as **Verbose**, and any number less than zero is treated as **Off**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0223f-139">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0223f-139">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="0223f-140">Beispielsweise `true` für einen <xref:System.Diagnostics.BooleanSwitch> oder den Text, der einem Enumerationswert entspricht, etwa `Error`, für einen <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="0223f-140">For example, `true` for a <xref:System.Diagnostics.BooleanSwitch> or the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="0223f-141">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="0223f-141">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
 <span data-ttu-id="0223f-142">Damit Endbenutzer die Möglichkeit haben, die Ablaufverfolgungsschalter einer Anwendung konfigurieren zu können, müssen Sie eine detaillierte Dokumentation zu den Schaltern in Ihrer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0223f-142">In order for end users to be able to configure an application's trace switches, you must provide detailed documentation on the switches in your application.</span></span> <span data-ttu-id="0223f-143">Sie sollten ausführlich beschreiben, welche Schalter welche Vorgänge steuern und wie die Schalter aktiviert und deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0223f-143">You should detail which switches control what and how to turn them on and off.</span></span> <span data-ttu-id="0223f-144">Außerdem sollten Sie Ihren Endbenutzern eine .config-Datei bereitstellen, die entsprechende Hilfen in den Kommentaren enthält.</span><span class="sxs-lookup"><span data-stu-id="0223f-144">You should also provide your end user with a .config file that has appropriate Help in the comments.</span></span>  
  
#### <a name="to-configure-trace-switches"></a><span data-ttu-id="0223f-145">So konfigurieren Sie Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="0223f-145">To configure trace switches</span></span>  
  
1. <span data-ttu-id="0223f-146">Um Ablaufverfolgungsschalter zu verwenden, müssen Sie diese zuerst erstellen und sie, wie im Abschnitt [Erstellen und Initialisieren eines Ablaufverfolgungsschalters](#create) beschrieben, in Ihrem Code platzieren.</span><span class="sxs-lookup"><span data-stu-id="0223f-146">In order to use trace switches, you must first create them and place them in your code as described in the section [Creating and initializing a trace switch](#create).</span></span>  
  
2. <span data-ttu-id="0223f-147">Enthält Ihr Projekt keine Konfigurationsdatei („app.config“ oder „Web.config“), dann wählen Sie im Menü **Projekt** den Befehl **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0223f-147">If your project does not contain a configuration file (app.config or Web.config), then from the **Project** menu, select **Add New Item**.</span></span>  
  
    -   <span data-ttu-id="0223f-148">**Visual Basic:** In der **neues Element hinzufügen** Dialogfeld wählen **Anwendungskonfigurationsdatei**.</span><span class="sxs-lookup"><span data-stu-id="0223f-148">**Visual Basic:** In the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
         <span data-ttu-id="0223f-149">Die Anwendungskonfigurationsdatei wird erstellt und geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0223f-149">The application configuration file is created and opened.</span></span> <span data-ttu-id="0223f-150">Diese Datei ist ein XML-Dokument mit dem Stammelement `<configuration>.`</span><span class="sxs-lookup"><span data-stu-id="0223f-150">This is an XML document whose root element is `<configuration>.`</span></span>  
  
    -   <span data-ttu-id="0223f-151">**Visual C#:** In der **neues Element hinzufügen** Dialogfeld wählen **XML-Datei**.</span><span class="sxs-lookup"><span data-stu-id="0223f-151">**Visual C#:** In the **Add New Item** dialog box, choose **XML File**.</span></span> <span data-ttu-id="0223f-152">Geben Sie dieser Datei den Namen **app.config**. Fügen Sie im XML-Editor nach der XML-Deklaration die folgende XML hinzu:</span><span class="sxs-lookup"><span data-stu-id="0223f-152">Name this file **app.config**. In the XML editor, after the XML declaration, add the following XML:</span></span>  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         <span data-ttu-id="0223f-153">Nachdem das Projekt kompiliert ist, wird die Datei „app.config“ in den Projektausgabeordner kopiert und in „*Anwendungsname*.exe.config“ umbenannt.</span><span class="sxs-lookup"><span data-stu-id="0223f-153">When your project is compiled, the app.config file is copied to the project output folder and is renamed *applicationname*.exe.config.</span></span>  
  
3. <span data-ttu-id="0223f-154">Fügen Sie nach dem `<configuration>`-Tag, aber vor dem `</configuration>`-Tag, die entsprechende XML ein, um die Schalter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0223f-154">After the `<configuration>` tag but before the `</configuration>` tag, add the appropriate XML to configure your switches.</span></span> <span data-ttu-id="0223f-155">In den folgenden Beispielen werden ein **BooleanSwitch** mit einer **DisplayName**-Eigenschaft von `DataMessageSwitch` und ein **TraceSwitch** mit einer **DisplayName**-Eigenschaft von `TraceLevelSwitch` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0223f-155">The following examples demonstrate a **BooleanSwitch** with a **DisplayName** property of `DataMessageSwitch` and a **TraceSwitch** with a **DisplayName** property of `TraceLevelSwitch`.</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     <span data-ttu-id="0223f-156">In dieser Konfiguration sind beide Schalter deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0223f-156">In this configuration, both switches are off.</span></span>  
  
4. <span data-ttu-id="0223f-157">Wenn Sie einen **BooleanSwitch**, wie `DataMessagesSwitch` im vorhergehenden Beispiel, aktivieren möchten, ändern Sie den **Wert** in eine beliebige ganze Zahl ungleich 0.</span><span class="sxs-lookup"><span data-stu-id="0223f-157">If you need to turn on a **BooleanSwitch**, such as `DataMessagesSwitch` shown in the previous example, change the **Value** to any integer other than 0.</span></span>  
  
5. <span data-ttu-id="0223f-158">Wenn Sie einen **TraceSwitch**, wie `TraceLevelSwitch` im vorhergehenden Beispiel, aktivieren möchten, ändern Sie den **Wert** in die entsprechende Ebeneneinstellung (1 bis 4).</span><span class="sxs-lookup"><span data-stu-id="0223f-158">If you need to turn on a **TraceSwitch**, such as `TraceLevelSwitch` shown in the previous example, change the **Value** to the appropriate level setting (1 to 4).</span></span>  
  
6. <span data-ttu-id="0223f-159">Fügen Sie der .config-Datei Kommentare hinzu , damit der Benutzer genau weiß, welche Werte geändert werden müssen, damit die Schalter geeignet konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0223f-159">Add comments to the .config file so the end user has a clear understanding of what values to change to configure the switches appropriately.</span></span>  
  
     <span data-ttu-id="0223f-160">Im folgenden Beispiel wird gezeigt, wie der endgültige Code einschließlich der Kommentare aussehen könnte:</span><span class="sxs-lookup"><span data-stu-id="0223f-160">The following example shows how the final code, including comments, might look:</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0223f-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0223f-161">See also</span></span>

- [<span data-ttu-id="0223f-162">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="0223f-162">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="0223f-163">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="0223f-163">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="0223f-164">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="0223f-164">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="0223f-165">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0223f-165">Trace and Debug Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
