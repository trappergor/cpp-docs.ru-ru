---
title: Создание календарь на месяц управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0fadc3b56d0aa64068071ee7230ed125c6af925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410875"
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

