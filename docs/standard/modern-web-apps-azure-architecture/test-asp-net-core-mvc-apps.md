---
title: Testen von ASP.NET Core MVC-Apps
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Testen von ASP.NET Core MVC-Apps
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 941c73f9a8b7b4c4336adfaec45775feec738f51
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804722"
---
# <a name="test-aspnet-core-mvc-apps"></a><span data-ttu-id="0d8bc-103">Testen von ASP.NET Core MVC-Apps</span><span class="sxs-lookup"><span data-stu-id="0d8bc-103">Test ASP.NET Core MVC apps</span></span>

> <span data-ttu-id="0d8bc-104">*„Wenn es Ihnen nicht gefällt, Komponententests für Ihr Produkt auszuführen, ist es sehr wahrscheinlich, dass es Ihren Kunden auch nicht gefallen wird.“*</span><span class="sxs-lookup"><span data-stu-id="0d8bc-104">*"If you don't like unit testing your product, most likely your customers won't like to test it, either."*</span></span>
 > <span data-ttu-id="0d8bc-105">\_–Anonym</span><span class="sxs-lookup"><span data-stu-id="0d8bc-105">\_- Anonymous-</span></span>

<span data-ttu-id="0d8bc-106">Software von beliebiger Komplexität kann aufgrund von Änderungen auf unerwartete Weisen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-106">Software of any complexity can fail in unexpected ways in response to changes.</span></span> <span data-ttu-id="0d8bc-107">Daher ist es erforderlich, Anwendungen auf Änderungen zu testen, mit Ausnahme von unbedeutenden (bzw. weniger wichtigen) Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-107">Thus, testing after making changes is required for all but the most trivial (or least critical) applications.</span></span> <span data-ttu-id="0d8bc-108">Manuelle Tests sind die langsamste, unzuverlässigste und aufwendigste Möglichkeit zum Testen von Software.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-108">Manual testing is the slowest, least reliable, most expensive way to test software.</span></span> <span data-ttu-id="0d8bc-109">Leider können diese die einzige verfügbare Methode sein, wenn Anwendungen nicht zum Testen entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-109">Unfortunately, if applications aren't designed to be testable, it can be the only means available.</span></span> <span data-ttu-id="0d8bc-110">Anwendungen, die nach den folgenden, in [Kapitel 4](architectural-principles.md) beschriebenen Architekturprinzipien geschrieben wurden, sollten mit Komponententests testbar sein, und ASP.NET Core-Anwendungen sollten zusätzlich die automatisierte Integration und Funktionstests unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-110">Applications written following the architectural principles laid out in [chapter 4](architectural-principles.md) should be unit testable, and ASP.NET Core applications support automated integration and functional testing as well.</span></span>

## <a name="kinds-of-automated-tests"></a><span data-ttu-id="0d8bc-111">Arten von automatisierten Tests</span><span class="sxs-lookup"><span data-stu-id="0d8bc-111">Kinds of automated tests</span></span>

<span data-ttu-id="0d8bc-112">Es gibt viele Arten von automatisierten Tests für Softwareanwendungen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-112">There are many kinds of automated tests for software applications.</span></span> <span data-ttu-id="0d8bc-113">Der einfachste, spezifischste Test ist der Komponententest.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-113">The simplest, lowest level test is the unit test.</span></span> <span data-ttu-id="0d8bc-114">Integrationstests und Funktionstests sind etwas allgemeiner.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-114">At a slightly higher level there are integration tests and functional tests.</span></span> <span data-ttu-id="0d8bc-115">Andere Arten von Tests werden in dieser Dokumentation nicht behandelt, z.B. UI-Tests, Auslastungstests, Belastungstests und Buildakzeptanztests.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-115">Other kinds of tests, like UI tests, load tests, stress tests, and smoke tests, are beyond the scope of this document.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="0d8bc-116">Komponententests</span><span class="sxs-lookup"><span data-stu-id="0d8bc-116">Unit tests</span></span>

<span data-ttu-id="0d8bc-117">Ein Komponententest überprüft einen einzelnen Teil der Logik Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-117">A unit test tests a single part of your application's logic.</span></span> <span data-ttu-id="0d8bc-118">Man kann diesen Test genauer beschreiben, indem man aufführt, was er nicht umfasst.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-118">One can further describe it by listing some of the things that it isn't.</span></span> <span data-ttu-id="0d8bc-119">Ein Komponententest überprüft nicht, wie Ihr Code mit Abhängigkeiten oder Infrastruktur interagiert. Dafür gibt es Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-119">A unit test doesn't test how your code works with dependencies or infrastructure – that's what integration tests are for.</span></span> <span data-ttu-id="0d8bc-120">Ein Komponententest überprüft nicht das Framework, auf dem Ihr Code geschrieben wurde. Sie sollten davon ausgehen, dass dieses funktioniert. Wenn es nicht funktioniert, melden Sie den Fehler und schreiben eine Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-120">A unit test doesn't test the framework your code is written on – you should assume it works or, if you find it doesn't, file a bug and code a workaround.</span></span> <span data-ttu-id="0d8bc-121">Komponententests werden vollständig im Arbeitsspeicher und im Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-121">A unit test runs completely in memory and in process.</span></span> <span data-ttu-id="0d8bc-122">Sie kommunizieren nicht mit dem Dateisystem, dem Netzwerk oder einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-122">It doesn't communicate with the file system, the network, or a database.</span></span> <span data-ttu-id="0d8bc-123">Komponententests sollten Ihren Code nur überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-123">Unit tests should only test your code.</span></span>

<span data-ttu-id="0d8bc-124">Aufgrund der Tatsache, dass Komponententests nur eine einzelne Komponente Ihres Codes überprüfen und über keine externen Abhängigkeiten verfügen, werden diese sehr schnell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-124">Unit tests, by virtue of the fact that they test only a single unit of your code, with no external dependencies, should execute extremely quickly.</span></span> <span data-ttu-id="0d8bc-125">Daher sollten Sie eine Testsammlung aus Hunderten von Komponententests in wenigen Sekunden ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-125">Thus, you should be able to run test suites of hundreds of unit tests in a few seconds.</span></span> <span data-ttu-id="0d8bc-126">Führen Sie diese regelmäßig aus, im Idealfall vor jedem Push an ein öffentliches Repository für die Quellcodeverwaltung und insbesondere vor jedem automatisierten Buildvorgang auf Ihrem Buildserver.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-126">Run them frequently, ideally before every push to a shared source control repository, and certainly with every automated build on your build server.</span></span>

### <a name="integration-tests"></a><span data-ttu-id="0d8bc-127">Integrationstests</span><span class="sxs-lookup"><span data-stu-id="0d8bc-127">Integration tests</span></span>

<span data-ttu-id="0d8bc-128">Obwohl es eine gute Idee ist, Code zu kapseln, der mit Infrastruktur interagiert (z.B. Datenbanken und Dateisysteme), wird ein Teil des Codes übrig bleiben, den Sie wahrscheinlich testen möchten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-128">Although it's a good idea to encapsulate your code that interacts with infrastructure like databases and file systems, you will still have some of that code, and you will probably want to test it.</span></span> <span data-ttu-id="0d8bc-129">Darüber hinaus sollten Sie sicherstellen, dass die Schichten Ihres Codes wie erwartet interagieren, wenn die Abhängigkeiten Ihrer Anwendung vollständig aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-129">Additionally, you should verify that your code's layers interact as you expect when your application's dependencies are fully resolved.</span></span> <span data-ttu-id="0d8bc-130">Hierfür sind Integrationstests verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-130">This is the responsibility of integration tests.</span></span> <span data-ttu-id="0d8bc-131">Integrationstests sind langsamer und schwieriger einzurichten als Komponententests, da sie oft von externen Abhängigkeiten und Infrastrukturen abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-131">Integration tests tend to be slower and more difficult to set up than unit tests, because they often depend on external dependencies and infrastructure.</span></span> <span data-ttu-id="0d8bc-132">Daher sollten Sie es vermeiden, Szenarios zu testen, die Tests mit Komponententests in Integrationstests darstellen könnten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-132">Thus, you should avoid testing things that could be tested with unit tests in integration tests.</span></span> <span data-ttu-id="0d8bc-133">Wenn Sie ein bestimmtes Szenario mit einem Komponententest testen können, sollten Sie dieses Szenario mit einem Komponententest testen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-133">If you can test a given scenario with a unit test, you should test it with a unit test.</span></span> <span data-ttu-id="0d8bc-134">Wenn dies nicht möglich ist, sollten Sie einen Integrationstest verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-134">If you can't, then consider using an integration test.</span></span>

<span data-ttu-id="0d8bc-135">Integrationstests verfügen meistens über komplexere Setup- und Nachbereitungsprozeduren als Komponententests.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-135">Integration tests will often have more complex setup and teardown procedures than unit tests.</span></span> <span data-ttu-id="0d8bc-136">Ein Integrationstest, der beispielsweise auf eine Datenbank angewendet wird, benötigt eine Möglichkeit, die Datenbank in einen bekannten Zustand zurückzusetzen, bevor jeder Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-136">For example, an integration test that goes against an actual database will need a way to return the database to a known state before each test run.</span></span> <span data-ttu-id="0d8bc-137">Wenn neue Tests hinzugefügt werden und das Datenbankschema für die Produktion sich weiterentwickelt, werden die Testskripts größer und komplexer.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-137">As new tests are added and the production database schema evolves, these test scripts will tend to grow in size and complexity.</span></span> <span data-ttu-id="0d8bc-138">In vielen großen Systemen ist es unpraktisch, vollständige Testsammlungen auf den Arbeitsstationen von Entwicklern auszuführen, bevor Änderungen in die Quellcodeverwaltung eingetragen werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-138">In many large systems, it is impractical to run full suites of integration tests on developer workstations before checking in changes to shared source control.</span></span> <span data-ttu-id="0d8bc-139">In diesen Fällen können Integrationstests auf einem Buildserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-139">In these cases, integration tests may be run on a build server.</span></span>

<span data-ttu-id="0d8bc-140">Die Implementierungsklasse `LocalFileImageService` implementiert die Logik zum Abrufen und Zurückgeben von Bytes einer Bilddatei aus einem bestimmten Ordner, dem eine ID zugewiesen wurde:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-140">The `LocalFileImageService` implementation class implements the logic for fetching and returning the bytes of an image file from a particular folder given an id:</span></span>

```csharp
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
        }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

### <a name="functional-tests"></a><span data-ttu-id="0d8bc-141">Funktionstests</span><span class="sxs-lookup"><span data-stu-id="0d8bc-141">Functional tests</span></span>

<span data-ttu-id="0d8bc-142">Integrationstests werden aus der Perspektive des Entwicklers geschrieben, um sicherzustellen, dass einige der Systemkomponenten ordnungsgemäß interagieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-142">Integration tests are written from the perspective of the developer, to verify that some components of the system work correctly together.</span></span> <span data-ttu-id="0d8bc-143">Funktionstests werden aus der Perspektive des Benutzers geschrieben, um die Richtigkeit des Systems basierend auf den Anforderungen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-143">Functional tests are written from the perspective of the user, and verify the correctness of the system based on its requirements.</span></span> <span data-ttu-id="0d8bc-144">Der folgende Auszug bietet eine nützliche Analogie zum Vergleich von Funktionstests und Komponententests:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-144">The following excerpt offers a useful analogy for how to think about functional tests, compared to unit tests:</span></span>

> <span data-ttu-id="0d8bc-145">„Oft wird das Entwickeln eines Systems mit dem Erbauen eines Hauses verglichen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-145">"Many times the development of a system is likened to the building of a house.</span></span> <span data-ttu-id="0d8bc-146">Auch wenn diese Analogie nicht ganz richtig ist, können wir sie verwenden, um den Unterschied zwischen Komponententests und Funktionstests besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-146">While this analogy isn't quite correct, we can extend it for the purposes of understanding the difference between unit and functional tests.</span></span> <span data-ttu-id="0d8bc-147">Komponententests entsprechen einem Bauinspektor, der die Baustelle eines Hauses begutachtet.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-147">Unit testing is analogous to a building inspector visiting a house's construction site.</span></span> <span data-ttu-id="0d8bc-148">Er konzentriert sich auf die verschiedenen internen Systeme des Hauses, also das Gebäudefundament, den Rohbau, die Stromversorgung, die sanitären Einrichtungen, usw.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-148">He is focused on the various internal systems of the house, the foundation, framing, electrical, plumbing, and so on.</span></span> <span data-ttu-id="0d8bc-149">Er stellt sicher (überprüft), dass die einzelnen Teile des Hauses voll funktionsfähig und sicher sind, d.h., dass sie der Bauordnung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-149">He ensures (tests) that the parts of the house will work correctly and safely, that is, meet the building code.</span></span> <span data-ttu-id="0d8bc-150">Funktionstests entsprechen in diesem Szenario dem Hauseigentümer, der ebenfalls diese Baustelle besucht.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-150">Functional tests in this scenario are analogous to the homeowner visiting this same construction site.</span></span> <span data-ttu-id="0d8bc-151">Er geht davon aus, dass die internen Systeme funktionieren und der Bauinspektor seine Arbeit macht.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-151">He assumes that the internal systems will behave appropriately, that the building inspector is performing his task.</span></span> <span data-ttu-id="0d8bc-152">Der Hauseigentümer konzentriert sich darauf, wie es sein wird, in diesem Haus zu leben.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-152">The homeowner is focused on what it will be like to live in this house.</span></span> <span data-ttu-id="0d8bc-153">Er kümmert sich zum Beispiel darum, wie das Haus aussieht, ob die verschiedenen Räume die passende Größe haben, ob das Haus den Bedürfnissen einer Familie gerecht wird, und ob die Fenster eine gute Ausrichtung dafür haben, die Morgensonne herein zu lassen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-153">He is concerned with how the house looks, are the various rooms a comfortable size, does the house fit the family's needs, are the windows in a good spot to catch the morning sun.</span></span> <span data-ttu-id="0d8bc-154">Der Hauseigentümer führt Funktionstests am Haus durch.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-154">The homeowner is performing functional tests on the house.</span></span> <span data-ttu-id="0d8bc-155">Seine Perspektive ist die des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-155">He has the user's perspective.</span></span> <span data-ttu-id="0d8bc-156">Der Bauinspektor führt Komponententests am Haus durch.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-156">The building inspector is performing unit tests on the house.</span></span> <span data-ttu-id="0d8bc-157">Seine Perspektive ist die des Entwicklers.“</span><span class="sxs-lookup"><span data-stu-id="0d8bc-157">He has the builder's perspective."</span></span>

<span data-ttu-id="0d8bc-158">Quelle: [Unit Testing versus Functional Tests (Vergleich von Komponententests und Funktionstests)](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span><span class="sxs-lookup"><span data-stu-id="0d8bc-158">Source: [Unit Testing versus Functional Tests](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span></span>

<span data-ttu-id="0d8bc-159">Unter Entwicklern sagt man gern: „Als Entwickler machen wir zwei Fehler: wir erstellen falsch, oder wir erstellen das Falsche.“</span><span class="sxs-lookup"><span data-stu-id="0d8bc-159">I'm fond of saying "As developers, we fail in two ways: we build the thing wrong, or we build the wrong thing."</span></span> <span data-ttu-id="0d8bc-160">Mit Komponententests stellen Sie sicher, dass Sie richtig erstellen. Funktionstests stellen sicher, dass Sie das Richtige erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-160">Unit tests ensure you are building the thing right; functional tests ensure you are building the right thing.</span></span>

<span data-ttu-id="0d8bc-161">Da Funktionstest auf der Systemebene ausgeführt werden, erfordern sie ein gewisses Maß an Automatisierung der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-161">Since functional tests operate at the system level, they may require some degree of UI automation.</span></span> <span data-ttu-id="0d8bc-162">Wie Integrationstests arbeiten auch die Funktionstests in der Regel mit einer Art Testinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-162">Like integration tests, they usually work with some kind of test infrastructure as well.</span></span> <span data-ttu-id="0d8bc-163">Dadurch werden sie langsamer und anfälliger für Fehler als Komponententests und Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-163">This makes them slower and more brittle than unit and integration tests.</span></span> <span data-ttu-id="0d8bc-164">Sie sollten nur so viele Funktionstests anwenden, wie Sie benötigen, um sich sicher zu sein, dass das System sich so verhält, wie Benutzer es erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-164">You should have only as many functional tests as you need to be confident the system is behaving as users expect.</span></span>

### <a name="testing-pyramid"></a><span data-ttu-id="0d8bc-165">Testpyramide</span><span class="sxs-lookup"><span data-stu-id="0d8bc-165">Testing Pyramid</span></span>

<span data-ttu-id="0d8bc-166">Martin Fowler schrieb über die Testpyramide. Ein Beispiel dafür wird in Abbildung 9–1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-166">Martin Fowler wrote about the testing pyramid, an example of which is shown in Figure 9-1.</span></span>

![](./media/image9-1.png)

<span data-ttu-id="0d8bc-167">Abbildung 9–1: Testpyramide</span><span class="sxs-lookup"><span data-stu-id="0d8bc-167">Figure 9-1 Testing Pyramid</span></span>

<span data-ttu-id="0d8bc-168">Die verschiedenen Schichten der Pyramide und ihre Größen stellen verschiedene Arten von Tests dar, und wie viele davon Sie für Ihre Anwendung schreiben sollten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-168">The different layers of the pyramid, and their relative sizes, represent different kinds of tests and how many you should write for your application.</span></span> <span data-ttu-id="0d8bc-169">Wie Sie sehen können, wird empfohlen, eine große Basis aus Komponententests zu verwenden, die von einer kleineren Menge von Integrationstests und einer noch kleineren Menge von Funktionstests unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-169">As you can see, the recommendation is to have a large base of unit tests, supported by a smaller layer of integration tests, with an even smaller layer of functional tests.</span></span> <span data-ttu-id="0d8bc-170">Im Idealfall sollte jede Schicht nur aus Tests bestehen, die auf niedrigeren Schichten nicht ordnungsgemäß ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-170">Each layer should ideally only have tests in it that cannot be performed adequately at a lower layer.</span></span> <span data-ttu-id="0d8bc-171">Behalten Sie die Testpyramide im Hinterkopf, wenn Sie sich entscheiden, welche Art von Test Sie für ein bestimmtes Szenario benötigen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-171">Keep the testing pyramid in mind when you are trying to decide which kind of test you need for a particular scenario.</span></span>

### <a name="what-to-test"></a><span data-ttu-id="0d8bc-172">Der Testgegenstand</span><span class="sxs-lookup"><span data-stu-id="0d8bc-172">What to test</span></span>

<span data-ttu-id="0d8bc-173">Herauszufinden, was getestet werden sollte, ist ein häufiges Problem für Entwickler, die noch unerfahren im Schreiben von automatisierten Tests sind.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-173">A common problem for developers who are inexperienced with writing automated tests is coming up with what to test.</span></span> <span data-ttu-id="0d8bc-174">Ein guter Startpunkt ist das Testen der bedingten Logik.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-174">A good starting point is to test conditional logic.</span></span> <span data-ttu-id="0d8bc-175">An jeder Stelle, an der eine Methode mit einem Verhalten vorhanden ist, das auf einer Bedingungsanweisung basiert (if-else, switch, usw.), sollten Sie ein paar Tests erstellen, die das richtige Verhalten für bestimmte Bedingungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-175">Anywhere you have a method with behavior that changes based on a conditional statement (if-else, switch, etc.), you should be able to come up at least a couple of tests that confirm the correct behavior for certain conditions.</span></span> <span data-ttu-id="0d8bc-176">Wenn Ihr Code über Fehlerbedingungen verfügt, sollten Sie mindestens einen Test für den „besten Pfad“ durch den Code (ohne Fehler) und einen Test für den „schlechtesten Pfad“ (mit Fehlern und ungewohnten Ergebnissen) verwenden, um sicherzustellen, dass Ihre Anwendung auf Fehler wie erwartet reagiert.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-176">If your code has error conditions, it's good to write at least one test for the "happy path" through the code (with no errors), and at least one test for the "sad path" (with errors or atypical results) to confirm your application behaves as expected in the face of errors.</span></span> <span data-ttu-id="0d8bc-177">Letztendlich sollten Sie sich darauf konzentrieren, Dinge zu testen, die fehlschlagen können, anstatt sich auf Metriken wie Code Coverage zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-177">Finally, try to focus on testing things that can fail, rather than focusing on metrics like code coverage.</span></span> <span data-ttu-id="0d8bc-178">Allgemein ist mehr Code Coverage besser als zu wenig.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-178">More code coverage is better than less, generally.</span></span> <span data-ttu-id="0d8bc-179">Allerdings können Sie Ihre Zeit sinnvoller nutzen, wenn Sie ein paar weitere Tests für eine komplexe und unternehmenskritische Methode schreiben, anstatt Tests für Auto-Eigenschaften zu schreiben, um die Code Coverage-Metrik zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-179">However, writing a few more tests of a very complex and business-critical method is usually a better use of time than writing tests for auto-properties just to improve test code coverage metrics.</span></span>

## <a name="organizing-test-projects"></a><span data-ttu-id="0d8bc-180">Organisieren von Testprojekten</span><span class="sxs-lookup"><span data-stu-id="0d8bc-180">Organizing test projects</span></span>

<span data-ttu-id="0d8bc-181">Sie können Testprojekte so organisieren, wie es für Sie am besten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-181">Test projects can be organized however works best for you.</span></span> <span data-ttu-id="0d8bc-182">Es kann hilfreich sein, Tests je nach Typ (Komponententest, Integrationstest) und Testsubjekt (Projekt, Namespace) voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-182">It's a good idea to separate tests by type (unit test, integration test) and by what they are testing (by project, by namespace).</span></span> <span data-ttu-id="0d8bc-183">Ob diese Trennung aus Ordnern in einem einzelnen Testprojekt oder mehreren Testprojekten besteht, ist eine Entwurfsentscheidung.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-183">Whether this separation consists of folders within a single test project, or multiple test projects, is a design decision.</span></span> <span data-ttu-id="0d8bc-184">Ein einzelnes Projekt ist am einfachsten. Für ein großes Projekt mit vielen Tests sollten Sie mehrere verschiedene Testprojekte besitzen, um verschiedene Testgruppen einfacher ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-184">One project is simplest, but for large projects with many tests, or in order to more easily run different sets of tests, you might want to have several different test projects.</span></span> <span data-ttu-id="0d8bc-185">Viele Teams organisieren Ihre Testprojekte basierend auf dem Projekt, das sie überprüfen. Dies resultiert bei Anwendungen mit einer größeren Anzahl von Projekten in einer großen Anzahl von Testprojekten, insbesondere dann, wenn Sie diese immer noch nach der Art von Tests in jedem Projekt sortieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-185">Many teams organize test projects based on the project they are testing, which for applications with more than a few projects can result in a large number of test projects, especially if you still break these down according to what kind of tests are in each project.</span></span> <span data-ttu-id="0d8bc-186">Ein Kompromiss für diesen Ansatz ist, ein Projekt mit Ordnern in den Testprojekten pro Art von Test für jede Anwendung zu besitzen, die das Projekt und die Klasse angeben, die geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-186">A compromise approach is to have one project per kind of test, per application, with folders inside the test projects to indicate the project (and class) being tested.</span></span>

<span data-ttu-id="0d8bc-187">Eine gängige Methode ist, die Anwendungsprojekte in einem SRC-Ordner und die Testprojekte der Anwendung im parallelen Ordner „Tests“ zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-187">A common approach is to organize the application projects under a ‘src' folder, and the application's test projects under a parallel ‘tests' folder.</span></span> <span data-ttu-id="0d8bc-188">Sie können entsprechende Projektmappenordner in Visual Studio anlegen, wenn Sie diese Organisierung hilfreich finden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-188">You can create matching solution folders in Visual Studio, if you find this organization useful.</span></span>

![](./media/image9-2.png)

<span data-ttu-id="0d8bc-189">Abbildung 9–2: Organisierung der Tests in Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="0d8bc-189">Figure 9-2 Test organization in your solution</span></span>

<span data-ttu-id="0d8bc-190">Sie können das Testframework verwenden, das Sie bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-190">You can use whichever test framework you prefer.</span></span> <span data-ttu-id="0d8bc-191">Das xUnit-Framework funktioniert gut und wird für alle Tests für ASP.NET Core und EF Core verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-191">The xUnit framework works well and is what all of the ASP.NET Core and EF Core tests are written in.</span></span> <span data-ttu-id="0d8bc-192">Mit der in Abbildung 9–3 gezeigten Vorlage können Sie ein xUnit-Testprojekt in Visual Studio oder über die CLI mithilfe des Befehls „dotnet new xunit“ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-192">You can add an xUnit test project in Visual Studio using the template shown in Figure 9-3, or from the CLI using dotnet new xunit.</span></span>

![](./media/image9-3.png)

<span data-ttu-id="0d8bc-193">Abbildung 9–3: xUnit-Testprojekt in Visual Studio hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0d8bc-193">Figure 9-3 Add an xUnit Test Project in Visual Studio</span></span>

### <a name="test-naming"></a><span data-ttu-id="0d8bc-194">Benennen von Tests</span><span class="sxs-lookup"><span data-stu-id="0d8bc-194">Test naming</span></span>

<span data-ttu-id="0d8bc-195">Sie sollten Ihren Tests konsistente Namen zuweisen, die angeben, was jeder Test bewirkt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-195">You should name your tests in a consistent fashion, with names that indicate what each test does.</span></span> <span data-ttu-id="0d8bc-196">Ein effektiver Ansatz ist, Testklassen nach der Klasse und Methode zu benennen, die sie testen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-196">One approach I've had great success with is to name test classes according to the class and method they are testing.</span></span> <span data-ttu-id="0d8bc-197">Dies resultiert in vielen kleinen Testklassen, verdeutlicht jedoch, wofür jeder Test zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-197">This results in many small test classes, but it makes it extremely clear what each test is responsible for.</span></span> <span data-ttu-id="0d8bc-198">Mit dem eingerichteten Testklassennamen zum Identifizieren der Klasse und Methode, die getestet werden, kann der Testmethodenname dafür verwendet werden, das zu testende Verhalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-198">With the test class name set up to identify the class and method to be tested, the test method name can be used to specify the behavior being tested.</span></span> <span data-ttu-id="0d8bc-199">Dies sollte das erwartete Verhalten und alle Eingaben oder Annahmen einschließen, die dieses Verhalten verursachen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-199">This should include the expected behavior and any inputs or assumptions that should yield this behavior.</span></span> <span data-ttu-id="0d8bc-200">Beispiele für Testnamen:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-200">Some example test names:</span></span>

- `CatalogControllerGetImage.CallsImageServiceWithId`

- `CatalogControllerGetImage.LogsWarningGivenImageMissingException`

- `CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess`

- `CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException`

<span data-ttu-id="0d8bc-201">Eine Variante dieses Ansatzes beendet jeden Testklassennamen mit „Should“ und ändert die Zeitform:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-201">A variation of this approach ends each test class name with "Should" and modifies the tense slightly:</span></span>

- <span data-ttu-id="0d8bc-202">`CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`</span><span class="sxs-lookup"><span data-stu-id="0d8bc-202">`CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`</span></span>

- <span data-ttu-id="0d8bc-203">`CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`</span><span class="sxs-lookup"><span data-stu-id="0d8bc-203">`CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`</span></span>

<span data-ttu-id="0d8bc-204">Einige Teams finden den zweiten Ansatz für die Benennung klarer, obwohl er etwas ausführlicher ist.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-204">Some teams find the second naming approach clearer, though slightly more verbose.</span></span> <span data-ttu-id="0d8bc-205">In jedem Fall sollten Sie versuchen, eine Namenskonvention zu verwenden, die einen Einblick zum Verhalten des Tests bietet, damit klar ist, welche Fälle fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-205">In any case, try to use a naming convention that provides insight into test behavior, so that when one or more tests fail, it's obvious from their names what cases have failed.</span></span> <span data-ttu-id="0d8bc-206">Vermeiden Sie ungenaue Namen, z.B. „ControllerTests.Test1“, da diese keine Informationen bieten, wenn diese in den Testergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-206">Avoid naming you tests vaguely, such as ControllerTests.Test1, as these offer no value when you see them in test results.</span></span>

<span data-ttu-id="0d8bc-207">Wenn Sie eine Namenskonvention befolgen, die viele kleine Testklassen produziert, wie eine der oben genannten, empfiehlt es sich, Ihre Tests auch mit Ordnern und Namespaces zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-207">If you follow a naming convention like the one above that produces many small test classes, it's a good idea to further organize your tests using folders and namespaces.</span></span> <span data-ttu-id="0d8bc-208">Abbildung 9–4 veranschaulicht einen Ansatz zum Organisieren von Tests mit Ordnern in mehreren Testprojekten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-208">Figure 9-4 shows one approach to organizing tests by folder within several test projects.</span></span>

![](./media/image9-4.png)

<span data-ttu-id="0d8bc-209">**Abbildung 9–4**</span><span class="sxs-lookup"><span data-stu-id="0d8bc-209">**Figure 9-4.**</span></span> <span data-ttu-id="0d8bc-210">Organisieren von Testklassen in Ordnern, basierend auf der Klasse, die getestet wird.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-210">Organizing test classes by folder based on class being tested.</span></span>

<span data-ttu-id="0d8bc-211">Wenn viele Methoden (d.h. auch viele Testklassen) in einer Anwendungsklasse getestet werden sollen, kann es sinnvoll sein, diese in einem Ordner zu platzieren, der zu der Anwendungsklasse gehört.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-211">Of course, if a particular application class has many methods being tested (and thus many test classes), it may make sense to place these in a folder corresponding to the application class.</span></span> <span data-ttu-id="0d8bc-212">Diese Organisierung gleicht der Organisierung von Dateien in Ordnern.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-212">This organization is no different than how you might organize files into folders elsewhere.</span></span> <span data-ttu-id="0d8bc-213">Wenn mehr als drei oder vier zusammengehörende Dateien in einem Ordner mit vielen anderen Dateien vorhanden sind, empfiehlt es sich, für diese einen Unterordner anzulegen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-213">If you have more than three or four related files in a folder containing many other files, it's often helpful to move them into their own subfolder.</span></span>

## <a name="unit-testing-aspnet-core-apps"></a><span data-ttu-id="0d8bc-214">Komponententests für ASP.NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="0d8bc-214">Unit testing ASP.NET Core apps</span></span>

<span data-ttu-id="0d8bc-215">In einer gut entworfenen ASP.NET Core-Anwendung ist der Großteil der Komplexitäts- und Geschäftslogik in Geschäftselementen und einer Vielzahl von Diensten gekapselt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-215">In a well-designed ASP.NET Core application, most of the complexity and business logic will be encapsulated in business entities and a variety of services.</span></span> <span data-ttu-id="0d8bc-216">Die ASP.NET Core MVC-App selbst sollte mitsamt ihrer Controller, Filter, ViewModels und Ansichten nur wenige Komponententests benötigen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-216">The ASP.NET Core MVC app itself, with its controllers, filters, viewmodels, and views, should require very few unit tests.</span></span> <span data-ttu-id="0d8bc-217">Viele der Funktionen einer bestimmten Aktion befinden sich außerhalb der Aktionsmethode.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-217">Much of the functionality of a given action lies outside the action method itself.</span></span> <span data-ttu-id="0d8bc-218">Ob das Routing oder die globale Fehlerbehandlung ordnungsgemäß funktioniert, kann mit einem Komponententest nicht effektiv geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-218">Testing whether routing works correctly, or global error handling, cannot be done effectively with a unit test.</span></span> <span data-ttu-id="0d8bc-219">Ebenso können alle Filter, einschließlich der Modellvalidierung und die Authentifizierung sowie die Autorisierungsfilter nicht mit Komponententests geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-219">Likewise, any filters, including model validation and authentication and authorization filters, cannot be unit tested.</span></span> <span data-ttu-id="0d8bc-220">Ohne diese Quellen für Verhalten sollten die meisten Aktionsmethoden unbedeutend klein sein und das meiste Ihrer Arbeit an Dienste delegieren, die unabhängig vom Controller geprüft werden, der sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-220">Without these sources of behavior, most action methods should be trivially small, delegating the bulk of their work to services that can be tested independent of the controller that uses them.</span></span>

<span data-ttu-id="0d8bc-221">In manchen Fällen müssen Sie Ihren Code umgestalten, um einen Komponententest durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-221">Sometimes you'll need to refactor your code in order to unit test it.</span></span> <span data-ttu-id="0d8bc-222">Dies umfasst häufig das Identifizieren von Abstraktionen und die Verwendung von Abhängigkeitsinjektionen, um auf den Code zuzugreifen, den Sie testen möchten, anstatt direkt auf die Infrastruktur zu codieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-222">Frequently this involves identifying abstractions and using dependency injection to access the abstraction in the code you'd like to test, rather than coding directly against infrastructure.</span></span> <span data-ttu-id="0d8bc-223">Ziehen Sie zum Beispiel die folgende einfache Aktionsmethode zum Anzeigen von Bildern in Betracht:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-223">For example, consider this simple action method for displaying images:</span></span>

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

<span data-ttu-id="0d8bc-224">Wegen der direkten Abhängigkeit von `System.IO.File`, die diese Methode zum Lesen aus dem Dateisystem verwendet, ist es schwer, Komponententests für sie durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-224">Unit testing this method is made difficult by its direct dependency on `System.IO.File`, which it uses to read from the file system.</span></span> <span data-ttu-id="0d8bc-225">Sie können dieses Verhalten testen, um sicherzustellen, dass es wie erwartet funktioniert. Wenn Sie dies jedoch mit echten Dateien durchführen, handelt es sich um einen Integrationstest.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-225">You can test this behavior to ensure it works as expected, but doing so with real files is an integration test.</span></span> <span data-ttu-id="0d8bc-226">Beachten Sie, dass Sie die Route dieser Methode nicht mit Komponententests testen können. Wie Sie diese mit einem Funktionstest testen können, wird im Folgenden erläutert.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-226">It's worth noting you can't unit test this method's route – you'll see how to do this with a functional test shortly.</span></span>

<span data-ttu-id="0d8bc-227">Wenn Sie keinen direkten Komponententest für das Verhalten des Dateisystems und die Route durchführen können, gibt es dennoch Tests, die Sie durchführen sollten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-227">If you can't unit test the file system behavior directly, and you can't test the route, what is there to test?</span></span> <span data-ttu-id="0d8bc-228">Nach dem Refactoring zum Ermöglichen von Komponententests werden Ihnen möglicherweise Testfälle und fehlendes Verhalten auffallen, wie z.B. die Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-228">Well, after refactoring to make unit testing possible, you may discover some test cases and missing behavior, such as error handling.</span></span> <span data-ttu-id="0d8bc-229">Wie reagiert die Methode, wenn eine Datei nicht gefunden werden kann?</span><span class="sxs-lookup"><span data-stu-id="0d8bc-229">What does the method do when a file isn't found?</span></span> <span data-ttu-id="0d8bc-230">Wie sollte sie reagieren?</span><span class="sxs-lookup"><span data-stu-id="0d8bc-230">What should it do?</span></span> <span data-ttu-id="0d8bc-231">In diesem Beispiel sieht die umgestaltete Methode wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-231">In this example, the refactored method looks like this:</span></span>

```csharp
[HttpGet("[controller]/pic/{id}")\]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

<span data-ttu-id="0d8bc-232">Sowohl \_logger als auch \_imageService werden als Abhängigkeiten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-232">The \_logger and \_imageService are both injected as dependencies.</span></span> <span data-ttu-id="0d8bc-233">Sie können nun prüfen, ob dieselbe ID, die an die Aktionsmethode übergeben wird, an \_imageService übergeben wird, und ob die resultierenden Bytes als Teil von FileResult zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-233">Now you can test that the same id that is passed to the action method is passed to the \_imageService, and that the resulting bytes are returned as part of the FileResult.</span></span> <span data-ttu-id="0d8bc-234">Sie können auch überprüfen, ob die Fehlerprotokollierung ordnungsgemäß erfolgt, und ob das Ergebnis „NotFound“ zurückgegeben wird, wenn das Bild fehlt, vorausgesetzt, dass dies wichtig für das Verhalten der Anwendung ist (d.h., dass dies nicht nur temporärer Code ist, der vom Entwickler hinzugefügt wurde, um ein Problem zu diagnostizieren).</span><span class="sxs-lookup"><span data-stu-id="0d8bc-234">You can also test that error logging is happening as expected, and that a NotFound result is returned if the image is missing, assuming this is important application behavior (that is, not just temporary code the developer added to diagnose an issue).</span></span> <span data-ttu-id="0d8bc-235">Die eigentliche Dateilogik wurde in einen separaten Implementierungsdienst verschoben und wurde erweitert, damit sie im Fall einer fehlenden Datei eine anwendungsspezifische Ausnahme zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-235">The actual file logic has moved into a separate implementation service, and has been augmented to return an application-specific exception for the case of a missing file.</span></span> <span data-ttu-id="0d8bc-236">Mit einem Integrationstest können Sie diese Implementierung unabhängig testen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-236">You can test this implementation independently, using an integration test.</span></span>

<span data-ttu-id="0d8bc-237">Für die meisten Fälle wird empfohlen, globale Ausnahmehandler in Ihren Controllern zu verwenden. Darum sollten der enthaltene Logikumfang minimal und Komponententests wahrscheinlich nicht notwendig sein.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-237">In most cases, you’ll want to use global exception handlers in your controllers, so the amount of logic in them should be minimal and probably not worth unit testing.</span></span> <span data-ttu-id="0d8bc-238">Für die meisten Tests von Controlleraktionen sollten Sie Funktionstests und die unten beschriebene `TestServer`-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-238">You should do most of your testing of controller actions using functional tests and the `TestServer` class described below.</span></span>

## <a name="integration-testing-aspnet-core-apps"></a><span data-ttu-id="0d8bc-239">Integrationstests für ASP.NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="0d8bc-239">Integration testing ASP.NET Core apps</span></span>

<span data-ttu-id="0d8bc-240">Die meisten Integrationstests in Ihren ASP.NET Core-Apps sollten Testdienste und andere Implementierungstypen sein, die in Ihrem Infrastrukturprojekt definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-240">Most of the integration tests in your ASP.NET Core apps should be testing services and other implementation types defined in your Infrastructure project.</span></span> <span data-ttu-id="0d8bc-241">Sie könnten beispielsweise über Ihre Datenzugriffsklassen im Infrastrukturprojekt [prüfen, ob EF Core die erwarteten Daten erfolgreich aktualisiert und abruft](https://docs.microsoft.com/ef/core/miscellaneous/testing/).</span><span class="sxs-lookup"><span data-stu-id="0d8bc-241">For example, you could [test that EF Core was successfully updating and retrieving the data that you expect](https://docs.microsoft.com/ef/core/miscellaneous/testing/) from your data access classes residing in the Infrastructure project.</span></span> <span data-ttu-id="0d8bc-242">Das korrekte Verhalten Ihres MVC-Projekts in ASP.NET Core können Sie am besten mit Funktionstests testen, die Sie für Ihre App ausführen, welche in einem Testhost ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-242">The best way to test that your ASP.NET Core MVC project is behaving correctly is with functional tests that run against your app running in a test host.</span></span>

## <a name="functional-testing-aspnet-core-apps"></a><span data-ttu-id="0d8bc-243">Funktionstests für ASP.NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="0d8bc-243">Functional testing ASP.NET Core apps</span></span>

<span data-ttu-id="0d8bc-244">Die `TestServer`-Klasse macht das Schreiben von Funktionstests für ASP.NET Core-Anwendungen relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-244">For ASP.NET Core applications, the `TestServer` class makes functional tests fairly easy to write.</span></span> <span data-ttu-id="0d8bc-245">Verwenden Sie einen `WebHostBuilder`, entweder direkt (wie Sie es normalerweise für Ihre Anwendung tun) oder mit dem `WebApplicationFactory`-Typ (verfügbar seit Version 2.1), um einen `TestServer` zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-245">You configure a `TestServer` using a `WebHostBuilder` directly (as you normally do for your application), or with the `WebApplicationFactory` type (available since version 2.1).</span></span> <span data-ttu-id="0d8bc-246">Sie sollten versuchen, einen Testhost zu verwenden, der dem Produktionshost so ähnlich wie möglich ist, damit das Verhalten der Tests dem Verhalten der App in der Produktion ähnelt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-246">You should try to match your test host to your production host as closely as possible, so your tests will exercise behavior similar to what the app will do in production.</span></span> <span data-ttu-id="0d8bc-247">Die `WebApplicationFactory`-Klasse ist hilfreich für die ContentRoot-Konfiguration der TestServer-Klasse, die von ASP.NET Core verwendet wird, um statische Ressourcen wie Ansichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-247">The `WebApplicationFactory` class is helpful for configuring the TestServer's ContentRoot, which is used by ASP.NET Core to locate static resource like Views.</span></span>

<span data-ttu-id="0d8bc-248">Sie können einfache Funktionstests erstellen, indem Sie eine Testklasse erstellen, die IClassFixture\<WebApplicationFactory\<TEntry>> implementiert, wobei es sich bei „TEntry“ um die Startklasse Ihrer Webanwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-248">You can create simple functional tests by creating a test class that implements IClassFixture\<WebApplicationFactory\<TEntry>> where TEntry is your web application's Startup class.</span></span> <span data-ttu-id="0d8bc-249">Mit diesen Vorkehrungen kann Ihre Testfixture einen Client mithilfe der CreateClient-Methode der Zuordnungsinstanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="0d8bc-249">With this in place, your test fixture can create a client using the factory's CreateClient method:</span></span>

```cs
public class BasicWebTests : IClassFixture<WebApplicationFactory<Startup>>
{
    protected readonly HttpClient _client;

    public BaseWebTest(WebApplicationFactory<Startup> factory)
    {
        _client = factory.CreateClient();
    }

    // write tests that use _client
}
```

<span data-ttu-id="0d8bc-250">In vielen Fällen führen Sie zusätzliche Konfigurationen für Ihre Website durch, bevor jeder Test ausgeführt wird, z.B. das Konfigurieren der Anwendung für die Verwendung eines Datenspeichers im Arbeitsspeicher und das anschließende Seeding der Anwendung mit Testdaten.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-250">Frequently, you'll want to perform some additional configuration of your site before each test runs, such as configuring the application to use an in memory data store and then seeding the application with test data.</span></span> <span data-ttu-id="0d8bc-251">Hierzu sollten Sie eine eigene Unterklasse von „WebApplicationFactory\<TEntry>“ erstellen und die dazugehörige Methode „ConfigureWebHost“ überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-251">To do this, you should create your own subclass of WebApplicationFactory\<TEntry> and override its ConfigureWebHost method.</span></span> <span data-ttu-id="0d8bc-252">Das folgende Beispiel stammt vom Funktionstestprojekt „eShopOnWeb“ und wird als Teil der Tests für die Hauptwebanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-252">The example below is from the eShopOnWeb FunctionalTests project and is used as part of the tests on the main web application.</span></span>

```cs
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.EntityFrameworkCore;
using Microsoft.eShopWeb.Infrastructure.Data;
using Microsoft.eShopWeb.Infrastructure.Identity;
using Microsoft.eShopWeb.Web;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Logging;
using System;

namespace Microsoft.eShopWeb.FunctionalTests.Web.Controllers
{
    public class CustomWebApplicationFactory<TStartup>
    : WebApplicationFactory<Startup>
    {
        protected override void ConfigureWebHost(IWebHostBuilder builder)
        {
            builder.ConfigureServices(services =>
            {
                // Create a new service provider.
                var serviceProvider = new ServiceCollection()
                    .AddEntityFrameworkInMemoryDatabase()
                    .BuildServiceProvider();

                // Add a database context (ApplicationDbContext) using an in-memory 
                // database for testing.
                services.AddDbContext<CatalogContext>(options =>
                {
                    options.UseInMemoryDatabase("InMemoryDbForTesting");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                services.AddDbContext<AppIdentityDbContext>(options =>
                {
                    options.UseInMemoryDatabase("Identity");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                // Build the service provider.
                var sp = services.BuildServiceProvider();

                // Create a scope to obtain a reference to the database
                // context (ApplicationDbContext).
                using (var scope = sp.CreateScope())
                {
                    var scopedServices = scope.ServiceProvider;
                    var db = scopedServices.GetRequiredService<CatalogContext>();
                    var loggerFactory = scopedServices.GetRequiredService<ILoggerFactory>();

                    var logger = scopedServices
                        .GetRequiredService<ILogger<CustomWebApplicationFactory<TStartup>>>();

                    // Ensure the database is created.
                    db.Database.EnsureCreated();

                    try
                    {
                        // Seed the database with test data.
                        CatalogContextSeed.SeedAsync(db, loggerFactory).Wait();
                    }
                    catch (Exception ex)
                    {
                        logger.LogError(ex, $"An error occurred seeding the " +
                            "database with test messages. Error: {ex.Message}");
                    }
                }
            });
        }
    }
}
```

<span data-ttu-id="0d8bc-253">Tests können die benutzerdefinierte WebApplicationFactory nutzen, um einen Client zu erstellen und dann mithilfe dieser Clientinstanz Anforderungen an die Anwendung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-253">Tests can make use of this custom WebApplicationFactory by using it to create a client and then making requests to the application using this client instance.</span></span> <span data-ttu-id="0d8bc-254">Die Anwendung verfügt über Daten, die als Teil der Assertionen des Tests verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-254">The application will have data seeded that can be used as part of the test's assertions.</span></span> <span data-ttu-id="0d8bc-255">Der folgende Test überprüft, ob die Startseite der Anwendung „eShopOnWeb“ ordnungsgemäß geladen wird und eine Produktliste enthält, die der Anwendung als Teil des Seedings hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-255">The following test verifies that the home page of the eShopOnWeb application loads correctly and includes a product listing that was added to the application as part of the seed data.</span></span>

```cs
using Microsoft.eShopWeb.FunctionalTests.Web.Controllers;
using Microsoft.eShopWeb.Web;
using System.Net.Http;
using System.Threading.Tasks;
using Xunit;

namespace Microsoft.eShopWeb.FunctionalTests.WebRazorPages
{
    public class HomePageOnGet : IClassFixture<CustomWebApplicationFactory<Startup>>
    {
        public HomePageOnGet(CustomWebApplicationFactory<Startup> factory)
        {
            Client = factory.CreateClient();
        }

        public HttpClient Client { get; }

        [Fact]
        public async Task ReturnsHomePageWithProductListing()
        {
            // Arrange & Act
            var response = await Client.GetAsync("/");
            response.EnsureSuccessStatusCode();
            var stringResponse = await response.Content.ReadAsStringAsync();

            // Assert
            Assert.Contains(".NET Bot Black Sweatshirt", stringResponse);
        }
    }
}
```

<span data-ttu-id="0d8bc-256">Dieser Funktionstest führt den gesamten ASP.NET Core MVC/Razor Pages-Anwendungsstapel aus, einschließlich aller Middleware, Filter, Binder usw., die verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-256">This functional test exercises the full ASP.NET Core MVC / Razor Pages application stack, including all middleware, filters, binders, etc. that may be in place.</span></span> <span data-ttu-id="0d8bc-257">Er überprüft, ob eine bestimmte Route („/“) den erwarteten Erfolgsstatuscode und die HTML-Ausgabe zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-257">It verifies that a given route ("/") returns the expected success status code and HTML output.</span></span> <span data-ttu-id="0d8bc-258">Das funktioniert, ohne dass ein echter Webserver eingerichtet werden muss, und vermeidet deshalb einen Großteil der Fehleranfälligkeit, die bei einem echten Webserver auftreten kann (z.B. Probleme mit den Einstellungen der Firewall).</span><span class="sxs-lookup"><span data-stu-id="0d8bc-258">It does so without setting up a real web server, and so avoids much of the brittleness that using a real web server for testing can experience (for example, problems with firewall settings).</span></span> <span data-ttu-id="0d8bc-259">Funktionstests, die für den TestServer ausgeführt werden, sind in der Regel langsamer als Integrations- und Komponententests, aber deutlich schneller als Tests, die über das Netzwerk auf einem Testwebserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-259">Functional tests that run against TestServer are usually slower than integration and unit tests, but are much faster than tests that would run over the network to a test web server.</span></span> <span data-ttu-id="0d8bc-260">Sie sollten Funktionstests verwenden, um sicherzustellen, dass der Front-End-Stapel Ihrer Anwendung wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-260">You should use functional tests to ensure your application's front-end stack is working as expected.</span></span> <span data-ttu-id="0d8bc-261">Diese Tests sind besonders hilfreich, wenn Sie Duplizierung in Ihren Controllern oder Seiten finden und Sie diese durch Hinzufügen von Filtern behandeln.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-261">These tests are especially useful when you find duplication in your controllers or pages and you address the duplication by adding filters.</span></span> <span data-ttu-id="0d8bc-262">Im Idealfall ändert dieses Refactoring nicht das Verhalten der Anwendung, und eine Reihe von Funktionstests überprüft, ob dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0d8bc-262">Ideally, this refactoring won't change the behavior of the application, and a suite of functional tests will verify this is the case.</span></span>

> ### <a name="references--test-aspnet-core-mvc-apps"></a><span data-ttu-id="0d8bc-263">Ressourcen: Testen von ASP.NET Core MVC-Apps</span><span class="sxs-lookup"><span data-stu-id="0d8bc-263">References – Test ASP.NET Core MVC apps</span></span>
>
> - <span data-ttu-id="0d8bc-264">**Testen in ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="0d8bc-264">**Testing in ASP.NET Core**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - <span data-ttu-id="0d8bc-265">**Namenskonvention für Komponententests**</span><span class="sxs-lookup"><span data-stu-id="0d8bc-265">**Unit Test Naming Convention**</span></span>  
>   <https://ardalis.com/unit-test-naming-convention>
> - <span data-ttu-id="0d8bc-266">**Testen von EF Core**</span><span class="sxs-lookup"><span data-stu-id="0d8bc-266">**Testing EF Core**</span></span>  
>   <https://docs.microsoft.com/ef/core/miscellaneous/testing/>

>[!div class="step-by-step"]
><span data-ttu-id="0d8bc-267">[Zurück](work-with-data-in-asp-net-core-apps.md)
>[Weiter](development-process-for-azure.md)</span><span class="sxs-lookup"><span data-stu-id="0d8bc-267">[Previous](work-with-data-in-asp-net-core-apps.md)
[Next](development-process-for-azure.md)</span></span>
