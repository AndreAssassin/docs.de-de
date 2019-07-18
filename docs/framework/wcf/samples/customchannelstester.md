---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 1517a2eb73da778c9b84ff857f4b8ad2b4334498
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425004"
---
# <a name="customchannelstester"></a>CustomChannelsTester
Der `CustomChannelsTester` ist ein Tool, das Sie zum Testen Ihrer benutzerdefinierten Channelimplementierungen mit einem Satz vordefinierter Dienstverträge verwenden können. Sie können einen Satz von Dienstverträgen auswählen und diesen mithilfe einer XML-Datei an das Tool übergeben. Anschließend generiert das Tool den Dienst und den Client, die die benutzerdefinierten Channelimplementierungen während des Nachrichtenaustauschs ausführen.  
  
### <a name="to-build-the-tool"></a>So erstellen Sie das Tool  
  
1. Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Erstellen der Projektmappe werden drei Dateien generiert: CustomChannelsTester.exe, "Testspec.xml" und "samplerun.cmd". Die Datei "samplerun.cmd" verfügt über eine Beispielbefehlszeile, die zeigt, wie Sie dieses Tool zum Testen verwenden die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.  
  
### <a name="to-run-the-tool"></a>So führen Sie das Tool aus  
  
- Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Die Verwendung der `/binding`-Option ist erforderlich.  
  
     `/dll` ist erforderlich, wenn "Bindung" keine vom System bereitgestellten Bindung von Windows Communication Foundation (WCF) bereitgestellt ist.  
  
     `/testspec` ist optional.  
  
     Auf diese Weise werden Server und Clients auf der Grundlage der Testspezifikationen und der Bindung erstellt.  
  
     Der Client und der Server werden ausgeführt und die Ergebnisse zurückgegeben.  
  
     Folgendes ist der Beispiel-XML-Code für die Beschreibung der Testspezifikationen (testspec.xml):  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
