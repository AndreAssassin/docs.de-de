---
title: Statische Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 87a7b16d3e096f6a5bf05475ccc7c43862324ae3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583356"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="8cfb1-102">Statische Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8cfb1-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="8cfb1-103">Ein statischer Konstruktor wird verwendet, um [static](../../../csharp/language-reference/keywords/static.md)-Daten zu initialisieren oder um eine bestimmte Aktion auszuführen, die nur einmal ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="8cfb1-104">Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="8cfb1-105">Statische Konstruktoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8cfb1-105">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="8cfb1-106">Ein statischer Konstruktor kann nicht über Zugriffsmodifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
- <span data-ttu-id="8cfb1-107">Ein statischer Konstruktor wird automatisch zum Initialisieren von [class](../../../csharp/language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erzeugt wird oder auf irgendwelche statischen Member verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
- <span data-ttu-id="8cfb1-108">Ein statischer Konstruktor kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-108">A static constructor cannot be called directly.</span></span>  
  
- <span data-ttu-id="8cfb1-109">Der Benutzer hat keine Kontrolle, wenn der statische Konstruktor im Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
- <span data-ttu-id="8cfb1-110">Eine typische Verwendung statischer Konstruktoren besteht darin, wenn die Klasse eine Protokolldatei verwendet und der Konstruktor verwendet wird, um Einträge in dieser Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
- <span data-ttu-id="8cfb1-111">Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`-Methode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
- <span data-ttu-id="8cfb1-112">Wenn ein statischer Konstruktor eine Ausnahme auslöst, wird die Laufzeit ihn kein zweites Mal aufrufen, und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cfb1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cfb1-113">Example</span></span>  
 <span data-ttu-id="8cfb1-114">In diesem Beispiel verfügt die Klasse `Bus` über einen statischen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="8cfb1-115">Wenn die erste Instanz von `Bus` erstellt wird (`bus1`), wird der statische Konstruktor zur Initialisierung der Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="8cfb1-116">Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden, und dass er vor dem Ausführen des Instanzkonstruktors ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="8cfb1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cfb1-117">See also</span></span>

- [<span data-ttu-id="8cfb1-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8cfb1-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8cfb1-119">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="8cfb1-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="8cfb1-120">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="8cfb1-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="8cfb1-121">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="8cfb1-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="8cfb1-122">Finalizer</span><span class="sxs-lookup"><span data-stu-id="8cfb1-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
