---
title: Создание выбора даты и времени элемента | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 864d6cfef599da61238baa92f7ab01a8ad82229d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393299"
---
# <a name="creating-the-date-and-time-picker-control"></a>Создание элемента выбора даты и времени

Создание элемента управления выбора даты и времени зависит от того с помощью элемента управления в диалоговом окне или создав его в окно nondialog.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Использование CDateTimeCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте даты и времени средства выбора ресурса шаблона диалогового окна. Укажите идентификатор своего элемента управления.

1. Укажите все стили, который требуется, используя диалоговое окно свойств элемента управления выбора даты и времени.

1. Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) добавить переменную-член типа [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CDateTimeCtrl` функций-членов.

1. Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон для любого элемента выбора даты времени [уведомления](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) сообщений, необходимо обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CDateTimeCtrl` объекта.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Использование CDateTimeCtrl в окне nondialog

1. Объявления элемента управления в классе представления или окно.

1. Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже родительского окна [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Применить стиль для элемента управления.

## <a name="see-also"></a>См. также

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

