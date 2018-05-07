---
title: Список элементов управления и представление списка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3279ae5edc02ec52ded065c4a45d18e3236802f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="list-control-and-list-view"></a>Элемент управления "Список" и представление списка
Для удобства MFC инкапсулирует управления списком двумя способами. Список-элементы управления можно использовать:  
  
-   Непосредственно, путем внедрения [CListCtrl](../mfc/reference/clistctrl-class.md) объекта в класс диалоговых окон.  
  
-   Неявно, с помощью класса [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView` позволяет легко интегрировать элемент управления списком с архитектурой документ/представление MFC инкапсуляции элемента управления как [CEditView](../mfc/reference/ceditview-class.md) инкапсулирует элемент управления редактированием: элемент управления заполняет всю область представления MFC. (Представление *—* управления, приводится к `CListView`.)  
  
 Объект `CListView` объект наследуется от [CCtrlView](../mfc/reference/cctrlview-class.md) и его базовых классов, а также добавляет функцию-член для извлечения базового элемента управления списка. Просмотр членов следует используйте для работы с представление как представление. Используйте [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) функции-члена для получения доступа к функции-члены элемента управления списком. Используйте эти члены в:  
  
-   Добавить, удалить или управлять «элементы» в списке.  
  
-   Задать или получить атрибуты элемента управления списка.  
  
 Для получения ссылки на `CListCtrl` базового `CListView`, вызовите `GetListCtrl` из класса представления списка:  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 В этом разделе описываются оба способа использования элемента управления списком.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

