---
title: Создание элемента выбора даты и времени
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: de9baf63577d163b82da1c5977a6ccba6539c73a
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907600"
---
# <a name="creating-the-date-and-time-picker-control"></a>Создание элемента выбора даты и времени

Способ создания элемента управления выбор даты и времени зависит от того, используется ли элемент управления в диалоговом окне или создается в диалоговом окне.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Использование CDateTimeCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте элемент управления выбора даты и времени в ресурс шаблона диалогового окна. Укажите идентификатор элемента управления.

1. Укажите все необходимые стили, используя диалоговое окно Свойства элемента управления выбор даты и времени.

1. Используйте [Мастер добавления переменной-члена](../ide/adding-a-member-variable-visual-cpp.md) , чтобы добавить переменную члена типа [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) с помощью свойства Control. Этот элемент можно использовать для вызова `CDateTimeCtrl` функций членов.

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе диалогового окна с любыми сообщениями [об](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) элементе управления средства выбора даты и времени, которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog)задайте дополнительные стили для `CDateTimeCtrl` объекта.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Использование CDateTimeCtrl в недиалоговом окне

1. Объявите элемент управления в классе представления или окна.

1. Вызовите функцию-член [CREATE](../mfc/reference/ctabctrl-class.md#create) элемента управления, возможно, в [онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate), которая может быть раньше, чем функция обработчика [OnCreate](../mfc/reference/cwnd-class.md#oncreate) родительского окна (если вы подклассировать элемент управления). Задайте стили для элемента управления.

## <a name="see-also"></a>См. также

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
