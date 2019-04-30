---
title: Binden einer benutzerdefinierten Aktivitätseigenschaft an ein Designersteuerelement
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 142a9eb273a98d3a2d83a1239d6d7c891d5cc305
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945898"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a>Binden einer benutzerdefinierten Aktivitätseigenschaft an ein Designersteuerelement

Das Binden eines Textfeld-Designersteuerelements an ein Aktivitätsargument ist recht einfach. Das Binden eines komplexes Designersteuerelements (z. B. ein Kombinationsfeld) an ein Aktivitätsargument kann jedoch eine besondere Herausforderung darstellen. In diesem Thema wird erläutert, wie ein Aktivitätsargument an ein Kombinationsfeld-Steuerelement in einem benutzerdefinierten Aktivitätsdesigner gebunden wird.

## <a name="creating-the-combo-box-item-converter"></a>Erstellen des Kombinationsfeldelement-Konverters

1. Erstellen Sie in Visual Studio eine neue leere Projektmappe mit dem Namen "CustomProperty".

2. Erstellen Sie eine neue Klasse mit dem Namen "ComboBoxItemConverter". Fügen Sie einen Verweis auf System.Windows.Data hinzu, und sorgen Sie dafür, dass die Klasse aus <xref:System.Windows.Data.IValueConverter> abgeleitet wird. Implementieren Sie die Schnittstelle über Visual Studio, um Stubs für `Convert` und `ConvertBack` zu generieren.

3. Fügen Sie der `Convert` -Methode folgenden Code hinzu. In diesem Code wird <xref:System.Activities.InArgument%601> der Aktivität vom Typ <xref:System.String> in den Wert konvertiert, der im Designer platziert werden soll.

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (vbexpression != null)
            {
                return vbexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

     Der Ausdruck im vorherigen Codeausschnitt kann auch mit <xref:Microsoft.CSharp.Activities.CSharpValue%601> anstelle von <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> erstellt werden.

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            CSharpValue<string> csexpression = expression as CSharpValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (csexpression != null)
            {
                return csexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

4. Fügen Sie der `ConvertBack` -Methode folgenden Code hinzu. Dieser Code konvertiert das eingehende Kombinationsfeldelement wieder zurück in ein <xref:System.Activities.InArgument%601>-Element.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     Der Ausdruck im vorherigen Codeausschnitt kann auch mit <xref:Microsoft.CSharp.Activities.CSharpValue%601> anstelle von <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> erstellt werden.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a>Hinzufügen von ComboBoxItemConverter zum benutzerdefinierten Designer einer Aktivität

1. Fügen Sie dem Projekt ein neues Element hinzu. Wählen Sie im Dialogfeld "Neues Element" den Knoten "Workflow" aus, und wählen Sie "Aktivitätsdesigner" als Typ des neuen Elements aus. Benennen Sie das CustomPropertyDesigner-Element.

2. Fügen Sie dem neuen Designer ein Kombinationsfeld hinzu. Fügen Sie in der Items-Eigenschaft dem Kombinationsfeld einige Elemente mit den Content-Werten "Item1" und 'Item2 hinzu.

3. Ändern Sie das XAML des Kombinationsfelds, um den neuen Elementkonverter als Elementkonverter hinzuzufügen, der für das Kombinationsfeld verwendet werden soll. Der Konverter wird dem ActivityDesigner.Resources-Segment als Ressource hinzugefügt und gibt den Konverter im Converter-Attribut für den <xref:System.Windows.Controls.ComboBox> an. Beachten Sie, dass der Namespace des Projekts in den Namespaceattributen für den Aktivitätsdesigner angegeben wird. Wenn der Designer in einem anderen Projekt verwendet werden soll, muss dieser Namespace geändert werden.

    ```xaml
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="clr-namespace:CustomProperty"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">

        <sap:ActivityDesigner.Resources>
            <ResourceDictionary>
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>
            </ResourceDictionary>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">
                <ComboBoxItem>item1</ComboBoxItem>
                <ComboBoxItem>item2</ComboBoxItem>
            </ComboBox>
        </Grid>
    </sap:ActivityDesigner>
    ```

4. Erstellen Sie ein neues Element vom Typ <xref:System.Activities.CodeActivity>. Der von der IDE für die Aktivität erstellte Standardcode ist für dieses Beispiel ausreichend.

5. Fügen Sie der Klassendefinition das folgende Attribut hinzu:

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     Diese Zeile verknüpft den neuen Designer mit der neuen Klasse.

 Die neue Aktivität sollte jetzt mit dem Designer verknüpft sein. Sie können die neue Aktivität testen, indem Sie sie einem Workflow hinzufügen und das Kombinationsfeld auf die zwei Werte festlegen. Das Eigenschaftenfenster sollte aktualisiert werden, um den Kombinationsfeldwert widerzuspiegeln.
