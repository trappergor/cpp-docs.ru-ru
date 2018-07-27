---
title: Операции перетаскивания и вставки элемента управления дерева | Документы Microsoft
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
ms.openlocfilehash: 73aa47a2d888c88dd58d114dd4f5ca9a3f086cd3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956256"
---
# <a name="tree-control-drag-and-drop-operations"></a>Операции перетаскивания древовидного элемента управления
Структура дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет уведомление, когда пользователь начинает перетаскивать элемент. Элемент управления отправляет [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) сообщение уведомления, когда пользователь начинает перетаскивать элемент с левой кнопки мыши и [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) сообщение уведомления, когда пользователь начинает перетаскивать с правой кнопки. Можно предотвратить отправки этих уведомлений, предоставляя дерево TVS_DISABLEDRAGDROP стиля элемента управления дерева.  
  
 Получить изображение, отображаемое в ходе операции перетаскивания путем вызова [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) функции-члена. Древовидный элемент управления создает перетаскивания растровое изображение на основе заголовка перетаскиваемый элемент. Затем дерево создает список изображений, добавляет к нему растрового изображения и возвращает указатель на [CImageList](../mfc/reference/cimagelist-class.md) объекта.  
  
 Необходимо предоставить код, который фактически перетаскивает элемент. Это обычно производится с помощью перетаскивания возможности функции списка изображений обработки [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) и [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (или [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) сообщения, отправленные после начала операции перетаскивания. Дополнительные сведения о функции списка изображений см. в разделе [CImageList](../mfc/reference/cimagelist-class.md) в *Справочник по библиотеке MFC* и [списки изображений](http://msdn.microsoft.com/library/windows/desktop/bb761389) в Windows SDK. Дополнительные сведения о перетаскивании элемента управления дерева см. в разделе [перетаскивание элемента представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760017), кроме того, в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Если являться целевыми для операции перетаскивания и вставки элементов в виде дерева, необходимо знать, когда указатель мыши наведен на целевой элемент. Чтобы узнать, вызвав [HitTest](../mfc/reference/ctreectrl-class.md#hittest) функции-члена. Укажите точку и целое число со знаком или адрес [TVHITTESTINFO будет СОДЕРЖАТЬ](http://msdn.microsoft.com/library/windows/desktop/bb773448) структура, содержащая текущие координаты указателя мыши. При возврате из функции целое число или структура содержит флаг, указывающий расположение указателя мыши относительно элемента управления дерева. Если курсор находится над элементом в элементе управления иерархического представления, эта структура содержит дескриптор элемента, а также.  
  
 Можно указать, что элемент является целевым объектом операции перетаскивания и вставки путем вызова [SetItem](../mfc/reference/ctreectrl-class.md#setitem) функции-члена для установки состояния `TVIS_DROPHILITED` значение. Элемент, имеющий это состояние отображается в стиль, используемый для указания цели перетаскивания и вставки.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

