---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen verwalteter Assemblys in Visual Studio'
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1a37a3bcc3b1bc352d6a2f59691819e0b2403d3d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523893"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="a8bc8-102">Exemplarische Vorgehensweise: Einbetten von Typen verwalteter Assemblys in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a8bc8-102">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="a8bc8-103">Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="a8bc8-104">Das heißt, Ihr Programm kann so geschrieben werden, dass Typen aus einer beliebigen Version einer verwalteten Bibliothek verwendet werden, ohne dass es für jede neue Version neu kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-104">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="a8bc8-105">Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="a8bc8-106">Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="a8bc8-107">Allerdings können Sie die Typeinbettung mit vollständig verwalteten Lösungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-107">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="a8bc8-108">Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-108">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="a8bc8-109">Ein Clientprogramm kann die Typinformationen für die Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-109">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="a8bc8-110">Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-110">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="a8bc8-111">Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der Compileroption `/link`.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-111">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> 

<span data-ttu-id="a8bc8-112">Wenn Sie eine neue Version Ihrer Runtimeassembly mit starkem Namen erstellen, muss das Clientprogramm nicht neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-112">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="a8bc8-113">Das Clientprogramm verwendet weiterhin die verfügbare Version der Runtimeassembly und die eingebetteten Typinformationen für die öffentlichen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-113">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="a8bc8-114">In dieser exemplarischen Vorgehensweise führen Sie folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-114">In this walkthrough, you:</span></span>

1. <span data-ttu-id="a8bc8-115">Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-115">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="a8bc8-116">Erstellen Sie eine Runtimeassembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-116">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="a8bc8-117">Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-117">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="a8bc8-118">Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-118">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="a8bc8-119">Führen Sie das Clientprogramm aus, um zu überprüfen, dass es die neue Version der Runtimeassembly verwendet, ohne eine erneute Kompilierung zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-119">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="a8bc8-120">Bedingungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a8bc8-120">Conditions and limitations</span></span>

<span data-ttu-id="a8bc8-121">Sie können Typinformationen einer Assembly unter folgenden Bedingungen einbetten:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-121">You can embed type information from an assembly under the following conditions:</span></span> 

- <span data-ttu-id="a8bc8-122">Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-122">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="a8bc8-123">Die eingebetteten Schnittstellen werden mit `ComImport`- und `Guid`-Attributen mit eindeutigen GUIDs versehen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-123">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="a8bc8-124">Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-124">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="a8bc8-125">Die Visual C#- und Visual Basic-Projektvorlagen enthalten standardmäßig ein `Guid`-Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-125">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="a8bc8-126">Da die primäre Funktion der Typeinbettung in der Unterstützung von COM-Interop-Assemblys besteht, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-126">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="a8bc8-127">Nur die für COM-Interop spezifischen Attribute werden eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-127">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="a8bc8-128">Andere Attribute werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-128">Other attributes are ignored.</span></span>
- <span data-ttu-id="a8bc8-129">Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-129">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="a8bc8-130">Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-130">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="a8bc8-131">Konstanten werden nicht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-131">Constants are not embedded.</span></span>
- <span data-ttu-id="a8bc8-132">Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-132">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="a8bc8-133">Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-133">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="a8bc8-134">Erstellen einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8bc8-134">Create an interface</span></span>

<span data-ttu-id="a8bc8-135">Der erste Schritt besteht darin, die Schnittstellenassembly mit Typäquivalenz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-135">The first step is to create the type equivalence interface assembly.</span></span> 

1. <span data-ttu-id="a8bc8-136">Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-136">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="a8bc8-137">Geben Sie *Klassenbibliothek* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-137">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="a8bc8-138">Wählen Sie die Vorlage **Klassenbibliothek (.NET Framework)** für C# oder VB aus der Liste aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-138">Select either the C# or VB **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="a8bc8-139">Geben Sie *TypeEquivalenceInterface* im Dialogfeld **Neues Projekt konfigurieren** unter **Projektname** ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-139">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="a8bc8-140">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-140">The new project is created.</span></span>
   
1. <span data-ttu-id="a8bc8-141">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *Class1.cs* oder *Class1.vb*, wählen Sie **Umbenennen** aus, und benennen Sie die Datei *Class1* in *ISampleInterface* um.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-141">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="a8bc8-142">Wählen Sie bei der Eingabeaufforderung **Ja** aus, um auch die Klasse in `ISampleInterface` umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-142">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="a8bc8-143">Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-143">This class represents the public interface for the class.</span></span>
   
1. <span data-ttu-id="a8bc8-144">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-144">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span> 
   
1. <span data-ttu-id="a8bc8-145">Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie einen Speicherort auf Ihrem Computer als **Ausgabepfad** fest, z. B. *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-145">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="a8bc8-146">Diesen Speicherort werden Sie im Rahmen dieser exemplarischen Vorgehensweise häufiger verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-146">You use the same location throughout this walkthrough.</span></span> 
   
1. <span data-ttu-id="a8bc8-147">Klicken Sie im linken Bereich der **Eigenschaften** auf **Signierung**, und aktivieren Sie dann das Kontrollkästchen **Assembly signieren**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-147">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="a8bc8-148">Klicken Sie im Dropdownfeld **Schlüsseldatei mit starkem Namen auswählen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-148">In the dropdown for **Choose a strong name key file**, select **New**.</span></span> 
   
1. <span data-ttu-id="a8bc8-149">Geben Sie *key.snk* im Dialogfeld **Schlüssel für einen starken Namen erstellen** unter **Schlüsseldateiname** ein.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-149">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="a8bc8-150">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-150">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-151">Öffnen Sie die Klassendatei *ISampleInterface* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um die `ISampleInterface`-Schnittstelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-151">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>
   
   ```csharp
   using System;
   using System.Runtime.InteropServices;
   
   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```
   
   ```vb
   Imports System.Runtime.InteropServices
   
   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```
   
1. <span data-ttu-id="a8bc8-152">Klicken Sie im Menü **Extras** auf **GUID erstellen**, und wählen Sie dann im Dialogfeld **GUID erstellen** das **Registrierungsformat** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-152">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="a8bc8-153">Klicken Sie auf **Kopieren** und dann auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-153">Select **Copy**, and then select **Exit**.</span></span>
   
1. <span data-ttu-id="a8bc8-154">Ersetzen Sie die Beispiel-GUID im `Guid`-Attribut Ihres Codes durch die kopierte GUID, und entfernen Sie die Klammern ( **{ }** ).</span><span class="sxs-lookup"><span data-stu-id="a8bc8-154">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>
   
1. <span data-ttu-id="a8bc8-155">Erweitern Sie den Ordner **Eigenschaften** im **Projektmappen-Explorer**, und wählen Sie die Datei *AssemblyInfo.cs* oder *AssemblyInfo.vb* aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-155">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="a8bc8-156">Fügen Sie das folgende Attribut im Code-Editor zur Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-156">In the code editor, add the following attribute to the file:</span></span>
   
   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```
   
   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```
   
1. <span data-ttu-id="a8bc8-157">Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-157">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="a8bc8-158">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-158">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="a8bc8-159">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert, z. B. *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-159">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="a8bc8-160">Erstellen einer Laufzeitklasse</span><span class="sxs-lookup"><span data-stu-id="a8bc8-160">Create a runtime class</span></span>

<span data-ttu-id="a8bc8-161">Als Nächstes erstellen Sie die Lauftzeitklasse für die Typäquivalenz.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-161">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="a8bc8-162">Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-162">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="a8bc8-163">Geben Sie *Klassenbibliothek* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-163">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="a8bc8-164">Wählen Sie die Vorlage **Klassenbibliothek (.NET Framework)** für C# oder VB aus der Liste aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-164">Select either the C# or VB **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="a8bc8-165">Geben Sie *TypeEquivalenceRuntime* unter **Projektname** im Dialogfeld **Neues Projekt konfigurieren** ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-165">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="a8bc8-166">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-166">The new project is created.</span></span>
   
1. <span data-ttu-id="a8bc8-167">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *Class1.cs* oder *Class1.vb*, wählen Sie **Umbenennen** aus, und benennen Sie die Datei *Class1* in *SampleClass* um.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-167">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="a8bc8-168">Wählen Sie bei der Eingabeaufforderung **Ja** aus, um auch die Klasse in `SampleClass` umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-168">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="a8bc8-169">Diese Klasse implementiert die `ISampleInterface` -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-169">This class implements the `ISampleInterface` interface.</span></span>
   
1. <span data-ttu-id="a8bc8-170">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-170">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="a8bc8-171">Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie dann denselben Speicherort als **Ausgabepfad** fest, den Sie für das TypeEquivalenceInterface-Projekt verwendet haben, z. B. *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-171">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>
   
1. <span data-ttu-id="a8bc8-172">Klicken Sie im linken Bereich der **Eigenschaften** auf **Signierung**, und aktivieren Sie dann das Kontrollkästchen **Assembly signieren**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-172">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="a8bc8-173">Klicken Sie im Dropdownfeld **Schlüsseldatei mit starkem Namen auswählen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-173">In the dropdown for **Choose a strong name key file**, select **New**.</span></span> 
   
1. <span data-ttu-id="a8bc8-174">Geben Sie *key.snk* im Dialogfeld **Schlüssel für einen starken Namen erstellen** unter **Schlüsseldateiname** ein.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-174">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="a8bc8-175">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-175">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-176">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Hinzufügen** > **Verweis** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-176">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span> 
   
1. <span data-ttu-id="a8bc8-177">Klicken Sie im Dialogfeld **Verweis-Manager** auf **Durchsuchen**, und navigieren Sie zum Ausgabepfadordner.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-177">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="a8bc8-178">Wählen Sie die Datei *TypeEquivalenceInterface.dll* aus, und klicken Sie dann auf **Hinzufügen** und auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-178">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-179">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**, und wählen Sie den Verweis **TypeEquivalenceInterface** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-179">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="a8bc8-180">Legen Sie für **Spezifische Version** im Bereich **Eigenschaften** die Option **FALSE** fest, wenn das noch nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-180">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>
   
1. <span data-ttu-id="a8bc8-181">Öffnen Sie die Klassendatei *SampleClass* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um die `SampleClass`-Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-181">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>
   
   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using System.Text;
   using TypeEquivalenceInterface;
   
   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }
   
           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```
   
   ```vb
   Imports TypeEquivalenceInterface
   
   Public Class SampleClass
       Implements ISampleInterface
   
       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property
   
       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```
   
1. <span data-ttu-id="a8bc8-182">Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-182">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="a8bc8-183">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-183">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="a8bc8-184">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-184">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="a8bc8-185">Erstellen eines Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="a8bc8-185">Create a client project</span></span>

<span data-ttu-id="a8bc8-186">Schließlich erstellen Sie ein Typäquivalenz-Clientprogramm, das auf die Schnittstellenassembly verweist.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-186">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="a8bc8-187">Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-187">In Visual Studio, select **File** > **New** > **Project**.</span></span>
   
1. <span data-ttu-id="a8bc8-188">Geben Sie *Konsole* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-188">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="a8bc8-189">Wählen Sie die Vorlage **Konsolen-App (.NET Framework)** für C# oder VB aus der Liste aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-189">Select either the C# or VB **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span> 
   
1. <span data-ttu-id="a8bc8-190">Geben Sie *TypeEquivalenceClient* unter **Projektname** im Dialogfeld **Neues Projekt konfigurieren** ein, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-190">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="a8bc8-191">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-191">The new project is created.</span></span>
   
1. <span data-ttu-id="a8bc8-192">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceClient**, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-192">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="a8bc8-193">Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie dann denselben Speicherort als **Ausgabepfad** fest, den Sie für das TypeEquivalenceInterface-Projekt verwendet haben, z. B. *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-193">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>
   
1. <span data-ttu-id="a8bc8-194">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceClient**, und wählen Sie dann **Hinzufügen** > **Verweis** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span> 
   
1. <span data-ttu-id="a8bc8-195">Wenn die Datei **TypeEquivalenceInterface.dll** bereits im Dialogfeld **Verweis-Manager** aufgeführt wird, wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-195">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="a8bc8-196">Wenn nicht, klicken Sie auf **Durchsuchen**, navigieren Sie zum Ausgabepfadordner, wählen Sie die Datei *TypeEquivalenceInterface.dll* aus (nicht die Datei *TypeEquivalenceRuntime.dll*), und klicken Sie schließlich auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-196">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="a8bc8-197">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-197">Select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-198">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**, und wählen Sie den Verweis **TypeEquivalenceInterface** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-198">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="a8bc8-199">Legen Sie für **Interoptypen einbetten** im Bereich **Eigenschaften** die Option **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-199">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>
   
1. <span data-ttu-id="a8bc8-200">Öffnen Sie die Datei *Program.cs* oder *Module1.vb* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um das Clientprogramm zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-200">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>
   
   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using System.Text;
   using TypeEquivalenceInterface;
   using System.Reflection;
   
   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```
   
   ```vb
   Imports TypeEquivalenceInterface
   Imports System.Reflection
   
   Module Module1
   
       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub
   
   End Module
   ```
   
1. <span data-ttu-id="a8bc8-201">Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-201">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="a8bc8-202">Drücken Sie **STRG**+**F5**, um das Programm zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-202">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="a8bc8-203">Beachten Sie, dass die Konsolenausgabe die Assemblyversion **1.0.0.0** zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-203">Note that the console output returns the assembly version **1.0.0.0**.</span></span> 
   
## <a name="modify-the-interface"></a><span data-ttu-id="a8bc8-204">Anpassen der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8bc8-204">Modify the interface</span></span>

<span data-ttu-id="a8bc8-205">Im Folgenden passen Sie de Schnittstellenassembly an und ändern ihre Version.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-205">Now, modify the interface assembly, and change its version.</span></span> 

1. <span data-ttu-id="a8bc8-206">Klicken Sie in Visual Studio auf **Datei** > **Öffnen** > **Projekt/Projektmappe**, und öffnen Sie das Projekt **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-206">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>
   
1. <span data-ttu-id="a8bc8-207">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-207">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="a8bc8-208">Klicken Sie im linken Bereich der **Eigenschaften** auf **Anwendung**, und klicken Sie dann auf **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-208">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span> 
   
1. <span data-ttu-id="a8bc8-209">Ändern Sie die Werte für **Assemblyversion** und **Dateiversion** im Dialogfeld **Assemblyinformationen** in *2.0.0.0*, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-209">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-210">Öffnen Sie die Datei *SampleInterface.cs* oder *SampleInterface.vb*, und fügen Sie die folgende Codezeile zur `ISampleInterface`-Schnittstelle hinzu:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-210">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>
   
   ```csharp
   DateTime GetDate();
   ```
   
   ```vb
   Function GetDate() As Date
   ```
   
1. <span data-ttu-id="a8bc8-211">Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-211">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="a8bc8-212">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-212">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="a8bc8-213">Eine neue Version der DLL-Datei für die Klassenbibliothek wird kompiliert und im Buildausgabepfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-213">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="a8bc8-214">Anpassen der Laufzeitklasse</span><span class="sxs-lookup"><span data-stu-id="a8bc8-214">Modify the runtime class</span></span>

<span data-ttu-id="a8bc8-215">Ändern Sie außerdem die Laufzeitklasse, und aktualisieren Sie ihre Version.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-215">Also modify the runtime class and update its version.</span></span> 

1. <span data-ttu-id="a8bc8-216">Klicken Sie in Visual Studio auf **Datei** > **Öffnen** > **Projekt/Projektmappe**, und öffnen Sie das Projekt **TypeEquivalenceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-216">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>
   
1. <span data-ttu-id="a8bc8-217">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-217">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span> 
   
1. <span data-ttu-id="a8bc8-218">Klicken Sie im linken Bereich der **Eigenschaften** auf **Anwendung**, und klicken Sie dann auf **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-218">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span> 
   
1. <span data-ttu-id="a8bc8-219">Ändern Sie die Werte für **Assemblyversion** und **Dateiversion** im Dialogfeld **Assemblyinformationen** in *2.0.0.0*, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-219">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>
   
1. <span data-ttu-id="a8bc8-220">Öffnen Sie die Datei *SampleClass.cs* oder *SampleClass.vb*, und fügen Sie den folgenden Code zur `SampleClass`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="a8bc8-220">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>
   
   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```
   
   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```
   
1. <span data-ttu-id="a8bc8-221">Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-221">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>
   
1. <span data-ttu-id="a8bc8-222">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-222">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="a8bc8-223">Eine neue Version der DLL-Datei für die Klassenbibliothek wird kompiliert und im Buildausgabepfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-223">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="a8bc8-224">Ausführen des aktualisierten Clientprogramms</span><span class="sxs-lookup"><span data-stu-id="a8bc8-224">Run the updated client program</span></span> 

<span data-ttu-id="a8bc8-225">Öffnen Sie den Speicherort des Buildausgabeordners, und führen Sie die Datei *TypeEquivalenceClient.exe* aus.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-225">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="a8bc8-226">Beachten Sie, dass die Konsolenausgabe nun die neue Version der `TypeEquivalenceRuntime`-Assembly (*2.0.0.0*) darstellt, ohne dass das Programm neu kompiliert werden musste.</span><span class="sxs-lookup"><span data-stu-id="a8bc8-226">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8bc8-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8bc8-227">See also</span></span>

- [<span data-ttu-id="a8bc8-228">-link (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a8bc8-228">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="a8bc8-229">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bc8-229">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="a8bc8-230">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a8bc8-230">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a8bc8-231">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bc8-231">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="a8bc8-232">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="a8bc8-232">Program with assemblies</span></span>](program.md)
- [<span data-ttu-id="a8bc8-233">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="a8bc8-233">Assemblies in .NET</span></span>](index.md)
