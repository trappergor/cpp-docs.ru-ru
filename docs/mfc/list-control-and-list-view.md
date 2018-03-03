---
title: "Список элементов управления и представление списка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46c9d559d642b6edf926b9feb49332ef7ec2924a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="list-control-and-list-view"></a>Элемент управления "Список" и представление списка
Для удобства MFC инкапсулирует управления списком двумя способами. Список-элементы управления можно использовать:  
  
-   Непосредственно, путем внедрения [CListCtrl](../mfc/reference/clistctrl-class.md) объекта в класс диалоговых окон.  
  
-   Неявно, с помощью класса [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView`позволяет легко интегрировать элемент управления списком с архитектурой документ/представление MFC инкапсуляции элемента управления как [CEditView](../mfc/reference/ceditview-class.md) инкапсулирует элемент управления редактированием: элемент управления заполняет всю область представления MFC. (Представление *—* управления, приводится к `CListView`.)  
  
 Объект `CListView` объект наследуется от [CCtrlView](../mfc/reference/cctrlview-class.md) и его базовых классов, а также добавляет функцию-член для извлечения базового элемента управления списка. Просмотр членов следует используйте для работы с представление как представление. Используйте [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) функции-члена для получения доступа к функции-члены элемента управления списком. Используйте эти члены в:  
  
-   Добавить, удалить или управлять «элементы» в списке.  
  
-   Задать или получить атрибуты элемента управления списка.  
  
 Для получения ссылки на `CListCtrl` базового `CListView`, вызовите `GetListCtrl` из класса представления списка:  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 В этом разделе описываются оба способа использования элемента управления списком.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

