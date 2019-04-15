---
title: 'Vorgehensweise: Erstellen von COM-Wrappern'
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c26c84ece1231a4e118144c163fa3e9c7619301
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324126"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="e23a6-102">Vorgehensweise: Erstellen von COM-Wrappern</span><span class="sxs-lookup"><span data-stu-id="e23a6-102">How to: Create COM Wrappers</span></span>

<span data-ttu-id="e23a6-103">Sie können mit Visual Studio 2005-Features oder den .NET Framework-Tools „Tlbimp.exe“ und „Regasm.exe“ COM-Wrapper (Component Object Model) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-103">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="e23a6-104">Beide Methoden generieren zwei Typen von COM-Wrappern:</span><span class="sxs-lookup"><span data-stu-id="e23a6-104">Both methods generate two types of COM wrappers:</span></span>

-   <span data-ttu-id="e23a6-105">Ein [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) aus einer Typbibliothek führt ein COM-Objekt in verwaltetem Code aus.</span><span class="sxs-lookup"><span data-stu-id="e23a6-105">A [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

-   <span data-ttu-id="e23a6-106">Ein [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) mit den erforderlichen Registrierungseinstellungen führt ein verwaltetes Objekt in einer nativen Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e23a6-106">A [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="e23a6-107">In Visual Studio 2005 können Sie den COM-Wrapper als Verweis zu Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-107">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="e23a6-108">Umschließen von COM-Objekten in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="e23a6-108">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="e23a6-109">Erstellen eines durch die Laufzeit aufrufbaren Wrappers mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e23a6-109">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="e23a6-110">Öffnen Sie das Projekt für Ihre verwaltete Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e23a6-110">Open the project for your managed application.</span></span>

2. <span data-ttu-id="e23a6-111">Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-111">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="e23a6-112">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="e23a6-112">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="e23a6-113">Klicken Sie im Dialogfeld „Verweis hinzufügen“ auf die Registerkarte **COM**, wählen Sie die Komponente aus, die Sie verwenden möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="e23a6-114">Beachten Sie, dass die COM-Komponente im **Projektmappen-Explorer** dem Projektordner „Verweise“ hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e23a6-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="e23a6-115">Sie können jetzt Code schreiben, um auf das COM-Objekt zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="e23a6-116">Sie können mit der Objektdeklaration beginnen, zum Beispiel mit einer `Imports`-Anweisung für [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] oder einer `Using`-Anweisung für [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e23a6-116">You can begin by declaring the object, such as with an `Imports` statement for [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] or a `Using` statement for [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="e23a6-117">Wenn Sie Microsoft Office-Komponenten programmieren möchten, installieren Sie zunächst die [primären Interop-Assemblys von Microsoft Office](https://go.microsoft.com/fwlink/?LinkId=50479) (PIAs), die im Microsoft Download Center verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e23a6-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](https://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="e23a6-118">Wählen Sie in Schritt 4 die aktuelle Version der Objektbibliothek aus, die für das gewünschte Office-Produkt zur Verfügung steht, z.B. **Microsoft Word 11.0-Objektbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="e23a6-119">Erstellen eines Runtime Callable Wrappers mit .NET Framework-Tools</span><span class="sxs-lookup"><span data-stu-id="e23a6-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="e23a6-120">Führen Sie das [Tlbimp.exe (Type Library Importer-Tool)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e23a6-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="e23a6-121">Dieses Tool erstellt eine Assembly, die Laufzeitmetadaten für die Typen enthält, die in der ursprünglichen Typbibliothek definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e23a6-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="e23a6-122">Umschließen von verwalteten Objekten in einer nativen Anwendung</span><span class="sxs-lookup"><span data-stu-id="e23a6-122">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="e23a6-123">Erstellen eines COM Callable Wrappers mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e23a6-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="e23a6-124">Erstellen Sie ein Klassenbibliotheksprojekt für die verwaltete Klasse, die Sie in nativem Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="e23a6-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="e23a6-125">Die Klasse muss über einen Standardkonstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-125">The class must have a default constructor.</span></span>  
  
     <span data-ttu-id="e23a6-126">Überprüfen Sie, ob Sie eine vollständige vierteilige Versionsnummer für die Assembly in der AssemblyInfo-Datei besitzen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="e23a6-127">Diese Zahl ist für die Versionszuweisung in der Windows-Registrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e23a6-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="e23a6-128">Weitere Informationen über die Versionsummern finden Sie unter [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="e23a6-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2. <span data-ttu-id="e23a6-129">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-129">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="e23a6-130">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-130">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="e23a6-131">Aktivieren Sie das Kontrollkästchen **Für COM-Interop registrieren**.</span><span class="sxs-lookup"><span data-stu-id="e23a6-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="e23a6-132">Wenn Sie das Projekt erstellen, wird die Assembly für COM-Interop automatisch registriert.</span><span class="sxs-lookup"><span data-stu-id="e23a6-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="e23a6-133">Wenn Sie in Visual Studio 2005 eine native Anwendung erstellen, können Sie die Assembly verwenden, indem Sie im Menü **Projekt** auf **Verweis hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="e23a6-133">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="e23a6-134">Erstellen eines COM Callable Wrappers mit .NET Framework-Tools</span><span class="sxs-lookup"><span data-stu-id="e23a6-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="e23a6-135">Führen Sie das Tool [Regasm.exe (Assembly Registration-Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e23a6-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="e23a6-136">Dieses Tool liest die Metadaten in einer Assembly und fügt der Registrierung die notwendigen Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e23a6-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="e23a6-137">Folglich können COM-Clients .NET Framework-Klassen transparent erstellen.</span><span class="sxs-lookup"><span data-stu-id="e23a6-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="e23a6-138">Sie können die Assembly verwenden, als handle es sich um eine native COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e23a6-138">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="e23a6-139">Sie können Regasm.exe für eine Assembly in jedem beliebigen Verzeichnis ausführen und anschließend das [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) ausführen, um sie in den globalen Assemblycache zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e23a6-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="e23a6-140">Beim Verschieben der Assembly werden die Registrierungseinträge für den Speicherort nicht ungültig, da der globale Assemblycache immer überprüft wird, wenn die Assembly nicht an einem anderen Speicherort gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e23a6-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23a6-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e23a6-141">See also</span></span>

- [<span data-ttu-id="e23a6-142">Runtime Callable Wrapper (RCW)</span><span class="sxs-lookup"><span data-stu-id="e23a6-142">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="e23a6-143">COM Callable Wrapper (CCW)</span><span class="sxs-lookup"><span data-stu-id="e23a6-143">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)
