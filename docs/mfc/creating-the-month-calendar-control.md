---
title: Создание элемента управления "Календарь на месяц"
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 809bc9fdf6b4477363d0a43d007a2884bb43a049
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258753"
---
# <a name="creating-the-month-calendar-control"></a>Создание элемента управления "Календарь на месяц"

Как создается элемент управления calendar month зависит от того с помощью элемента управления в диалоговом окне или создав его в окно nondialog.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Использование CMonthCalCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон Добавление элемента управления Календарь месяца ваш ресурс шаблона диалоговых окон. Укажите идентификатор своего элемента управления.

1. Укажите все стили, требуемое диалоговое окно свойств элемента управления calendar month.

1. Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) добавить переменную-член типа [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CMonthCalCtrl` функций-членов.

1. Используйте окно свойств для сопоставления функции обработчика в классе диалогового окна сообщений уведомлений управления Календарь месяца, вам нужно обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CMonthCalCtrl` объекта.

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Использование CMonthCalCtrl в окне nondialog

1. Определите элемент управления в классе представления или окно.

1. Вызов элемента управления [создать](../mfc/reference/cmonthcalctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже родительского окна [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Применить стиль для элемента управления.

## <a name="see-also"></a>См. также

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
