---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 0315645eccdc899ac9cf4d0be105297e1fa2a4c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335478"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="fa2c9-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa2c9-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="fa2c9-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa2c9-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="fa2c9-105">oder</span><span class="sxs-lookup"><span data-stu-id="fa2c9-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa2c9-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="fa2c9-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="fa2c9-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-107">Required.</span></span> <span data-ttu-id="fa2c9-108">The resource file to link to the assembly.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="fa2c9-109">If the file name contains a space, enclose the name in quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="fa2c9-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="fa2c9-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-110">Optional.</span></span> <span data-ttu-id="fa2c9-111">The logical name for the resource.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-111">The logical name for the resource.</span></span> <span data-ttu-id="fa2c9-112">The name that is used to load the resource.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-112">The name that is used to load the resource.</span></span> <span data-ttu-id="fa2c9-113">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-113">The default is the name of the file.</span></span> <span data-ttu-id="fa2c9-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="fa2c9-115">By default, `filename` is public in the assembly.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa2c9-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa2c9-116">Remarks</span></span>  
 <span data-ttu-id="fa2c9-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="fa2c9-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="fa2c9-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="fa2c9-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="fa2c9-121">The file name can be any file format.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-121">The file name can be any file format.</span></span> <span data-ttu-id="fa2c9-122">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="fa2c9-123">Die Kurzform von `-linkresource` ist `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa2c9-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa2c9-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa2c9-125">Example</span></span>  
 <span data-ttu-id="fa2c9-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="fa2c9-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa2c9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa2c9-127">See also</span></span>

- [<span data-ttu-id="fa2c9-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="fa2c9-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fa2c9-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa2c9-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="fa2c9-130">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa2c9-130">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="fa2c9-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="fa2c9-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
