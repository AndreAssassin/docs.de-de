---
title: Entwicklungsworkflow für Docker-Apps
description: Erläuterungen zu den Workflowdetails für die Entwicklung von auf Docker basierenden Anwendungen. Beginnen Sie mit den Grundlagen. Gehen Sie dann ausführlicher auf das Optimieren von Dockerfiles ein. Arbeiten Sie zum Schluss mit dem vereinfachten Workflow, der bei der Verwendung mit Visual Studio verfügbar ist.
ms.date: 01/07/2019
ms.openlocfilehash: 34d2a90cb5208736b1b414e25ac3e627929f45a0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644492"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="f81b3-104">Entwicklungsworkflow für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="f81b3-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="f81b3-105">Der Lebenszyklus der Anwendungsentwicklung beginnt auf Ihrem Computer. Als Entwickler programmieren Sie die Anwendung mit Ihrer bevorzugten Programmiersprache und testen sie lokal.</span><span class="sxs-lookup"><span data-stu-id="f81b3-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="f81b3-106">Mit diesem Workflow entwickeln und testen Sie Docker-Container stets lokal, unabhängig davon, welche Sprache, welches Framework und welche Plattform Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="f81b3-107">Jeder Container (eine Instanz eines Docker-Images) umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="f81b3-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="f81b3-108">Eine Betriebssystemauswahl, z. B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core</span><span class="sxs-lookup"><span data-stu-id="f81b3-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="f81b3-109">Dateien, die während der Entwicklung hinzugefügt wurden, z. B. Quellcode- und Anwendungsbinärdateien</span><span class="sxs-lookup"><span data-stu-id="f81b3-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="f81b3-110">Konfigurationsinformationen, z. B. Umgebungseinstellungen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f81b3-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="f81b3-111">Workflow für die Entwicklung von Docker-Container-basierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f81b3-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="f81b3-112">In diesem Abschnitt wird der *Entwicklungsworkflow* für Docker-Container-basierte Anwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f81b3-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="f81b3-113">Der innere Entwicklungsworkflow berücksichtigt nicht den breiteren DevOps-Workflow, der bis zur Produktionsbereitstellung reichen kann. Stattdessen liegt der Fokus nur auf die Entwicklungsarbeit, die auf dem Computer des Entwicklers vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-113">The inner-loop workflow means it's not considering the broader DevOps workflow, that can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="f81b3-114">Die ersten Schritte zum Einrichten der Umgebung wurden nicht berücksichtigt, da diese nur einmal durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="f81b3-115">Eine Anwendung besteht aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="f81b3-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="f81b3-116">Im Folgenden sind die grundlegenden Schritte dargestellt, die Sie normalerweise beim Erstellen einer Docker-Anwendung ausführen, wie in Abbildung 5-1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![<span data-ttu-id="f81b3-117">Der Entwicklungsprozess für Docker-Apps: 1. Programmieren der App, 2. Schreiben der Dockerfile(s), 3. Erstellen der in der Dockerfile definierten Images, 4. Erstellen von Diensten in der docker-compose.yml-Datei (optional), 5. Ausführen des Containers oder der docker-compose-App, 6. Testen der App oder des Microservices, 7. Mithilfe von Push an das Repository übertragen und Prozedur wiederholen</span><span class="sxs-lookup"><span data-stu-id="f81b3-117">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span> ](./media/image1.png)

<span data-ttu-id="f81b3-118">**Abbildung 5-1.**</span><span class="sxs-lookup"><span data-stu-id="f81b3-118">**Figure 5-1.**</span></span> <span data-ttu-id="f81b3-119">Workflowschritte für die Entwicklung von Containeranwendungen für Docker</span><span class="sxs-lookup"><span data-stu-id="f81b3-119">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="f81b3-120">In diesem Abschnitt wird der gesamte Prozess ausführlich beschrieben, und jeder wichtige Schritt wird unter besonderer Berücksichtigung einer Visual Studio-Umgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-120">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="f81b3-121">Bei Verwendung eines Editor-/CLI-Entwicklungsansatzes (z. B. Visual Studio Code plus Docker-CLI auf macOS oder Windows) müssen Sie die einzelnen Schritte in der Regel detaillierter kennen als bei Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f81b3-121">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="f81b3-122">Weitere Informationen zum Arbeiten in einer CLI-Umgebung finden Sie im E-Book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Lebenszyklus von Docker-Containeranwendungen mit Microsoft-Plattformen und Tools)](https://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="f81b3-122">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="f81b3-123">Wenn Sie Visual Studio 2017 verwenden, werden viele dieser Schritte für Sie ausgeführt, wodurch sich Ihre Produktivität entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="f81b3-123">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="f81b3-124">Dies gilt insbesondere, wenn Sie Visual Studio 2017 verwenden und Anwendungen mit mehreren Containern das Ziel sind.</span><span class="sxs-lookup"><span data-stu-id="f81b3-124">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="f81b3-125">Visual Studio fügt beispielsweise mit nur einem Mausklick die Dateien Dockerfile und docker-compose.yml mit der Konfiguration für Ihre Anwendung Ihren Projekten hinzu.</span><span class="sxs-lookup"><span data-stu-id="f81b3-125">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="f81b3-126">Wenn Sie die Anwendung in Visual Studio ausführen, wird das Docker-Image erstellt und die Anwendung mit mehreren Containern wird direkt in Docker ausgeführt. Sie haben sogar die Möglichkeit, mehrere Container auf einmal zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-126">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="f81b3-127">Diese Features erhöhen Ihre Entwicklungsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="f81b3-127">These features will boost your development speed.</span></span>

<span data-ttu-id="f81b3-128">Allerdings bedeutet die Tatsache, dass Visual Studio die Schritte automatisch ausführt, nicht, dass Sie nicht wissen müssen, was im Hintergrund mit Docker geschieht.</span><span class="sxs-lookup"><span data-stu-id="f81b3-128">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="f81b3-129">Aus diesem Grund werden im folgenden Leitfaden alle Schritte ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-129">Therefore, the following guidance details every step.</span></span>

![1: Programmieren Ihrer App](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="f81b3-131">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="f81b3-131">Step 1.</span></span> <span data-ttu-id="f81b3-132">Beginnen Sie mit dem Codieren, und erstellen Sie eine erste Anwendungs- oder Dienstbaseline</span><span class="sxs-lookup"><span data-stu-id="f81b3-132">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="f81b3-133">Das Entwickeln einer Docker-Anwendung ist mit der Art und Weise vergleichbar, wie Anwendungen ohne Docker entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-133">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="f81b3-134">Der Unterschied besteht darin, dass Sie beim Entwickeln für Docker Ihre Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt werden (entweder in einem Setup für eine Linux-VM von Docker oder direkt unter Windows, wenn Sie Windows-Container verwenden).</span><span class="sxs-lookup"><span data-stu-id="f81b3-134">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="f81b3-135">Einrichten der lokalen Umgebung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="f81b3-136">Stellen Sie zuerst sicher, dass [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) für Windows wie nachfolgend erläutert installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="f81b3-136">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="f81b3-137">Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)</span><span class="sxs-lookup"><span data-stu-id="f81b3-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="f81b3-138">Zudem benötigen Sie Visual Studio 2017, Version 15.7 oder höher, mit installierter Workload für die **plattformübergreifende .NET Core-Entwicklung**, wie in Abbildung 5.2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-138">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Ausgewählte Workload für die plattformübergreifende .NET Core-Entwicklung während der Installation in Visual](./media/image3.png)

<span data-ttu-id="f81b3-140">**Abbildung 5-2**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-140">**Figure 5-2**.</span></span> <span data-ttu-id="f81b3-141">Auswahl der **Workload für die plattformübergreifende .NET Core-Entwicklung** während des Setups in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f81b3-141">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="f81b3-142">Sie können mit dem Codieren Ihrer Anwendung in einer einfachen .NET-Umgebung beginnen (normalerweise in .NET Core, wenn Sie Container verwenden möchten), noch bevor Sie Docker in Ihrer Anwendung aktivieren und in Docker Bereitstellungsprozesse und Tests durchführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-142">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="f81b3-143">Allerdings wird empfohlen, dass Sie so bald wie möglich mit Docker arbeiten, d.h. in der realen Umgebung, sodass etwaige Probleme schnellstmöglich erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="f81b3-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="f81b3-144">Dies wird empfohlen, da Visual Studio die Arbeit mit Docker so erleichtert, dass sie fast transparent erscheint – insbesondere beim Debuggen von Anwendungen mit mehreren Containern über Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f81b3-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-145">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-145">Additional resources</span></span>

- <span data-ttu-id="f81b3-146">**Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-146">**Get started with Docker CE for Windows** \\</span></span>
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="f81b3-147">**Visual Studio 2017** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-147">**Visual Studio 2017** \\</span></span>
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

![2: Schreiben von Dockerfiles](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="f81b3-149">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="f81b3-149">Step 2.</span></span> <span data-ttu-id="f81b3-150">Erstellen Sie eine Dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basisimage</span><span class="sxs-lookup"><span data-stu-id="f81b3-150">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="f81b3-151">Für jedes benutzerdefinierte Image, das Sie erstellen möchten, benötigen Sie eine Dockerfile-Datei. Außerdem benötigen Sie eine Dockerfile-Datei für jeden bereitzustellenden Container unabhängig davon, ob Sie automatisch über Visual Studio oder manuell mithilfe der Docker-CLI bereitstellen (Befehle „docker run“ und „docker-compose“).</span><span class="sxs-lookup"><span data-stu-id="f81b3-151">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="f81b3-152">Wenn Ihre Anwendung einen benutzerdefinierten Dienst enthält, benötigen Sie eine einzelne Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="f81b3-152">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="f81b3-153">Wenn Ihre Anwendung mehrere Dienste enthält (wie in einer Microservicearchitektur), benötigen Sie pro Dienst eine Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="f81b3-153">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="f81b3-154">Die Dockerfile-Datei befindet sich im Stammordner der Anwendung oder des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f81b3-154">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="f81b3-155">Sie enthält die Befehle, die Docker mitteilen, wie die Anwendung oder der Dienst in einem Container eingerichtet und ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-155">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="f81b3-156">Sie können eine Dockerfile-Datei manuell im Code erstellen und mit Ihren .NET-Abhängigkeiten Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-156">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="f81b3-157">Mit Visual Studio und den Tools für Docker erledigen Sie diese Aufgabe mit einigen wenigen Mausklicks.</span><span class="sxs-lookup"><span data-stu-id="f81b3-157">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="f81b3-158">Beim Erstellen eines neuen Projekts in Visual Studio 2017 ist die Option **Enable Container (Docker) Support** (Containerunterstützung (Docker) aktivieren) verfügbar, wie in Abbildung 5.3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-158">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![Kontrollkästchen „Enable Docker Support“ (Docker-Unterstützung aktivieren) beim Erstellen eines neuen ASP.NET Core-Projekts in Visual Studio 2017](./media/image5.png)

<span data-ttu-id="f81b3-160">**Abbildung 5-3**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-160">**Figure 5-3**.</span></span> <span data-ttu-id="f81b3-161">Aktivieren der Docker-Unterstützung beim Erstellen eines neuen ASP.NET Core-Projekts in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f81b3-161">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="f81b3-162">Sie können die Docker-Unterstützung auch für ein vorhandenes ASP.NET Core-Web-App-Projekt aktivieren, indem Sie mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** klicken und **Hinzufügen** > **Docker-Unterstützung** auswählen, wie in Abbildung 5.4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-162">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Menüoption „Add Docker support“ (Docker-Unterstützung hinzufügen) in Visual Studio](./media/image6.png)

<span data-ttu-id="f81b3-164">**Abbildung 5-4**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-164">**Figure 5-4**.</span></span> <span data-ttu-id="f81b3-165">Aktivieren der Unterstützung für Docker in einem vorhandenen Visual Studio 2017-Projekt</span><span class="sxs-lookup"><span data-stu-id="f81b3-165">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="f81b3-166">Durch diesen Vorgang wird dem Projekt eine *Dockerfile* mit der erforderlichen Konfiguration hinzugefügt, die nur für ASP.NET Core-Projekte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f81b3-166">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="f81b3-167">Visual Studio kann auf ganz ähnliche Weise eine docker-compose.yml-Datei für die gesamte Projektmappe hinzufügen. Dazu wird die Option **Add > Container Orchestrator Support** (Hinzufügen > Containerorchestratorunterstützung) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-167">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="f81b3-168">In Schritt 4 wird diese Option genauer erläutert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-168">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="f81b3-169">Verwenden eines vorhandenen offiziellen .NET Docker-Images</span><span class="sxs-lookup"><span data-stu-id="f81b3-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="f81b3-170">Sie erstellen ein benutzerdefiniertes Image für den Container in der Regel auf einem Basisimage, das Sie von einem offiziellen Repository in der [Docker-Hub](https://hub.docker.com/)-Registrierung erhalten.</span><span class="sxs-lookup"><span data-stu-id="f81b3-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="f81b3-171">Das ist genau das, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="f81b3-172">Die Dockerfile verwendet ein vorhandenes `aspnetcore`-Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-172">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="f81b3-173">Es wurde bereits erläutert, welche Docker-Images und Repositorys Sie abhängig vom Framework und Betriebssystem, das Sie ausgewählt haben, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f81b3-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="f81b3-174">Wenn Sie beispielsweise ASP.NET Core (Linux oder Windows) verwenden möchten, muss das Image `mcr.microsoft.com/dotnet/core/aspnet:2.2` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="f81b3-175">Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages Sie für den Container verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="f81b3-176">Fügen Sie hierzu `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` Ihrer Dockerfile hinzu.</span><span class="sxs-lookup"><span data-stu-id="f81b3-176">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` to your Dockerfile.</span></span> <span data-ttu-id="f81b3-177">Dies wird automatisch von Visual Studio ausgeführt, aber wenn Sie die Version aktualisieren müssen, aktualisieren Sie diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="f81b3-178">Durch Verwendung eines offiziellen .NET Image-Repositorys von Docker-Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f81b3-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="f81b3-179">Das folgende Beispiel veranschaulicht eine Dockerfile-Beispieldatei für einen ASP.NET Core-Container.</span><span class="sxs-lookup"><span data-stu-id="f81b3-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="f81b3-180">In diesem Fall basiert das Image auf Version 2.2 des offiziellen ASP.NET Core-Docker-Images (mehrere Architekturen für Linux und Windows).</span><span class="sxs-lookup"><span data-stu-id="f81b3-180">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="f81b3-181">Dies ist die Einstellung `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="f81b3-181">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="f81b3-182">(Weitere Informationen zu diesem Basisimage finden Sie unter [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core/).) In der Dockerfile-Datei müssen Sie auch angeben, dass Docker an dem TCP-Port lauscht, den Sie zur Runtime verwenden (in diesem Fall Port 80 gemäß Konfiguration mit der EXPOSE-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="f81b3-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="f81b3-183">Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben.</span><span class="sxs-lookup"><span data-stu-id="f81b3-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="f81b3-184">Beispielsweise weist die ENTRYPOINT-Zeile mit `["dotnet", "MySingleContainerWebApp.dll"]` Docker an, eine .NET Core-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="f81b3-185">Wenn Sie das SDK und die .NET Core-CLI (Dotnet-CLI) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="f81b3-186">Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen je nach Sprache und Plattform variieren können, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-187">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-187">Additional resources</span></span>

- <span data-ttu-id="f81b3-188">**Erstellen von Docker-Images für .NET Core-Anwendungen** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-188">**Building Docker Images for .NET Core Applications** \\</span></span>
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="f81b3-189">**Build your own image (Entwickeln eines eigenen Images)**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-189">**Build your own image**.</span></span> <span data-ttu-id="f81b3-190">In der offiziellen Docker-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="f81b3-190">In the official Docker documentation.\\</span></span>
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="f81b3-191">**Staying up-to-date with .NET Container Images (Immer auf dem neuesten Stand mit .NET-Containerimages)** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-191">**Staying up-to-date with .NET Container Images** \\</span></span>
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="f81b3-192">**Using .NET and Docker together - DockerCon 2018 Update (Gemeinsame Verwendung von .NET und Docker: Update zu DockerCon 2018)** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-192">**Using .NET and Docker Together - DockerCon 2018 Update** \\</span></span>
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="f81b3-193">Verwenden von Repositorys für Images für mehrere Architekturen</span><span class="sxs-lookup"><span data-stu-id="f81b3-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="f81b3-194">Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="f81b3-195">Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="f81b3-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="f81b3-196">Das in der Docker-Hub-Registrierung verfügbare [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Repositoryname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-196">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="f81b3-197">Wenn Sie ein explizites Tag für eine bestimmte Plattform angeben, wie in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="f81b3-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="f81b3-198">Ziele: Nur .NET Core 2.2-Runtime unter Linux</span><span class="sxs-lookup"><span data-stu-id="f81b3-198">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="f81b3-199">Ziele: Nur .NET Core 2.2-Runtime unter Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="f81b3-199">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="f81b3-200">Die Images für mehrere Architekturen (z. B. das `aspnetcore`-Image) verwenden bei Angabe des gleichen Imagenamens, auch mit dem gleichen Tag, je nach dem von Ihnen bereitgestellten Docker-Host-Betriebssystem die Linux- oder die Windows-Version, was im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="f81b3-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="f81b3-201">Mehrfacharchitektur: Nur .NET Core 2.2-Runtime unter Linux und Windows Nano Server, abhängig vom Betriebssystem des Docker-Hosts</span><span class="sxs-lookup"><span data-stu-id="f81b3-201">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="f81b3-202">Wenn Sie also ein Image von einem Windows-Host pullen, wird die Windows-Variante gepullt. Wenn der gleiche Imagename von einem Linux-Host gepullt wird, wird die Linux-Variante gepullt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="f81b3-203">Mehrstufige Builds in einer Dockerfile</span><span class="sxs-lookup"><span data-stu-id="f81b3-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="f81b3-204">Die Dockerfile ähnelt einem Batchskript.</span><span class="sxs-lookup"><span data-stu-id="f81b3-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="f81b3-205">Die Vorgehensweise ist in etwa so wie beim Einrichten des Computers über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f81b3-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="f81b3-206">Sie beginnen mit einem Basisimage, das den Anfangskontext einrichtet, was dem Startdateisystem ähnelt, das sich auf dem Hostbetriebssystem befindet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="f81b3-207">Dabei handelt es sich jedoch nicht um ein Betriebssystem, Sie können es sich eher als „das“ Betriebssystem innerhalb des Containers vorstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-207">It's not an OS, but you can think of if like "the" OS inside the container.</span></span>

<span data-ttu-id="f81b3-208">Durch die Ausführung jeder Befehlszeile wird eine neue Ebene im Dateisystem erstellt, wobei jede Ebene die Änderungen der vorherigen enthält. Das gesamte Konstrukt ergibt zusammen das Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="f81b3-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="f81b3-209">Da jede Ebene auf der vorherigen „aufliegt“, und die daraus resultierende Imagegröße mit jedem Befehl zunimmt, können Images sehr groß werden, wenn darin beispielsweise das für die Erstellung und Veröffentlichung einer Anwendung benötigte SDK enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="f81b3-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="f81b3-210">Zu diesem Zeitpunkt kommen mehrstufige Builds (ab Docker 17.05 und höher) ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="f81b3-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="f81b3-211">Die Kernidee dahinter ist, dass Sie den Ausführungsprozess für die Dockerfile in Stufen aufteilen können, wobei jede Stufe ein anfängliches Image darstellt, auf das mindestens ein Befehl folgt. Die letzte Stufe bestimmt die endgültige Imagegröße.</span><span class="sxs-lookup"><span data-stu-id="f81b3-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="f81b3-212">Zusammengefasst bedeutet das also, dass für mehrstufige Builds die Erstellung in unterschiedlichen „Phasen“ ablaufen kann und das endgültige Image dann ausschließlich mit den relevanten Verzeichnissen aus den weiterführenden Stufen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="f81b3-213">Die allgemeine Strategie zur Verwendung dieses Features ist die folgende:</span><span class="sxs-lookup"><span data-stu-id="f81b3-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="f81b3-214">Verwenden Sie ein SDK-Basisimage (dabei ist die Größe nicht wichtig) mit allen Elementen, die zum Erstellen und Veröffentlichen der Anwendung in einem Ordner erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f81b3-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="f81b3-215">Verwenden Sie anschließend ein kleines Image, das nur als Runtime dient, und kopieren Sie den Veröffentlichungsordner aus der vorherigen Stufe, um ein kleineres endgültiges Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="f81b3-216">Sie können den mehrstufigen Prozess am besten verstehen, wenn Sie eine Dockerfile ausführlich durchlaufen, und zwar Zeile für Zeile. Beginnen wir also mit der ursprünglichen Dockerfile, die von Visual Studio erstellt wird, wenn zu einem Projekt Docker-Unterstützung hinzugefügt wird. Später erhalten Sie noch mehr Informationen zu einigen Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="f81b3-217">Die ursprüngliche Dockerfile kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f81b3-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="f81b3-218">Hier sind die Details zeilenweise dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f81b3-218">And these are the details, line by line:</span></span>

<!-- markdownlint-disable MD029-->
1. <span data-ttu-id="f81b3-219">Beginnen Sie eine Stufe mit einem „kleinen“ Basisimage, das nur als Runtime dient. Nennen Sie es zu Referenzzwecken **base**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-219">Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>
2. <span data-ttu-id="f81b3-220">Erstellen Sie das **/app**-Verzeichnis im Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-220">Create **/app** directory in the image.</span></span>
3. <span data-ttu-id="f81b3-221">Machen Sie den Port **80** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f81b3-221">Expose port **80**.</span></span>
<!-- skip -->
5. <span data-ttu-id="f81b3-222">Beginnen Sie eine Stufe mit einem „großen“ Basisimage zur Erstellung/Veröffentlichung. Nennen Sie es zu Referenzzwecken **build**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-222">Begin a new stage with "large" image for building/publishing, call it **build** for reference.</span></span>
6. <span data-ttu-id="f81b3-223">Erstellen Sie das **/src**-Verzeichnis im Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-223">Create directory **/src** in the image.</span></span>
7. <span data-ttu-id="f81b3-224">Kopieren Sie bis zur Zeile 16 die **.csproj**-Projektdateien, auf die verwiesen wird, damit Sie zu einem späteren Zeitpunkt Pakete wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="f81b3-224">Up to line 16, copy referenced projects **.csproj** files, to be able to restore packages later.</span></span>
<!-- skip -->
17. <span data-ttu-id="f81b3-225">Stellen Sie die Pakete für das **Catalog.API**-Projekt und die Projekte, auf die verwiesen wird, wieder her.</span><span class="sxs-lookup"><span data-stu-id="f81b3-225">Restore packages for the **Catalog.API** project and the referenced projects.</span></span>
18. <span data-ttu-id="f81b3-226">Kopieren Sie **alle Verzeichnisstrukturen für die Projektmappe** (außer die Dateien und Verzeichnisse in der **.dockerignore**-Datei) aus dem **/src**-Verzeichnis in das Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-226">Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) from to the **/src** directory in the image.</span></span>
19. <span data-ttu-id="f81b3-227">Ändern Sie den aktuellen Ordner in das **Catalog.API**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-227">Change current folder to **Catalog.API** project.</span></span>
20. <span data-ttu-id="f81b3-228">Erstellen Sie das Projekt (und andere Projektabhängigkeiten) sowie die Ausgabe im **/app**-Verzeichnis im Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-228">Build project (and other project dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
22. <span data-ttu-id="f81b3-229">Beginnen Sie eine Stufe aus dem vorherigen Build, und nennen Sie sie zu Referenzzwecken **publish**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-229">Begin a new stage continuing from build, call it **publish** for reference.</span></span>
23. <span data-ttu-id="f81b3-230">Veröffentlichen Sie das Projekt (und die Abhängigkeiten) sowie die Ausgabe im **/app**-Verzeichnis im Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-230">Publish project (and dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
25. <span data-ttu-id="f81b3-231">Beginnen Sie eine neue Stufe aus dem Image **base**, und nennen Sie sie **final**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-231">Begin a new stage continuing from **base** and call it **final**</span></span>
26. <span data-ttu-id="f81b3-232">Ändern Sie das aktuelle Verzeichnis in **/app**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-232">Change current directory to **/app**</span></span>
27. <span data-ttu-id="f81b3-233">Kopieren Sie das Verzeichnis **/app** aus der Stufe **publish** in das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f81b3-233">Copy the **/app** directory from stage **publish** to the current directory</span></span>
28. <span data-ttu-id="f81b3-234">Definieren Sie den Befehl, der ausgeführt werden soll, sobald der Container gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-234">Define the command to run when the container is started.</span></span>
<!-- markdownlint-enable MD029-->

<span data-ttu-id="f81b3-235">Lernen Sie nun einige Optimierungen kennen, die Ihnen dabei helfen, die gesamte Prozessleistung zu verbessern. Im Falle von eShopOnContainers bedeutet dies, dass es 22 Minuten oder länger dauert, um die gesamte Projektmappe in Linux-Containern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-235">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="f81b3-236">Sie nutzen die Cachefunktion für die Ebenen in Docker. Das ist ganz einfach: Wenn sich das Basisimage und die Befehle nicht von den zuvor ausgeführten unterscheiden, kann einfach die sich daraus resultierende Ebene verwendet werden, ohne dass die Befehle ausgeführt werden müssen, wodurch Sie Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-236">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="f81b3-237">Konzentrieren wir uns daher auf die **build**-Stufe: Die Zeilen 5–6 unterscheiden sich kaum, jedoch unterscheiden sich die Zeilen 7–17 für jeden eShopOnContainers-Dienst, weshalb sie jedes Mal ausgeführt werden müssen. Ganz anders sieht es aus, wenn Sie die Zeilen 7–16 wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="f81b3-237">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```Dockerfile
COPY . .
```

<span data-ttu-id="f81b3-238">Die Vorgehensweise wäre dann für jeden Dienst die gleiche: Die gesamte Projektmappe wird kopiert, und es wird eine größere Ebene erstellt. Dazu ist jedoch Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="f81b3-238">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1) <span data-ttu-id="f81b3-239">Der Kopiervorgang würde nur zum ersten Mal ausgeführt (und bei einer Neuerstellung, wenn eine Datei geändert wird) und würde den Cache für alle anderen Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-239">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2) <span data-ttu-id="f81b3-240">Da das größere Image in einem Zwischenstadium auftritt, wirkt es sich nicht auf die endgültige Imagegröße aus.</span><span class="sxs-lookup"><span data-stu-id="f81b3-240">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="f81b3-241">Die nächste wichtige Optimierung umfasst den `restore`-Befehl, der in Zeile 17 ausgeführt wird, der sich jedoch auch für jeden Dienst von eShopOnContainers unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-241">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="f81b3-242">Wenn Sie also diese Zeile nur wie folgt ändern...</span><span class="sxs-lookup"><span data-stu-id="f81b3-242">If you change that line to just:</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="f81b3-243">...dann werden die Pakete für die gesamte Projektmappe wiederhergestellt. Dies geschieht jedoch nur ein einziges Mal und nicht 15 Mal wie bei der aktuellen Strategie.</span><span class="sxs-lookup"><span data-stu-id="f81b3-243">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="f81b3-244">Jedoch wird `dotnet restore` nur ausgeführt, wenn sich ein einzelnes Projekt oder eine einzelne Projektmappendatei im Ordner befindet. Der Weg dahin ist etwas komplizierter, und der Lösungsweg (ohne dass Sie sich in zu vielen Details verlieren) sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f81b3-244">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1. <span data-ttu-id="f81b3-245">Fügen Sie der **.dockerignore**-Datei die folgenden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="f81b3-245">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="f81b3-246">`*.sln`, um alle Projektmappendateien in der Hauptordnerstruktur zu ignorieren</span><span class="sxs-lookup"><span data-stu-id="f81b3-246">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="f81b3-247">`!eShopOnContainers-ServicesAndWebApps.sln`, um nur diese Projektmappendatei einzufügen</span><span class="sxs-lookup"><span data-stu-id="f81b3-247">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2. <span data-ttu-id="f81b3-248">Schließen Sie das `/ignoreprojectextensions:.dcproj`-Argument in `dotnet restore` ein, damit auch das docker-compose-Projekt ignoriert und nur das Paket für die Projektmappe „eShopOnContainers-ServicesAndWebApps“ wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-248">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="f81b3-249">Für die letzte Optimierung kann es der Fall sein, dass Zeile 20 redundant wird, da Zeile 23 ebenso die Anwendung erstellt und im Grunde genommen gleich auf Zeile 20 folgt. So sparen Sie sich daher einen weiteren zeitaufwändigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="f81b3-249">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="f81b3-250">Die Datei, die sich daraus ergibt, sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f81b3-250">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="f81b3-251">Neuerstellung des Basisimages</span><span class="sxs-lookup"><span data-stu-id="f81b3-251">Creating your base image from scratch</span></span>

<span data-ttu-id="f81b3-252">Sie können ein eigenes Docker-Basisimage von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-252">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="f81b3-253">Dieses Szenario wird Docker-Einsteigern nicht empfohlen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="f81b3-253">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-254">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-254">Additional resources</span></span>

- <span data-ttu-id="f81b3-255">**Multi-arch .NET Core images (.NET Core-Images für mehrere Architekturen)**</span><span class="sxs-lookup"><span data-stu-id="f81b3-255">**Multi-arch .NET Core images**.\\</span></span>
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="f81b3-256">**Create a base image (Erstellen eines Basisimages)**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-256">**Create a base image**.</span></span> <span data-ttu-id="f81b3-257">Offizielle Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f81b3-257">Official Docker documentation.\\</span></span>
  <https://docs.docker.com/develop/develop-images/baseimages/>

![3. Erstellen von in Dockerfiles definierten Images](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="f81b3-259">Schritt 3</span><span class="sxs-lookup"><span data-stu-id="f81b3-259">Step 3.</span></span> <span data-ttu-id="f81b3-260">Erstellen Sie Ihre benutzerdefinierten Docker-Images, und betten Sie Ihre Anwendung oder Ihren Dienst in diese ein</span><span class="sxs-lookup"><span data-stu-id="f81b3-260">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="f81b3-261">Sie müssen für jeden Dienst in Ihrer Anwendung ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-261">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="f81b3-262">Wenn Ihre Anwendung aus einem einzelnen Dienst oder einer einzelnen Webanwendung besteht, benötigen Sie nur ein Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-262">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="f81b3-263">Beachten Sie, dass die Docker-Images in Visual Studio automatisch erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-263">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="f81b3-264">Die folgenden Schritte sind nur für den Editor-/CLI-Workflow und zur Erläuterung der Vorgänge, die im Hintergrund ablaufen, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f81b3-264">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="f81b3-265">Als Entwickler entwickeln und testen Sie so lange lokal, bis Sie ein abgeschlossenes Feature pushen oder zu Ihrem Quellkontrollsystem wechseln (z.B. zu GitHub).</span><span class="sxs-lookup"><span data-stu-id="f81b3-265">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="f81b3-266">Dies bedeutet, dass Sie die Docker-Images erstellen und Container auf einem lokalen Docker-Host (Windows- oder Linux-VM) bereitstellen und für die lokalen Container ausführen, testen und debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-266">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="f81b3-267">Mithilfe des Befehls „docker build“ können Sie, wie in Abbildung 5-5 gezeigt, unter Verwendung der Docker-CLI und Ihrer Dockerfile-Datei ein benutzerdefiniertes Image in ihrer lokalen Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-267">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Bildschirm für den Fortschritt bei der Erstellung eines Docker-Images](./media/image8.png)

<span data-ttu-id="f81b3-269">**Abbildung 5-5**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-269">**Figure 5-5**.</span></span> <span data-ttu-id="f81b3-270">Erstellen eines benutzerdefinierten Docker-Images</span><span class="sxs-lookup"><span data-stu-id="f81b3-270">Creating a custom Docker image</span></span>

<span data-ttu-id="f81b3-271">Optional können Sie, anstatt „docker build“ über den Projektordner direkt auszuführen, zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken und Binärdateien generieren, indem Sie erst `dotnet publish` ausführen und dann den Befehl `docker build` verwenden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-271">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="f81b3-272">Dadurch wird ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` erstellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-272">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="f81b3-273">In diesem Fall ist :first ein Tag, das eine bestimmte Version darstellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-273">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="f81b3-274">Sie können diesen Schritt für jedes benutzerdefinierte Image wiederholen, das Sie für Ihre zusammengesetzte Docker-Anwendung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-274">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="f81b3-275">Wenn eine Anwendung aus mehreren Containern besteht, können Sie auch den Befehl `docker-compose up --build` verwenden, um alle zugehörigen Images mit einem Befehl unter Verwendung der in den zugehörigen docker-compose.yml-Dateien verfügbar gemachten Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-275">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="f81b3-276">Sie können die vorhandenen Images in Ihrem lokalen Repository suchen, indem Sie den „docker images“-Befehl, wie in Abbildung 5-6 dargestellt, verwenden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-276">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Bildschirmansicht der Auflistung von Images aus dem Befehl für Docker Images](./media/image9.png)

<span data-ttu-id="f81b3-278">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="f81b3-278">**Figure 5-6.**</span></span> <span data-ttu-id="f81b3-279">Anzeigen vorhandener Images mithilfe des Befehls „docker images“</span><span class="sxs-lookup"><span data-stu-id="f81b3-279">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="f81b3-280">Erstellen von Docker-Images mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-280">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="f81b3-281">Wenn Sie Visual Studio zum Erstellen eines Projekts mit Docker-Unterstützung verwenden, erstellen Sie nicht explizit ein Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-281">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="f81b3-282">Stattdessen wird das Image für Sie erstellt, wenn Sie **F5** (oder **STRG+F5**) drücken und die dockerisierte Anwendung oder den dockerisierten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-282">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="f81b3-283">Dieser Schritt wird in Visual Studio automatisch und für Sie nicht erkennbar ausgeführt, aber es ist wichtig, dass Sie wissen, was im Hintergrund passiert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-283">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![4. (Optional) Erstellen der Dienste in der docker-compose.yml-Datei](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="f81b3-285">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="f81b3-285">Step 4.</span></span> <span data-ttu-id="f81b3-286">Definieren Sie Ihre Dienste in der Datei docker-compose.yml beim Erstellen einer Docker-Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="f81b3-286">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="f81b3-287">Mithilfe der Datei [docker compose.yml](https://docs.docker.com/compose/compose-file/) können Sie mehrere verwandte Dienste definieren, die als zusammengesetzte Anwendung mit Bereitstellungsbefehlen bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-287">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="f81b3-288">Dadurch werden ebenso die Abhängigkeitsbeziehungen und die Laufzeitkonfiguration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-288">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="f81b3-289">Wenn Sie eine docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in Ihrem Haupt- oder Stammlösungsordner mit Inhalt erstellen, der mit dem in dem folgenden Beispiel verwendeten vergleichbar ist:</span><span class="sxs-lookup"><span data-stu-id="f81b3-289">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="f81b3-290">Diese „docker-compose.yml“-Datei ist eine vereinfachte und zusammengeführte Version.</span><span class="sxs-lookup"><span data-stu-id="f81b3-290">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="f81b3-291">Sie enthält die statischen Konfigurationsdaten für jeden Container (z. B. den Namen des benutzerdefinierten Images), das erforderlich ist, sowie Konfigurationsinformationen, die sich nach der Bereitstellungsumgebung richten können, z. B. die Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f81b3-291">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="f81b3-292">In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der docker-compose.yml-Datei in mehrere docker-compose-Dateien aufteilen und Werte je nach Umgebung und Ausführungstyp (Debug oder Release) außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="f81b3-292">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="f81b3-293">Im Beispiel der Datei „docker-compose.yml“ werden vier Dienste definiert: der `webmvc`-Dienst (eine Webanwendung), zwei Microservices (`ordering.api` und `basket.api`) und ein Datenquellcontainer, `sql.data`, basierend auf von als Container ausgeführtem SQL Server für Linux.</span><span class="sxs-lookup"><span data-stu-id="f81b3-293">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="f81b3-294">Da jeder Dienst als ein Container bereitgestellt wird, ist für jeden ein Docker-Image erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f81b3-294">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="f81b3-295">Die docker-compose.yml-Datei gibt nicht nur an, welche Container verwendet werden, sondern auch, wie diese einzeln konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-295">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="f81b3-296">Die `webmvc`-Containerdefinition in der .yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="f81b3-296">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="f81b3-297">Verwendet ein vorab erstelltes `eshop/web:latest`-Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-297">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="f81b3-298">Sie können jedoch das als Teil der docker-compose-Ausführung zu erstellende Image mit einer zusätzlichen, auf einem build:-Abschnitt in der docker-compose-Datei basierenden Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-298">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="f81b3-299">Initialisiert die beiden Umgebungsvariablen (CatalogUrl und OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="f81b3-299">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="f81b3-300">Leitet den verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer weiter.</span><span class="sxs-lookup"><span data-stu-id="f81b3-300">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="f81b3-301">Verknüpft die Web-App mit dem Katalog- und Bestelldienst mit der depends_on-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="f81b3-301">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="f81b3-302">Dies bewirkt, dass der Dienst wartet, bis diese Dienste gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-302">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="f81b3-303">Wir gehen in einem der folgenden Abschnitte erneut auf die Datei docker-compose.yml ein, wenn wir uns damit beschäftigen, wie Microservices und Apps mit mehreren Containern implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-303">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="f81b3-304">Arbeiten mit docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f81b3-304">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="f81b3-305">Visual Studio 2017 (ab Version 15.8) kann, wie zuvor erwähnt, eine Dockerfile zu einem Projekt hinzufügen und zusätzlich noch Orchestratorunterstützung für Docker Compose zu einer Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="f81b3-305">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="f81b3-306">Wenn Sie zum ersten Mal Containerorchestratorunterstützung hinzufügen, wie in Abbildung 5.7 gezeigt, erstellt Visual Studio die Dockerfile für das Projekt sowie ein neues Projekt (Dienstbereich) in Ihrer Projektmappe mit mehreren globalen `docker-compose*.yml`-Dateien. Anschließend wird das Projekt diesen Dateien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-306">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="f81b3-307">Sie können dann die docker-compose.yml-Dateien öffnen und mit zusätzlichen Features aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-307">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="f81b3-308">Sie müssen diesen Vorgang für alle Projekte wiederholen, die Sie in die docker-compose.yml-Datei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f81b3-308">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="f81b3-309">Zum Zeitpunkt der Erstellung dieses Dokuments unterstützt Visual Studio Docker Compose- und Service Fabric-Orchestratoren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-309">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![Kontextmenüoption zum Hinzufügen der Orchestratorunterstützung zu einem ASP.NET Core-Projekt](./media/image21.png)

<span data-ttu-id="f81b3-311">**Abbildung 5-7**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-311">**Figure 5-7**.</span></span> <span data-ttu-id="f81b3-312">Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein ASP.NET Core-Projekt</span><span class="sxs-lookup"><span data-stu-id="f81b3-312">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="f81b3-313">Nachdem Sie der Projektmappe in Visual Studio Orchestratorunterstützung hinzugefügt haben, sehen Sie auch einen neuen Knoten (in der `docker-compose.dcproj`Projektdatei) im Projektmappen-Explorer mit den hinzugefügten docker-compose.yml-Dateien, wie in Abbildung 5.8 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-313">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Knoten „docker-compose“ im Projektmappen-Explorer](./media/image11.png)

<span data-ttu-id="f81b3-315">**Abbildung 5-8**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-315">**Figure 5-8**.</span></span> <span data-ttu-id="f81b3-316">Der im Projektmappen-Editor in Visual Studio 2017 hinzugefügte **docker-compose**-Strukturknoten</span><span class="sxs-lookup"><span data-stu-id="f81b3-316">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="f81b3-317">Eine Anwendung mit mehreren Containern kann unter Verwendung des Befehls `docker-compose up` mit einer einzelnen „docker-compose.yml“-Datei bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-317">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="f81b3-318">Da Visual Studio jedoch eine Gruppe von Dateien hinzufügt, können Sie abhängig von der Umgebung (Entwicklung oder Produktion) und vom Ausführungstyp (Release oder Debug) Werte außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-318">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="f81b3-319">Diese Funktion wird in späteren Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="f81b3-319">This capability will be explained in later sections.</span></span>

![5. Ausführen von Containern oder zusammengesetzten Apps](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="f81b3-321">Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="f81b3-321">Step 5.</span></span> <span data-ttu-id="f81b3-322">Erstellen Sie Ihre Docker-Anwendung, und führen Sie sie aus</span><span class="sxs-lookup"><span data-stu-id="f81b3-322">Build and run your Docker application</span></span>

<span data-ttu-id="f81b3-323">Wenn die Anwendung nur über einen einzelnen Container verfügt, können Sie sie ausführen, indem Sie sie auf dem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-323">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="f81b3-324">Enthält Ihre Anwendung dagegen mehrere Dienste, können Sie sie als zusammengesetzte Anwendung bereitstellen, indem Sie entweder einen einzelnen CLI-Befehl (docker-compose up) oder Visual Studio verwenden, wobei der Befehl dann im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-324">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="f81b3-325">Betrachten wir die unterschiedlichen Optionen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-325">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="f81b3-326">Option A: Ausführen einer Anwendung mit einem einzelnen Container</span><span class="sxs-lookup"><span data-stu-id="f81b3-326">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="f81b3-327">Verwendung von Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="f81b3-327">Using Docker CLI</span></span>

<span data-ttu-id="f81b3-328">Sie können einen Docker-Container mit dem Befehl `docker run`, wie in Abbildung 5.9 dargestellt, ausführen:</span><span class="sxs-lookup"><span data-stu-id="f81b3-328">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="f81b3-329">Der obige Befehl erstellt bei jeder Ausführung eine neue Containerinstanz aus dem angegebenen Image.</span><span class="sxs-lookup"><span data-stu-id="f81b3-329">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="f81b3-330">Sie können den `--name`-Parameter verwenden, um dem Container einen Namen zu geben und anschließend `docker start {name}` (alternativ die Container-ID oder den automatischen Namen), um eine vorhandene Containerinstanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-330">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![Bildschirmansicht beim Ausführen eines Docker-Containers mithilfe des Befehls „docker run“](./media/image13.png)

<span data-ttu-id="f81b3-332">**Abbildung 5-9**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-332">**Figure 5-9**.</span></span> <span data-ttu-id="f81b3-333">Ausführen eines Docker-Containers mithilfe des Befehls „docker run“</span><span class="sxs-lookup"><span data-stu-id="f81b3-333">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="f81b3-334">In diesem Fall bindet der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers.</span><span class="sxs-lookup"><span data-stu-id="f81b3-334">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="f81b3-335">Dies bedeutet, dass der Host an Port 80 lauscht und an Port 5000 des Containers weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-335">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="f81b3-336">Der dargestellte Hash ist die Container-ID, zudem wird ihm ein zufälliger lesbarer Name zugewiesen, wenn die `--name`-Option nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-336">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="f81b3-337">Verwenden von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-337">Using Visual Studio</span></span>

<span data-ttu-id="f81b3-338">Wenn Sie die Containerorchestratorunterstützung nicht hinzugefügt haben, können Sie auch eine einzelne Container-App in Visual Studio ausführen, indem Sie **STRG+F5** drücken. Sie können auch **F5** drücken, um die Anwendung innerhalb des Containers zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-338">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="f81b3-339">Der Container wird lokal mit „docker run“ ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-339">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="f81b3-340">Option B: Ausführen einer Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="f81b3-340">Option B: Running a multi-container application</span></span>

<span data-ttu-id="f81b3-341">In den meisten Unternehmensszenarios setzt sich eine Docker-Anwendung aus mehreren Diensten zusammen. Dies bedeutet, dass Sie eine Anwendung mit mehreren Containern, wie in Abbildung 5-10 dargestellt, ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-341">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![VM mit mehreren Docker-Containern](./media/image14.png)

<span data-ttu-id="f81b3-343">**Abbildung 5-10**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-343">**Figure 5-10**.</span></span> <span data-ttu-id="f81b3-344">VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="f81b3-344">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="f81b3-345">Verwendung von Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="f81b3-345">Using Docker CLI</span></span>

<span data-ttu-id="f81b3-346">Verwenden Sie den `docker-compose up`-Befehl, um eine Anwendung mit mehreren Containern mithilfe der Docker-CLI auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-346">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="f81b3-347">Dieser Befehl stellt mithilfe der **docker-compose.yml**-Datei, die auf Projektmappenebene verfügbar ist, eine Anwendung mit mehreren Containern bereit.</span><span class="sxs-lookup"><span data-stu-id="f81b3-347">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="f81b3-348">Abbildung 5.11 zeigt die Ergebnisse an, wenn der Befehl aus Ihrem Hauptprojektmappenverzeichnis ausgeführt wird, das die docker-compose.yml-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="f81b3-348">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Bildschirmansicht bei der Ausführung des Befehls „docker-compose up“](./media/image15.png)

<span data-ttu-id="f81b3-350">**Abbildung 5-11**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-350">**Figure 5-11**.</span></span> <span data-ttu-id="f81b3-351">Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“</span><span class="sxs-lookup"><span data-stu-id="f81b3-351">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="f81b3-352">Nachdem der Befehl „docker-compose up“ ausgeführt wurde, werden wie in Abbildung 5.10 die Anwendung und ihre zugehörigen Container in Ihrem Docker-Host bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-352">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="f81b3-353">Verwenden von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-353">Using Visual Studio</span></span>

<span data-ttu-id="f81b3-354">Das Ausführen einer Anwendung mit mehreren Containern mit Visual Studio 2017 ist denkbar einfach.</span><span class="sxs-lookup"><span data-stu-id="f81b3-354">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="f81b3-355">Drücken Sie einfach **STRG+F5** oder nur **F5**, um den Debugvorgang zu starten und wie üblich dabei das **docker-compose**-Projekt als Startprojekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-355">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="f81b3-356">Visual Studio kümmert sich um das erforderliche Setup. Sie können sich also darauf konzentrieren, Breakpoints zu erstellen und unabhängige Prozesse zu debuggen, die auf Remoteservern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-356">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="f81b3-357">Wie bereits erwähnt, wird jedes Mal, wenn Sie Unterstützung für die Docker-Projektmappe einem Projekt in einer Projektmappe hinzufügen, das Projekt in der globalen docker-compose.yml-Datei (Projektmappenebene) konfiguriert wird, wodurch Sie die gesamte Projektmappe auf einmal ausführen oder debuggen können.</span><span class="sxs-lookup"><span data-stu-id="f81b3-357">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="f81b3-358">Visual Studio startet einen Container für jede Projektmappe, für die die Docker-Projektmappenunterstützung aktiviert ist, und führt alle internen Schritte aus (dotnet publish, docker build usw.).</span><span class="sxs-lookup"><span data-stu-id="f81b3-358">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="f81b3-359">Wenn Sie einen Blick auf Ihre bisherige Arbeit werfen möchten, sehen Sie sich diese Datei an:</span><span class="sxs-lookup"><span data-stu-id="f81b3-359">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="f81b3-360">Wichtig dabei ist, dass Visual Studio 2017, wie in Abbildung 5-12 dargestellt, über einen zusätzlichen **Docker**-Befehl für die Aktion der F5-Taste verfügt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-360">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="f81b3-361">Diese Option ermöglicht Ihnen, eine Anwendung mit mehreren Containern auszuführen oder zu debuggen, indem Sie alle in den docker-compose.yml-Dateien auf Projektmappenebene definierten Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-361">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="f81b3-362">Die Möglichkeit, Lösungen mit mehreren Containern zu debuggen, bedeutet, das Sie mehrere Haltepunkte festlegen und jeden Haltepunkt in einem anderen Projekt (Container) festlegen können. Während des Debuggings in Visual Studio halten Sie an Haltepunkten an, die in verschiedenen Projekten definiert sind und in verschiedenen Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-362">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Symbolleiste zum Debuggen in Visual Studio über die das docker-compose-Projekt ausgeführt wird](./media/image16.png)

<span data-ttu-id="f81b3-364">**Abbildung 5-12**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-364">**Figure 5-12**.</span></span> <span data-ttu-id="f81b3-365">Ausführen von Apps mit mehreren Containern in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f81b3-365">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-366">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-366">Additional resources</span></span>

- <span data-ttu-id="f81b3-367">**Deploy an ASP.NET container to a remote Docker host (Bereitstellen eines ASP.NET-Containers in einem Docker-Remotehost)** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-367">**Deploy an ASP.NET container to a remote Docker host** \\</span></span>
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="f81b3-368">Ein Hinweis zum Testen und Bereitstellen mit Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="f81b3-368">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="f81b3-369">Die Befehle „docker-compose up“ und „docker run“ (oder Ausführen und Debuggen der Container in Visual Studio) sind zum Testen von Containern in der Entwicklungsumgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-369">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="f81b3-370">Verwenden Sie diesen Ansatz jedoch nicht für Produktionsbereitstellungen. Für diese sollten Sie Orchestratoren wie [Kubernetes](https://kubernetes.io/) oder [Service Fabric](https://azure.microsoft.com/services/service-fabric/) anzielen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-370">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="f81b3-371">Wenn Sie Kubernetes verwenden, müssen Sie [Pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) zum Organisieren von Container verwenden sowie [Dienste](https://kubernetes.io/docs/concepts/services-networking/service/), um diese zu vernetzen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-371">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="f81b3-372">Sie können ebenso [Bereitstellungen](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) verwenden, um die Erstellung und Änderung von Pods zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-372">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6. Testen Ihrer App oder Ihres Microservices](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="f81b3-374">Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="f81b3-374">Step 6.</span></span> <span data-ttu-id="f81b3-375">Testen Sie die Docker-Anwendung mithilfe des lokalen Docker-Hosts</span><span class="sxs-lookup"><span data-stu-id="f81b3-375">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="f81b3-376">Dieser Schritt hängt davon ab, welche Vorgänge die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="f81b3-376">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="f81b3-377">In einer einfachen .NET Core-Webanwendung, die als einzelner Container oder Dienst bereitgestellt wird, können Sie auf den Dienst zugreifen, indem Sie einen Browser auf dem Docker-Host öffnen und, wie in Abbildung 5-13 gezeigt, zu dieser Site navigieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-377">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="f81b3-378">(Wenn die Konfiguration in der Docker-Datei den Container einem anderen Port als Port 80 auf dem Host zuordnet, berücksichtigen Sie den Host-Port in der URL.)</span><span class="sxs-lookup"><span data-stu-id="f81b3-378">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Browseransicht einer Antwort des API-Endpunkts](./media/image18.png)

<span data-ttu-id="f81b3-380">**Abbildung 5-13**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-380">**Figure 5-13**.</span></span> <span data-ttu-id="f81b3-381">Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“</span><span class="sxs-lookup"><span data-stu-id="f81b3-381">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="f81b3-382">Wenn „localhost“ nicht auf die Docker-Host-IP verweist (was bei Verwendung von Docker CE jedoch standardmäßig der Fall sein sollte), verwenden Sie die IP-Adresse der Netzwerkkarte Ihres Computers, um zum Dienst zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="f81b3-382">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="f81b3-383">Beachten Sie, dass diese URL im Browser Port 80 für das besprochene Containerbeispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="f81b3-383">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="f81b3-384">Allerdings werden intern die Anforderungen zu Port 5000 umgeleitet, da die Bereitstellung, wie in einem vorherigen Schritt beschrieben, mit dem Befehl „docker run“ erfolgte.</span><span class="sxs-lookup"><span data-stu-id="f81b3-384">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="f81b3-385">Sie können die Anwendung auch mithilfe von „curl“ über das Terminal testen, was in Abbildung 5-14 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f81b3-385">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="f81b3-386">Bei einer Docker-Installation unter Windows lautet die standardmäßige Docker-Host-IP zusätzlich zur eigentlichen IP-Adresse Ihres Computers stets 10.0.75.1.</span><span class="sxs-lookup"><span data-stu-id="f81b3-386">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Bildschirmansicht einer Antwort des API-Endpunkts mit curl](./media/image19.png)

<span data-ttu-id="f81b3-388">**Abbildung 5-14**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-388">**Figure 5-14**.</span></span> <span data-ttu-id="f81b3-389">Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“</span><span class="sxs-lookup"><span data-stu-id="f81b3-389">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="f81b3-390">Testen und Debuggen von Containern mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f81b3-390">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="f81b3-391">Beim Ausführen und Debuggen des Containers mit Visual Studio 2017 können Sie die .NET-Anwendung in etwa so debuggen wie ohne Ausführung von Containern.</span><span class="sxs-lookup"><span data-stu-id="f81b3-391">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="f81b3-392">Testen und Debuggen ohne Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-392">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="f81b3-393">Wenn Sie mit dem Editor-/CLI-Ansatz entwickeln, ist das Debuggen von Containern schwieriger. Es ist ratsam zu debuggen, indem Traces generiert werden.</span><span class="sxs-lookup"><span data-stu-id="f81b3-393">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-394">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-394">Additional resources</span></span>

- <span data-ttu-id="f81b3-395">**Debuggen von Apps in einem lokalen Docker-Container** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-395">**Debugging apps in a local Docker container** \\</span></span>
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="f81b3-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker (Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker).**</span><span class="sxs-lookup"><span data-stu-id="f81b3-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="f81b3-397">Video.</span><span class="sxs-lookup"><span data-stu-id="f81b3-397">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="f81b3-398">Vereinfachter Workflow bei der Entwicklung von Containern mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-398">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="f81b3-399">Der Workflow bei Verwendung von Visual Studio ist wesentlich einfacher als bei Verwendung des Editor/CLI-Ansatzes.</span><span class="sxs-lookup"><span data-stu-id="f81b3-399">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="f81b3-400">Die meisten der von Docker vorausgesetzten Schritte in Zusammenhang mit der Dockerfile-Datei und den docker-compose.yml-Dateien werden, wie in Abbildung 5-15 gezeigt, von Visual Studio ausgeblendet oder vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="f81b3-400">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Vereinfachter Workflow zur Containerentwicklung mit Visual Studio: 1. Programmieren Ihrer App, 2. Hinzufügen von Docker-Unterstützung zu Projekten (einmalig), 3. Ausführen des Containers oder der docker-compose-App, 4. Testen Ihrer App oder Ihres Microservices, 5. Übertragung an das Repository mithilfe von Push und Wiederholung](./media/image20.png)

<span data-ttu-id="f81b3-402">**Abbildung 5-15**.</span><span class="sxs-lookup"><span data-stu-id="f81b3-402">**Figure 5-15**.</span></span> <span data-ttu-id="f81b3-403">Vereinfachter Workflow bei der Entwicklung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f81b3-403">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="f81b3-404">Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-404">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="f81b3-405">Aus diesem Grund ähnelt der Workflow den üblichen Entwicklungsaufgaben bei Verwendung von .NET für andere Entwicklungsarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f81b3-405">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="f81b3-406">Sie müssen wissen, was im Hintergrund passiert (Imageerstellungsprozess, verwendete Basisimages, Bereitstellung von Containern usw.), und in einigen Fällen müssen Sie auch die Dockerfile oder die docker-compose.yml-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f81b3-406">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="f81b3-407">Aber der Großteil der Arbeit wird durch Verwendung von Visual Studio, stark vereinfacht, und Ihre Produktivität wird entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="f81b3-407">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f81b3-408">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-408">Additional resources</span></span>

- <span data-ttu-id="f81b3-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017 (.NET-Docker-Entwicklung mit Visual Studio 2017)** \\</span><span class="sxs-lookup"><span data-stu-id="f81b3-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \\</span></span>
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="f81b3-410">Verwenden von PowerShell-Befehlen in einer Dockerfile-Datei zum Einrichten von Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="f81b3-410">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="f81b3-411">[Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/index) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images zu konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f81b3-411">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="f81b3-412">Um Windows-Container zu verwenden, führen Sie PowerShell-Befehle in der Dockerfile-Datei aus, was im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f81b3-412">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="f81b3-413">In diesem Fall wird ein Windows Server Core-Basisimage (FROM-Einstellung) verwendet und IIS wird mit einem PowerShell-Befehl ausgeführt (RUN-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="f81b3-413">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="f81b3-414">Auf ähnliche Weise können Sie auch PowerShell-Befehle verwenden, um zusätzliche Komponenten wie ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f81b3-414">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="f81b3-415">Der folgende Befehl in einer Dockerfile-Datei richtet z.B. ASP.NET 4.5 ein:</span><span class="sxs-lookup"><span data-stu-id="f81b3-415">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="f81b3-416">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f81b3-416">Additional resources</span></span>

- <span data-ttu-id="f81b3-417">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="f81b3-417">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="f81b3-418">PowerShell-Beispielbefehle, die über Dockerfile-Dateien ausgeführt werden, um Windows-Features zu berücksichtigen</span><span class="sxs-lookup"><span data-stu-id="f81b3-418">Example PowerShell commands to run from dockerfiles to include Windows features.\\</span></span>
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="f81b3-419">[Zurück](index.md)
>[Weiter](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="f81b3-419">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
