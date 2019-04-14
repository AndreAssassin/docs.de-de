---
title: Erstellen einer Visual Basic .NET Standard-Klassenbibliothek in Visual Studio 2017
description: Erfahren Sie, wie Sie eine in Visual Basic geschriebene .NET Standard-Klassenbibliothek mithilfe von Visual Studio 2017 erstellen.
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: f14e4ffbebfe0d7e01d548a6d4f2dc8924633682
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157299"
---
# <a name="build-a-net-standard-library-with-visual-basic-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="b4352-103">Erstellen einer .NET Standard-Bibliothek mit Visual Basic und .NET Core SDK in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b4352-103">Build a .NET Standard library with Visual Basic and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="b4352-104">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="b4352-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="b4352-105">Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4352-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="b4352-106">Wenn Sie die Klassenbibliothek fertig stellen, können Sie entscheiden, ob Sie sie als Drittanbieterkomponente verteilen oder als Komponente mit einer oder mehreren Anwendungen in ein Paket einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="b4352-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="b4352-107">Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET-Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="b4352-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="b4352-108">In diesem Thema erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="b4352-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="b4352-109">Sie implementieren sie als [Erweiterungsmethode](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b4352-109">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="b4352-110">Erstellen einer Klassenbibliotheks-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="b4352-110">Creating a class library solution</span></span>

<span data-ttu-id="b4352-111">Zunächst erstellen Sie eine Projektmappe für Ihre Klassenbibliotheksprojekt und die zugehörigen Projekte.</span><span class="sxs-lookup"><span data-stu-id="b4352-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="b4352-112">Eine Visual Studio-Projektmappe dient nur als Container für ein oder mehrere Projekte.</span><span class="sxs-lookup"><span data-stu-id="b4352-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="b4352-113">So erstellen Sie die Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="b4352-113">To create the solution:</span></span>

1. <span data-ttu-id="b4352-114">Wählen Sie auf der Visual Studio-Menüleiste **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="b4352-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="b4352-115">Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Andere Projekttypen**, und wählen Sie **Visual Studio-Projektmappen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4352-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="b4352-116">Nennen Sie die Projektmappe „ClassLibraryProjects“, und wählen Sie die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="b4352-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Visual Studio-Dialogfeld „Neues Testprojekt erstellen“](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="b4352-118">Erstellen des Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="b4352-118">Creating the class library project</span></span>

<span data-ttu-id="b4352-119">Erstellen Sie Ihr Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="b4352-119">Create your class library project:</span></span>

1. <span data-ttu-id="b4352-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappendatei **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="b4352-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="b4352-121">Erweitern Sie den Knoten **Visual Basic** im Dialogfeld **Neues Projekt hinzufügen**, klicken Sie dann auf den Knoten **.NET Standard** und anschließend auf die Projektvorlage **Klassenbibliothek (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="b4352-121">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="b4352-122">Geben Sie im Textfeld **Name** „StringLibrary“ als Namen des Projekts ein.</span><span class="sxs-lookup"><span data-stu-id="b4352-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="b4352-123">Wählen Sie **OK**, um das Klassenbibliotheksprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4352-123">Select **OK** to create the class library project.</span></span>

   ![Visual Studio-Dialogfeld „Neues Bibliotheksprojekt hinzufügen“](./media/vb-library-with-visual-studio/create-new-library-project.png)

   <span data-ttu-id="b4352-125">Das Codefenster öffnet sich dann in der Visual Studio-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="b4352-125">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Visual Studio-Anwendungsfenster, das die den Standardvorlagencode der Klassenbibliothek zeigt](./media/vb-library-with-visual-studio/visual-studio-library.png)

1. <span data-ttu-id="b4352-127">Stellen Sie sicher, dass die Bibliothek auf die richtige Version von .NET Standard zielt.</span><span class="sxs-lookup"><span data-stu-id="b4352-127">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="b4352-128">Klicken Sie mit der rechten Maustaste auf das Bibliotheksprojekt im Fenster des **Projektmappen-Explorer**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b4352-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="b4352-129">Das Textfeld **Zielframework** zeigt dann, dass .NET Standard 2.0 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4352-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="b4352-131">Löschen Sie im Dialogfeld **Eigenschaften** außerdem den Text im Textfeld **Stammnamespace**.</span><span class="sxs-lookup"><span data-stu-id="b4352-131">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="b4352-132">Für jedes Projekt erstellt Visual Basic automatisch einen Namespace, der dem Projektnamen entspricht. Außerdem sind alle Namespaces, die in den Quellcodedateien definiert sind, übergeordnete Elemente dieses Namespace.</span><span class="sxs-lookup"><span data-stu-id="b4352-132">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="b4352-133">Wir möchten einen Namespace auf oberster Ebene definieren, indem wir das Schlüsselwort [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4352-133">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="b4352-134">Ersetzen Sie den Code im Codefenster durch den folgenden Code, und speichern Sie die Datei:</span><span class="sxs-lookup"><span data-stu-id="b4352-134">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="b4352-135">Die Klassenbibliothek, `UtilityLibraries.StringLibrary`, enthält eine Methode namens `StartsWithUpper`, welche einen <xref:System.Boolean> Wert zurückgibt, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="b4352-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="b4352-136">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="b4352-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="b4352-137">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="b4352-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="b4352-138">Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4352-138">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="b4352-139">Das Projekt sollte fehlerfrei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b4352-139">The project should compile without error.</span></span>

   ![Ausgabebereich, der zeigt, dass der Buildvorgang erfolgreich war](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="b4352-141">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b4352-141">Next step</span></span>

<span data-ttu-id="b4352-142">Sie haben die Bibliothek erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="b4352-142">You've successfully built the library.</span></span> <span data-ttu-id="b4352-143">Aber da Sie keine ihrer Methoden aufgerufen haben, wissen Sie nicht, ob sie wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b4352-143">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="b4352-144">Der nächste Schritt bei der Entwicklung Ihrer Bibliothek ist ihr Test mithilfe eines [Komponententestprojekts](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b4352-144">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
