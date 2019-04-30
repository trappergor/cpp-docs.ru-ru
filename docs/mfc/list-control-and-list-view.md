---
title: Элемент управления "Список" и представление списка
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: 5c9612a22eab27d568c0dbb86d29ba031fe5985e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365337"
---
# <a name="list-control-and-list-view"></a>Элемент управления "Список" и представление списка

Для удобства MFC инкапсулирует элемент управления "список" двумя способами. Можно использовать список элементов управления:

- Непосредственно, путем внедрения [CListCtrl](../mfc/reference/clistctrl-class.md) объект в класс диалогового окна.

- Косвенно, с помощью класса [CListView](../mfc/reference/clistview-class.md).

`CListView` позволяет легко интегрировать элементе управления списком с архитектурой документ/представление MFC, инкапсулируя элемент управления как [CEditView](../mfc/reference/ceditview-class.md) инкапсулирует элемент управления редактированием: элемент управления заполняет всю контактную зону представления MFC. (Представление *—* элемент управления, приведенное к `CListView`.)

Объект `CListView` объект наследуется от [CCtrlView](../mfc/reference/cctrlview-class.md) и его базовых классов, а также добавляет функцию-член для получения базового элемента управления списка. Просмотр членов следует используйте для работы с представление как представление. Используйте [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) функция-член для получения доступа к функции-члены элемента управления списком. Используйте эти члены в:

- Добавление, удаление или работы с «элементами» в списке.

- Задать или получить атрибуты элемента управления списка.

Для получения ссылки на `CListCtrl` базового `CListView`, вызовите `GetListCtrl` от вашего класса представления списка:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

В этом разделе описываются оба способа использования элемента управления списком.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
