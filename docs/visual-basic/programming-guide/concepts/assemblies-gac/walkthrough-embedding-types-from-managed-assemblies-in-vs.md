---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 18f22a771ab7279f177fe39d8c372a8517056890
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754834"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="546cb-102">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="546cb-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="546cb-103">Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden.</span><span class="sxs-lookup"><span data-stu-id="546cb-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="546cb-104">Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek geschrieben werden; eine erneute Kompilierung für jede Version ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="546cb-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>

<span data-ttu-id="546cb-105">Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet.</span><span class="sxs-lookup"><span data-stu-id="546cb-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="546cb-106">Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="546cb-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="546cb-107">Sie können das Einbetten von Typen jedoch auch mit einer vollständig verwalteten Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="546cb-107">However, you can also use type embedding with a fully managed solution.</span></span>

<span data-ttu-id="546cb-108">Typinformationen können von einer Assembly aus eingebettet werden, die die folgenden Merkmale aufweist:</span><span class="sxs-lookup"><span data-stu-id="546cb-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>

- <span data-ttu-id="546cb-109">Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="546cb-109">The assembly exposes at least one public interface.</span></span>

- <span data-ttu-id="546cb-110">Die eingebetteten Schnittstellen werden mit einem `ComImport`-Attribut und einem `Guid`-Attribut (und einer eindeutigen GUID) kommentiert.</span><span class="sxs-lookup"><span data-stu-id="546cb-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>

- <span data-ttu-id="546cb-111">Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert.</span><span class="sxs-lookup"><span data-stu-id="546cb-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="546cb-112">(Visual Basic-Projektvorlagen enthalten standardmäßig eine auf Assemblyebene `Guid` Attribut.)</span><span class="sxs-lookup"><span data-stu-id="546cb-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>

<span data-ttu-id="546cb-113">Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="546cb-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="546cb-114">Ein Clientprogramm kann dann die Typinformationen für diese Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="546cb-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="546cb-115">Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der Compileroption `/link`.</span><span class="sxs-lookup"><span data-stu-id="546cb-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="546cb-116">Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind.</span><span class="sxs-lookup"><span data-stu-id="546cb-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="546cb-117">Wenn Sie eine neue Version Ihrer Runtime-Assembly mit starkem Namen erstellen, muss das Clientprogramm nicht erneut mit der aktualisierten Runtime-Assembly kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="546cb-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="546cb-118">Stattdessen verwendet das Clientprogramm weiterhin die verfügbare Version der Runtime-Assembly und verwendet die eingebetteten Typinformationen für die öffentlichen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="546cb-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="546cb-119">Da die primäre Funktion des Einbettens von Typen die Unterstützung des Einbettens von Typinformationen von COM-Interop-Assemblys ist, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:</span><span class="sxs-lookup"><span data-stu-id="546cb-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>

- <span data-ttu-id="546cb-120">Nur die für COM-Interop spezifischen Attribute werden eingebettet; andere Attribute werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="546cb-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>

- <span data-ttu-id="546cb-121">Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="546cb-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="546cb-122">Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="546cb-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>

- <span data-ttu-id="546cb-123">Konstanten werden nicht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="546cb-123">Constants are not embedded.</span></span>

- <span data-ttu-id="546cb-124">Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="546cb-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="546cb-125">Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="546cb-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>

 <span data-ttu-id="546cb-126">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="546cb-126">In this walkthrough, you will do the following:</span></span>

- <span data-ttu-id="546cb-127">Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.</span><span class="sxs-lookup"><span data-stu-id="546cb-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>

- <span data-ttu-id="546cb-128">Erstellen Sie eine Runtime-Assembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="546cb-128">Create a strong-named runtime assembly that implements that public interface.</span></span>

- <span data-ttu-id="546cb-129">Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.</span><span class="sxs-lookup"><span data-stu-id="546cb-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>

- <span data-ttu-id="546cb-130">Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="546cb-130">Modify and rebuild the runtime assembly.</span></span>

- <span data-ttu-id="546cb-131">Führen Sie das Clientprogramm aus, um zu prüfen, dass die neue Version der Runtime-Assembly verwendet wird, ohne dass das Clientprogramm erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="546cb-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-an-interface"></a><span data-ttu-id="546cb-132">Erstellen einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="546cb-132">Creating an Interface</span></span>

#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="546cb-133">So erstellen Sie das Schnittstellenprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="546cb-133">To create the type equivalence interface project</span></span>

1. <span data-ttu-id="546cb-134">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="546cb-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="546cb-135">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="546cb-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="546cb-136">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="546cb-137">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceInterface` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="546cb-138">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="546cb-138">The new project is created.</span></span>

3. <span data-ttu-id="546cb-139">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb", und klicken Sie auf **umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="546cb-140">Benennen Sie die Datei in `ISampleInterface.vb` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="546cb-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="546cb-141">Durch Umbenennen der Datei wird die Klasse ebenfalls in `ISampleInterface` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="546cb-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="546cb-142">Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="546cb-142">This class will represent the public interface for the class.</span></span>

4. <span data-ttu-id="546cb-143">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="546cb-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="546cb-144">Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer fest, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="546cb-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="546cb-145">Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="546cb-145">This location will also be used in a later step in this walkthrough.</span></span>

5. <span data-ttu-id="546cb-146">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="546cb-147">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="546cb-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="546cb-148">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="546cb-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="546cb-149">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="546cb-150">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-150">Click **OK**.</span></span>

6. <span data-ttu-id="546cb-151">Öffnen Sie die ISampleInterface.vb-Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="546cb-152">Fügen Sie den folgenden Code zur Klasse „ISampleInterface“ hinzu, um die ISampleInterface-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="546cb-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>

    ```vb
    Imports System.Runtime.InteropServices

    <ComImport()>
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
    Public Interface ISampleInterface
        Sub GetUserInput()
        ReadOnly Property UserInput As String
    End Interface
    ```

7. <span data-ttu-id="546cb-153">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="546cb-154">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="546cb-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="546cb-155">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-155">Click **Exit**.</span></span>

8. <span data-ttu-id="546cb-156">Löschen Sie die Beispiel-GUID im Attribut `Guid`, und fügen Sie die GUID ein, die Sie aus dem Dialogfeld **GUID erstellen** kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="546cb-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="546cb-157">Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.</span><span class="sxs-lookup"><span data-stu-id="546cb-157">Remove the braces ({}) from the copied GUID.</span></span>

9. <span data-ttu-id="546cb-158">Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-158">On the **Project** menu, click **Show All Files**.</span></span>

10. <span data-ttu-id="546cb-159">In **Projektmappen-Explorer**, erweitern Sie die **Mein Projekt** Ordner.</span><span class="sxs-lookup"><span data-stu-id="546cb-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="546cb-160">Doppelklicken Sie auf die AssemblyInfo.vb.</span><span class="sxs-lookup"><span data-stu-id="546cb-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="546cb-161">Fügen Sie folgendes Attribut zur Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="546cb-161">Add the following attribute to the file.</span></span>

    ```vb
    <Assembly: ImportedFromTypeLib("")>
    ```

    <span data-ttu-id="546cb-162">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-162">Save the file.</span></span>

11. <span data-ttu-id="546cb-163">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="546cb-163">Save the project.</span></span>

12. <span data-ttu-id="546cb-164">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="546cb-165">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="546cb-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-runtime-class"></a><span data-ttu-id="546cb-166">Erstellen einer Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="546cb-166">Creating a Runtime Class</span></span>

#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="546cb-167">So erstellen Sie das Runtime-Projekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="546cb-167">To create the type equivalence runtime project</span></span>

1. <span data-ttu-id="546cb-168">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="546cb-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="546cb-169">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="546cb-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="546cb-170">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="546cb-171">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceRuntime` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="546cb-172">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="546cb-172">The new project is created.</span></span>

3. <span data-ttu-id="546cb-173">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb", und klicken Sie auf **umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="546cb-174">Benennen Sie die Datei in `SampleClass.vb` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="546cb-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="546cb-175">Durch Umbenennen der Datei wird die Klasse ebenfalls in `SampleClass` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="546cb-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="546cb-176">Diese Klasse implementiert die `ISampleInterface`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="546cb-176">This class will implement the `ISampleInterface` interface.</span></span>

4. <span data-ttu-id="546cb-177">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="546cb-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="546cb-178">Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="546cb-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

5. <span data-ttu-id="546cb-179">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="546cb-180">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="546cb-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="546cb-181">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="546cb-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="546cb-182">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="546cb-183">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-183">Click **OK**.</span></span>

6. <span data-ttu-id="546cb-184">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="546cb-185">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="546cb-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="546cb-186">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>

7. <span data-ttu-id="546cb-187">Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-187">On the **Project** menu, click **Show All Files**.</span></span>

8. <span data-ttu-id="546cb-188">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="546cb-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="546cb-189">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="546cb-190">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Spezifische Version** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="546cb-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>

9. <span data-ttu-id="546cb-191">Fügen Sie den folgenden Code zur Klassendatei „SampleClass“ hinzu, um die Klasse SampleClass zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="546cb-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>

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

10. <span data-ttu-id="546cb-192">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="546cb-192">Save the project.</span></span>

11. <span data-ttu-id="546cb-193">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="546cb-194">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="546cb-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-client-project"></a><span data-ttu-id="546cb-195">Erstellen eines Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="546cb-195">Creating a Client Project</span></span>

#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="546cb-196">So erstellen Sie das Clientprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="546cb-196">To create the type equivalence client project</span></span>

1. <span data-ttu-id="546cb-197">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="546cb-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="546cb-198">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="546cb-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="546cb-199">Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="546cb-200">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceClient` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="546cb-201">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="546cb-201">The new project is created.</span></span>

3. <span data-ttu-id="546cb-202">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="546cb-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="546cb-203">Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="546cb-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

4. <span data-ttu-id="546cb-204">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Verweis Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="546cb-205">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="546cb-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="546cb-206">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus (nicht „TypeEquivalenceRuntime.dll“), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="546cb-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>

5. <span data-ttu-id="546cb-207">Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-207">On the **Project** menu, click **Show All Files**.</span></span>

6. <span data-ttu-id="546cb-208">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="546cb-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="546cb-209">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="546cb-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="546cb-210">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Einbetten von Interop-Typen** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="546cb-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>

7. <span data-ttu-id="546cb-211">Fügen Sie den folgenden Code, um die Datei "Module1.vb", um das Clientprogramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="546cb-211">Add the following code to the Module1.vb file to create the client program.</span></span>

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

8. <span data-ttu-id="546cb-212">Drücken Sie STRG+F5, um das Programm zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="546cb-212">Press CTRL+F5 to build and run the program.</span></span>

## <a name="modifying-the-interface"></a><span data-ttu-id="546cb-213">Ändern der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="546cb-213">Modifying the Interface</span></span>

#### <a name="to-modify-the-interface"></a><span data-ttu-id="546cb-214">So ändern Sie die Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="546cb-214">To modify the interface</span></span>

1. <span data-ttu-id="546cb-215">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="546cb-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="546cb-216">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="546cb-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="546cb-217">Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="546cb-218">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="546cb-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="546cb-219">Öffnen Sie die ISampleInterface.vb-Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="546cb-220">Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="546cb-220">Add the following line of code to the ISampleInterface interface.</span></span>

    ```vb
    Function GetDate() As Date
    ```

    <span data-ttu-id="546cb-221">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-221">Save the file.</span></span>

4. <span data-ttu-id="546cb-222">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="546cb-222">Save the project.</span></span>

5. <span data-ttu-id="546cb-223">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="546cb-224">Eine neue Version der DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="546cb-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="modifying-the-runtime-class"></a><span data-ttu-id="546cb-225">Ändern der Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="546cb-225">Modifying the Runtime Class</span></span>

#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="546cb-226">So ändern Sie die Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="546cb-226">To modify the runtime class</span></span>

1. <span data-ttu-id="546cb-227">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="546cb-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="546cb-228">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="546cb-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="546cb-229">Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="546cb-230">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="546cb-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="546cb-231">Öffnen Sie die SampleClass.vb-Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-231">Open the SampleClass.vb file.</span></span> <span data-ttu-id="546cb-232">Fügen Sie folgenden Codezeilen zur Klasse „SampleClass“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="546cb-232">Add the following lines of code to the SampleClass class.</span></span>

    ```vb
    Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
        Return Now
    End Function
    ```

    <span data-ttu-id="546cb-233">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="546cb-233">Save the file.</span></span>

4. <span data-ttu-id="546cb-234">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="546cb-234">Save the project.</span></span>

5. <span data-ttu-id="546cb-235">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="546cb-235">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="546cb-236">Eine aktualisierte Version der DLL-Datei der Klassenbibliothek wird kompiliert und im vorher angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="546cb-236">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

6. <span data-ttu-id="546cb-237">Öffnen Sie im Datei-Explorer den Ordner mit dem Ausgabepfad (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="546cb-237">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="546cb-238">Doppelklicken Sie auf die Datei „TypeEquivalenceClient.exe“, um das Programm auszuführen.</span><span class="sxs-lookup"><span data-stu-id="546cb-238">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="546cb-239">Das Programm reflektiert die neue Version der TypeEquivalenceRuntime-Assembly, ohne dass sie erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="546cb-239">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="546cb-240">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="546cb-240">See also</span></span>

- [<span data-ttu-id="546cb-241">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="546cb-241">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="546cb-242">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="546cb-242">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="546cb-243">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="546cb-243">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="546cb-244">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="546cb-244">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
