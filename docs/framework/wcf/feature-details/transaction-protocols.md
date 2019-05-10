---
title: Transaktionsprotokolle
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 31fa6a776cc69c09f030c4de857085b30bf2edba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585767"
---
# <a name="transaction-protocols"></a><span data-ttu-id="d6493-102">Transaktionsprotokolle</span><span class="sxs-lookup"><span data-stu-id="d6493-102">Transaction Protocols</span></span>
<span data-ttu-id="d6493-103">Windows Communication Foundation (WCF) implementiert die WS-Atomic Transaction und WS-Coordination-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="d6493-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="d6493-104">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="d6493-104">Specification/Document</span></span>|<span data-ttu-id="d6493-105">Version</span><span class="sxs-lookup"><span data-stu-id="d6493-105">Version</span></span>|<span data-ttu-id="d6493-106">Link</span><span class="sxs-lookup"><span data-stu-id="d6493-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="d6493-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="d6493-107">WS-Coordination</span></span>|<span data-ttu-id="d6493-108">1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-108">1.0</span></span><br /><br /> <span data-ttu-id="d6493-109">1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-109">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96104><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96079](https://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="d6493-110">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="d6493-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="d6493-111">1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-111">1.0</span></span><br /><br /> <span data-ttu-id="d6493-112">1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-112">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96080><br /><br /> https://go.microsoft.com/fwlink/?LinkId=96081|  
  
 <span data-ttu-id="d6493-113">Die Interoperabilität für diese Protokolle ist für zwei Ebenen erforderlich: zwischen Anwendungen und zwischen Transaktions-Managern (siehe folgende Abbildung).</span><span class="sxs-lookup"><span data-stu-id="d6493-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="d6493-114">In den Spezifikationen werden die Nachrichtenformate und der Nachrichtenaustausch für beide Interoperabilitätsebenen ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="d6493-115">Bestimmte Sicherheits- und Zuverlässigkeitsstufen sowie Codierungen gelten für einen Austausch von Anwendung zu Anwendung wie bei einem normalen Anwendungsaustausch.</span><span class="sxs-lookup"><span data-stu-id="d6493-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="d6493-116">Für eine erfolgreiche Interoperabilität zwischen den Transaktions-Managern ist eine Einigung auf eine bestimmte Bindung erforderlich, weil diese in der Regel nicht vom Benutzer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d6493-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="d6493-117">In diesem Thema wird die Verbindung der WS-Atomic-Transaktion (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d6493-118">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet, u.&amp;#160;a. IBM, IONA und Sun Microsystems.</span><span class="sxs-lookup"><span data-stu-id="d6493-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="d6493-119">Die folgende Abbildung zeigt die Interoperabilität zwischen zwei Transaktions-Managern, Transaktions-Manager 1 und Transaktions-Manager 2, und zwei Anwendungen, Anwendung 1 und Anwendung 2:</span><span class="sxs-lookup"><span data-stu-id="d6493-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Screenshot mit Interaktion zwischen Transaction Manager.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="d6493-121">Betrachten Sie ein typisches WS-Coordination/WS-AtomicTransaction-Szenario mit einem Initiator (I) und einem Teilnehmer (P).</span><span class="sxs-lookup"><span data-stu-id="d6493-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="d6493-122">Sowohl Initiator als auch Teilnehmer verfügen über Transaktions-Manager (ITM und PTM).</span><span class="sxs-lookup"><span data-stu-id="d6493-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="d6493-123">In diesem Thema wird das Zweiphasen-Commit als 2PC bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d6493-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6493-124">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d6493-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="d6493-125">12. Anwendungsnachrichtenantwort</span><span class="sxs-lookup"><span data-stu-id="d6493-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="d6493-126">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d6493-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d6493-127">13. Commit (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d6493-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="d6493-128">3. Register (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d6493-128">3. Register (Completion)</span></span>|<span data-ttu-id="d6493-129">14. Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d6493-130">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d6493-130">4. RegisterResponse</span></span>|<span data-ttu-id="d6493-131">15. Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d6493-132">5. Anwendungsnachricht</span><span class="sxs-lookup"><span data-stu-id="d6493-132">5. Application Message</span></span>|<span data-ttu-id="d6493-133">16. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d6493-134">6. CreateCoordinationContext mit Kontext</span><span class="sxs-lookup"><span data-stu-id="d6493-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="d6493-135">17. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d6493-136">7. Register (Durable)</span><span class="sxs-lookup"><span data-stu-id="d6493-136">7. Register (Durable)</span></span>|<span data-ttu-id="d6493-137">18. Commit ausgeführt (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d6493-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="d6493-138">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d6493-138">8. RegisterResponse</span></span>|<span data-ttu-id="d6493-139">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="d6493-140">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d6493-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d6493-141">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="d6493-142">10. Register (Durable)</span><span class="sxs-lookup"><span data-stu-id="d6493-142">10. Register (Durable)</span></span>|<span data-ttu-id="d6493-143">21. Commit ausgeführt (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="d6493-144">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d6493-144">11. RegisterResponse</span></span>|<span data-ttu-id="d6493-145">22. Commit ausgeführt (2PC)</span><span class="sxs-lookup"><span data-stu-id="d6493-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="d6493-146">In diesem Dokument wird die Verbindung der WS-AtomicTransaction (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d6493-147">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet.</span><span class="sxs-lookup"><span data-stu-id="d6493-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="d6493-148">In der Abbildung und in der Tabelle werden vier Nachrichtenklassen vom Standpunkt der Sicherheit dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d6493-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="d6493-149">Aktivierungsnachrichten (CreateCoordinationContext und CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="d6493-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="d6493-150">Registrierungsnachrichten (Register und RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="d6493-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="d6493-151">Protokollnachrichten (Prepare, Rollback, Commit, Aborted usw.).</span><span class="sxs-lookup"><span data-stu-id="d6493-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="d6493-152">Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d6493-152">Application messages.</span></span>  
  
 <span data-ttu-id="d6493-153">Die ersten drei Nachrichten werden als Transaktions-Manager-Nachrichten betrachtet, deren Bindungskonfiguration weiter unten in diesem Thema unter „Anwendungsnachrichtenaustausch“ behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="d6493-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="d6493-154">Bei der vierten Klasse von Nachrichten handelt es sich um Nachrichten von Anwendung zu Anwendung, die weiter unten in diesem Thema im Abschnitt "Nachrichtenbeispiele" beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d6493-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="d6493-155">Dieser Abschnitt beschreibt die protokollbindungen, die von WCF für jede dieser Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6493-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="d6493-156">Die folgenden XML-Namespaces und zugeordneten Präfixe werden in diesem Thema verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6493-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="d6493-157">Präfix</span><span class="sxs-lookup"><span data-stu-id="d6493-157">Prefix</span></span>|<span data-ttu-id="d6493-158">Version</span><span class="sxs-lookup"><span data-stu-id="d6493-158">Version</span></span>|<span data-ttu-id="d6493-159">Namespace-URI</span><span class="sxs-lookup"><span data-stu-id="d6493-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="d6493-160">s11</span><span class="sxs-lookup"><span data-stu-id="d6493-160">s11</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96014>|  
|<span data-ttu-id="d6493-161">wsa</span><span class="sxs-lookup"><span data-stu-id="d6493-161">wsa</span></span>|<span data-ttu-id="d6493-162">Vor 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="d6493-163">1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-163">1.0</span></span>|http://www.w3.org/2004/08/addressing<br /><br /> <https://go.microsoft.com/fwlink/?LinkId=96022>|  
|<span data-ttu-id="d6493-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="d6493-164">wscoor</span></span>|<span data-ttu-id="d6493-165">1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-165">1.0</span></span><br /><br /> <span data-ttu-id="d6493-166">1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-166">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96078><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96079](https://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="d6493-167">wsat</span><span class="sxs-lookup"><span data-stu-id="d6493-167">wsat</span></span>|<span data-ttu-id="d6493-168">1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-168">1.0</span></span><br /><br /> <span data-ttu-id="d6493-169">1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-169">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96080><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96081](https://go.microsoft.com/fwlink/?LinkId=96081)|  
|<span data-ttu-id="d6493-170">t</span><span class="sxs-lookup"><span data-stu-id="d6493-170">t</span></span>|<span data-ttu-id="d6493-171">Vor 1.3</span><span class="sxs-lookup"><span data-stu-id="d6493-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="d6493-172">1.3</span><span class="sxs-lookup"><span data-stu-id="d6493-172">1.3</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96082><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96100](https://go.microsoft.com/fwlink/?LinkId=96100)|  
|<span data-ttu-id="d6493-173">o</span><span class="sxs-lookup"><span data-stu-id="d6493-173">o</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96101>|  
|<span data-ttu-id="d6493-174">xsd</span><span class="sxs-lookup"><span data-stu-id="d6493-174">xsd</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96102>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="d6493-175">Transaktions-Manager-Bindungen</span><span class="sxs-lookup"><span data-stu-id="d6493-175">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="d6493-176">R1001: Transaktions-Managern, die Teilnahme an einer Transaktions WS-AT 1.0 müssen SOAP 1.1 und WS-Adressierung 2004/08 für WS-Atomic Transaction und WS-Coordination-Nachrichtenaustausch verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6493-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="d6493-177">R1002: Transaktions-Managern, die Teilnahme an einer Transaktions WS-AT 1.1 müssen SOAP 1.1 und WS-Adressierung 2005/08 für WS-Atomic Transaction und WS-Coordination-Nachrichtenaustausch verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6493-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="d6493-178">Anwendungsnachrichten werden nicht auf diese Bindungen eingeschränkt und werden später beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="d6493-179">HTTPS-Bindungen des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="d6493-179">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="d6493-180">Die HTTPS-Bindung des Transaktions-Managers richtet sich lediglich nach der Transportsicherheit, um Sicherheit zu gewährleisten und eine Vertrauenswürdigkeit zwischen den einzelnen Absender-Empfänger-Paaren in der Transaktionsstruktur herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6493-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d6493-181">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6493-181">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d6493-182">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6493-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d6493-183">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="d6493-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="d6493-184">R1111: X. 509-Zertifikate, die angezeigt wird, über das Netzwerk müssen es sich um einen Antragstellernamen aufweisen, der den vollqualifizierten Domänennamen (FQDN) des sendenden Computers entspricht.</span><span class="sxs-lookup"><span data-stu-id="d6493-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="d6493-185">B1112: DNS muss zwischen jeder Absender-Empfänger-Paaren im System für die Überprüfung von x. 509-Subject Name erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6493-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="d6493-186">Bindungskonfiguration von Aktivierung und Registrierung</span><span class="sxs-lookup"><span data-stu-id="d6493-186">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="d6493-187">WCF erfordert Anforderung/Antwort-duplexbindung mit Korrelation über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d6493-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="d6493-188">(Weitere Informationen über Korrelation und Beschreibungen der Anforderungs-/Antwortnachrichten-Austauschmuster finden Sie unter WS-AtomicTransaction, Abschnitt 8.)</span><span class="sxs-lookup"><span data-stu-id="d6493-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d6493-189">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="d6493-189">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="d6493-190">WCF unterstützt unidirektionale (Datagramm-) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d6493-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d6493-191">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d6493-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d6493-192">B1131: Implementierungen unterstützen müssen `wsa:ReferenceParameters` wie beschrieben in WS-Adressierung, Korrelation WCFs-2PC-Nachrichten zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d6493-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="d6493-193">Gemischte Sicherheitsbindung des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="d6493-193">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="d6493-194">Hierbei handelt es sich um eine alternative Bindung (gemischter Modus), der die Transportsicherheit kombiniert mit dem WS-Coordination Issued Token-Modell zu Identitätserstellungszwecken verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6493-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="d6493-195">Aktivierung und Registrierung sind die einzigen Elemente, die sich zwischen den beiden Bindungen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d6493-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d6493-196">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6493-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d6493-197">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6493-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d6493-198">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="d6493-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="d6493-199">Bindungskonfiguration von Aktivierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-199">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="d6493-200">Aktivierungsnachrichten nehmen in der Regel nicht an der Interoperabilität teil, da sie normalerweise zwischen einer Anwendung und dem lokalen Transaktions-Manager auftreten.</span><span class="sxs-lookup"><span data-stu-id="d6493-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="d6493-201">B1221: WCF verwendet eine duplex-HTTPS-Bindung (beschrieben [Messaging-Protokolle](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) für Aktivierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d6493-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="d6493-202">Es besteht eine Korrelation zwischen Anforderungs- und Antwortnachrichten, die WS-Adressierung 2004/08 für WS-AT 1.0 und WS-Adressierung 2005/08 für WS-AT 1.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6493-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="d6493-203">In der WS-Atomic Transaktion-Spezifikation, Abschnitt 8, werden die Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="d6493-204">R1222: Bei Empfang einer `CreateCoordinationContext`, muss der Koordinator Ausgeben einer `SecurityContextToken` mit zugewiesenem geheimen `STx`.</span><span class="sxs-lookup"><span data-stu-id="d6493-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="d6493-205">Dieses Token wird entsprechend der WS-Trust-Spezifikation in einem `t:IssuedTokens`-Header zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6493-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="d6493-206">R1223: Wenn es sich bei Aktivierung innerhalb eines bereits vorhandenen Koordinationskontexts stattfindet der `t:IssuedTokens` -Header mit der `SecurityContextToken` zugeordneten, vorhandenen Kontextfluss muss auf die `CreateCoordinationContext` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d6493-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="d6493-207">Ein neues `t:IssuedTokens` Header generiert werden soll, für das Anfügen an den ausgehenden `wscoor:CreateCoordinationContextResponse` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d6493-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="d6493-208">Bindungskonfiguration von Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-208">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="d6493-209">B1231: WCF verwendet eine duplex-HTTPS-Bindung (beschrieben [Messaging-Protokolle](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="d6493-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="d6493-210">Es besteht eine Korrelation zwischen Anforderungs- und Antwortnachrichten, die WS-Adressierung 2004/08 für WS-AT 1.0 und WS-Adressierung 2005/08 für WS-AT 1.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6493-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="d6493-211">In der WS-AtomicTransaction-Spezifikation, Abschnitt 8, werden weitere Details zur Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6493-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="d6493-212">R1232: Ausgehende `wscoor:Register` Nachrichten verwenden, müssen die `IssuedTokenOverTransport` Authentifizierungsmodus in beschriebenen [Sicherheitsprotokolle](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d6493-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="d6493-213">Die `wsse:Timestamp` Element muss signiert sein, mit der `SecurityContextToken STx` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6493-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="d6493-214">Diese Signatur ist Beweis für den Besitz des einer bestimmten Transaktion zugewiesenen Tokens und wird für die Authentifizierung einer Teilnehmerliste während der Transaktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6493-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="d6493-215">Die RegistrationResponse-Nachricht wird über HTTPS zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="d6493-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d6493-216">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="d6493-216">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="d6493-217">WCF unterstützt unidirektionale (Datagramm-) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d6493-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d6493-218">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d6493-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d6493-219">B1241: Implementierungen unterstützen müssen `wsa:ReferenceParameters` wie beschrieben in WS-Adressierung, Korrelation WCFs-2PC-Nachrichten zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d6493-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="d6493-220">Austausch von Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-220">Application Message Exchange</span></span>  
 <span data-ttu-id="d6493-221">In Anwendungen können beliebige Bindungen für Nachrichten verwendet werden, die von Anwendung zu Anwendung gesendet werden, solange die Bindung die folgenden Sicherheitsanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="d6493-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="d6493-222">R2001: Anwendung-zu-Anwendung übertragen müssen die `t:IssuedTokens` -Header zusammen mit den `CoordinationContext` im Header der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d6493-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="d6493-223">R2002: Integrität und Vertraulichkeit der `t:IssuedToken` muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d6493-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="d6493-224">Der `CoordinationContext`-Header enthält `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="d6493-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="d6493-225">Während die Definition von `xsd:AnyURI` ermöglicht die Verwendung von absolute und relative URIs, WCF unterstützt nur `wscoor:Identifiers`, der es sich um absolute URIs.</span><span class="sxs-lookup"><span data-stu-id="d6493-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="d6493-226">B2003: Wenn die `wscoor:Identifier` von der `wscoor:CoordinationContext` ist ein relativer URI, Fehler werden von WCF-Dienste, die transaktionale zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d6493-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="d6493-227">Nachrichtenbeispiele</span><span class="sxs-lookup"><span data-stu-id="d6493-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="d6493-228">CreateCoordinationContext-Anforderungs-/Antwortmeldungen</span><span class="sxs-lookup"><span data-stu-id="d6493-228">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="d6493-229">Die folgenden Nachrichten folgen einem Anforderungs-/Antwortmuster.</span><span class="sxs-lookup"><span data-stu-id="d6493-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="d6493-230">CreateCoordinationContext mit WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="d6493-231">CreateCoordinationContext mit WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>   
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
<a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
<a:ReplyTo>   
<Address>https://...</a:Address>   
</a:ReplyTo>   
<a:To>https://...</a:To>   
<wsse:Security>  
 <u:Timestamp>  
<wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
<wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
</u:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
<wscoor:CreateCoordinationContext>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
</wscoor:CreateCoordinationContext>  
 </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="d6493-232">CreateCoordinationContextResponse mit Vertrauenswürdigkeit vor 1.3 und WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="d6493-233">CreateCoordinationContextResponse mit Vertrauenswürdigkeit vor 1.3 und WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->   
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>   
<t:IssuedTokens>   
<wst:RequestSecurityTokenResponse   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
</wst:RequestedSecurityToken>   
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
<wst:RequestedAttachedReference>   
<wsse:SecurityTokenReference >   
<wsse:Reference  
  ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
 URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedUnattachedReference>   
<wst:RequestedProofToken>   
<wst:BinarySecret  
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
  <!-- base64 encoded value -->   
</wst:BinarySecret>   
</wst:RequestedProofToken>   
<wst:Lifetime>   
<wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
<wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
</wst:Lifetime>   
<wst:KeySize>256</wst:KeySize>   
</wst:RequestSecurityTokenResponse>   
</t:IssuedTokens>   
<o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">   
<u:Timestamp u:Id="_0">   
<u:Created>2005-12-15T23:36:12.015Z</u:Created>   
<u:Expires>2005-12-15T23:41:12.015Z</u:Expires>   
</u:Timestamp>   
</o:Security>   
</s:Header>   
<s:Body>   
<wscoor:CreateCoordinationContextResponse>   
<wscoor:CoordinationContext>   
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>   
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>   
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>   
</wscoor:CoordinationContext>   
</wscoor:CreateCoordinationContextResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="d6493-234">Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-234">Registration Messages</span></span>  
 <span data-ttu-id="d6493-235">Bei den folgenden Nachrichten handelt es sich um Registrierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d6493-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="d6493-236">Register mit WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-236">Register with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="d6493-237">Register mit WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
<a:ReplyTo>   
<a:Address>https://...</a:Address>   
</a:ReplyTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
<!-- supporting signature over the timestamp -->  
<wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
<ds:SignedInfo>   
<ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
<ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>   
<ds:Reference URI="#_0">   
<ds:Transforms>   
<ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
</ds:Transforms>   
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>   
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>   
</ds:Reference>   
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>   
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</ds:KeyInfo>   
</wsse:Signature>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:Register>   
<wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
<wscoor:ParticipantProtocolService>   
<a:Address>https://... </a:Address>  
</wscoor:ParticipantProtocolService>   
</wscoor:Register>   
</s:Body>   
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="d6493-238">RegisterResponse mit WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-238">Register Response with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="d6493-239">RegisterResponse mit WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp>   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:RegisterResponse>   
<wscoor:CoordinatorProtocolService>  
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>   
</wscoor:RegisterResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="d6493-240">Zweiphasen-Commit-Protokollnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-240">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="d6493-241">Die folgende Nachricht bezieht sich auf das Zweiphasen-Commit-Protokoll (2PC).</span><span class="sxs-lookup"><span data-stu-id="d6493-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="d6493-242">Commit mit WSAT 1.0</span><span class="sxs-lookup"><span data-stu-id="d6493-242">Commit with WSAT 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="d6493-243">Commit mit WSAT 1.1</span><span class="sxs-lookup"><span data-stu-id="d6493-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wsat:Commit />   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="d6493-244">Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d6493-244">Application Messages</span></span>  
 <span data-ttu-id="d6493-245">Bei den folgenden Nachrichten handelt es sich um Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d6493-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="d6493-246">Anwendungsnachrichtenanforderung</span><span class="sxs-lookup"><span data-stu-id="d6493-246">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
