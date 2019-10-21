---
title: 'Vorgehensweise: Verwenden der XML-Dokumentationsfeatures – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 3e59783a7f306d3d2a510fe3337a4c6490dcb3e8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523452"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="ce67e-102">Vorgehensweise: Verwenden der XML-Dokumentationsfeatures</span><span class="sxs-lookup"><span data-stu-id="ce67e-102">How to: Use the XML documentation features</span></span>

<span data-ttu-id="ce67e-103">Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ce67e-103">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="ce67e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce67e-104">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="ce67e-105">Im Beispiel wird eine XML-Datei mit folgendem Inhalt generiert:</span><span class="sxs-lookup"><span data-stu-id="ce67e-105">The example generates an .xml file with the following contents:</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member 
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="ce67e-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ce67e-106">Compiling the code</span></span>

<span data-ttu-id="ce67e-107">Geben Sie die folgende Befehlszeile ein, um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="ce67e-107">To compile the example, type the following command line:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="ce67e-108">Mit diesem Befehl wird die XML-Datei *XMLsample.xml* erstellt, die Sie in Ihrem Browser oder mithilfe des TYPE-Befehls anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ce67e-108">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the TYPE command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="ce67e-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ce67e-109">Robust programming</span></span>

<span data-ttu-id="ce67e-110">XML-Dokumentation beginnt mit ///.</span><span class="sxs-lookup"><span data-stu-id="ce67e-110">XML documentation starts with ///.</span></span> <span data-ttu-id="ce67e-111">Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige ///-Startzeilen für Sie ein.</span><span class="sxs-lookup"><span data-stu-id="ce67e-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="ce67e-112">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="ce67e-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="ce67e-113">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="ce67e-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="ce67e-114">Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ce67e-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="ce67e-115">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce67e-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="ce67e-116">Es gibt eine Reihe empfohlener Tags (siehe [Empfohlene Tags für Dokumentationskommentare](recommended-tags-for-documentation-comments.md)).</span><span class="sxs-lookup"><span data-stu-id="ce67e-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="ce67e-117">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="ce67e-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="ce67e-118">Das \<param>-Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ce67e-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="ce67e-119">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist, und ob alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ce67e-119">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="ce67e-120">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="ce67e-120">If the verification failed, the compiler issues a warning.</span></span>

  - <span data-ttu-id="ce67e-121">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ce67e-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="ce67e-122">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ce67e-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="ce67e-123">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="ce67e-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="ce67e-124">Der Compiler berücksichtigt alle `using`-Anweisungen, wenn er nach einem Typ sucht, der im `cref`-Attribut beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ce67e-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="ce67e-125">Das \<summary>-Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce67e-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce67e-126">Die XML-Datei enthält keine vollständigen Informationen über den Typ und die Member (z. B. fehlen Typinformationen).</span><span class="sxs-lookup"><span data-stu-id="ce67e-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="ce67e-127">Um vollständige Informationen zu einem Typ oder Member zu erhalten, muss die Dokumentationsdatei zusammen mit Reflektion über den tatsächlichen Typ oder Member verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce67e-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce67e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce67e-128">See also</span></span>

- [<span data-ttu-id="ce67e-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ce67e-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ce67e-130">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ce67e-130">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="ce67e-131">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="ce67e-131">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="ce67e-132">DocFX-Dokumentationsprozessor</span><span class="sxs-lookup"><span data-stu-id="ce67e-132">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="ce67e-133">Sandcastle-Dokumentationsprozessor</span><span class="sxs-lookup"><span data-stu-id="ce67e-133">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
