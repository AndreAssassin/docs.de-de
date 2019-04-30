---
title: 'Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032174"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="c7d57-102">Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7d57-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="c7d57-103">In diesem Beispiel gibt eine `Boolean` Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7d57-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="c7d57-104">Die Validierung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="c7d57-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7d57-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7d57-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="c7d57-106">In diesem Beispiel überprüft nicht, wenn Sie der Namen Doppelpunkte oder Verzeichnisse ohne Namen falsch platziert wurden oder die Länge des Namens vom System definierte maximale Länge überschreitet.</span><span class="sxs-lookup"><span data-stu-id="c7d57-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="c7d57-107">Es wird auch nicht überprüft, wenn die Anwendung die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="c7d57-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d57-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7d57-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="c7d57-109">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7d57-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
