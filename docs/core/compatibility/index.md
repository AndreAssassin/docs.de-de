---
title: Auswerten von Breaking Changes – .NET Core
description: Erfahren Sie mehr darüber, wie .NET Core versucht, die Kompatibilität für Entwickler in allen .NET-Versionen aufrechtzuerhalten.
author: rpetrusha
ms.author: ronpet
ms.date: 06/10/2019
ms.openlocfilehash: c68a19b8b98a98bb9c64f5b9fa60b378935e6e93
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2019
ms.locfileid: "67736556"
---
# <a name="evaluate-breaking-changes-in-net-core"></a><span data-ttu-id="11a4b-103">Auswerten von Breaking Changes in .NET Core</span><span class="sxs-lookup"><span data-stu-id="11a4b-103">Evaluate breaking changes in .NET Core</span></span>

<span data-ttu-id="11a4b-104">Im Laufe seines Bestehens hat .NET versucht, ein hohes Maß an Kompatibilität von Version zu Version und zwischen den verschiedenen Varianten von.NET aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="11a4b-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="11a4b-105">Dies gilt auch für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="11a4b-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="11a4b-106">Obwohl .NET Core als eine von .NET Framework unabhängige neue Technologie betrachtet werden kann, schränken zwei wesentliche Faktoren die Möglichkeit von .NET Core ein, von .NET Framework abzuweichen:</span><span class="sxs-lookup"><span data-stu-id="11a4b-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="11a4b-107">Eine große Anzahl von Entwicklern hat entweder ursprünglich .NET Framework-Anwendungen entwickelt oder entwickelt diese weiterhin.</span><span class="sxs-lookup"><span data-stu-id="11a4b-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="11a4b-108">Sie erwarten ein konsistentes Verhalten in .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="11a4b-109">.NET Standard-Bibliotheksprojekte ermöglichen es Entwicklern, Bibliotheken zu erstellen, die auf gemeinsame APIs ausgerichtet sind, die von .NET Core und.NET Framework gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="11a4b-110">Entwickler erwarten, dass sich eine in einer .NET Core-Anwendung verwendete Bibliothek genauso verhält, wie dieselbe Bibliothek, die in einer .NET Framework-Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11a4b-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="11a4b-111">Neben der Kompatibilität zwischen .NET-Implementierungen erwarten Entwickler ein hohes Maß an Kompatibilität zwischen .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="11a4b-112">Insbesondere sollte Code, der für eine frühere Version von .NET Core geschrieben wurde, problemlos auf einer späteren Version von .NET Core ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="11a4b-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="11a4b-113">Tatsächlich erwarten viele Entwickler, dass die neuen APIs in den neu veröffentlichten Versionen von .NET Core auch mit den Vorabversionen kompatibel sein sollten, in denen diese APIs eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="11a4b-114">Dieser Artikel beschreibt die Kategorien von Kompatibilitätsänderungen (oder Breaking Changes) und die Art und Weise, wie das .NET-Team Änderungen in jeder dieser Kategorien bewertet.</span><span class="sxs-lookup"><span data-stu-id="11a4b-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="11a4b-115">Zu verstehen, wie das .NET-Team mit möglichen Breaking Changes umgeht, ist besonders hilfreich für Entwickler, die Pull Requests im GitHub-Repository [dotnet/corefx](https://github.com/dotnet/corefx) öffnen, das das Verhalten bestehender APIs ändert.</span><span class="sxs-lookup"><span data-stu-id="11a4b-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who are opening pull requests in the [dotnet/corefx](https://github.com/dotnet/corefx) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="11a4b-116">Eine Definition von Kompatibilitätskategorien, wie z.B. Binärkompatibilität und Abwärtskompatibilität, finden Sie unter [Breaking Change-Kategorien](categories.md).</span><span class="sxs-lookup"><span data-stu-id="11a4b-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="11a4b-117">In den folgenden Abschnitten werden die Kategorien der Änderungen an den .NET Core-APIs und deren Auswirkungen auf die Anwendungskompatibilität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11a4b-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="11a4b-118">Das Symbol ✔️ zeigt an, dass eine bestimmte Art von Änderung erlaubt ist, ❌ zeigt an, dass sie nicht erlaubt ist, und ❓ zeigt an, dass eine Änderung möglicherweise zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="11a4b-119">Bei Änderungen in dieser letzten Kategorie muss beurteilt und bewertet werden, wie vorhersehbar, offensichtlich und konsistent das bisherige Verhalten war.</span><span class="sxs-lookup"><span data-stu-id="11a4b-119">Changes in this last category require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="11a4b-120">Bibliotheksentwickler können diese Kriterien nicht nur als Leitfaden für die Bewertung von Änderungen an .NET Core-Bibliotheken verwenden, sondern auch für die Bewertung von Änderungen an ihren Bibliotheken, die auf mehrere .NET-Implementierungen und -Versionen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="11a4b-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="11a4b-121">Änderungen am öffentlichen Vertrag</span><span class="sxs-lookup"><span data-stu-id="11a4b-121">Modifications to the public contract</span></span>

<span data-ttu-id="11a4b-122">Änderungen in dieser Kategorie *modifizieren* die öffentliche Oberfläche eines Typs.</span><span class="sxs-lookup"><span data-stu-id="11a4b-122">Changes in this category *modify* the public surface area of a type.</span></span> <span data-ttu-id="11a4b-123">Die meisten Änderungen in dieser Kategorie sind unzulässig, da sie die *Abwärtskompatibilität* verletzen (die Fähigkeit einer Anwendung, die mit einer früheren Version einer API entwickelt wurde, ohne Neukompilierung auf einer späteren Version ausgeführt zu werden).</span><span class="sxs-lookup"><span data-stu-id="11a4b-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="11a4b-124">Typen</span><span class="sxs-lookup"><span data-stu-id="11a4b-124">Types</span></span>

- <span data-ttu-id="11a4b-125">**✔️ Entfernen einer Schnittstellenimplementierung aus einem Typ, wenn die Schnittstelle bereits durch einen Basistyp implementiert ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="11a4b-126">**❓ Hinzufügen einer neuen Schnittstellenimplementierung zu einem Typ**</span><span class="sxs-lookup"><span data-stu-id="11a4b-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="11a4b-127">Dies ist eine zulässige Änderung, da sie bestehende Clients nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="11a4b-128">Jede Änderung des Typs muss innerhalb der hier definierten Grenzen für zulässige Änderungen erfolgen, damit die neue Implementierung weiterhin zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="11a4b-129">Extreme Vorsicht ist geboten, wenn Schnittstellen hinzugefügt werden, die die Fähigkeit eines Designers oder Serialisierungsmoduls direkt beeinflussen, Code oder Daten zu generieren, die nicht auf unteren Ebenen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="11a4b-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="11a4b-130">Ein Beispiel ist die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="11a4b-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="11a4b-131">**❓ Einführen einer neuen Basisklasse**</span><span class="sxs-lookup"><span data-stu-id="11a4b-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="11a4b-132">Ein Typ kann in eine Hierarchie zwischen zwei bestehenden Typen eingefügt werden, wenn er keinen neuen [abstract](../../csharp/language-reference/keywords/abstract.md)-Member einführt oder die Semantik oder das Verhalten bestehender Typen ändert.</span><span class="sxs-lookup"><span data-stu-id="11a4b-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="11a4b-133">So wurde beispielsweise in .NET Framework 2.0 die Klasse <xref:System.Data.Common.DbConnection> zu einer neuen Basisklasse für <xref:System.Data.SqlClient.SqlConnection>, die zuvor direkt von <xref:System.ComponentModel.Component> abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="11a4b-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="11a4b-134">**✔️ Verschieben eines Typs von einer Assembly zu einer anderen**</span><span class="sxs-lookup"><span data-stu-id="11a4b-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="11a4b-135">Beachten Sie, dass die *alte* Assembly mit dem <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> markiert werden muss, das auf die neue Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="11a4b-136">**✔️ Ändern des Typs [struct](../../csharp/language-reference/keywords/struct.md) in einen Typ`readonly struct`**</span><span class="sxs-lookup"><span data-stu-id="11a4b-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="11a4b-137">Beachten Sie, dass ein `readonly struct`-Typ nicht in einen `struct`-Typ geändert werden darf.</span><span class="sxs-lookup"><span data-stu-id="11a4b-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>
  
- <span data-ttu-id="11a4b-138">**✔️ Hinzufügen des Schlüsselworts [sealed](../../csharp/language-reference/keywords/sealed.md) oder [abstract](../../csharp/language-reference/keywords/abstract.md) zu einem Typ, wenn keine *zugänglichen* (öffentlichen oder geschützten) Konstruktoren vorhanden sind**</span><span class="sxs-lookup"><span data-stu-id="11a4b-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="11a4b-139">**✔️ Erweitern der Sichtbarkeit eines Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="11a4b-140">**❌ Ändern des Namespace oder des Namens eines Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="11a4b-141">**❌ Umbenennen oder Entfernen eines öffentlichen Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="11a4b-142">Dies unterbricht sämtlichen Code, der den umbenannten oder entfernten Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="11a4b-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="11a4b-143">**❌ Ändern des einer Enumeration zugrunde liegenden Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="11a4b-144">Dies ist ein Breaking Change der Kompilierzeit und des Verhaltens und darüber hinaus ein binärer Breaking Change, durch die die Analyse der Attributargumente unterbunden werden könnte.</span><span class="sxs-lookup"><span data-stu-id="11a4b-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="11a4b-145">**❌ Versiegeln eines bisher nicht versiegelten Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="11a4b-146">**❌ Hinzufügen einer Schnittstelle zur Menge der Basistypen einer Schnittstelle**</span><span class="sxs-lookup"><span data-stu-id="11a4b-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="11a4b-147">Wenn ein Schnittstelle eine Schnittstelle implementiert, die sie zuvor nicht implementiert hat, werden alle Typen, die die ursprüngliche Version der Schnittstelle implementiert haben, beschädigt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="11a4b-148">**❓ Entfernen eine Klasse aus der Menge von Basisklassen oder einer Schnittstelle aus der Menge der implementierten Schnittstellen**</span><span class="sxs-lookup"><span data-stu-id="11a4b-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="11a4b-149">Es gibt eine Ausnahme von der Regel zur Entfernung von Schnittstellen: Sie können die Implementierung einer Schnittstelle hinzufügen, die aus der entfernten Schnittstelle abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="11a4b-150">Sie können beispielsweise <xref:System.IDisposable> entfernen, wenn der Typ oder die Schnittstelle nun <xref:System.ComponentModel.IComponent> implementiert, wodurch <xref:System.IDisposable> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="11a4b-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="11a4b-151">**❌ Ändern des Typs `readonly struct` in einen Typ [struct](../../csharp/language-reference/keywords/struct.md)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="11a4b-152">Beachten Sie, dass ein `struct`-Typ nicht in einen `readonly struct`-Typ geändert werden darf.</span><span class="sxs-lookup"><span data-stu-id="11a4b-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="11a4b-153">**✔️ Ändern des Typs [struct](../../csharp/language-reference/keywords/struct.md) in einen Typ`ref struct` und umgekehrt**</span><span class="sxs-lookup"><span data-stu-id="11a4b-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="11a4b-154">**✔️ Reduzieren der Sichtbarkeit eines Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="11a4b-155">Die Sichtbarkeit eines Typs darf jedoch erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="11a4b-156">Member</span><span class="sxs-lookup"><span data-stu-id="11a4b-156">Members</span></span>

- <span data-ttu-id="11a4b-157">**✔️ Erweitern der Sichtbarkeit eines nicht [virtuellen](../../csharp/language-reference/keywords/sealed.md) Members**</span><span class="sxs-lookup"><span data-stu-id="11a4b-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="11a4b-158">**✔️ Hinzufügen eines abstrakten Members zu einem öffentlichen Typ, der keine *zugänglichen* (öffentlichen oder geschützten) Konstruktoren hat, oder wenn der Typ [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="11a4b-159">Das Hinzufügen eines abstrakten-Members zu einem Typ mit zugänglichen (öffentlichen oder geschützten) Konstruktoren, der nicht `sealed` ist, ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="11a4b-160">**✔️ Einschränken der Sichtbarkeit eines [geschützten](../../csharp/language-reference/keywords/protected.md) Members, wenn der Typ keine zugänglichen (öffentlichen oder geschützten) Konstruktoren hat, oder wenn der Typ [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="11a4b-161">**✔️ Verschieben eines Members in eine Klasse, die in der Hierarchie höher liegt als der Typ, aus dem es entfernt wurde**</span><span class="sxs-lookup"><span data-stu-id="11a4b-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="11a4b-162">**✔️ Hinzufügen oder Entfernen einer Außerkraftsetzung**</span><span class="sxs-lookup"><span data-stu-id="11a4b-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="11a4b-163">Beachten Sie, dass die Einführung einer Außerkraftsetzung dazu führen kann, dass vorherige Consumer beim Aufrufen von [base](../../csharp/language-reference/keywords/base.md) die Außerkraftsetzung überspringen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="11a4b-164">**✔️ Hinzufügen eines Konstruktors zu einer Klasse, zusammen mit einem Standardkonstruktor (ohne Parameter), wenn die Klasse zuvor keine Konstruktoren hatte**</span><span class="sxs-lookup"><span data-stu-id="11a4b-164">**✔️ Adding a constructor to a class, along with a default (parameterless) constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="11a4b-165">Das Hinzufügen eines Konstruktors zu einer Klasse, die bisher keine Konstruktoren hatte, *ohne* den parameterlosen Konstruktor hinzuzufügen, ist jedoch nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-165">However, adding a constructor to a class that previously had no constructors *without* adding the parameterless constructor is not allowed.</span></span>

- <span data-ttu-id="11a4b-166">**✔️ Ändern eines Members von [abstrakt](../../csharp/language-reference/keywords/abstract.md) zu [virtuell](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="11a4b-167">**✔️ Wechseln von einem `ref readonly`- zu einem `ref`-Rückgabewert (mit Ausnahme von virtuellen Methoden oder Schnittstellen)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="11a4b-168">**✔️ Entfernen von [readonly](../../csharp/language-reference/keywords/readonly.md) aus einem Feld, es sei denn, der statische Typ des Feldes ist ein veränderlicher Werttyp**</span><span class="sxs-lookup"><span data-stu-id="11a4b-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="11a4b-169">**✔️ Aufrufen eines bisher noch nicht definierten neuen Ereignisses**</span><span class="sxs-lookup"><span data-stu-id="11a4b-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="11a4b-170">**❓ Hinzufügen eines neuen Instanzenfelds zu einem Typ**</span><span class="sxs-lookup"><span data-stu-id="11a4b-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="11a4b-171">Diese Änderung wirkt sich auf die Serialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="11a4b-171">This change impacts serialization.</span></span>

- <span data-ttu-id="11a4b-172">**❌ Umbenennen oder Entfernen eines öffentlichen Members oder Parameters**</span><span class="sxs-lookup"><span data-stu-id="11a4b-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="11a4b-173">Dies unterbricht sämtlichen Code, der den umbenannten oder entfernten Member oder Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="11a4b-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="11a4b-174">Beachten Sie, dass dazu auch das Entfernen oder Umbenennen eines Getters oder Setters aus einer Eigenschaft sowie das Umbenennen oder Entfernen von Enumerationsmembern gehört.</span><span class="sxs-lookup"><span data-stu-id="11a4b-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="11a4b-175">**❌ Hinzufügen eines Members zu einer Schnittstelle**</span><span class="sxs-lookup"><span data-stu-id="11a4b-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="11a4b-176">**❌ Ändern des Werts eine öffentlichen Konstanten oder des Enumerationsmember**</span><span class="sxs-lookup"><span data-stu-id="11a4b-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="11a4b-177">**❌ Ändern des Typs einer Eigenschaft, eines Felds, Parameters oder Rückgabewerts**</span><span class="sxs-lookup"><span data-stu-id="11a4b-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="11a4b-178">**❌ Hinzufügen, Entfernen oder Ändern der Reihenfolge von Parametern**</span><span class="sxs-lookup"><span data-stu-id="11a4b-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="11a4b-179">**❌ Hinzufügen oder Entfernen des Schlüsselworts [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) oder [ref](../../csharp/language-reference/keywords/ref.md) zu oder aus einem Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="11a4b-180">**❌ Umbenennen eines Parameters (einschließlich der Änderung der Groß-/Kleinbuchschreibung)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="11a4b-181">Dies gilt aus zwei Gründen als Unterbrechung:</span><span class="sxs-lookup"><span data-stu-id="11a4b-181">This is considered breaking for two reasons:</span></span>
  
  - <span data-ttu-id="11a4b-182">Damit werden spät gebundene Szenarien wie die späte Bindungsfunktion in Visual Basic und [dynamic](../../csharp/language-reference/keywords/dynamic.md) in C# unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/keywords/dynamic.md) in C#.</span></span>
  
  - <span data-ttu-id="11a4b-183">Es unterbricht die [Quellenkompatibilität](categories.md#source-compatibility), wenn Entwickler [benannte Argumente](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments) verwenden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="11a4b-184">**❌ Wechseln von einem `ref`- zu einem `ref readonly`-Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="11a4b-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="11a4b-185">**❌️ Wechseln von einem `ref readonly`- zu einem `ref`-Rückgabewert bei einer virtuellen Methoden oder Schnittstelle**</span><span class="sxs-lookup"><span data-stu-id="11a4b-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="11a4b-186">**❌ Hinzufügen oder Entfernen von [abstract](../../csharp/language-reference/keywords/abstract.md) zu oder aus einem Member**</span><span class="sxs-lookup"><span data-stu-id="11a4b-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="11a4b-187">**❌ Entfernen des Schlüsselworts [virtual](../../csharp/language-reference/keywords/virtual.md) aus einem Member**</span><span class="sxs-lookup"><span data-stu-id="11a4b-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="11a4b-188">Obwohl dies oft keinen Breaking Change darstellt, da der C#-Compiler dazu tendiert, zum Aufrufen nicht virtueller Methoden Intermediate Language (IL)-Anweisungen [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) auszugeben (`callvirt` führt eine Prüfung auf NULL durch, was bei einem normalen Aufruf nicht der Fall ist), ist dieses Verhalten aus verschiedenen Gründe nicht unveränderlich:</span><span class="sxs-lookup"><span data-stu-id="11a4b-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="11a4b-189">C# ist nicht die einzige Sprache, auf die .NET ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-189">C# is not the only language that .NET targets.</span></span>
  
  - <span data-ttu-id="11a4b-190">Der C#-Compiler versucht zunehmend, `callvirt` für einen normalen Aufruf zu optimieren, wenn die Zielmethode nicht virtuell und wahrscheinlich nicht Null ist (z.B. eine Methode, auf die über den [NULL-bedingten Operator „?“](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-) zugegriffen wird).</span><span class="sxs-lookup"><span data-stu-id="11a4b-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>
  
  <span data-ttu-id="11a4b-191">Aus einer Methode eine virtuelle Methode zu machen bedeutet, dass der Consumercode sie oft nicht virtuell aufruft.</span><span class="sxs-lookup"><span data-stu-id="11a4b-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="11a4b-192">**❌ Hinzufügen des Schlüsselworts [virtual](../../csharp/language-reference/keywords/virtual.md) zu einem Member**</span><span class="sxs-lookup"><span data-stu-id="11a4b-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="11a4b-193">**❌ Umwandeln eines virtuellen Members in einen abstrakten Member**</span><span class="sxs-lookup"><span data-stu-id="11a4b-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="11a4b-194">Ein [virtueller Member](../../csharp/language-reference/keywords/virtual.md) stellt eine Methodenimplementierung bereit, die von einer abgeleiteten Klasse außer Kraft gesetzt werden *kann*.</span><span class="sxs-lookup"><span data-stu-id="11a4b-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="11a4b-195">Ein [abstrakter Member](../../csharp/language-reference/keywords/abstract.md) stellt keine Implementierung bereit und *muss* außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="11a4b-196">**❌ Hinzufügen eines abstrakten-Members zu einem öffentlichen Typ mit zugänglichen (öffentlichen oder geschützten) Konstruktoren, der nicht [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="11a4b-197">**❌ Hinzufügen oder Entfernen des Schlüsselworts [static](../../csharp/language-reference/keywords/static.md) zu oder aus einem Member**</span><span class="sxs-lookup"><span data-stu-id="11a4b-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="11a4b-198">**❌ Hinzufügen einer Überladung, die eine vorhandene Überladung ausschließt und ein anderes Verhalten definiert**</span><span class="sxs-lookup"><span data-stu-id="11a4b-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="11a4b-199">Dies unterbricht vorhandene Clients, die an die vorherige Überladung gebunden waren.</span><span class="sxs-lookup"><span data-stu-id="11a4b-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="11a4b-200">Wenn eine Klasse beispielsweise eine einzelne Version einer Methode hat, die <xref:System.UInt32> akzeptiert, wird ein vorhandener Consumer erfolgreich an diese Überladung gebunden, wenn ein <xref:System.Int32>-Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="11a4b-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="11a4b-201">Wenn Sie jedoch eine Überladung hinzufügen, die <xref:System.Int32> akzeptiert, bindet sich der Compiler beim Neukompilieren oder beim Verwenden der späten Bindung an die neue Überladung.</span><span class="sxs-lookup"><span data-stu-id="11a4b-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="11a4b-202">Wenn dies ein anderes Verhalten zur Folge hat, ist dies ein Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="11a4b-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="11a4b-203">**❌ Hinzufügen eines Konstruktors zu einer Klasse, die bisher keine Konstruktoren hatte, ohne den parameterlosen Konstruktor hinzuzufügen**</span><span class="sxs-lookup"><span data-stu-id="11a4b-203">**❌ Adding a constructor to a class that previously had no constructor without adding the parameterless constructor**</span></span>

- <span data-ttu-id="11a4b-204">**❌️ Hinzufügen von [readonly](../../csharp/language-reference/keywords/readonly.md) zu einem Feld**</span><span class="sxs-lookup"><span data-stu-id="11a4b-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="11a4b-205">**❌ Reduzieren der Sichtbarkeit eines Members**</span><span class="sxs-lookup"><span data-stu-id="11a4b-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="11a4b-206">Dazu gehört das Reduzieren der Sichtbarkeit eines [geschützten](../../csharp/language-reference/keywords/protected.md) Members, wenn *zugängliche* (öffentliche oder geschützte) Konstruktoren vorhanden sind und der Typ *nicht* [versiegelt](../../csharp/language-reference/keywords/sealed.md) ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="11a4b-207">Wenn dies nicht der Fall ist, ist das Reduzieren der Sichtbarkeit eines geschützten Members zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="11a4b-208">Beachten Sie, dass die Sichtbarkeit eines Members erhöht werden darf.</span><span class="sxs-lookup"><span data-stu-id="11a4b-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="11a4b-209">**❌ Ändern des Typs eines Members**</span><span class="sxs-lookup"><span data-stu-id="11a4b-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="11a4b-210">Der Rückgabewert einer Methode oder der Typ einer Eigenschaft oder eines Feldes kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="11a4b-211">So kann beispielsweise die Signatur einer Methode, die ein <xref:System.Object> zurückgibt, nicht geändert werden, um ein <xref:System.String> zurückzugeben, oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="11a4b-212">**❌ Hinzufügen eines Felds zu einer Struktur, die bisher keinen Status hatte**</span><span class="sxs-lookup"><span data-stu-id="11a4b-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="11a4b-213">Definitive Zuweisungsregeln erlauben die Verwendung von nicht initialisierten Variablen, sofern der Variablentyp eine zustandslose Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="11a4b-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="11a4b-214">Wenn die Struktur zustandsbehaftet gemacht wird, könnte der Code nicht initialisierte Daten erhalten.</span><span class="sxs-lookup"><span data-stu-id="11a4b-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="11a4b-215">Dies ist möglicherweise sowohl ein Quell-Breaking Change als auch ein binärer Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="11a4b-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="11a4b-216">**❌ Auslösen eines vorhandenen Ereignisses, das bisher noch nicht ausgelöst wurde**</span><span class="sxs-lookup"><span data-stu-id="11a4b-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="11a4b-217">Verhaltensänderungen</span><span class="sxs-lookup"><span data-stu-id="11a4b-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="11a4b-218">Assemblys</span><span class="sxs-lookup"><span data-stu-id="11a4b-218">Assemblies</span></span>

- <span data-ttu-id="11a4b-219">**✔️ Übertragbarmachen einer Assembly, wenn dieselben Plattformen weiterhin unterstützt werden**</span><span class="sxs-lookup"><span data-stu-id="11a4b-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="11a4b-220">**❌ Ändern des Namens einer Assembly**</span><span class="sxs-lookup"><span data-stu-id="11a4b-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="11a4b-221">**❌ Ändern des öffentlichen Schlüssels einer Assembly**</span><span class="sxs-lookup"><span data-stu-id="11a4b-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="11a4b-222">Eigenschaften, Felder, Parameter und Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="11a4b-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="11a4b-223">**✔️ Ändern des Wertes einer Eigenschaft, eines Feldes, eines Rückgabewertes oder eines [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameters in einen stärker abgeleiteten Typ**</span><span class="sxs-lookup"><span data-stu-id="11a4b-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="11a4b-224">Beispielsweise kann eine Methode, die einen Typ von <xref:System.Object> zurückgibt, eine <xref:System.String>-Instanz zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="11a4b-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="11a4b-225">(Allerdings kann nicht die Signatur der Methode nicht geändert werden.)</span><span class="sxs-lookup"><span data-stu-id="11a4b-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="11a4b-226">**✔️ Erhöhung des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter, wenn der Member nicht [virtuell](../../csharp/language-reference/keywords/virtual.md) ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="11a4b-227">Beachten Sie, dass der Bereich der Werte, die an die Methode übergeben werden können oder vom Member zurückgegeben werden, erweitert werden kann, der Parameter- oder der Membertyp jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="11a4b-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="11a4b-228">Beispielsweise können die an eine Methode übergebenen Werte von 0-124 auf 0-255 erweitert werden, der Parametertyp kann jedoch nicht von <xref:System.Byte> in <xref:System.Int32> geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="11a4b-229">**❌ Erweitern des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter, wenn der Member [virtuell](../../csharp/language-reference/keywords/virtual.md) ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="11a4b-230">Diese Änderung unterbricht bestehende, außer Kraft gesetzte Member, die für den erweiterten Wertebereich dann nicht korrekt funktionieren.</span><span class="sxs-lookup"><span data-stu-id="11a4b-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="11a4b-231">**❌ Verkleinern des Bereichs der zulässigen Werte für eine Eigenschaft oder einen Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="11a4b-232">**❌ Erweitern des Bereichs der zurückgegebenen Werte für eine Eigenschaft, ein Feld, einen Rückgabewert oder den [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="11a4b-233">**❌ Ändern der zurückgegebenen Werte für eine Eigenschaft, ein Feld, einen Rückgabewert einer Methode oder den [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="11a4b-234">**❌ Ändern des Standardwerts einer Eigenschaft, eines Felds oder eines Parameters**</span><span class="sxs-lookup"><span data-stu-id="11a4b-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="11a4b-235">**❌ Ändern der Genauigkeit eines numerischen Rückgabewerts**</span><span class="sxs-lookup"><span data-stu-id="11a4b-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="11a4b-236">**❓ Eine Änderung im Analysieren von Eingaben und das Auslösen neuer Ausnahmen (auch wenn das Analyseverhalten nicht in der Dokumentation angegeben ist)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="11a4b-237">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="11a4b-237">Exceptions</span></span>

- <span data-ttu-id="11a4b-238">**✔️ Auslösen einer Ausnahme, die stärker abgeleitet ist als eine vorhandene**</span><span class="sxs-lookup"><span data-stu-id="11a4b-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="11a4b-239">Da die neue Ausnahme eine Unterklasse einer vorhandenen Ausnahme ist, wird der bisherige Code zur Ausnahmebehandlung die Ausnahme weiterhin behandeln.</span><span class="sxs-lookup"><span data-stu-id="11a4b-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="11a4b-240">In .NET Framework 4 wurden bei der Kulturerstellung und bei Abrufmethoden eine <xref:System.Globalization.CultureNotFoundException> anstelle einer <xref:System.ArgumentException> ausgelöst, wenn die Kultur nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="11a4b-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="11a4b-241">Da sich <xref:System.Globalization.CultureNotFoundException> aus <xref:System.ArgumentException> ableitet, ist dies eine zulässige Änderung.</span><span class="sxs-lookup"><span data-stu-id="11a4b-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="11a4b-242">**✔️ Auslösen einer spezifischeren Ausnahme als <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span><span class="sxs-lookup"><span data-stu-id="11a4b-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="11a4b-243">**✔️ Auslösen einer Ausnahme, die als nicht behebbar gilt**</span><span class="sxs-lookup"><span data-stu-id="11a4b-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="11a4b-244">Nicht behebbare Ausnahmen sollten nicht abgefangen werden, sondern von einem übergeordneten Catch-All-Handler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="11a4b-245">Daher wird nicht erwartet, dass Benutzer über Code verfügen, der diese expliziten Ausnahmen abfängt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="11a4b-246">Nicht behebbare Ausnahmen sind:</span><span class="sxs-lookup"><span data-stu-id="11a4b-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="11a4b-247">**✔️ Auslösen einer neuen Ausnahme in einem neuen Codepfad**</span><span class="sxs-lookup"><span data-stu-id="11a4b-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="11a4b-248">Die Ausnahme darf nur für einen neuen Codepfad gelten, der mit neuen Parameterwerten oder einen neuen Zustand ausgeführt wird, und der nicht mit vorhandenem Code ausgeführt werden kann, der auf die vorherige Version abzielt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="11a4b-249">**✔️ Entfernen eine Ausnahme aus, um ein stabileres Verhalten oder neue Szenarien zu ermöglichen**</span><span class="sxs-lookup"><span data-stu-id="11a4b-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="11a4b-250">So kann beispielsweise eine `Divide`-Methode, die bisher nur positive Werte behandelt und andernfalls ein <xref:System.ArgumentOutOfRangeException> ausgelöst hat, so geändert werden, dass sowohl negative als auch positive Werte unterstützt werden, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="11a4b-251">**✔️ Ändern des Textes einer Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="11a4b-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="11a4b-252">Entwickler sollten sich nicht auf den Text von Fehlermeldungen verlassen, die sich auch aufgrund der Kultur des Benutzers ändern.</span><span class="sxs-lookup"><span data-stu-id="11a4b-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="11a4b-253">**❌ Auslösen einer Ausnahme in allen anderen Fällen, die oben nicht aufgeführt sind**</span><span class="sxs-lookup"><span data-stu-id="11a4b-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="11a4b-254">**❌ Entfernen einer Ausnahme in allen anderen Fällen, die oben nicht aufgeführt sind**</span><span class="sxs-lookup"><span data-stu-id="11a4b-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="11a4b-255">Attribute</span><span class="sxs-lookup"><span data-stu-id="11a4b-255">Attributes</span></span>

- <span data-ttu-id="11a4b-256">**✔️ Ändern des Werts eines Attributs, das *nicht* überwachbar ist**</span><span class="sxs-lookup"><span data-stu-id="11a4b-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="11a4b-257">**❌ Ändern des Werts eines Attributs, das überwachbar *ist***</span><span class="sxs-lookup"><span data-stu-id="11a4b-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="11a4b-258">**❓ Entfernen eines Attributs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="11a4b-259">In den meisten Fällen ist das Entfernen eines Attributs (wie <xref:System.NonSerializedAttribute>) ein Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="11a4b-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="11a4b-260">Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="11a4b-260">Platform support</span></span>

- <span data-ttu-id="11a4b-261">**✔️ Unterstützen eines Vorgangs auf einer Plattform, der bisher nicht unterstützt wurde**</span><span class="sxs-lookup"><span data-stu-id="11a4b-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="11a4b-262">**❌ Kein Unterstützung oder das Erfordern eines bestimmten Service Packs für einen Vorgang, der zuvor auf einer Plattform unterstützt wurde**</span><span class="sxs-lookup"><span data-stu-id="11a4b-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="11a4b-263">Änderungen an der internen Implementierung</span><span class="sxs-lookup"><span data-stu-id="11a4b-263">Internal implementation changes</span></span>

- <span data-ttu-id="11a4b-264">**❓ Ändern der Oberfläche eines internen Typs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="11a4b-265">Derartige Änderungen sind im Allgemeinen zulässig, auch wenn sie die private Reflektion unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="11a4b-266">In einigen Fällen, in denen beliebte Bibliotheken von Drittanbietern oder eine große Anzahl von Entwicklern von den internen APIs abhängen, sind solche Änderungen möglicherweise nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="11a4b-267">**❓Ändern der internen Implementierung eines Members**</span><span class="sxs-lookup"><span data-stu-id="11a4b-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="11a4b-268">Diese Änderungen sind im Allgemeinen zulässig, auch wenn sie die private Reflektion unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="11a4b-269">In einigen Fällen, in denen der Kundencode häufig von privater Reflexion abhängt, oder in denen die Änderung unbeabsichtigte Nebenwirkungen mit sich bringt, sind diese Änderungen möglicherweise nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="11a4b-270">**✔️ Verbessern der Leistung eines Vorgangs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="11a4b-271">Die Möglichkeit, die Leistung eines Vorgangs zu ändern, ist unerlässlich, aber solche Änderungen können Code unterbrechen, der von der aktuellen Geschwindigkeit eines Vorgangs abhängt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="11a4b-272">Dies gilt insbesondere für Code, der vom Zeitpunkt des asynchronen Vorgangs abhängt.</span><span class="sxs-lookup"><span data-stu-id="11a4b-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="11a4b-273">Beachten Sie, dass die Leistungsänderung keinen Einfluss auf das andere Verhalten der betreffenden API haben sollte; andernfalls ist diese Änderung ein Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="11a4b-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="11a4b-274">**✔️ Indirektes (und häufig negatives) Ändern der Leistung eines Vorgangs**</span><span class="sxs-lookup"><span data-stu-id="11a4b-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="11a4b-275">Wenn die betreffende Änderung aus einem sonstigen Grund nicht als Breaking Change eingestuft wird, ist dies zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="11a4b-276">Häufig müssen Maßnahmen ergriffen werden, die zusätzliche Vorgänge beinhalten können oder neue Funktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11a4b-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="11a4b-277">Dies hat fast immer Auswirkungen auf die Leistung, kann aber unerlässlich sein, damit die betreffende API wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="11a4b-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="11a4b-278">**❌ Ändern einer synchronen API in eine asynchrone API (und umgekehrt)**</span><span class="sxs-lookup"><span data-stu-id="11a4b-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="11a4b-279">Änderungen am Code</span><span class="sxs-lookup"><span data-stu-id="11a4b-279">Code changes</span></span>

- <span data-ttu-id="11a4b-280">**✔️ Hinzufügen von [params](../../csharp/language-reference/keywords/params.md) zu einem Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="11a4b-281">**✔️ Ändern einer [Struktur](../../csharp/language-reference/keywords/struct.md) in eine [Klasse](../../csharp/language-reference/keywords/class.md) und umgekehrt**</span><span class="sxs-lookup"><span data-stu-id="11a4b-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="11a4b-282">**❌ Hinzufügen des Schlüsselworts [checked](../../csharp/language-reference/keywords/virtual.md) zu einem Codeblock**</span><span class="sxs-lookup"><span data-stu-id="11a4b-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="11a4b-283">Diese Änderung kann dazu führen, dass Code, der zuvor so ausgeführt wurde, eine <xref:System.OverflowException> ausgelöst. Dies ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11a4b-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="11a4b-284">**❌ Entfernen von [params](../../csharp/language-reference/keywords/params.md) aus einem Parameter**</span><span class="sxs-lookup"><span data-stu-id="11a4b-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="11a4b-285">**❌ Ändern der Reihenfolge, in der Ereignisse ausgelöst werden**</span><span class="sxs-lookup"><span data-stu-id="11a4b-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="11a4b-286">Entwickler können vernünftigerweise erwarten, dass Ereignisse in der gleichen Reihenfolge ausgelöst werden, und Entwicklercode hängt häufig von der Reihenfolge ab, in der Ereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="11a4b-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="11a4b-287">**❌ Entfernen das Auftretens eines Ereignisses für eine bestimmte Aktion**</span><span class="sxs-lookup"><span data-stu-id="11a4b-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="11a4b-288">**❌ Ändern, wie oft bestimmte Ereignisse aufgerufen werden**</span><span class="sxs-lookup"><span data-stu-id="11a4b-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="11a4b-289">**❌ Hinzufügen des <xref:System.FlagsAttribute> zu einem Enumerationstyp**</span><span class="sxs-lookup"><span data-stu-id="11a4b-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
