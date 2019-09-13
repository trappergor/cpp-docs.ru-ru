---
title: Создание элементов управления "Расширенное поле со списком"
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 87e2e1cd3c29ba838a17c24ece4a89adda21db0c
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907724"
---
# <a name="creating-an-extended-combo-box-control"></a>Создание элементов управления "Расширенное поле со списком"

Способ создания расширенного элемента управления "поле со списком" зависит от того, используется ли элемент управления в диалоговом окне или создается в диалоговом окне.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>Использование CComboBoxEx непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте расширенный элемент управления "поле со списком" в ресурс шаблона диалогового окна. Укажите идентификатор элемента управления.

1. Укажите все необходимые стили, используя диалоговое окно свойства расширенного элемента управления "поле со списком".

1. Используйте [Мастер добавления переменной-члена](../ide/adding-a-member-variable-visual-cpp.md) , чтобы добавить переменную члена типа [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) с помощью свойства Control. Этот элемент можно использовать для вызова `CComboBoxEx` функций членов.

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе диалогового окна для любых расширенных сообщений уведомления элемента управления "поле со списком", которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog)задайте дополнительные стили для `CComboBoxEx` объекта.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Использование CComboBoxEx в недиалоговом окне

1. Определите элемент управления в классе представления или окна.

1. Вызовите функцию [создания](../mfc/reference/ctabctrl-class.md#create) элемента управления, возможно, в [онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate), которая может быть раньше, чем функция обработчика [OnCreate](../mfc/reference/cwnd-class.md#oncreate) родительского окна. Задайте стили для элемента управления.

## <a name="see-also"></a>См. также

[Использование CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
