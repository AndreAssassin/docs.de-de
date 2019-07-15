---
title: protected internal – C#-Referenz
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ddfefa2a0bb145aa49a60f06a40725d2706cecb5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661653"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="c8ad5-102">protected internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c8ad5-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="c8ad5-103">Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c8ad5-104">Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="c8ad5-105">Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c8ad5-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="c8ad5-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8ad5-106">Example</span></span>

<span data-ttu-id="c8ad5-107">Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="c8ad5-108">Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="c8ad5-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="c8ad5-109">For example, consider the following code segment:</span></span>

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="c8ad5-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="c8ad5-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="c8ad5-112">`BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="c8ad5-113">In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="c8ad5-114">Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c8ad5-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8ad5-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c8ad5-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c8ad5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8ad5-116">See also</span></span>

- [<span data-ttu-id="c8ad5-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c8ad5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8ad5-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c8ad5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8ad5-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c8ad5-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c8ad5-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="c8ad5-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c8ad5-121">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="c8ad5-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c8ad5-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="c8ad5-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="c8ad5-123">public</span><span class="sxs-lookup"><span data-stu-id="c8ad5-123">public</span></span>](public.md)
- [<span data-ttu-id="c8ad5-124">private</span><span class="sxs-lookup"><span data-stu-id="c8ad5-124">private</span></span>](private.md)
- [<span data-ttu-id="c8ad5-125">internal</span><span class="sxs-lookup"><span data-stu-id="c8ad5-125">internal</span></span>](internal.md)
- <span data-ttu-id="c8ad5-126">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c8ad5-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
