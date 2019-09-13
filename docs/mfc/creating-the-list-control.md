---
title: Создание элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: f1c5d8db93421e1d3ae0e39aec82bdf0f5529f1f
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907927"
---
# <a name="creating-the-list-control"></a>Создание элемента управления "Список"

Способ создания элемента управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)) зависит от того, используется ли элемент управления напрямую или вместо него используется класс [CListView](../mfc/reference/clistview-class.md) . При использовании `CListView`платформа конструирует представление в рамках последовательности создания документа или представления. При создании представления списка также создается элемент управления "список" (два из них одинаковы). Элемент управления создается в функции обработчика [OnCreate](../mfc/reference/cwnd-class.md#oncreate) представления. В этом случае элемент управления готов к добавлению элементов с помощью вызова [getlistctr](../mfc/reference/clistview-class.md#getlistctrl).

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Использование CListCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте элемент управления списка в ресурс шаблона диалогового окна. Укажите идентификатор элемента управления.

1. С помощью [мастера добавления переменной](../ide/adding-a-member-variable-visual-cpp.md) -члена добавьте переменную типа `CListCtrl` в свойство элемента управления. Этот элемент можно использовать для вызова `CListCtrl` функций членов.

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе диалогового окна с любыми сообщениями уведомления элемента управления списка, которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog)Задайте стили для `CListCtrl`. См. раздел [изменение стилей элемента управления "список](../mfc/changing-list-control-styles.md)". Это определяет вид «представления», получаемого в элементе управления, хотя это представление можно изменить позже.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Использование CListCtrl в недиалоговом окне

1. Определите элемент управления в классе представления или окна.

1. Вызовите функцию-член [CREATE](../mfc/reference/clistctrl-class.md#create) элемента управления, возможно, в [онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate), которая может быть раньше, чем функция обработчика [OnCreate](../mfc/reference/cwnd-class.md#oncreate) родительского окна (если вы подклассировать элемент управления). Задайте стили для элемента управления.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
