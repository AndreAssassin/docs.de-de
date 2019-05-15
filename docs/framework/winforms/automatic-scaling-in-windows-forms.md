---
title: Automatische Skalierung in Windows Forms
ms.date: 06/15/2017
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.assetid: 68fad25b-afbc-44bd-8e1b-966fc43507a4
ms.openlocfilehash: 4902cd8ab97771f75e5421a9de7ed1150a7443a8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586579"
---
# <a name="automatic-scaling-in-windows-forms"></a>Automatische Skalierung in Windows Forms

Die automatische Skalierung ermöglicht, dass ein Formular und seine Steuerelemente, die auf einem Computer mit einer bestimmten Bildschirmauflösung oder Systemschriftart entworfen wurden, ordnungsgemäß auf einem anderen Computer angezeigt werden, der eine andere Bildschirmauflösung oder Systemschriftart hat. Durch sie wird sichergestellt, dass die Größen des Formulars und seiner Steuerelemente intelligent geändert werden, sodass diese sowohl auf den Computern von Benutzern als auch auf denen von anderen Entwicklern konsistent zu systemeigenen Fenstern sowie anderen Anwendungen sind. Die Unterstützung von .NET Framework für die automatische Skalierung und visuelle Stile aktiviert .NET Framework-Anwendungen ein konsistentes Aussehen und Verhalten im Vergleich zu systemeigenen Windows-Anwendungen auf dem Computer jedes Benutzers zu verwalten.

Zum größten Teil, erwartet funktioniert die automatische Skalierung als in .NET Framework-Version, 2.0 und höher. Änderungen des Schriftartenschemas können jedoch problematisch sein. Ein Beispiel dafür, wie zum Beheben dieses Problems finden Sie unter [Vorgehensweise: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md).

## <a name="need-for-automatic-scaling"></a>Erforderlich für die automatische Skalierung

Ohne automatische Skalierung würde eine Anwendung, die für eine bestimmte Bildschirmauflösung oder Schriftart entworfen wurde, entweder zu klein oder zu groß angezeigt, wenn diese Auflösung oder Schriftart geändert wird. Wurde die Anwendung beispielsweise mit Tahoma 9 Punkt als Basis entworfen, würde sie ohne Anpassung zu klein angezeigt, wenn sie auf einem Computer ausgeführt würde, der die Systemschriftart Tahoma 12 Punkt hat. Textelemente wie Titel, Menüs, Textfeldinhalt usw. werden kleiner gerendert als andere Anwendungen. Darüber hinaus richtet sich die Größe der Benutzeroberflächenelemente, die Text enthalten, etwa die Titelleiste, Menüs und viele Steuerelemente, nach der verwendeten Schriftart. In diesem Beispiel werden diese Elemente zusätzlich relativ kleiner angezeigt.

Die gleiche Situation ergibt sich, wenn eine Anwendung für eine bestimmte Bildschirmauflösung entworfen wurde. Die häufigste Bildschirmauflösung ist 96 dpi (Dots per Inch), die gleich 100 % anzeigeskalierung, aber höhere Auflösung angezeigt, die Unterstützung von 125 %, 150 %, 200 % (die jeweils gleich 120, 144 und Unterstützung von 192 DPI) und höher werden immer häufiger. Ohne Anpassung wird eine Anwendung, insbesondere eine Grafikanwendung, die für eine bestimme Auflösung entworfen wurde, entweder zu groß oder zu klein angezeigt, wenn sie mit einer anderen Auflösung ausgeführt wird.

Mit der automatischen Skalierung lassen sich diese Probleme abschwächen, indem die Größen des Formulars und seiner untergeordneten Steuerelemente entsprechend der relativen Schriftgröße oder Bildschirmauflösung geändert werden. Windows unterstützt die automatische Skalierung von Dialogfeldern durch Verwenden einer relativen Maßeinheit, die als Dialogeinheiten bezeichnet wird. Eine Dialogeinheit basiert auf der Systemschriftart, und ihre Beziehung zu Pixeln kann über die Win32 SDK-Funktion `GetDialogBaseUnits` bestimmt werden. Wenn ein Benutzer das von Windows verwendete Design ändert, werden alle Dialogfelder automatisch entsprechend angepasst. Darüber hinaus unterstützt .NET Framework, automatische Skalierung entweder entsprechend der Standardsystemschriftart oder Auflösung. Optional kann die automatische Skalierung in einer Anwendung deaktiviert werden.

## <a name="original-support-for-automatic-scaling"></a>Ursprüngliche Unterstützung für die automatische Skalierung

Die Versionen 1.0 und 1.1 von .NET Framework unterstützt automatische Skalierung auf einfache Weise, die von der für die Benutzeroberfläche, dargestellt durch den Win32 SDK-Wert verwendeten Windows-Standardschriftart abhängt **DEFAULT_GUI_FONT**. Diese Schriftart wird normalerweise nur geändert, wenn sich die Bildschirmauflösung ändert. Der folgende Mechanismus wurde verwendet, um die automatische Skalierung zu implementieren:

1. Zur Entwurfszeit wurde die <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A>-Eigenschaft (die jetzt veraltet ist) auf die Höhe und die Breite der Systemstandardschriftart des Entwicklercomputers festgelegt.

2. Zur Laufzeit wurde die Systemstandardschriftart des Benutzercomputers verwendet, um die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft der <xref:System.Windows.Forms.Form>-Klasse zu initialisieren.

3. Vor dem Anzeigen des Formulars wurde die <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>-Methode aufgerufen, um das Formular zu skalieren. Diese Methode hat die relative Skalierungsgröße aus <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> und <xref:System.Windows.Forms.Control.Font%2A> berechnet und dann die <xref:System.Windows.Forms.Control.Scale%2A>-Methode aufgerufen, um das Formular und dessen untergeordneten Elemente tatsächlich zu skalieren.

4. Der Wert von <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> wurde aktualisiert, sodass nachfolgende Aufrufe von <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A> die Größe des Formulars nicht zunehmend geändert haben.

Während dieser Mechanismus für die meisten Zwecke ausreichend war, brachte er folgenden Einschränkungen mit sich:

- Da die <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> Eigenschaft steht für den Baseline-Schriftgrad als ganze Zahlen, treten Rundungsfehler auf, die offensichtlich werden, wenn ein Formular mehrere Auflösungen durchlaufen hat.

- Automatische Skalierung war nur in der <xref:System.Windows.Forms.Form>-Klasse, nicht in der <xref:System.Windows.Forms.ContainerControl>-Klasse implementiert. Daher wurden Benutzersteuerelemente nur ordnungsgemäß skaliert, wenn das Benutzersteuerelement mit derselben Auflösung wie das Formular entworfen und zur Entwurfszeit im Formular positioniert wurde.

- Formulare und deren untergeordneten Steuerelemente konnten nur dann gleichzeitig von mehreren Entwicklern gestaltet werden, wenn die Bildschirmauflösungen ihrer Computer identisch waren. Dies bedingte außerdem, dass das Erben durch ein Formular von der Auflösung abhängig war, die dem übergeordneten Formular zugeordnet war.

- Es ist nicht kompatibel mit neueren Layout-Managern, die mit .NET Framework, Version 2.0, eingeführt wurde, z. B. <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.

- Der Mechanismus unterstützte keine Skalierung, die direkt auf der Bildschirmauflösung basiert, aber für Kompatibilität mit [!INCLUDE[compact](../../../includes/compact-md.md)] erforderlich ist.

Obwohl dieser Mechanismus in .NET Framework, Version 2.0 Abwärtskompatibilität beibehalten wird, wurde es durch den robusteren Skalierungsmechanismus beschrieben abgelöst. Als Folge davon sind <xref:System.Windows.Forms.Form.AutoScale%2A>, <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>, <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> und bestimmte <xref:System.Windows.Forms.Control.Scale%2A>-Überladungen als veraltet gekennzeichnet.

> [!NOTE]
> Sie können Verweise auf diese Member problemlos löschen, wenn Sie Ihren Legacycode auf .NET Framework, Version 2.0 aktualisieren.

## <a name="current-support-for-automatic-scaling"></a>Aktuelle Unterstützung für die automatische Skalierung

.NET Framework, Version 2.0 deutlich besser abschneidet zuvor enthaltene Einschränkungen durch die folgenden Änderungen eingeführt, um die automatische Skalierung von Windows Forms:

- Die Grundunterstützung für Skalierung wurde in die <xref:System.Windows.Forms.ContainerControl>-Klasse verschoben, sodass Formulare, systemeigene zusammengesetzte Steuerelemente und Benutzersteuerelemente eine einheitliche Skalierungsunterstützung haben. Die neuen Member <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> und <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> wurden hinzugefügt.

- Die <xref:System.Windows.Forms.Control>-Klasse hat außerdem mehrere neue Member, die ihre Mitwirkung an der Skalierung und die Unterstützung der gemischten Skalierung im selben Formular ermöglichen. Insbesondere die Member <xref:System.Windows.Forms.Control.Scale%2A>, <xref:System.Windows.Forms.Control.ScaleChildren%2A> und <xref:System.Windows.Forms.Control.GetScaledBounds%2A> unterstützen die Skalierung.

- Unterstützung für Skalierung auf Basis der Bildschirmauflösung wurde hinzugefügt, um die Unterstützung der Systemschriftarten zu ergänzen, wie dies durch die <xref:System.Windows.Forms.AutoScaleMode>-Enumeration definiert ist. Dieser Modus ist mit der automatischen Skalierung kompatibel, die von [!INCLUDE[compact](../../../includes/compact-md.md)] unterstützt wird, wodurch eine einfachere Anwendungsmigration ermöglicht wird.

- Kompatibilität mit Layout-Managern wie <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel> wurde der Implementierung der automatischen Skalierung hinzugefügt.

- Skalierungsfaktoren werden jetzt als Gleitkommawerte dargestellt, wozu üblicherweise die <xref:System.Drawing.SizeF>-Struktur verwendet wird, sodass Rundungsfehler so gut wie eliminiert sind.

> [!CAUTION]
> Beliebige Kombinationen aus DPI- und Schriftartskalierungsmodi werden nicht unterstützt. Obwohl Sie ein Benutzersteuerelement mithilfe eines Modus (z. B. DPI) skalieren und ohne Probleme auf einem Formular platzieren können, für das ein anderer Modus (Schriftart) verwendet wird, kann es zu unerwarteten Ergebnissen kommen, wenn Sie ein Grundformular in einem Modus mit einem abgeleiteten Formular in einem anderen Modus mischen.

### <a name="automatic-scaling-in-action"></a>Automatische Skalierung in Aktion

Windows Forms verwendet jetzt die folgende Logik, um Formulare und deren Inhalte automatisch zu skalieren:

1. Zur Entwurfszeit speichert jede <xref:System.Windows.Forms.ContainerControl>-Instanz den Skalierungsmodus und ihre aktuelle Auflösung in der <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>- bzw. der <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>-Eigenschaft.

2. Zur Laufzeit wird die tatsächliche Auflösung in der <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A>-Eigenschaft gespeichert. Die <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A>-Eigenschaft berechnet dynamisch das Verhältnis zwischen der Laufzeit- und der Entwurfszeitskalierungsauflösung.

3. Wenn das Formular geladen wird und sich die Werte von <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> und <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> unterscheiden, wird die <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>-Methode aufgerufen, um das Steuerelement und dessen untergeordneten Elemente zu skalieren. Diese Methode übergeht das Layout und ruft die <xref:System.Windows.Forms.Control.Scale%2A>-Methode auf, um die tatsächliche Skalierung auszuführen. Danach wird der Wert von <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> aktualisiert, um weitere Skalierung zu vermeiden.

4. <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> wird auch in den folgenden Situationen automatisch aufgerufen:

    - Als Reaktion auf das <xref:System.Windows.Forms.Control.OnFontChanged%2A>-Ereignis, wenn der Skalierungsmodus gleich <xref:System.Windows.Forms.AutoScaleMode.Font> ist.

    - Wenn wieder das Layout des Containersteuerelements verwendet wird und eine Änderung in der <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>- oder der <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>-Eigenschaft erkannt wurde.

    - Wenn, wie soeben erwähnt, ein übergeordnetes <xref:System.Windows.Forms.ContainerControl> skaliert wird. Jedes Containersteuerelement muss seine untergeordneten Elemente mit seinen eigenen Skalierungsfaktoren skalieren, es darf dafür nicht den Faktor seines übergeordneten Containers verwenden.

5. Untergeordnete Steuerelemente können ihr Skalierungsverhalten auf mehrere Arten ändern:

    - Die <xref:System.Windows.Forms.Control.ScaleChildren%2A>-Eigenschaft kann überschrieben werden, um zu bestimmen, ob die untergeordneten Steuerelemente skaliert werden sollen oder nicht.

    - Die <xref:System.Windows.Forms.Control.GetScaledBounds%2A>-Methode kann überschrieben werden, um die Begrenzungen für die Skalierung des Steuerelements, aber nicht die Skalierungslogik anzupassen.

    - Die <xref:System.Windows.Forms.Control.ScaleControl%2A>-Methode kann überschrieben werden, um die Skalierungslogik für das aktuelle Steuerelement zu ändern.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
- [Rendering von Steuerelementen mit visuellen Stilen](./controls/rendering-controls-with-visual-styles.md)
- [Vorgehensweise: Verbessern der Leistung durch Vermeiden der automatischen Skalierung](./advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)
