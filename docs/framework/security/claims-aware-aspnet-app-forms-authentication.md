---
title: 'Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung'
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: ecaf1de0b806d5568d81fac2ddb2b39b697135ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792743"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="a34ed-102">Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>

## <a name="applies-to"></a><span data-ttu-id="a34ed-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="a34ed-103">Applies To</span></span>

- <span data-ttu-id="a34ed-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="a34ed-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>

- <span data-ttu-id="a34ed-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="a34ed-105">ASP.NET® Web Forms</span></span>

## <a name="summary"></a><span data-ttu-id="a34ed-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a34ed-106">Summary</span></span>

<span data-ttu-id="a34ed-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung, die Formularauthentifizierung verwendet, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="a34ed-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="a34ed-108">Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a34ed-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>

## <a name="contents"></a><span data-ttu-id="a34ed-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="a34ed-109">Contents</span></span>

- <span data-ttu-id="a34ed-110">Ziele</span><span class="sxs-lookup"><span data-stu-id="a34ed-110">Objectives</span></span>

- <span data-ttu-id="a34ed-111">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a34ed-111">Overview</span></span>

- <span data-ttu-id="a34ed-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="a34ed-112">Summary of Steps</span></span>

- <span data-ttu-id="a34ed-113">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a34ed-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="a34ed-114">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="a34ed-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a34ed-115">Step 3 – Test Your Solution</span></span>

## <a name="objectives"></a><span data-ttu-id="a34ed-116">Ziele</span><span class="sxs-lookup"><span data-stu-id="a34ed-116">Objectives</span></span>

- <span data-ttu-id="a34ed-117">Konfigurieren einer ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>

- <span data-ttu-id="a34ed-118">Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a34ed-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>

## <a name="overview"></a><span data-ttu-id="a34ed-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a34ed-119">Overview</span></span>

<span data-ttu-id="a34ed-120">In .NET 4.5 wurden WIF und seine anspruchsbasierte Autorisierung als wesentlicher Bestandteil in das Framework integriert.</span><span class="sxs-lookup"><span data-stu-id="a34ed-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="a34ed-121">Wenn Sie zuvor die Ansprüche eines ASP.NET-Benutzers abrufen wollten, war es erforderlich, WIF zu installieren und anschließend Schnittstellen in Principal-Objekte wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="a34ed-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="a34ed-122">Nun werden Ansprüche automatisch von diesen Principal-Objekten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a34ed-122">Now, claims are served automatically by these Principal objects.</span></span>

<span data-ttu-id="a34ed-123">Die Formularauthentifizierung profitiert von der Integration von WIF in .NET 4.5, da allen Benutzern, die über Formularauthentifizierung authentifiziert wurden, automatisch Ansprüche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a34ed-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="a34ed-124">Sie können diese Ansprüche sofort in einer ASP.NET-Anwendung verwenden, die die Formularauthentifizierung verwendet. Dies wird in dieser Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a34ed-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>

## <a name="summary-of-steps"></a><span data-ttu-id="a34ed-125">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="a34ed-125">Summary of Steps</span></span>

- <span data-ttu-id="a34ed-126">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a34ed-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="a34ed-127">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="a34ed-128">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a34ed-128">Step 3 – Test Your Solution</span></span>

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="a34ed-129">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a34ed-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

<span data-ttu-id="a34ed-130">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a34ed-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>

#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="a34ed-131">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a34ed-131">To create a simple ASP.NET application</span></span>

1. <span data-ttu-id="a34ed-132">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a34ed-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>

2. <span data-ttu-id="a34ed-133">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="a34ed-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>

3. <span data-ttu-id="a34ed-134">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a34ed-134">In **Name**, enter `TestApp` and press **OK**.</span></span>

## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a34ed-135">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

<span data-ttu-id="a34ed-136">In diesem Schritt fügen Sie einen Konfigurationseintrag zur Konfigurationsdatei *Web.config* hinzu und bearbeiten die Datei *Default.aspx*, damit diese die Informationen zu den Ansprüchen eines Kontos anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a34ed-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>

#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a34ed-137">Konfigurieren einer ASP.NET-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-137">To configure ASP.NET application for claims using Forms authentication</span></span>

1. <span data-ttu-id="a34ed-138">Ersetzten Sie das vorhandene Markup in der Datei *Default.aspx* durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="a34ed-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>

    ```aspx
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>

    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
        <p>
            This page displays the claims associated with a Forms authenticated user.
        </p>
        <h3>Your Claims</h3>
        <p>
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">
                <AlternatingRowStyle BackColor="White" />
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />
            </asp:GridView>
        </p>
    </asp:Content>
    ```

    <span data-ttu-id="a34ed-139">In diesem Schritt wird eine „GridView“-Steuerung zu Ihrer Seite *Default.aspx* hinzugefügt, die mit den Ansprüchen aufgefüllt wird, die von der Formularauthentifizierung abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="a34ed-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>

2. <span data-ttu-id="a34ed-140">Speichern Sie die Datei *Default.aspx*, und öffnen Sie dann die CodeBehind-Datei *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="a34ed-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="a34ed-141">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="a34ed-141">Replace the existing code with the following:</span></span>

    ```csharp
    using System;
    using System.Web.UI;
    using System.Security.Claims;

    namespace TestApp
    {
        public partial class _Default : Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;

                if (claimsPrincipal != null)
                {
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;
                    this.ClaimsGridView.DataBind();
                }
            }
        }
    }
    ```

    <span data-ttu-id="a34ed-142">Der obige Code zeigt die Ansprüche bezüglich eines authentifizierten Benutzers, einschließlich Benutzer, die durch die Formularauthentifizierung identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a34ed-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>

## <a name="step-3--test-your-solution"></a><span data-ttu-id="a34ed-143">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a34ed-143">Step 3 – Test Your Solution</span></span>

<span data-ttu-id="a34ed-144">In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a34ed-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>

#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a34ed-145">Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a34ed-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>

1. <span data-ttu-id="a34ed-146">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a34ed-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="a34ed-147">*Default.aspx* sollte mit den Links **Registrieren** und **Anmelden** rechts oben auf der Seite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a34ed-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="a34ed-148">Klicken Sie auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="a34ed-148">Click **Register**.</span></span>

2. <span data-ttu-id="a34ed-149">Erstellen Sie auf der Seite **Registrieren** ein Benutzerkonto, und klicken Sie dann auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="a34ed-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="a34ed-150">Ihr Konto wird unter Verwendung der Formularauthentifizierung erstellt, und Sie werden automatisch angemeldet.</span><span class="sxs-lookup"><span data-stu-id="a34ed-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>

3. <span data-ttu-id="a34ed-151">Nachdem Sie zur Startseite umgeleitet werden, sollte unter der Überschrift **Ihre Ansprüche** eine Tabelle angezeigt werden, die die Anspruchsinformationen **Aussteller**, **Originalaussteller**, **Typ**, **Welt** und **Werttyp** Ihres Kontos enthält.</span><span class="sxs-lookup"><span data-stu-id="a34ed-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
