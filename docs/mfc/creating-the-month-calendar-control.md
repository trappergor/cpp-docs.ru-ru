---
title: Создание элемента управления "Календарь на месяц"
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 9e430a86c2ac08bde0f031a4c91b9ae5c6f570f3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907504"
---
# <a name="creating-the-month-calendar-control"></a>Создание элемента управления "Календарь на месяц"

Создание элемента управления "Календарь на месяц" зависит от того, используется ли элемент управления в диалоговом окне или создается в диалоговом окне.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Использование CMonthCalCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте элемент управления "календарь месяца" в ресурс шаблона диалогового окна. Укажите идентификатор элемента управления.

1. Укажите все необходимые стили, используя диалоговое окно Свойства элемента управления ' календарь на месяц '.

1. Используйте [Мастер добавления переменной-члена](../ide/adding-a-member-variable-visual-cpp.md) , чтобы добавить переменную члена типа [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) с помощью свойства Control. Этот элемент можно использовать для вызова `CMonthCalCtrl` функций членов.

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе диалогового окна для любых сообщений с уведомлениями об управлении календарем месяца, которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog)задайте дополнительные стили для `CMonthCalCtrl` объекта.

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Использование CMonthCalCtrl в недиалоговом окне

1. Определите элемент управления в классе представления или окна.

1. Вызовите функцию-член [CREATE](../mfc/reference/cmonthcalctrl-class.md#create) элемента управления, возможно, в [онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate), которая может быть раньше, чем функция обработчика [OnCreate](../mfc/reference/cwnd-class.md#oncreate) родительского окна (если вы подклассировать элемент управления). Задайте стили для элемента управления.

## <a name="see-also"></a>См. также

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
