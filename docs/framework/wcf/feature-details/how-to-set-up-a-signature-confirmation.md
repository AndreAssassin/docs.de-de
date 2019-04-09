---
title: 'Vorgehensweise: Einrichten einer Signaturbestätigung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 78ad6a88d5c123272e1796f1a75e2bd226bfc8f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176162"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="eaddf-102">Vorgehensweise: Einrichten einer Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="eaddf-102">How to: Set Up a Signature Confirmation</span></span>
<span data-ttu-id="eaddf-103">*Signaturbestätigung* ist ein Mechanismus für einen nachrichteninitiator, um sicherzustellen, dass eine empfangene Antwort als Antwort auf die ursprüngliche Nachricht des Absenders generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eaddf-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="eaddf-104">Die Signaturbestätigung wird in der WS-Sicherheit 1.1-Spezifikation definiert.</span><span class="sxs-lookup"><span data-stu-id="eaddf-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="eaddf-105">Wenn ein Endpunkt WS-Sicherheit 1.0 unterstützt, können Sie keine Signaturbestätigung verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaddf-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>  
  
 <span data-ttu-id="eaddf-106">In den folgenden Verfahren wird beschrieben, wie die Signaturbestätigung mit <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="eaddf-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="eaddf-107">Sie können das gleiche Verfahren mit <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaddf-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="eaddf-108">Das Verfahren baut auf die grundlegenden Schritte finden Sie im [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="eaddf-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="eaddf-109">So aktivieren Sie die Signaturbestätigung in Code</span><span class="sxs-lookup"><span data-stu-id="eaddf-109">To enable signature confirmation in code</span></span>  
  
1.  <span data-ttu-id="eaddf-110">Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eaddf-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>  
  
2.  <span data-ttu-id="eaddf-111">Erstellen Sie eine Instanz von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="eaddf-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>  
  
3.  <span data-ttu-id="eaddf-112">Legen Sie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> auf `true` fest</span><span class="sxs-lookup"><span data-stu-id="eaddf-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="eaddf-113">Fügen Sie der Bindungsauflistung das Sicherheitselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="eaddf-113">Add the security element to the binding collection.</span></span>  
  
5.  <span data-ttu-id="eaddf-114">Erstellen Sie eine benutzerdefinierte Bindung gemäß [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="eaddf-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="eaddf-115">So aktivieren Sie die Signaturbestätigung in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="eaddf-115">To enable signature confirmation in configuration</span></span>  
  
1.  <span data-ttu-id="eaddf-116">Fügen Sie dem `<customBinding>``<bindings>`-Abschnitt der Konfigurationsdatei ein -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="eaddf-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="eaddf-117">Fügen Sie ein `<binding>`-Element hinzu, und legen Sie das Namensattribut auf einen passenden Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eaddf-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="eaddf-118">Fügen Sie ein entsprechendes Codierungselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="eaddf-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="eaddf-119">Im folgenden Beispiel wird ein `<TextMessageEncoding>`-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eaddf-119">The following example adds a `<TextMessageEncoding>` element.</span></span>  
  
4.  <span data-ttu-id="eaddf-120">Hinzufügen einer `<security>` untergeordnete Element, und legen die `requireSignatureConfirmation` -Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="eaddf-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>  
  
5.  <span data-ttu-id="eaddf-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="eaddf-121">Optional.</span></span> <span data-ttu-id="eaddf-122">Um signaturbestätigung während des Bootstraps aktivieren möchten, fügen einen [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) untergeordneten-Element, und legen die `equireSignatureConfirmation` Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="eaddf-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `equireSignatureConfirmation` attribute to `true`.</span></span>  
  
6.  <span data-ttu-id="eaddf-123">Fügen Sie ein entsprechendes Transportelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="eaddf-123">Add an appropriate transport element.</span></span> <span data-ttu-id="eaddf-124">Im folgenden Beispiel wird ein [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span><span class="sxs-lookup"><span data-stu-id="eaddf-124">The following example adds an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a><span data-ttu-id="eaddf-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eaddf-125">Example</span></span>  
 <span data-ttu-id="eaddf-126">Der folgende Code erstellt eine Instanz von <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und legt die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="eaddf-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="eaddf-127">Beachten Sie, dass in diesem Beispiel das im vorangehenden Beispiel gezeigte `<secureConversationBootstrap>`-Element nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eaddf-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="eaddf-128">In diesem Beispiel wird die Signaturbestätigung veranschaulicht, wenn ein Windows-(Kerberos-Protokoll)-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eaddf-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="eaddf-129">In diesem Fall wird die Signatur des Clients in allen Antworten vom Dienst zurückgegeben und vom Client bestätigt.</span><span class="sxs-lookup"><span data-stu-id="eaddf-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eaddf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaddf-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="eaddf-131">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="eaddf-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="eaddf-132">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="eaddf-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
