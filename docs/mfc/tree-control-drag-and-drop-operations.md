---
title: Дерево операций перетаскивания и вставки элемента управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e1c642642f94c021001ae67d2dcc3fd87f4f287
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589089"
---
# <a name="tree-control-drag-and-drop-operations"></a>Операции перетаскивания древовидного элемента управления
Дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет уведомление, когда пользователь начинает перетаскивать элемент. Элемент управления отправляет [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) сообщение уведомления, когда пользователь начинает перетаскивать элемент с левой кнопкой мыши и [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) сообщение уведомления, когда пользователь начинает перетаскивать с расположенную справа кнопку. Дерево отказаться от отправки этих уведомлений, предоставляя дерево TVS_DISABLEDRAGDROP стиль.  
  
 Получить изображение для отображения во время операции перетаскивания путем вызова [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) функция-член. Дерево создает перетаскивания точечный рисунок, на основе метки перетаскиваемый элемент. Затем дерево создает список изображений, добавляет в него растрового изображения и возвращает указатель на [CImageList](../mfc/reference/cimagelist-class.md) объекта.  
  
 Необходимо указать код, который фактически перетаскивает элемент. Это обычно включает в себя с помощью перетаскивания возможности функции списка изображений и обработки [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) и [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (или [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) сообщения, отправленные после начала операции перетаскивания. Дополнительные сведения о функции списка изображений, см. в разделе [CImageList](../mfc/reference/cimagelist-class.md) в *Справочник по библиотеке MFC* и [списки изображений](http://msdn.microsoft.com/library/windows/desktop/bb761389) в пакете Windows SDK. Дополнительные сведения о перетаскивании элемента управления дерева, см. в разделе [перетаскивания элемента представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760017), также в пакете Windows SDK.  
  
 Если элементы в виде дерева быть целевыми для операции перетаскивания и вставки, необходимо знать, когда указатель мыши находится на целевой элемент. Чтобы узнать, вызвав [HitTest](../mfc/reference/ctreectrl-class.md#hittest) функция-член. Укажите точку и целое число или адрес [TVHITTESTINFO будет СОДЕРЖАТЬ](http://msdn.microsoft.com/library/windows/desktop/bb773448) структуру, содержащую текущие координаты курсора мыши. При возврате функции, целое число или структура содержит флаг, указывающий расположение указателя мыши относительно элемента управления дерева. Если курсор находится над элементом в элементе управления иерархического представления, эта структура содержит дескриптор элемента, а также.  
  
 Можно указать, что элемент является целевым объектом операции перетаскивания и вставки путем вызова [SetItem](../mfc/reference/ctreectrl-class.md#setitem) функцию-член для начального состояния задать `TVIS_DROPHILITED` значение. Элемент, имеющий это состояние отображается в стиль, используемый для указания целевой объект перетаскивания и вставки.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

