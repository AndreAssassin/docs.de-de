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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090614"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="74a5a-102">Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="74a5a-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="74a5a-103">`ShouldSerialize` und `Reset` sind optionale Methoden, die Sie für eine Eigenschaft angeben können, wenn die Eigenschaft nicht der Fall ist eine einfache Standardwert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="74a5a-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="74a5a-104">Wenn die Eigenschaft einen einfachen Standardwert verfügt, sollten Sie anwenden der <xref:System.ComponentModel.DefaultValueAttribute> , und geben Sie stattdessen den Standardwert an den Attributkonstruktor-Klasse.</span><span class="sxs-lookup"><span data-stu-id="74a5a-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="74a5a-105">Einen dieser Mechanismen können im Designer die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="74a5a-105">Either of these mechanisms enables the following features in the designer:</span></span>  
  
-   <span data-ttu-id="74a5a-106">Die Eigenschaft enthält visuelle Anzeige im Eigenschaftenbrowser an, wenn er von seinem Standardwert geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="74a5a-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>  
  
-   <span data-ttu-id="74a5a-107">Der Benutzer kann mit der rechten Maustaste auf die Eigenschaft, und wählen Sie **zurücksetzen** die Eigenschaft auf den Standardwert wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="74a5a-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>  
  
-   <span data-ttu-id="74a5a-108">Der Designer generiert effizienteren Code.</span><span class="sxs-lookup"><span data-stu-id="74a5a-108">The designer generates more efficient code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74a5a-109">Eine erfüllt die <xref:System.ComponentModel.DefaultValueAttribute> , oder geben Sie `Reset` *PropertyName* und `ShouldSerialize` *PropertyName* Methoden.</span><span class="sxs-lookup"><span data-stu-id="74a5a-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="74a5a-110">Verwenden Sie nicht beide.</span><span class="sxs-lookup"><span data-stu-id="74a5a-110">Do not use both.</span></span>  
  
 <span data-ttu-id="74a5a-111">Die `Reset` *PropertyName* Methode legt eine Eigenschaft auf den Standardwert fest, wie im folgenden Codefragment dargestellt.</span><span class="sxs-lookup"><span data-stu-id="74a5a-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>  
  
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
>  <span data-ttu-id="74a5a-112">Wenn eine Eigenschaft keine `Reset` -Methode ist nicht mit gekennzeichnet eine <xref:System.ComponentModel.DefaultValueAttribute>, und verfügt nicht über einen Standardwert, der in der Deklaration angegeben die `Reset` option für diese Eigenschaft, im Kontextmenü des deaktiviert ist der **Eigenschaften** Fenster der Windows Forms-Designer in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="74a5a-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>  
  
 <span data-ttu-id="74a5a-113">Verwenden Sie die Designer wie Visual Studio die `ShouldSerialize` *PropertyName* Methode, um zu überprüfen, ob eine Eigenschaft von seinem Standardwert geändert hat und Code schreiben, in das Formular nur, wenn eine Eigenschaft geändert wird, sodass für eine effizientere Code die Generierung.</span><span class="sxs-lookup"><span data-stu-id="74a5a-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="74a5a-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74a5a-114">For example:</span></span>  
  
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
  
 <span data-ttu-id="74a5a-115">Ein vollständiges Codebeispiel folgt.</span><span class="sxs-lookup"><span data-stu-id="74a5a-115">A complete code example follows.</span></span>  
  
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
  
 <span data-ttu-id="74a5a-116">In diesem Fall, auch wenn der Wert der privaten Variablen zugreifen der `MyFont` -Eigenschaft ist `null`, der Eigenschaftenbrowser zeigt keine `null`; stattdessen wird die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft des übergeordneten Elements, wenn er nicht ist `null`, Der Standardwert <xref:System.Windows.Forms.Control.Font%2A> in definierten <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="74a5a-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="74a5a-117">Daher ist der Standardwert für `MyFont` kann nicht einfach festgelegt werden, und ein <xref:System.ComponentModel.DefaultValueAttribute> nicht auf diese Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74a5a-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="74a5a-118">Stattdessen die `ShouldSerialize` und `Reset` -Methode müssen implementiert werden, für die `MyFont` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="74a5a-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a5a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a5a-119">See also</span></span>

- [<span data-ttu-id="74a5a-120">Eigenschaften in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="74a5a-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="74a5a-121">Definieren einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="74a5a-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="74a5a-122">Durch geänderte Eigenschaften ausgelöste Ereignisse</span><span class="sxs-lookup"><span data-stu-id="74a5a-122">Property-Changed Events</span></span>](property-changed-events.md)
