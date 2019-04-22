---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822725"
---
# <a name="-removeintchecks"></a><span data-ttu-id="b8e3e-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="b8e3e-102">-removeintchecks</span></span>
<span data-ttu-id="b8e3e-103">Aktiviert die Überlauf-fehlerüberprüfung für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8e3e-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8e3e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b8e3e-105">Arguments</span></span>  
  
|<span data-ttu-id="b8e3e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b8e3e-106">Term</span></span>|<span data-ttu-id="b8e3e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b8e3e-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b8e3e-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b8e3e-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b8e3e-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-109">Optional.</span></span> <span data-ttu-id="b8e3e-110">Die `-removeintchecks-` Option veranlasst den Compiler, alle integerberechnungen auf Ganzzahlüberlauf-Fehler zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="b8e3e-111">Die Standardeinstellung ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="b8e3e-112">Angeben von `-removeintchecks` oder `-removeintchecks+` verhindert die Überprüfung von Fehlern und können ganzzahlige Berechnungen zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="b8e3e-113">Allerdings ohne Überprüfung von Fehlern, und wenn datenkapazitäten auf Typ ist ein Überlauf aufgetreten sind, können falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="b8e3e-114">-Removeintchecks in der integrierten Entwicklungsumgebung von Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b8e3e-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b8e3e-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="b8e3e-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="b8e3e-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="b8e3e-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="b8e3e-119">4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b8e3e-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8e3e-120">Example</span></span>  
 <span data-ttu-id="b8e3e-121">Der folgende code kompiliert `Test.vb` Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b8e3e-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8e3e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8e3e-122">See also</span></span>

- [<span data-ttu-id="b8e3e-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b8e3e-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b8e3e-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b8e3e-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
