---
title: Создание элемента управления в поле Расширенное поле со списком | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1a4a27e7d233f1ee6f68dbcfa2a70d3d50e9984
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394677"
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

