---
title: Instance Completion Action
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 646015fbcdb7c734ae8584c7ca3979d64b81339f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791117"
---
# <a name="instance-completion-action"></a><span data-ttu-id="71299-102">Instance Completion Action</span><span class="sxs-lookup"><span data-stu-id="71299-102">Instance Completion Action</span></span>
<span data-ttu-id="71299-103">Die **Instance Completion Action** Eigenschaft von der SQL-Workflow-Instanz-Store ermöglicht die Angabe, ob die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht wird, nachdem die Instanzen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="71299-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="71299-104">Die zulässigen Werte für diese Eigenschaft sind **DeleteAll** und **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="71299-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="71299-105">In der folgenden Liste werden diese Optionen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="71299-105">The following list describes these options:</span></span>  
  
- <span data-ttu-id="71299-106">**DeleteAll (Standard).**</span><span class="sxs-lookup"><span data-stu-id="71299-106">**DeleteAll (default).**</span></span> <span data-ttu-id="71299-107">Wenn der Wert der Eigenschaft auf DeleteAll festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht, nachdem die Instanzen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="71299-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
- <span data-ttu-id="71299-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="71299-108">**DeleteNothing.**</span></span> <span data-ttu-id="71299-109">Wenn der Wert der Eigenschaft auf DeleteNothing festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen in der Persistenzdatenbank beibehalten, nachdem die Instanzen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="71299-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="71299-110">Das Beibehalten von Instanzzustandsinformationen nach dem Abschluss von Instanzen führt dazu, dass die Größe der Persistenzdatenbank zunimmt.</span><span class="sxs-lookup"><span data-stu-id="71299-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="71299-111">Mit wachsender Größe der Datenbank dauern die Datenbankvorgänge, die das Persistenzsubsystem ausführt, immer länger. Deshalb müssen Sie die Instanzzustandsinformationen in regelmäßigen Abständen endgültig aus der Persistenzdatenbank löschen, damit die die Dienste Ihren Leistungsanforderungen entsprechend ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="71299-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
