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
ms.openlocfilehash: d308cfe83f02dcfe3687790c6638d268cc69fc24
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621432"
---
# <a name="list-control-and-list-view"></a>Элемент управления "Список" и представление списка

Для удобства MFC инкапсулирует элемент управления List двумя способами. Элементы управления "список" можно использовать:

- Непосредственно, путем встраивания объекта [CListCtrl](reference/clistctrl-class.md) в класс диалогового окна.

- Косвенно, с помощью класса [CListView](reference/clistview-class.md).

`CListView`упрощает интеграцию элемента управления "список" с архитектурой "документ-представление MFC", инкапсулирующие элемент управления так, как [CEditView](reference/ceditview-class.md) инкапсулирует элемент управления "поле ввода". элемент управления заполняет всю контактную зону представления MFC. (Представление *— это* элемент управления, приведенный к `CListView` .)

`CListView`Объект наследует от [кктрлвиев](reference/cctrlview-class.md) и его базовых классов и добавляет функцию-член для получения базового элемента управления "список". Используйте представление элементы для работы с представлением в виде представления. Используйте функцию члена [getlistctr](reference/clistview-class.md#getlistctrl) для получения доступа к функциям элементов элемента управления "список". Используйте следующие члены:

- Добавление, удаление и изменение элементов в списке.

- Установка или получение атрибутов элемента управления "список".

Чтобы получить ссылку на `CListCtrl` Базовый `CListView` вызов a, вызовите `GetListCtrl` из класса представления списка:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

В этом разделе описываются оба способа использования элемента управления "список".

## <a name="see-also"></a>См. также раздел

[Использование CListCtrl](using-clistctrl.md)<br/>
[Элементы управления](controls-mfc.md)
