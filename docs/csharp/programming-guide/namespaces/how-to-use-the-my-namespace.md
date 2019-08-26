---
title: 'Vorgehensweise: Verwenden des My-Namespaces – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: ff00a60d92ec6abbeb257abec76ed2812867f651
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588875"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="a207c-102">Vorgehensweise: Verwenden des My-Namespaces (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a207c-102">How to: Use the My Namespace (C# Programming Guide)</span></span>
<span data-ttu-id="a207c-103">Der <xref:Microsoft.VisualBasic.MyServices>-Namespace (`My` in Visual Basic) bietet einfachen und intuitiven Zugriff auf mehrere .NET Framework-Klassen, mit denen Sie Code schreiben können, der mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagiert.</span><span class="sxs-lookup"><span data-stu-id="a207c-103">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET Framework classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="a207c-104">Auch wenn er ursprünglich für Visual Basic entwickelt wurde, kann der `MyServices`-Namespace auch in C#-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a207c-104">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="a207c-105">Weitere Informationen zum Verwenden des `MyServices`-Namespace in Visual Basic finden Sie unter [Development with My (Entwicklung mit „My“)](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="a207c-105">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="adding-a-reference"></a><span data-ttu-id="a207c-106">Hinzufügen eines Verweises</span><span class="sxs-lookup"><span data-stu-id="a207c-106">Adding a Reference</span></span>  
 <span data-ttu-id="a207c-107">Bevor Sie die `MyServices`-Klassen in Ihrer Projektmappe verwenden, müssen Sie einen Verweis auf die Visual Basic-Bibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a207c-107">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="a207c-108">So fügen Sie einen Verweis auf die Visual Basic-Bibliothek hinzu</span><span class="sxs-lookup"><span data-stu-id="a207c-108">To add a reference to the Visual Basic library</span></span>  
  
1. <span data-ttu-id="a207c-109">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a207c-109">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="a207c-110">Wenn das Dialogfeld **Verweise** geöffnet wird, durchscrollen Sie die Liste, und klicken Sie auf „Microsoft.VisualBasic.dll“.</span><span class="sxs-lookup"><span data-stu-id="a207c-110">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="a207c-111">Sie sollten auch die folgende Zeile im Abschnitt `using` am Anfang Ihres Programms einfügen.</span><span class="sxs-lookup"><span data-stu-id="a207c-111">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a><span data-ttu-id="a207c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a207c-112">Example</span></span>  
 <span data-ttu-id="a207c-113">In diesem Beispiel werden mehrere statische Methoden aufgerufen, die im `MyServices`-Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a207c-113">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="a207c-114">Damit dieser Code kompiliert wird, muss dem Projekt ein Verweis auf „Microsoft.VisualBasic.dll“ hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a207c-114">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 <span data-ttu-id="a207c-115">Nicht alle Klassen des `MyServices`-Namespace können aus einer C#-Anwendung aufgerufen werden: die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>-Klasse ist z.B. nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a207c-115">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="a207c-116">In diesem Fall können stattdessen die statischen Methoden verwendet werden, die Teil von <xref:Microsoft.VisualBasic.FileIO.FileSystem> sind und die außerdem in „VisualBasic.dll“ enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a207c-116">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="a207c-117">So können Sie z.B. eine derartige Methode verwenden, um ein Verzeichnis zu duplizieren:</span><span class="sxs-lookup"><span data-stu-id="a207c-117">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a><span data-ttu-id="a207c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a207c-118">See also</span></span>

- [<span data-ttu-id="a207c-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a207c-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a207c-120">Namespaces</span><span class="sxs-lookup"><span data-stu-id="a207c-120">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="a207c-121">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="a207c-121">Using Namespaces</span></span>](./using-namespaces.md)
