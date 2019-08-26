---
title: 'Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: ffb00325bc04aad79d61558925546e0aa8544551
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921747"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="90d40-102">Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="90d40-102">How to: Convert a byte Array to an int (C# Programming Guide)</span></span>
<span data-ttu-id="90d40-103">In diesem Beispiel wird veranschaulicht, wie Sie die <xref:System.BitConverter>-Klasse dazu verwenden, einen Bytearray in einen [int](../../language-reference/builtin-types/integral-numeric-types.md)-Typ und wieder zurück in ein Bytearray zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="90d40-103">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../language-reference/builtin-types/integral-numeric-types.md) and back to an array of bytes.</span></span> <span data-ttu-id="90d40-104">Sie müssen möglicherweise Bytes in einen integrierten Datentyp konvertieren, wenn Sie z.B. Bytes aus dem Netzwerk gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="90d40-104">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="90d40-105">Die folgende Tabelle enthält zusätzlich zu der Methode [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) aus dem Beispiel auch die Methoden in der <xref:System.BitConverter>-Klasse, die Bytes (aus einem Bytearray) in andere integrierte Typen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="90d40-105">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>  
  
|<span data-ttu-id="90d40-106">Zurückgegebener Typ</span><span class="sxs-lookup"><span data-stu-id="90d40-106">Type returned</span></span>|<span data-ttu-id="90d40-107">Methode</span><span class="sxs-lookup"><span data-stu-id="90d40-107">Method</span></span>|  
|-------------------|------------|  
|`bool`|<span data-ttu-id="90d40-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-108">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|  
|`char`|<span data-ttu-id="90d40-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-109">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|  
|`double`|<span data-ttu-id="90d40-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-110">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|  
|`short`|<span data-ttu-id="90d40-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-111">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|  
|`int`|<span data-ttu-id="90d40-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-112">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|  
|`long`|<span data-ttu-id="90d40-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-113">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|  
|`float`|<span data-ttu-id="90d40-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-114">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|  
|`ushort`|<span data-ttu-id="90d40-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-115">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|  
|`uint`|<span data-ttu-id="90d40-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-116">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|  
|`ulong`|<span data-ttu-id="90d40-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="90d40-117">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90d40-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90d40-118">Example</span></span>  
 <span data-ttu-id="90d40-119">In diesem Beispiel wird ein Bytearray initialisiert und umgekehrt, wenn die Computerarchitektur Little-Endian entspricht (das kleinstwertige Byte wird am Anfang gespeichert). Anschließend wird die Methode [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) aufgerufen, um vier Bytes im Array in einen `int` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="90d40-119">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="90d40-120">Das zweite Argument für [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) gibt den Startindex des Bytearrays an.</span><span class="sxs-lookup"><span data-stu-id="90d40-120">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90d40-121">Die Ausgabe kann sich je nach der Bytereihenfolge der Architektur Ihres Computers unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="90d40-121">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]  
  
## <a name="example"></a><span data-ttu-id="90d40-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90d40-122">Example</span></span>  
 <span data-ttu-id="90d40-123">In diesem Beispiel wird die Methode <xref:System.BitConverter.GetBytes%28System.Int32%29> der Klasse <xref:System.BitConverter> aufgerufen, um `int` in ein Bytearray zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="90d40-123">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90d40-124">Die Ausgabe kann sich je nach der Bytereihenfolge der Architektur Ihres Computers unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="90d40-124">The output may differ depending on the endianess of your computer's architecture.</span></span>  
  
 [!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]  
  
## <a name="see-also"></a><span data-ttu-id="90d40-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90d40-125">See also</span></span>

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [<span data-ttu-id="90d40-126">Typen</span><span class="sxs-lookup"><span data-stu-id="90d40-126">Types</span></span>](./index.md)
