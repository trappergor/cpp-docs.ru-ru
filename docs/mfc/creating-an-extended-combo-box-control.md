---
title: Создание элементов управления "Расширенное поле со списком"
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: d1e81664403f45a0a35cd24ceea16e1425b03403
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668771"
---
# <a name="creating-an-extended-combo-box-control"></a>Создание элементов управления "Расширенное поле со списком"

Создание расширенных поле со списком зависит от того с помощью элемента управления в диалоговом окне или создав его в окно nondialog.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>Использование CComboBoxEx непосредственно в диалоговом окне

1. В редакторе диалоговых окон Добавление элемента управления списком расширенных ваш ресурс шаблона диалоговых окон. Укажите идентификатор своего элемента управления.

1. Укажите все стили, требуемое диалоговое окно свойств элемента управления Расширенное поле со списком.

1. Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) добавить переменную-член типа [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CComboBoxEx` функций-членов.

1. Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон для любого Расширенное поле со списком поле уведомляющих сообщений элемента управления необходимо обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CComboBoxEx` объекта.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Использование CComboBoxEx в окне nondialog

1. Определите элемент управления в классе представления или окно.

1. Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже родительского окна [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика. Применить стиль для элемента управления.

## <a name="see-also"></a>См. также

[Использование CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

