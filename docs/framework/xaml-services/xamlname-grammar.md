---
title: XamlName-Grammatik
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938748"
---
# <a name="xamlname-grammar"></a>XamlName-Grammatik
XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier der Einfachheit halber reproduziert wird.  
  
## <a name="from-the-xaml-specification"></a>Der XAML-Spezifikation  
 Die [MS-XAML]-Spezifikation definiert die XamlName-Grammatik zur die zulässigen symbolischen Bezeichner für Typen und Eigenschaften zu identifizieren.  
  
 Zeichenfolgenwerte des Typs, die in der folgenden Grammatik XamlName entsprechen soll:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Die die folgenden Werte der allgemeinen Kategorie setzt voraus, wie in der Datenbank der Unicode-Zeichen definiert  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML definiert, einer zweiten Grammatik, DottedXamlName, die für die Eigenschaft verwendet wird, und Ereignis qualifizierten verweisen, und auch für die angefügte Member. Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).  
  
 Zeichenfolgenwerte des Typs, die in der folgenden Grammatik DottedXamlName entsprechen soll:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Hinweise  
 Die vollständige Spezifikation finden Sie unter [ \[MS-XAML-\]](https://go.microsoft.com/fwlink/?LinkId=114525).
