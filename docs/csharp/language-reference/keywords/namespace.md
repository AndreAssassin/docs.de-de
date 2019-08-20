---
title: namespace-Schlüsselwort – C#-Programmierreferenz
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 8cc1d1461a33ab94f8ae399d6ff40f26eaf7f74a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039449"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="3cc77-102">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3cc77-102">namespace (C# Reference)</span></span>

<span data-ttu-id="3cc77-103">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="3cc77-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="3cc77-104">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3cc77-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="3cc77-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3cc77-105">Remarks</span></span>

<span data-ttu-id="3cc77-106">Innerhalb eines Namespace können Sie 0 (null) oder mehr der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="3cc77-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="3cc77-107">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="3cc77-107">another namespace</span></span>

- [<span data-ttu-id="3cc77-108">class</span><span class="sxs-lookup"><span data-stu-id="3cc77-108">class</span></span>](class.md)

- [<span data-ttu-id="3cc77-109">interface</span><span class="sxs-lookup"><span data-stu-id="3cc77-109">interface</span></span>](interface.md)

- [<span data-ttu-id="3cc77-110">struct</span><span class="sxs-lookup"><span data-stu-id="3cc77-110">struct</span></span>](struct.md)

- [<span data-ttu-id="3cc77-111">enum</span><span class="sxs-lookup"><span data-stu-id="3cc77-111">enum</span></span>](enum.md)

- [<span data-ttu-id="3cc77-112">delegate</span><span class="sxs-lookup"><span data-stu-id="3cc77-112">delegate</span></span>](delegate.md)

<span data-ttu-id="3cc77-113">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="3cc77-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="3cc77-114">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3cc77-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="3cc77-115">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3cc77-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="3cc77-116">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3cc77-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="3cc77-117">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="3cc77-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="3cc77-118">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3cc77-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="3cc77-119">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="3cc77-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="3cc77-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cc77-120">Example</span></span>

<span data-ttu-id="3cc77-121">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3cc77-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="3cc77-122">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3cc77-122">C# language specification</span></span>

<span data-ttu-id="3cc77-123">Weitere Informationen finden Sie im Abschnitt [Namespaces](~/_csharplang/spec/namespaces.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3cc77-123">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cc77-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cc77-124">See also</span></span>

- [<span data-ttu-id="3cc77-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3cc77-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3cc77-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3cc77-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3cc77-127">using</span><span class="sxs-lookup"><span data-stu-id="3cc77-127">using</span></span>](using-directive.md)
- [<span data-ttu-id="3cc77-128">using static</span><span class="sxs-lookup"><span data-stu-id="3cc77-128">using static</span></span>](using-static.md)
- [<span data-ttu-id="3cc77-129">Namespacealias-Qualifizierer `::`</span><span class="sxs-lookup"><span data-stu-id="3cc77-129">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="3cc77-130">Namespaces</span><span class="sxs-lookup"><span data-stu-id="3cc77-130">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
