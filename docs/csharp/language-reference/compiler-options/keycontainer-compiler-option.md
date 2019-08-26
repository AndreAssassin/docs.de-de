---
title: -keycontainer (C#-Compileroptionen)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 0d4ca602859c4f7f80a8fcdc09182c7da8a5fb31
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602848"
---
# <a name="-keycontainer-c-compiler-options"></a>-keycontainer (C#-Compileroptionen)
Gibt den Namen des kryptografischen Schlüsselcontainers an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Argumente  
 `string`  
 Der Name des Containers mit dem Schlüssel für einen starken Namen  
  
## <a name="remarks"></a>Anmerkungen  
 Wenn die Option **-keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente. Der Compiler fügt einen öffentlichen Schlüssel vom angegebenen Container in das Assemblymanifest ein und signiert die endgültige Assembly mit dem privaten Schlüssel. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. `sn -i` installiert das Schlüsselpaar im Container. Diese Option wird nicht unterstützt, wenn der Compiler auf CoreCLR ausgeführt wird. Verwenden Sie zum Signieren einer Assembly beim Erstellen auf CoreCLR die Option [-keyfile](keyfile-compiler-option.md).
  
 Wenn Sie mit der Option [-target:module](./target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [-addmodule](./addmodule-compiler-option.md) kompilieren.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](./keyfile-compiler-option.md) an den Compiler übergeben. Verwenden Sie [-delaysign](./delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren verzögern möchten, bis diese getestet wurde.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.  
  
 Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroption „-keyfile“](keyfile-compiler-option.md)
- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
