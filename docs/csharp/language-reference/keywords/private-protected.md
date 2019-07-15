---
title: private protected – C#-Referenz
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: c739dd0b5a5457a66c11962ed86bcd2ffbf811ab
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661673"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="3ba44-102">private protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3ba44-102">private protected (C# Reference)</span></span>

<span data-ttu-id="3ba44-103">Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="3ba44-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="3ba44-104">Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="3ba44-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="3ba44-105">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3ba44-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3ba44-106">Der Zugriffsmodifizierer `private protected` ist in C# 7.2 und höher gültig.</span><span class="sxs-lookup"><span data-stu-id="3ba44-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="3ba44-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ba44-107">Example</span></span>

<span data-ttu-id="3ba44-108">Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="3ba44-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="3ba44-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="3ba44-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="3ba44-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="3ba44-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="3ba44-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="3ba44-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="3ba44-112">`BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="3ba44-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="3ba44-113">Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="3ba44-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="3ba44-114">Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.</span><span class="sxs-lookup"><span data-stu-id="3ba44-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="3ba44-115">In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ba44-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="3ba44-116">Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ba44-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="3ba44-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3ba44-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="3ba44-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ba44-118">See also</span></span>

- [<span data-ttu-id="3ba44-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3ba44-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3ba44-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3ba44-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3ba44-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3ba44-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3ba44-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="3ba44-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="3ba44-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="3ba44-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="3ba44-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="3ba44-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="3ba44-125">public</span><span class="sxs-lookup"><span data-stu-id="3ba44-125">public</span></span>](public.md)
- [<span data-ttu-id="3ba44-126">private</span><span class="sxs-lookup"><span data-stu-id="3ba44-126">private</span></span>](private.md)
- [<span data-ttu-id="3ba44-127">internal</span><span class="sxs-lookup"><span data-stu-id="3ba44-127">internal</span></span>](internal.md)
- <span data-ttu-id="3ba44-128">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3ba44-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
