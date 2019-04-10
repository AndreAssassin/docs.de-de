---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 28f78161e14604c1f59872801855ccc918faec58
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299253"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="81aba-102">Ungültiger Ordinalwert.</span><span class="sxs-lookup"><span data-stu-id="81aba-102">Ordinal is not valid</span></span>
<span data-ttu-id="81aba-103">Beim Aufruf einer Dynamic Link Library (DLL) wurde angegeben, eine Anzahl anstelle einer Prozedur verwendet mit dem `#num` Syntax.</span><span class="sxs-lookup"><span data-stu-id="81aba-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="81aba-104">Dieser Fehler hat die folgenden möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="81aba-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="81aba-105">Ein Versuch, konvertieren die `#num` Ausdruck, der eine Ordnungszahl ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="81aba-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="81aba-106">Die `#num` angegebenen gibt keine Funktion in der DLL.</span><span class="sxs-lookup"><span data-stu-id="81aba-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="81aba-107">Eine Typbibliothek weist eine ungültige Deklaration, die interne Verwendung des eine ungültige Ordinalzahl zu.</span><span class="sxs-lookup"><span data-stu-id="81aba-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="81aba-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="81aba-108">To correct this error</span></span>  
  
1. <span data-ttu-id="81aba-109">Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder rufen Sie die Prozedur nach Namen.</span><span class="sxs-lookup"><span data-stu-id="81aba-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="81aba-110">Stellen Sie sicher, dass `#num` identifiziert eine gültige Funktion in der DLL.</span><span class="sxs-lookup"><span data-stu-id="81aba-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="81aba-111">Isolieren Sie den Aufruf der Prozedur das Problem verursachen, durch den Code auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="81aba-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="81aba-112">Schreiben einer `Declare` -Anweisung für die Prozedur, und klicken Sie auf Bericht des Problems an den Hersteller der Bibliothek weiter.</span><span class="sxs-lookup"><span data-stu-id="81aba-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aba-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81aba-113">See also</span></span>

- [<span data-ttu-id="81aba-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="81aba-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
