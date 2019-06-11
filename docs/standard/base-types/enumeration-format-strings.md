---
title: Enumerations-Formatzeichenfolgen – .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2e5dbe0d02bcec8974a1e52c0dce107d3bf46b
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052854"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="5d9e1-102">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5d9e1-102">Enumeration format strings</span></span>

<span data-ttu-id="5d9e1-103">Sie können die <xref:System.Enum.ToString%2A?displayProperty=nameWithType>-Methode verwenden, um ein neues Zeichenfolgenobjekt zu erstellen, das den numerischen, den Hexadezimal- oder den Zeichenfolgenwert eines Enumerationsmembers darstellt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="5d9e1-104">Diese Methode akzeptiert eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, der zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="5d9e1-105">In den folgenden Abschnitten werden die Enumerationsformatzeichenfolgen sowie die Werte aufgeführt, die diese zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-105">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="5d9e1-106">Bei diesen Formatbezeichnern wird die Groß- und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-106">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="5d9e1-107">G oder g</span><span class="sxs-lookup"><span data-stu-id="5d9e1-107">G or g</span></span>

<span data-ttu-id="5d9e1-108">Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an, zeigt andernfalls den ganzzahligen Wert der aktuellen Instanz an.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-108">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="5d9e1-109">Wenn die Enumeration mit festgelegtem **Flags**-Attribut definiert ist, werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-109">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="5d9e1-110">Wenn das **Flags**-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-110">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="5d9e1-111">Das folgende Beispiel veranschaulicht den Formatbezeichner „G“.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-111">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="5d9e1-112">F oder f</span><span class="sxs-lookup"><span data-stu-id="5d9e1-112">F or f</span></span>

<span data-ttu-id="5d9e1-113">Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-113">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="5d9e1-114">Wenn der Wert vollständig als Summe der Einträge in der Enumeration angezeigt werden kann (selbst wenn das **Flags**-Attribut nicht vorhanden ist), werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-114">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="5d9e1-115">Wenn der Wert nicht vollständig durch die Enumerationseinträge ermittelt werden kann, wird der Wert als ganzzahliger Wert formatiert.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-115">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="5d9e1-116">Das folgende Beispiel veranschaulicht den Formatbezeichner „F“.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-116">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="5d9e1-117">D oder d</span><span class="sxs-lookup"><span data-stu-id="5d9e1-117">D or d</span></span>

<span data-ttu-id="5d9e1-118">Zeigt den Enumerationseintrag in der kürzestmöglichen Darstellung als ganzzahligen Wert an.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-118">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="5d9e1-119">Das folgende Beispiel veranschaulicht den Formatbezeichner „D“.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-119">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="5d9e1-120">X oder x</span><span class="sxs-lookup"><span data-stu-id="5d9e1-120">X or x</span></span>

<span data-ttu-id="5d9e1-121">Zeigt den Enumerationseintrag als Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-121">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="5d9e1-122">Der Wert wird ggf. mit führenden Nullen dargestellt, um sicherzustellen, dass die resultierende Zeichenfolge für jedes Byte im [zugrunde liegenden numerischen Typ](xref:System.Enum.GetUnderlyingType%2A) des Enumerationstyps über zwei Zeichen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-122">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="5d9e1-123">Das folgende Beispiel veranschaulicht den Formatbezeichner „X“.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-123">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="5d9e1-124">Der zugrunde liegende Typ sowohl für <xref:System.ConsoleColor> als auch für <xref:System.IO.FileAttributes> in diesem Beispiel ist <xref:System.Int32> oder ein Integertyp mit 32 Bit (bzw. 4 Byte), wodurch eine Ergebniszeichenfolge mit 8 Zeichen erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-124">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]      
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="5d9e1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d9e1-125">Example</span></span>

<span data-ttu-id="5d9e1-126">Das folgende Beispiel definiert eine Enumeration namens `Colors`, die aus drei Einträgen besteht: `Red`, `Blue` und `Green`.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-126">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="5d9e1-127">Nachdem die Enumeration definiert wurde, kann auf folgende Weise eine Instanz deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-127">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="5d9e1-128">Dann kann die `Color.ToString(System.String)`-Methode verwendet werden, um den Enumerationswert je nach übergebenem Formatbezeichner auf verschiedene Arten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d9e1-128">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="5d9e1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d9e1-129">See also</span></span>

- [<span data-ttu-id="5d9e1-130">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="5d9e1-130">Formatting Types</span></span>](formatting-types.md)
