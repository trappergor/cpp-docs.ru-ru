---
title: Создание элемента управления "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 7b2cb47699339dd413dc1bfae7623069da56e7a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242254"
---
# <a name="creating-the-list-control"></a>Создание элемента управления "Список"

Как контролировать список ([CListCtrl](../mfc/reference/clistctrl-class.md)) создается зависит ли вы напрямую с помощью элемента управления или с помощью класса [CListView](../mfc/reference/clistview-class.md) вместо этого. Если вы используете `CListView`, платформа создает представление как часть его последовательности создания документов и представлений. Создание представления списка создается список элемент управления также (два — то же самое). Элемент управления создается в представлении [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика. В этом случае элемент управления можно добавлять элементы, используя вызов [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Использование CListCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон Добавление элемента управления списка ваш ресурс шаблона диалоговых окон. Укажите идентификатор своего элемента управления.

1. Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) добавить переменную-член типа `CListCtrl` со свойством элемента управления. Этот элемент можно использовать для вызова `CListCtrl` функций-членов.

1. Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон, сообщений уведомлений элемента управления списка, вы должны обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), установка стилей для `CListCtrl`. См. в разделе [изменение стилей элемента управления списка](../mfc/changing-list-control-styles.md). Этот параметр определяет тип «View», вы получаете в элементе управления, несмотря на то, что представление можно изменить позже.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Для использования в окне nondialog CListCtrl

1. Определите элемент управления в классе представления или окно.

1. Вызов элемента управления [создать](../mfc/reference/clistctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже родительского окна [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Применить стиль для элемента управления.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
