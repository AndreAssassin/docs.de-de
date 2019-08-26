---
title: -linkresource (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 454915454f3faf15933257f3e3e221afec51d0ee
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606753"
---
# <a name="-linkresource-c-compiler-options"></a>-linkresource (C#-Compileroptionen)
Erstellt einen Link zur .NET Framework-Ressource in der Ausgabedatei Die Ressourcendateien wird nicht in die Ausgabedatei eingefügt. Dies ist ein Unterschied zur Option [-resource](./resource-compiler-option.md), die eine Ressourcendatei in die Ausgabedatei einbettet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten  
  
 `identifier` (optional)  
 Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird. Der Standardwert ist der Name der Datei.  
  
 `accessibility-modifier` (optional)  
 Barrierefreiheit der Ressource: öffentlich oder privat. Der Standardwert ist „öffentlich“.  
  
## <a name="remarks"></a>Anmerkungen  
 Verknüpfte Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mit den C#-Compiler erstellt werden. Geben Sie `private` als Modifizierer der Barrierefreiheit an. Außer `public` und `private` sind keine anderen Modifizierer zulässig.  
  
 **-linkresource** erfordert eine andere [-target](./target-compiler-option.md)-Option als **-target:module**.  
  
 Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise von [resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.  
  
 Die in `filename` angegebene Datei kann jedes Format haben. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann. Das zweite Beispiel zeigt die dazu erforderliche Vorgehensweise. Sie können dasselbe aber auch im Assemblylinker vornehmen. Das dritte Beispiel zeigt die dazu erforderliche Vorgehensweise. Weitere Informationen finden Sie unter [Al.exe (Assembly Linker-Tool)](../../../framework/tools/al-exe-assembly-linker.md) und [Arbeiten mit Assemblys und dem globalen Assemblycache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **-linkres** ist die Kurzform von **-linkresource**.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs` und verknüpfen Sie die Ressourcendatei `rf.resource`:  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `A.cs` in eine DLL, verknüpfen Sie eine native DLL „n.dll“, und fügen Sie die Ausgabe in den globalen Assemblycache (GAC) ein. In diesem Beispiel befinden sich sowohl „a.dll“ als auch „n.dll“ im GAC.  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Gleiche wie im vorherigen Beispiel erreicht, allerdings mithilfe von Assemblylinkeroptionen.  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Al.exe (Assembly Linker-Tool)](../../../framework/tools/al-exe-assembly-linker.md)
- [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
