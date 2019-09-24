---
ms.openlocfilehash: 748e7f484227b6a60a2309bde185079b30fe19de
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117173"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="8d4b0-101">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="8d4b0-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="8d4b0-102">ZIP-Archive listen sowohl die komprimierte als auch die unkomprimierte Größe im zentralen Verzeichnis und im lokalen Header auf.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="8d4b0-103">Die Eintragsdaten selbst geben die Größe ebenfalls an.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="8d4b0-104">In .NET Core 2.2 und früheren Versionen wurden diese Werte nie auf Konsistenz geprüft.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="8d4b0-105">Ab .NET Core 3.0 ist dies jetzt der Fall.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8d4b0-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8d4b0-106">Change description</span></span>

<span data-ttu-id="8d4b0-107">In .NET Core 2.2 und früheren Versionen ist <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> selbst dann erfolgreich, wenn der lokale Header nicht mit dem zentralen Header der ZIP-Datei übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="8d4b0-108">Die Daten werden dekomprimiert, bis das Ende des komprimierten Datenstroms erreicht ist, auch wenn seine Länge die im zentralen Verzeichnis/lokalen Header angegebene unkomprimierte Dateigröße überschreitet.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="8d4b0-109">Ab .NET Core 3.0 überprüft die <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>-Methode, ob der lokale Header und der zentrale Header hinsichtlich der komprimierten und unkomprimierten Größen eines Eintrags übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="8d4b0-110">Wenn dies nicht der Fall ist, löst die Methode eine <xref:System.IO.InvalidDataException> aus, wenn die lokalen Größen der Header- und/oder Datendeskriptorlisten des Archivs nicht mit dem zentralen Verzeichnis der ZIP-Datei übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="8d4b0-111">Beim Lesen eines Eintrags werden dekomprimierte Daten auf die nicht komprimierte Dateigröße abgeschnitten, die im Header aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="8d4b0-112">Diese Änderung wurde vorgenommen, um sicherzustellen, dass ein <xref:System.IO.Compression.ZipArchiveEntry> die Größe seiner Daten richtig darstellt und nur diese Menge an Daten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8d4b0-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8d4b0-113">Version introduced</span></span>

<span data-ttu-id="8d4b0-114">3.0</span><span class="sxs-lookup"><span data-stu-id="8d4b0-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8d4b0-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8d4b0-115">Recommended action</span></span>

<span data-ttu-id="8d4b0-116">Packen Sie jedes ZIP-Archiv neu, das diese Probleme aufweist.</span><span class="sxs-lookup"><span data-stu-id="8d4b0-116">Repackage any zip archive which exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="8d4b0-117">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="8d4b0-117">Category</span></span>

<span data-ttu-id="8d4b0-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="8d4b0-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8d4b0-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8d4b0-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`


-->
