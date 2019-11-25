---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 00cb62827381146c172e0d15a2c64b167c21f025
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352190"
---
# <a name="typeparam-visual-basic"></a>\<typeparam> (Visual Basic)
Defines a type parameter name and description.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
 `description`  
 A description of the type parameter.  
  
## <a name="remarks"></a>Hinweise  
 Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 This example uses the `<typeparam>` tag to describe the `id` parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
