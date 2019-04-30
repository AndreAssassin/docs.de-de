---
title: 'Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 27b19e47d108b9af43a6d8882264d62c726ffe56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972080"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="a0796-102">Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0796-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="a0796-103">Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement kann Tage in Fettschrift, anzeigen, entweder als einzelne Datumsangaben oder einer wiederholten Basis.</span><span class="sxs-lookup"><span data-stu-id="a0796-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="a0796-104">Diese Option, um die Aufmerksamkeit auf spezielle Datumsangaben, z. B. Feiertage und für Wochenenden empfiehlt sich.</span><span class="sxs-lookup"><span data-stu-id="a0796-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="a0796-105">Drei Eigenschaften steuern, diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="a0796-105">Three properties control this feature.</span></span> <span data-ttu-id="a0796-106">Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> Eigenschaft enthält die einzelne Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="a0796-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="a0796-107">Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jedes Jahr fett formatiert sein.</span><span class="sxs-lookup"><span data-stu-id="a0796-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="a0796-108">Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jeden Monat fett formatiert sein.</span><span class="sxs-lookup"><span data-stu-id="a0796-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="a0796-109">Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a0796-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="a0796-110">Zum Hinzufügen oder entfernen ein Datum aus diesen Listen, müssen Sie hinzufügen oder Entfernen einer <xref:System.DateTime> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a0796-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="a0796-111">Um ein Datum in Fettschrift anzeigen</span><span class="sxs-lookup"><span data-stu-id="a0796-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="a0796-112">Erstellen der <xref:System.DateTime> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a0796-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. <span data-ttu-id="a0796-113">Ein einzelnes Datum fett formatieren, durch den Aufruf der <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> Methode der <xref:System.Windows.Forms.MonthCalendar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a0796-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a0796-114">– oder –</span><span class="sxs-lookup"><span data-stu-id="a0796-114">–or–</span></span>  
  
     <span data-ttu-id="a0796-115">Formatieren Sie einen Satz mit Datumsangaben fett gleichzeitig durch Erstellen eines Arrays von <xref:System.DateTime> Objekte und auf eine der Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a0796-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="a0796-116">Um ein Datum in normaler Schrift anzeigen</span><span class="sxs-lookup"><span data-stu-id="a0796-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="a0796-117">Stellen Sie ein einzelnes fett formatiertes Datum in normaler Schrift angezeigt werden, durch den Aufruf der <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a0796-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a0796-118">– oder –</span><span class="sxs-lookup"><span data-stu-id="a0796-118">–or–</span></span>  
  
     <span data-ttu-id="a0796-119">Entfernen Sie alle fett formatierten Datumsangaben aus einem der drei Listen durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a0796-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="a0796-120">Aktualisieren Sie die Darstellung der Schriftart durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a0796-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0796-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0796-121">See also</span></span>

- [<span data-ttu-id="a0796-122">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a0796-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="a0796-123">Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a0796-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="a0796-124">Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a0796-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="a0796-125">Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a0796-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
