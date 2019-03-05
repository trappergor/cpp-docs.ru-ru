---
title: Создание элемента управления "Вкладка"
ms.date: 11/04/2016
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
ms.openlocfilehash: 4627009e2e07d1c5692d83d8d6262a9fcd37977e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304916"
---
# <a name="creating-the-tab-control"></a>Создание элемента управления "Вкладка"

Создании вкладок зависит от того с помощью элемента управления в диалоговом окне или создав его в окно nondialog.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>Использование CTabCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте набор вкладок для вашего ресурса шаблона диалоговых окон. Укажите идентификатор своего элемента управления.

1. Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) добавить переменную-член типа [CTabCtrl](../mfc/reference/ctabctrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CTabCtrl` функций-членов.

1. Сопоставьте функции обработчика в классе диалогового окна для любой вкладке уведомляющих сообщений элемента управления, необходимые для обработки. Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).

1. В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), установка стилей для `CTabCtrl`.

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Использование CTabCtrl в окне nondialog

1. Определите элемент управления в классе представления или окно.

1. Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже родительского окна [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Применить стиль для элемента управления.

После `CTabCtrl` объект был создан, можно установить или снять следующие расширенные стили:

- **TCS_EX_FLATSEPARATORS** вкладок элемента управления, рисующий разделители между элементов вкладки. Это расширенный стиль только влияет на вкладке элементов управления, имеющих **TCS_BUTTONS** и **TCS_FLATBUTTONS** стили. По умолчанию создание вкладок с **TCS_FLATBUTTONS** стиль устанавливает это расширенный стиль.

- **TCS_EX_REGISTERDROP** создает элемент управления вкладки **TCN_GETOBJECT** объекта уведомляющих сообщений для запроса целевого объекта перетаскивания, когда объект перетаскивается над элементы вкладок в элементе управления.

    > [!NOTE]
    >  Для получения **TCN_GETOBJECT** уведомления, необходимо инициализировать библиотеки OLE с вызовом [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit).

Эти стили можно получить и настроить, после создания элемента управления, с соответствующими вызовами [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) и [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) функций-членов.

Например, задать **TCS_EX_FLATSEPARATORS** стиль, содержащий следующие строки кода:

[!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]

Очистить **TCS_EX_FLATSEPARATORS** стиля `CTabCtrl` объект, содержащий следующие строки кода:

[!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]

Это приведет к удалению разделители, которые отображаются между кнопками из вашей `CTabCtrl` объекта.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
