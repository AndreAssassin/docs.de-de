---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 75369c3bcb19afbf98bfb80bc3e439f996d2a9d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796077"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Zeigt die Compilerausgabe mit UTF-8-Codierung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Der Standardwert für diese Option ist `-utf8output-`, was bedeutet der Ausgabe des Compilers nicht UTF-8-Codierung verwendet. Die Angabe von `-utf8output` ist mit der Angabe von `-utf8output+` identisch.  
  
## <a name="remarks"></a>Hinweise  
 Bei einigen internationalen Konfigurationen kann nicht der Ausgabe des Compilers ordnungsgemäß in der Konsole angezeigt werden. Verwenden Sie in solchen Situationen `-utf8output` und Compiler-Ausgabe in eine Datei umleiten.  
  
> [!NOTE]
>  Die `-utf8output` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und weist den Compiler anzuzeigende Ausgabe mit UTF-8-Codierung.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
