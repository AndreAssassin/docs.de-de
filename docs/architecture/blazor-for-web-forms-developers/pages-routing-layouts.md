---
title: Seiten, Routing und Layouts
description: Erfahren Sie, wie Sie Seiten in blazor erstellen, mit dem Client seitigen Routing arbeiten und Seitenlayouts verwalten.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841234"
---
# <a name="pages-routing-and-layouts"></a><span data-ttu-id="802b1-103">Seiten, Routing und Layouts</span><span class="sxs-lookup"><span data-stu-id="802b1-103">Pages, routing, and layouts</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="802b1-104">ASP.net Web Forms-apps bestehen aus Seiten, die in *aspx* -Dateien definiert sind.</span><span class="sxs-lookup"><span data-stu-id="802b1-104">ASP.NET Web Forms apps are composed of pages defined in *.aspx* files.</span></span> <span data-ttu-id="802b1-105">Die Adresse jeder Seite basiert auf dem physischen Dateipfad im Projekt.</span><span class="sxs-lookup"><span data-stu-id="802b1-105">Each page's address is based on its physical file path in the project.</span></span> <span data-ttu-id="802b1-106">Wenn ein Browser eine Anforderung an die Seite sendet, wird der Inhalt der Seite auf dem Server dynamisch gerendert.</span><span class="sxs-lookup"><span data-stu-id="802b1-106">When a browser makes a request to the page, the contents of the page are dynamically rendered on the server.</span></span> <span data-ttu-id="802b1-107">Die renderingkonten sowohl für das HTML-Markup der Seite als auch für die zugehörigen Server Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="802b1-107">The rendering accounts for both the page's HTML markup and its server controls.</span></span>

<span data-ttu-id="802b1-108">In blazor ist jede Seite in der App eine Komponente, die in der Regel in einer *Razor* -Datei mit einer oder mehreren angegebenen Routen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="802b1-108">In Blazor, each page in the app is a component, typically defined in a *.razor* file, with one or more specified routes.</span></span> <span data-ttu-id="802b1-109">Das Routing erfolgt größtenteils auf Clientseite, ohne eine bestimmte Server Anforderung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="802b1-109">Routing mostly happens client-side without involving a specific server request.</span></span> <span data-ttu-id="802b1-110">Der Browser sendet zuerst eine Anforderung an die Stamm Adresse der app.</span><span class="sxs-lookup"><span data-stu-id="802b1-110">The browser first makes a request to the root address of the app.</span></span> <span data-ttu-id="802b1-111">Eine Stamm `Router` Komponente in der blazor-App verarbeitet dann abfangen-Navigationsanforderungen und Sie an die richtige Komponente.</span><span class="sxs-lookup"><span data-stu-id="802b1-111">A root `Router` component in the Blazor app then handles intercepting navigation requests and them to the correct component.</span></span>

<span data-ttu-id="802b1-112">Blazor unterstützt auch *Deep Linking*.</span><span class="sxs-lookup"><span data-stu-id="802b1-112">Blazor also supports *deep linking*.</span></span> <span data-ttu-id="802b1-113">Eine Deep-Verknüpfung tritt auf, wenn der Browser eine Anforderung an eine bestimmte Route sendet, die nicht der Stamm der APP ist.</span><span class="sxs-lookup"><span data-stu-id="802b1-113">Deep linking occurs when the browser makes a request to a specific route other than the root of the app.</span></span> <span data-ttu-id="802b1-114">Anforderungen für Deep-Links, die an den Server gesendet werden, werden an die blazor-App weitergeleitet, die dann die Client seitige Anforderung an die richtige Komponente weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="802b1-114">Requests for deep links sent to the server are routed to the Blazor app, which then routes the request client-side to the correct component.</span></span>

<span data-ttu-id="802b1-115">Eine einfache Seite in ASP.net-Web Forms kann das folgende Markup enthalten:</span><span class="sxs-lookup"><span data-stu-id="802b1-115">A simple page in ASP.NET Web Forms might contain the following markup:</span></span>

<span data-ttu-id="802b1-116">*Name. aspx*</span><span class="sxs-lookup"><span data-stu-id="802b1-116">*Name.aspx*</span></span>

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

<span data-ttu-id="802b1-117">*Name.aspx.cs*</span><span class="sxs-lookup"><span data-stu-id="802b1-117">*Name.aspx.cs*</span></span>

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

<span data-ttu-id="802b1-118">Die entsprechende Seite in einer blazor-APP würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="802b1-118">The equivalent page in a Blazor app would look like this:</span></span>

<span data-ttu-id="802b1-119">*Name. Razor*</span><span class="sxs-lookup"><span data-stu-id="802b1-119">*Name.razor*</span></span>

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a><span data-ttu-id="802b1-120">Erstellen von Seiten</span><span class="sxs-lookup"><span data-stu-id="802b1-120">Create pages</span></span>

<span data-ttu-id="802b1-121">Um eine Seite in blazor zu erstellen, erstellen Sie eine-Komponente, und fügen Sie die `@page` Razor-Direktive hinzu, um die Route für die Komponente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-121">To create a page in Blazor, create a component and add the `@page` Razor directive to specify the route for the component.</span></span> <span data-ttu-id="802b1-122">Die `@page`-Direktive nimmt einen einzelnen Parameter, der der Komponente hinzugefügt werden soll, an.</span><span class="sxs-lookup"><span data-stu-id="802b1-122">The `@page` directive takes a single parameter, which is the route template to add to that component.</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="802b1-123">Der Routen Vorlagen Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="802b1-123">The route template parameter is required.</span></span> <span data-ttu-id="802b1-124">Im Gegensatz zu ASP.net Web Forms wird die Route zu einer blazor-Komponente nicht von Ihrem Datei Speicherort abgeleitet (obwohl dies möglicherweise eine in der Zukunft hinzugefügte Funktion *ist* ).</span><span class="sxs-lookup"><span data-stu-id="802b1-124">Unlike ASP.NET Web Forms, the route to a Blazor component *isn't* inferred from its file location (although that may be a feature added in the future).</span></span>

<span data-ttu-id="802b1-125">Die Syntax der Routen Vorlage ist die gleiche grundlegende Syntax, die für das Routing in ASP.net-Web Forms verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="802b1-125">The route template syntax is the same basic syntax used for routing in ASP.NET Web Forms.</span></span> <span data-ttu-id="802b1-126">Routen Parameter werden in der Vorlage mithilfe von geschweiften Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-126">Route parameters are specified in the template using braces.</span></span> <span data-ttu-id="802b1-127">Blazor bindet Routen Werte an Komponenten Parameter mit dem gleichen Namen (ohne Beachtung der Groß-/Kleinschreibung).</span><span class="sxs-lookup"><span data-stu-id="802b1-127">Blazor will bind route values to component parameters with the same name (case-insensitive).</span></span>

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

<span data-ttu-id="802b1-128">Sie können auch Einschränkungen für den Wert des Routen Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-128">You can also specify constraints on the value of the route parameter.</span></span> <span data-ttu-id="802b1-129">Um z. b. die Produkt-ID auf einen `int`zu beschränken, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="802b1-129">For example, to constrain the product ID to be an `int`:</span></span>

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

<span data-ttu-id="802b1-130">Eine vollständige Liste der Routen Einschränkungen, die von blazor unterstützt werden, finden Sie unter [Routen Einschränkungen](/aspnet/core/blazor/routing#route-constraints).</span><span class="sxs-lookup"><span data-stu-id="802b1-130">For a full list of the route constraints supported by Blazor, see [Route constraints](/aspnet/core/blazor/routing#route-constraints).</span></span>

## <a name="router-component"></a><span data-ttu-id="802b1-131">Routerkomponente</span><span class="sxs-lookup"><span data-stu-id="802b1-131">Router component</span></span>

<span data-ttu-id="802b1-132">Das Routing in blazor wird von der `Router` Komponente behandelt.</span><span class="sxs-lookup"><span data-stu-id="802b1-132">Routing in Blazor is handled by the `Router` component.</span></span> <span data-ttu-id="802b1-133">Die `Router` Komponente wird in der Regel in der Stamm Komponente der APP (*app. Razor*) verwendet.</span><span class="sxs-lookup"><span data-stu-id="802b1-133">The `Router` component is typically used in the app's root component (*App.razor*).</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

<span data-ttu-id="802b1-134">Die `Router` Komponente ermittelt die Routing fähigen Komponenten in der angegebenen `AppAssembly` und in der optional angegebenen `AdditionalAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="802b1-134">The `Router` component discovers the routable components in the specified `AppAssembly` and in the optionally specified `AdditionalAssemblies`.</span></span> <span data-ttu-id="802b1-135">Wenn der Browser navigiert, fängt der `Router` die Navigation ab und rendert den Inhalt seines `Found`-Parameters mit dem extrahierten `RouteData`, wenn eine Route mit der Adresse übereinstimmt, andernfalls rendert der `Router` den `NotFound` Parameter.</span><span class="sxs-lookup"><span data-stu-id="802b1-135">When the browser navigates, the `Router` intercepts the navigation and renders the contents of its `Found` parameter with the extracted `RouteData` if a route matches the address, otherwise the `Router` renders its `NotFound` parameter.</span></span>

<span data-ttu-id="802b1-136">Die `RouteView` Komponente übernimmt das Rendern der übereinstimmenden Komponente, die durch den `RouteData` angegeben ist, mit dem zugehörigen Layout</span><span class="sxs-lookup"><span data-stu-id="802b1-136">The `RouteView` component handles rendering the matched component specified by the `RouteData` with its layout if it has one.</span></span> <span data-ttu-id="802b1-137">Wenn die übereinstimmende Komponente kein Layout hat, wird der optional angegebene `DefaultLayout` verwendet.</span><span class="sxs-lookup"><span data-stu-id="802b1-137">If the matched component doesn't have a layout, then the optionally specified `DefaultLayout` is used.</span></span>

<span data-ttu-id="802b1-138">Die `LayoutView` Komponente rendert ihren untergeordneten Inhalt innerhalb des angegebenen Layouts.</span><span class="sxs-lookup"><span data-stu-id="802b1-138">The `LayoutView` component renders its child content within the specified layout.</span></span> <span data-ttu-id="802b1-139">Im weiteren Verlauf dieses Kapitels betrachten wir die Layouts ausführlicher.</span><span class="sxs-lookup"><span data-stu-id="802b1-139">We'll look at layouts more in detail later in this chapter.</span></span>

## <a name="navigation"></a><span data-ttu-id="802b1-140">Navigation</span><span class="sxs-lookup"><span data-stu-id="802b1-140">Navigation</span></span>

<span data-ttu-id="802b1-141">In ASP.net Web Forms wird die Navigation zu einer anderen Seite durch Zurückgeben einer Umleitungs Antwort an den Browser auslöst.</span><span class="sxs-lookup"><span data-stu-id="802b1-141">In ASP.NET Web Forms, you trigger navigation to a different page by returning a redirect response to the browser.</span></span> <span data-ttu-id="802b1-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="802b1-142">For example:</span></span>

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

<span data-ttu-id="802b1-143">Die Rückgabe einer Umleitungs Antwort ist in der Regel in blazor nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="802b1-143">Returning a redirect response isn't typically possible in Blazor.</span></span> <span data-ttu-id="802b1-144">Blazor verwendet kein Anforderungs-Antwort-Modell.</span><span class="sxs-lookup"><span data-stu-id="802b1-144">Blazor doesn't use a request-reply model.</span></span> <span data-ttu-id="802b1-145">Sie können Browser Navigation jedoch direkt wie bei JavaScript auslassen.</span><span class="sxs-lookup"><span data-stu-id="802b1-145">You can, however, trigger browser navigations directly, as you can with JavaScript.</span></span>

<span data-ttu-id="802b1-146">Blazor bietet einen `NavigationManager` Dienst, der für folgende Aktionen verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="802b1-146">Blazor provides a `NavigationManager` service that can be used to:</span></span>

- <span data-ttu-id="802b1-147">Aktuelle Browser Adresse erhalten</span><span class="sxs-lookup"><span data-stu-id="802b1-147">Get the current browser address</span></span>
- <span data-ttu-id="802b1-148">Basisadresse erhalten</span><span class="sxs-lookup"><span data-stu-id="802b1-148">Get the base address</span></span>
- <span data-ttu-id="802b1-149">Navigations Navigation</span><span class="sxs-lookup"><span data-stu-id="802b1-149">Trigger navigations</span></span>
- <span data-ttu-id="802b1-150">Benachrichtigen, wenn sich die Adresse ändert</span><span class="sxs-lookup"><span data-stu-id="802b1-150">Get notified when the address changes</span></span>

<span data-ttu-id="802b1-151">Verwenden Sie die `NavigateTo`-Methode, um zu einer anderen Adresse zu navigieren:</span><span class="sxs-lookup"><span data-stu-id="802b1-151">To navigate to a different address, use the `NavigateTo` method:</span></span>

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

<span data-ttu-id="802b1-152">Eine Beschreibung aller `NavigationManager` Mitglieder finden Sie unter [URI-und Navigations Zustands Hilfen](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span><span class="sxs-lookup"><span data-stu-id="802b1-152">For a description of all `NavigationManager` members, see [URI and navigation state helpers](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span></span>

## <a name="base-urls"></a><span data-ttu-id="802b1-153">Basis-URLs</span><span class="sxs-lookup"><span data-stu-id="802b1-153">Base URLs</span></span>

<span data-ttu-id="802b1-154">Wenn Ihre blazor-app unter einem Basispfad bereitgestellt wird, müssen Sie die Basis-URL in den Seiten Metadaten mithilfe des `<base>`-Tags für die Routing-to-work-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-154">If your Blazor app is deployed under a base path, then you need to specify the base URL in the page metadata using the `<base>` tag for routing to work property.</span></span> <span data-ttu-id="802b1-155">Wenn die Hostseite für die App mithilfe von Razor Server gerendert wird, können Sie die `~/`-Syntax verwenden, um die Basisadresse der APP anzugeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-155">If the host page for the app is server-rendered using Razor, then you can use the `~/` syntax to specify the app's base address.</span></span> <span data-ttu-id="802b1-156">Wenn die Hostseite statischer HTML-Code ist, müssen Sie die Basis-URL explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-156">If the host page is static HTML, then you need to specify the base URL explicitly.</span></span>

```html
<base href="~/" />
```

## <a name="page-layout"></a><span data-ttu-id="802b1-157">Seitenlayout</span><span class="sxs-lookup"><span data-stu-id="802b1-157">Page layout</span></span>

<span data-ttu-id="802b1-158">Das Seitenlayout in ASP.net-Web Forms wird von Master Seiten behandelt.</span><span class="sxs-lookup"><span data-stu-id="802b1-158">Page layout in ASP.NET Web Forms is handled by Master Pages.</span></span> <span data-ttu-id="802b1-159">Master Seiten definieren eine Vorlage mit einem oder mehreren Inhalts Platzhaltern, die dann von einzelnen Seiten bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="802b1-159">Master Pages define a template with one or more content placeholders that can then be supplied by individual pages.</span></span> <span data-ttu-id="802b1-160">Masterseiten werden in *Master* Dateien definiert und beginnen mit der `<%@ Master %>`-Direktive.</span><span class="sxs-lookup"><span data-stu-id="802b1-160">Master Pages are defined in *.master* files and start with the `<%@ Master %>` directive.</span></span> <span data-ttu-id="802b1-161">Der Inhalt der *Master* Dateien ist so codiert wie eine *aspx* -Seite, aber mit `<asp:ContentPlaceHolder>`-Steuerelementen, um zu markieren, wo Seiteninhalte bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="802b1-161">The content of the *.master* files is coded as you would an *.aspx* page, but with the addition of `<asp:ContentPlaceHolder>` controls to mark where pages can supply content.</span></span>

<span data-ttu-id="802b1-162">*Site. Master*</span><span class="sxs-lookup"><span data-stu-id="802b1-162">*Site.master*</span></span>

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

<span data-ttu-id="802b1-163">In blazor wird das Seitenlayout mithilfe von Layoutkomponenten behandelt.</span><span class="sxs-lookup"><span data-stu-id="802b1-163">In Blazor, you handle page layout using layout components.</span></span> <span data-ttu-id="802b1-164">Layoutkomponenten erben von `LayoutComponentBase`, das eine einzelne `Body` Eigenschaft des Typs `RenderFragment`definiert, die zum Rendering der Inhalte der Seite verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="802b1-164">Layout components inherit from `LayoutComponentBase`, which defines a single `Body` property of type `RenderFragment`, which can be used to render the contents of the page.</span></span>

<span data-ttu-id="802b1-165">*MainLayout. Razor*</span><span class="sxs-lookup"><span data-stu-id="802b1-165">*MainLayout.razor*</span></span>

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

<span data-ttu-id="802b1-166">Wenn die Seite mit einem Layout gerendert wird, wird die Seite im Inhalt des angegebenen Layouts an der Position gerendert, an der das Layout ihre `Body`-Eigenschaft rendert.</span><span class="sxs-lookup"><span data-stu-id="802b1-166">When the page with a layout is rendered, the page is rendered within the contents of the specified layout at the location where the layout renders its `Body` property.</span></span>

<span data-ttu-id="802b1-167">Wenn Sie ein Layout auf eine Seite anwenden möchten, verwenden Sie die `@layout`-Direktive:</span><span class="sxs-lookup"><span data-stu-id="802b1-167">To apply a layout to a page, use the `@layout` directive:</span></span>

```razor
@layout MainLayout
```

<span data-ttu-id="802b1-168">Sie können das Layout für alle Komponenten in einem Ordner und in Unterordnern mithilfe einer *_Imports Razor* -Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-168">You can specify the layout for all components in a folder and subfolders using an *_Imports.razor* file.</span></span> <span data-ttu-id="802b1-169">Sie können auch ein Standardlayout für alle Seiten mithilfe der [Routerkomponente](#router-component)angeben.</span><span class="sxs-lookup"><span data-stu-id="802b1-169">You can also specify a default layout for all your pages using the [Router component](#router-component).</span></span>

<span data-ttu-id="802b1-170">Master Seiten können mehrere Inhalts Platzhalter definieren, aber Layouts in blazor verfügen nur über eine einzige `Body`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="802b1-170">Master Pages can define multiple content placeholders, but layouts in Blazor only have a single `Body` property.</span></span> <span data-ttu-id="802b1-171">Diese Einschränkung der blazor-Layoutkomponenten wird in einer zukünftigen Version hoffentlich behoben werden.</span><span class="sxs-lookup"><span data-stu-id="802b1-171">This limitation of Blazor layout components will hopefully be addressed in a future release.</span></span>

<span data-ttu-id="802b1-172">Master Seiten in ASP.net-Web Forms können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="802b1-172">Master Pages in ASP.NET Web Forms can be nested.</span></span> <span data-ttu-id="802b1-173">Das heißt, eine Master Seite kann auch eine Master Seite verwenden.</span><span class="sxs-lookup"><span data-stu-id="802b1-173">That is, a Master Page may also use a Master Page.</span></span> <span data-ttu-id="802b1-174">Layoutkomponenten in blazor können ebenfalls eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="802b1-174">Layout components in Blazor may be nested too.</span></span> <span data-ttu-id="802b1-175">Sie können eine Layoutkomponente auf eine Layoutkomponente anwenden.</span><span class="sxs-lookup"><span data-stu-id="802b1-175">You can apply a layout component to a layout component.</span></span> <span data-ttu-id="802b1-176">Der Inhalt des inneren Layouts wird innerhalb des äußeren Layouts gerendert.</span><span class="sxs-lookup"><span data-stu-id="802b1-176">The contents of the inner layout will be rendered within the outer layout.</span></span>

<span data-ttu-id="802b1-177">*Childlayout. Razor*</span><span class="sxs-lookup"><span data-stu-id="802b1-177">*ChildLayout.razor*</span></span>

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

<span data-ttu-id="802b1-178">*Index. Razor*</span><span class="sxs-lookup"><span data-stu-id="802b1-178">*Index.razor*</span></span>

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

<span data-ttu-id="802b1-179">Die gerenderte Ausgabe für die Seite würde dann wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="802b1-179">The rendered output for the page would then be:</span></span>

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

<span data-ttu-id="802b1-180">Layouts in blazor definieren in der Regel nicht die Stamm-HTML-Elemente für eine Seite (`<html>`, `<body>`, `<head>`usw.).</span><span class="sxs-lookup"><span data-stu-id="802b1-180">Layouts in Blazor don't typically define the root HTML elements for a page (`<html>`, `<body>`, `<head>`, and so on).</span></span> <span data-ttu-id="802b1-181">Die Stamm-HTML-Elemente werden stattdessen auf der Hostseite einer blazor-App definiert, die zum Rendering der anfänglichen HTML-Inhalte für die APP verwendet wird (siehe [Bootstrap blazor](project-structure.md#bootstrap-blazor)).</span><span class="sxs-lookup"><span data-stu-id="802b1-181">The root HTML elements are instead defined in a Blazor app's host page, which is used to render the initial HTML content for the app (see [Bootstrap Blazor](project-structure.md#bootstrap-blazor)).</span></span> <span data-ttu-id="802b1-182">Die Hostseite kann mehrere Stamm Komponenten für die APP mit umgebenden Markup Rendering darstellen.</span><span class="sxs-lookup"><span data-stu-id="802b1-182">The host page can render multiple root components for the app with surrounding markup.</span></span>

<span data-ttu-id="802b1-183">Komponenten in blazor, einschließlich Seiten, können keine `<script>` Tags Rendering.</span><span class="sxs-lookup"><span data-stu-id="802b1-183">Components in Blazor, including pages, can't render `<script>` tags.</span></span> <span data-ttu-id="802b1-184">Diese Renderingleistung besteht darin, dass `<script>` Tags einmal geladen werden und dann nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="802b1-184">This rendering restriction exists because `<script>` tags get loaded once and then can't be changed.</span></span> <span data-ttu-id="802b1-185">Unerwartetes Verhalten kann auftreten, wenn Sie versuchen, die Tags mithilfe Razor-Syntax dynamisch zu rendern.</span><span class="sxs-lookup"><span data-stu-id="802b1-185">Unexpected behavior may occur if you try to render the tags dynamically using Razor syntax.</span></span> <span data-ttu-id="802b1-186">Stattdessen sollten alle `<script>` Tags der Host Seite der app hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="802b1-186">Instead, all `<script>` tags should be added to the app's host page.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="802b1-187">[Zurück](components.md)
>[Weiter](state-management.md)</span><span class="sxs-lookup"><span data-stu-id="802b1-187">[Previous](components.md)
[Next](state-management.md)</span></span>