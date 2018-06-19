---
title: Элементы управления заголовка и список | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a84386781bf28edb9223f608fa7a64040eb68379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346104"
---
# <a name="header-control-and-list-control"></a>Элементы управления "Заголовок" и "Список"
В большинстве случаев используется, внедренный в элемент управления заголовка [CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView](../mfc/reference/clistview-class.md) объекта. Однако существуют случаев, когда объект отдельный заголовок элемента управления является нежелательной, например обработки данных, расположенных в столбцы или строки, в [CView](../mfc/reference/cview-class.md)-производного объекта. В этих случаях необходимо контролировать внешний вид и поведение по умолчанию элемента управления внедренных заголовок.  
  
 В общем случае нужных элемента управления "Заголовок" для предоставления стандартное поведение по умолчанию, может потребоваться использовать [CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView](../mfc/reference/clistview-class.md) вместо него. Используйте `CListCtrl` при необходимости функциональные возможности управления заголовка по умолчанию, внедренных в общего элемента управления представления списка. Используйте [CListView](../mfc/reference/clistview-class.md) при необходимости функциональные возможности управления заголовка по умолчанию, внедренных в объекте представления.  
  
> [!NOTE]
>  Эти элементы управления включать встроенные заголовка элемента управления, только если элемент представления списка создается с помощью `LVS_REPORT` стиля.  
  
 В большинстве случаев можно изменить внешний вид элемента управления внедренных заголовок, изменив стили содержащего элемента управления представления списка. Кроме того можно получить сведения об элементе управления заголовка посредством функции-члены родительского элемента управления представления списка. Тем не менее для полного контроля и доступ к атрибутам и стили элемента управления внедренных заголовок рекомендуется получить указатель на объект заголовка элемента управления.  
  
 Объект элемента управления внедренных заголовок может осуществляться из любого **CListCtrl** или `CListView` с помощью вызова соответствующего класса `GetHeaderCtrl` функции-члена. Это демонстрируется в следующем коде:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Использование списков изображений с элементами управления заголовка](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

