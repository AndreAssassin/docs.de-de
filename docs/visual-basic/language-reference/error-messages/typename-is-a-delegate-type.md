---
title: <typename> ist ein Delegattyp
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 45dc0403468fa40888a6c5e6bdfe6ca782e98325
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664189"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="91a80-102">"\<Typname >' ist ein Delegattyp</span><span class="sxs-lookup"><span data-stu-id="91a80-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="91a80-103">"\<Typname >' ist ein Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="91a80-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="91a80-104">Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="91a80-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="91a80-105">Häufig kann ein AddressOf-Ausdruck anstelle einer Delegatkonstruktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91a80-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="91a80-106">Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse gibt eine ungültige Argumentliste für den Delegatkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="91a80-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="91a80-107">Sie können angeben, dass nur eine einzige `AddressOf` Ausdruck verwenden, wenn eine neue Delegatinstanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91a80-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="91a80-108">Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben, wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, keinen gültigen `AddressOf` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="91a80-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="91a80-109">**Fehler-ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="91a80-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91a80-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="91a80-110">To correct this error</span></span>  
  
- <span data-ttu-id="91a80-111">Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="91a80-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a80-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a80-112">See also</span></span>

- [<span data-ttu-id="91a80-113">New-Operator</span><span class="sxs-lookup"><span data-stu-id="91a80-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="91a80-114">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="91a80-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="91a80-115">Delegaten</span><span class="sxs-lookup"><span data-stu-id="91a80-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="91a80-116">Vorgehensweise: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="91a80-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
