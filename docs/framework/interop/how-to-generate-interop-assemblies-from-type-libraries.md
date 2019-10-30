---
title: 'Gewusst wie: Generieren von Interop-Assemblys aus Typbibliotheken'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 7cca21630bd1dbd6896f882d058f288f603e95df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123898"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="fc732-102">Gewusst wie: Generieren von Interop-Assemblys aus Typbibliotheken</span><span class="sxs-lookup"><span data-stu-id="fc732-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="fc732-103">[Type Library Importer (Tlbexp.exe)](../tools/tlbimp-exe-type-library-importer.md) ist ein Befehlszeilentool, das die Co-Klassen- und Schnittstellen einer COM-Typbibliothek in Metadaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fc732-103">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="fc732-104">Dieses Tool erstellt automatisch eine Interop-Assembly und den Namespace für die Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="fc732-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="fc732-105">Nachdem die Metadaten einer Klasse verfügbar sind, können verwaltete Clients Instanzen des COM-Typs erstellen und seine Methoden aufrufen, als ob es sich um eine .NET-Instanz handeln würde.</span><span class="sxs-lookup"><span data-stu-id="fc732-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="fc732-106">„Tlbimp.exe“ konvertiert eine ganze Typbibliothek auf einmal in Metadaten und kann keine Typinformationen für eine Teilmenge der in einer Typbibliothek definierten Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="fc732-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="fc732-107">Generieren einer Interop-Assembly aus einer Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="fc732-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="fc732-108">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="fc732-108">Use the following command:</span></span>  
  
     <span data-ttu-id="fc732-109">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="fc732-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="fc732-110">Das Hinzufügen des **/out:** -Schalters erzeugt eine Interop-Assembly mit einem geänderten Namen, z.B. „LOANLib.dll“.</span><span class="sxs-lookup"><span data-stu-id="fc732-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="fc732-111">Das Ändern des Namens der Interop-Assembly kann dabei helfen, sie von der ursprünglichen COM-DLL zu unterscheiden und Probleme zu verhindern, die aufgrund der doppelten Namen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="fc732-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc732-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc732-112">Example</span></span>  
 <span data-ttu-id="fc732-113">Der folgende Befehl erstellt die „Loanlib.dll“-Assembly im `Loanlib`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="fc732-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="fc732-114">Der folgende Befehl erzeugt eine Interop-Assembly mit einem geänderten Namen (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="fc732-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc732-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc732-115">See also</span></span>

- [<span data-ttu-id="fc732-116">Importieren einer Typbibliothek als Assembly</span><span class="sxs-lookup"><span data-stu-id="fc732-116">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="fc732-117">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fc732-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
