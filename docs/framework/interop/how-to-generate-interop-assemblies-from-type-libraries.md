---
title: 'Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a3ee82a9091f0caeee010ec79632ce703efb589
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338838"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="53e4b-102">Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken</span><span class="sxs-lookup"><span data-stu-id="53e4b-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="53e4b-103">[Type Library Importer (Tlbexp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) ist ein Befehlszeilentool, das die Co-Klassen- und Schnittstellen einer COM-Typbibliothek in Metadaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="53e4b-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="53e4b-104">Dieses Tool erstellt automatisch eine Interop-Assembly und den Namespace für die Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="53e4b-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="53e4b-105">Nachdem die Metadaten einer Klasse verfügbar sind, können verwaltete Clients Instanzen des COM-Typs erstellen und seine Methoden aufrufen, als ob es sich um eine .NET-Instanz handeln würde.</span><span class="sxs-lookup"><span data-stu-id="53e4b-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="53e4b-106">„Tlbimp.exe“ konvertiert eine ganze Typbibliothek auf einmal in Metadaten und kann keine Typinformationen für eine Teilmenge der in einer Typbibliothek definierten Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="53e4b-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="53e4b-107">Generieren einer Interop-Assembly aus einer Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="53e4b-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="53e4b-108">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="53e4b-108">Use the following command:</span></span>  
  
     <span data-ttu-id="53e4b-109">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="53e4b-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="53e4b-110">Das Hinzufügen des **/out:**-Schalters erzeugt eine Interop-Assembly mit einem geänderten Namen, z.B. „LOANLib.dll“.</span><span class="sxs-lookup"><span data-stu-id="53e4b-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="53e4b-111">Das Ändern des Namens der Interop-Assembly kann dabei helfen, sie von der ursprünglichen COM-DLL zu unterscheiden und Probleme zu verhindern, die aufgrund der doppelten Namen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="53e4b-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53e4b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53e4b-112">Example</span></span>  
 <span data-ttu-id="53e4b-113">Der folgende Befehl erstellt die „Loanlib.dll“-Assembly im `Loanlib`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="53e4b-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="53e4b-114">Der folgende Befehl erzeugt eine Interop-Assembly mit einem geänderten Namen (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="53e4b-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="53e4b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53e4b-115">See also</span></span>

- [<span data-ttu-id="53e4b-116">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="53e4b-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="53e4b-117">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="53e4b-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)
