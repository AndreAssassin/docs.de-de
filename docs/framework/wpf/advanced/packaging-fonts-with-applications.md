---
title: Verpacken von Schriftarten mit Anwendungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: fb91d4b413db512021b90f0d4ba3049fe7333601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773232"
---
# <a name="packaging-fonts-with-applications"></a>Verpacken von Schriftarten mit Anwendungen
Dieses Thema enthält eine Übersicht über das Verpacken von Schriftarten mit Ihrem [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung.  
  
> [!NOTE]
>  Wie die meisten Arten von Software werden Schriftartdateien eher lizenziert als verkauft. Lizenzen, die die Verwendung von Schriftarten steuern, sind von Anbieter zu Anbieter jedoch im Allgemeinen die meisten Lizenzen, darunter auch die Schriftarten unterschiedlich [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] bereitstellt, mit Anwendungen und [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], lassen sich nicht auf die Schriftarten eingebettet in Anwendungen oder auf andere sein neu verteilt. Deshalb liegt es in Ihrer Verantwortung als Entwickler sicherzustellen, dass Sie über die erforderlichen Lizenzrechte für alle Schriftarten verfügen, die Sie in eine Anwendung einbetten oder anderweitig verbreiten.  

<a name="introduction_to_packaging_fonts"></a>   
## <a name="introduction-to-packaging-fonts"></a>Einführung in das Verpacken von Schriftarten  
 Sie können Schriftarten problemlos als Ressourcen in Verpacken Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basierende Anwendungen zum Anzeigen von Text der Benutzeroberfläche und anderen Typen von Text-Inhalt. Die Schriftarten können getrennt von den Assemblydateien oder eingebettet in die Assemblydateien der Anwendung vorkommen. Sie können auch eine Schriftartenbibliothek nur für Ressourcen erstellen, auf die die Anwendung verweisen kann.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] und [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] Schriftarten ein Typflag, FsType, der angibt, für die schriftarteneinbettung Lizenzierung Rechte für die Schriftart enthalten. Dieses Typflag bezieht sich jedoch nur auf eingebettete Schriftarten, die in einem Dokument gespeichert sind, und nicht auf Schriftarten, die in eine Anwendung eingebettet sind. Können Sie abrufen, die für die schriftarteneinbettung Rechte für eine Schriftart durch das Erstellen einer <xref:System.Windows.Media.GlyphTypeface> -Objekt und verweisen auf die <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> Eigenschaft. Finden Sie im Abschnitt "OS/2 and Windows Metrics", der die [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/os2.htm) für Weitere Informationen zum FsType-Flag.  
  
 Die [Microsoft Typography](https://docs.microsoft.com/typography/) Website enthält Kontaktinformationen, mit denen Sie suchen Sie einen bestimmten Händler oder einen Händler für benutzerdefinierte Schriftarten zu finden.  
  
<a name="adding_fonts_as_content_items"></a>   
## <a name="adding-fonts-as-content-items"></a>Hinzufügen von Schriftarten als Inhaltselemente  
 Sie können Schriftarten als Projektinhaltselemente zu Ihrer Anwendung hinzufügen, die von den Assemblydateien der Anwendung getrennt sind. Dies bedeutet, dass Inhaltselemente nicht als Ressourcen in eine Assembly eingebettet werden. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Inhaltselemente definiert werden.  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 Um sicherzustellen, dass die Anwendung die Schriftarten zur Laufzeit verwenden kann, müssen die Schriftarten im Bereitstellungsverzeichnis der Anwendung zugänglich sein. Die `<CopyToOutputDirectory>` -Element in der Projektdatei der Anwendung können Sie die Schriftarten in das Bereitstellungsverzeichnis der Anwendung während des Buildprozesses automatisch zu kopieren. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten in das Bereitstellungsverzeichnis kopiert werden.  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie auf die Schriftart der Anwendung als Inhaltselement verwiesen wird. Das Inhaltselement, auf das verwiesen wird, muss sich im selben Verzeichnis wie die Assemblydateien der Anwendung befinden.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## <a name="adding-fonts-as-resource-items"></a>Hinzufügen von Schriftarten als Ressourcenelemente  
 Sie können Schriftarten als Projektressourcenelemente zu Ihrer Anwendung hinzufügen, die in die Assemblydateien der Anwendung eingebettet werden. Die Verwendung eines separaten Unterverzeichnisses für Ressourcen hilft beim Organisieren der Projektdateien der Anwendung. In der folgenden Beispielprojektdatei wird veranschaulicht, wie Schriftarten als Ressourcenelemente in einem separaten Unterverzeichnis definiert werden.  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  Wenn Sie Ihrer Anwendung Schriftarten als Ressourcen hinzufügen, stellen Sie sicher, dass beim Festlegen des der `<Resource>` -Element, und nicht die `<EmbeddedResource>` -Element in Ihrer Anwendung-Projektdatei. Die `<EmbeddedResource>` -Element für die Buildaktion wird nicht unterstützt.  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie auf die Schriftartenressourcen der Anwendung verwiesen wird.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a>Verweisen auf Schriftartenressourcenelemente aus Code  
 Um schriftartenressourcenelemente aus Code verweisen zu können, müssen Sie einen zweiteiligen schriftartenressourcenverweis angeben: die Basis [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; und den Speicherortverweis der Schriftart. Diese Werte werden verwendet, als Parameter für die <xref:System.Windows.Media.FontFamily.%23ctor%2A> Methode. Im folgenden Codebeispiel wird veranschaulicht, wie auf die schriftartenressourcen der der Anwendung im Projektunterverzeichnis `resources`.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 Die Basis [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] zählen das Unterverzeichnis der Anwendung, wo sich die schriftartenressource befindet. In diesem Fall der Verweis auf die Schriftart-Speicherort muss also kein Verzeichnis angeben, jedoch müsste ein vorangestelltes "`./`", womit die schriftartenressource im selben Verzeichnis angegeben, die von den Basis-ist [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Im folgenden Codebeispiel wird eine alternative Möglichkeit veranschaulicht, wie auf das Schriftartenressourcenelement verwiesen werden kann. Es entspricht dem vorherigen Codebeispiel.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a>Verweisen auf Schriftarten aus dem gleichen Anwendungsunterverzeichnis  
 Sie können Anwendungsinhalt und Ressourcendateien im selben benutzerdefinierten Unterverzeichnis Ihres Anwendungsprojekts platzieren. In der folgenden Beispielprojektdatei wird veranschaulicht, wie eine Inhaltsseite und Schriftartenressourcen im selben Unterverzeichnis definiert werden.  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Da sich Anwendungsinhalt und Schriftart im selben Unterverzeichnis befinden, ist der Schriftartenverweis relativ zum Anwendungsinhalt. In den folgenden Beispielen wird veranschaulicht, wie auf die Schriftartenressource der Anwendung verwiesen werden kann, wenn sich die Schriftart im selben Verzeichnis wie die Anwendung befindet.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a>Auflisten von Schriftarten in einer Anwendung  
 Zum Auflisten von Schriftarten als Ressourcenelemente in Ihrer Anwendung verwenden Sie entweder die <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> oder <xref:System.Windows.Media.Fonts.GetTypefaces%2A> Methode. Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> Methode zum Zurückgeben der Auflistung der <xref:System.Windows.Media.FontFamily> Objekte aus dem Speicherort der Schriftarten. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Fonts.GetTypefaces%2A> Methode zum Zurückgeben der Auflistung der <xref:System.Windows.Media.Typeface> Objekte aus dem Speicherort der Schriftarten. In diesem Fall enthält die Anwendung ein Unterverzeichnis mit dem Namen „Ressourcen“.  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## <a name="creating-a-font-resource-library"></a>Erstellen einer Schriftartenressourcenbibliothek  
 Sie können eine Bibliothek nur für Ressourcen erstellen, die ausschließlich Schriftarten enthält. In dieser Art von Bibliothek ist kein Code enthalten. Das Erstellen einer Bibliothek nur für Ressourcen dient häufig dem Entkoppeln von Ressourcen vom Anwendungscode, der sie verwendet. Dies ermöglicht außerdem, dass die Bibliotheksassembly in mehreren Anwendungsprojekten enthalten sein kann. In der folgenden Beispielprojektdatei werden die Hauptbestandteile einer Bibliothek nur für Ressourcen gezeigt.  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...  
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a>Verweisen auf eine Schriftart in einer Ressourcenbibliothek  
 Um aus Ihrer Anwendung auf eine Schriftart in einer Ressourcenbibliothek zu verweisen, müssen Sie dem Verweis auf die Schriftart den Namen der Bibliotheksassembly voranstellen. In diesem Fall ist die Schriftartenressourcenassembly „FontLibrary“. Verwenden Sie ein Semikolon (;), um den Assemblynamen vom Verweis innerhalb der Assembly zu trennen. Durch Hinzufügen des Schlüsselworts „Component“ gefolgt vom Verweis auf den Namen der Schriftart wird der Verweis auf die Ressource der Schriftartenbibliothek vervollständigt. Im folgenden Codebeispiel wird veranschaulicht, wie auf eine Schriftart in einer Ressourcenbibliotheksassembly verwiesen wird.  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  Dieses SDK enthält eine Reihe von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten, mit denen Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen. Die Schriftarten werden in einer Bibliothek nur für Ressourcen definiert. Weitere Informationen finden Sie unter [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>   
## <a name="limitations-on-font-usage"></a>Einschränkungen der Verwendung von Schriftarten  
 Die folgende Liste beschreibt einige Einschränkungen für das Verpacken und die Verwendung von Schriftarten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen:  
  
- **Berechtigungsbits für die Schriftarteneinbettung:** Von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen werden keine Berechtigungsbits für die Schriftarteneinbettung überprüft oder durchgesetzt. Finden Sie unter den [Einführung in das Verpacken von Schriftarten](#introduction_to_packaging_fonts) Abschnitt, um weitere Informationen.  
  
- **Site der Ursprungsschriftarten:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen lassen sich nicht auf einen Schriftartverweis auf einen HTTP- oder FTP- [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  
  
- **Absoluter URI mit Pack: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen nicht erlauben Ihnen die Erstellung einer <xref:System.Windows.Media.FontFamily> -Objekt programmgesteuert mit "Pack:" als Bestandteil des absoluten [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Verweis auf eine Schriftart. Z. B. `"pack://application:,,,/resources/#Pericles Light"` ist ein ungültiger schriftartenverweis.  
  
- **Automatische schriftarteneinbettung:** Während der Entwurfszeit besteht keine Unterstützung für die Suche nach einer Anwendung die Verwendung von Schriftarten und automatische Einbetten der Schriftarten in die Ressourcen der Anwendung zur Verfügung.  
  
- **Schriftartteilmengen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen keine Erstellung von Schriftartteilmengen für Dokumente ohne festes Format.  
  
- Bei einem falschen Verweis greift die Anwendung auf eine verfügbare Schriftart zurück.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [Microsoft-Typografie: Links, Neuigkeiten und Kontakte](https://docs.microsoft.com/typography/)
- [OpenType-Spezifikation](https://www.microsoft.com/typography/otspec/)
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md)
