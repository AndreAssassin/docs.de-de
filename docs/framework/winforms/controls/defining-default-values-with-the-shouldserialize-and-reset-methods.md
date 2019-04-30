---
title: Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: f1f5a668c5d4f52ef7dd9f60a31c04f2173165f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972366"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode
`ShouldSerialize` und `Reset` sind optionale Methoden, die Sie für eine Eigenschaft angeben können, wenn die Eigenschaft nicht der Fall ist eine einfache Standardwert aufweisen. Wenn die Eigenschaft einen einfachen Standardwert verfügt, sollten Sie anwenden der <xref:System.ComponentModel.DefaultValueAttribute> , und geben Sie stattdessen den Standardwert an den Attributkonstruktor-Klasse. Einen dieser Mechanismen können im Designer die folgenden Funktionen:  
  
- Die Eigenschaft enthält visuelle Anzeige im Eigenschaftenbrowser an, wenn er von seinem Standardwert geändert wurde.  
  
- Der Benutzer kann mit der rechten Maustaste auf die Eigenschaft, und wählen Sie **zurücksetzen** die Eigenschaft auf den Standardwert wiederherzustellen.  
  
- Der Designer generiert effizienteren Code.  
  
    > [!NOTE]
    >  Eine erfüllt die <xref:System.ComponentModel.DefaultValueAttribute> , oder geben Sie `Reset` *PropertyName* und `ShouldSerialize` *PropertyName* Methoden. Verwenden Sie nicht beide.  
  
 Die `Reset` *PropertyName* Methode legt eine Eigenschaft auf den Standardwert fest, wie im folgenden Codefragment dargestellt.  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  Wenn eine Eigenschaft keine `Reset` -Methode ist nicht mit gekennzeichnet eine <xref:System.ComponentModel.DefaultValueAttribute>, und verfügt nicht über einen Standardwert, der in der Deklaration angegeben die `Reset` option für diese Eigenschaft, im Kontextmenü des deaktiviert ist der **Eigenschaften** Fenster der Windows Forms-Designer in Visual Studio.  
  
 Verwenden Sie die Designer wie Visual Studio die `ShouldSerialize` *PropertyName* Methode, um zu überprüfen, ob eine Eigenschaft von seinem Standardwert geändert hat und Code schreiben, in das Formular nur, wenn eine Eigenschaft geändert wird, sodass für eine effizientere Code die Generierung. Zum Beispiel:  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 Ein vollständiges Codebeispiel folgt.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 In diesem Fall, auch wenn der Wert der privaten Variablen zugreifen der `MyFont` -Eigenschaft ist `null`, der Eigenschaftenbrowser zeigt keine `null`; stattdessen wird die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft des übergeordneten Elements, wenn er nicht ist `null`, Der Standardwert <xref:System.Windows.Forms.Control.Font%2A> in definierten <xref:System.Windows.Forms.Control>. Daher ist der Standardwert für `MyFont` kann nicht einfach festgelegt werden, und ein <xref:System.ComponentModel.DefaultValueAttribute> nicht auf diese Eigenschaft angewendet werden. Stattdessen die `ShouldSerialize` und `Reset` -Methode müssen implementiert werden, für die `MyFont` Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
- [Definieren einer Eigenschaft](defining-a-property-in-windows-forms-controls.md)
- [Durch geänderte Eigenschaften ausgelöste Ereignisse](property-changed-events.md)
