---
title: 'Vorgehensweise: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316504"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="43e16-102">Vorgehensweise: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43e16-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="43e16-103">Sie können ein Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente, um ein Fehlersymbol angezeigt wird, wenn der Benutzer unzulässige Daten eingibt.</span><span class="sxs-lookup"><span data-stu-id="43e16-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="43e16-104">Sie müssen mindestens zwei Steuerelemente im Formular aus, um zwischen diesen gewechselt und aufgerufen Validierungscode verfügen.</span><span class="sxs-lookup"><span data-stu-id="43e16-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="43e16-105">Um ein Fehlersymbol angezeigt wird, wenn der Wert eines Steuerelements ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="43e16-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="43e16-106">Hinzufügen von zwei Steuerelementen, z. B. Textfelder, zu einem Windows-Formular.</span><span class="sxs-lookup"><span data-stu-id="43e16-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="43e16-107">Hinzufügen einer <xref:System.Windows.Forms.ErrorProvider> -Komponente zum Formular.</span><span class="sxs-lookup"><span data-stu-id="43e16-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="43e16-108">Wählen Sie das erste Steuerelement, und fügen Sie Code in die <xref:System.Windows.Forms.Control.Validating> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="43e16-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="43e16-109">Damit dieser Code ordnungsgemäß ausgeführt werden kann muss die Prozedur mit dem Ereignis bestehen.</span><span class="sxs-lookup"><span data-stu-id="43e16-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="43e16-110">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="43e16-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="43e16-111">Der folgende Code überprüft die Gültigkeit der Daten, die der Benutzer eingegeben hat; Wenn die Daten ungültig ist, werden die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="43e16-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="43e16-112">Das erste Argument von der <xref:System.Windows.Forms.ErrorProvider.SetError%2A> Methode gibt an, die steuern, auf das Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43e16-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="43e16-113">Das zweite Argument ist der, die anzuzeigende Fehlertext.</span><span class="sxs-lookup"><span data-stu-id="43e16-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="43e16-114">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="43e16-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="43e16-115">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="43e16-115">Run the project.</span></span> <span data-ttu-id="43e16-116">Geben Sie (in diesem Beispiel nicht numerischen) ungültige Daten in das erste Steuerelement, und klicken Sie dann die zweite Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="43e16-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="43e16-117">Wenn das Symbol "Fehler" angezeigt wird, stellen Sie den Mauszeiger an den Fehlertext finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="43e16-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e16-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43e16-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="43e16-119">Übersicht über die ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="43e16-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="43e16-120">Vorgehensweise: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43e16-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
