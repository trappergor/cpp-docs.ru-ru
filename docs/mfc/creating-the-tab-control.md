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
ms.openlocfilehash: 6d5aa6873966ecb4c845f1c503b24c07b6c0c7a3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619612"
---
# <a name="creating-the-tab-control"></a>Создание элемента управления "Вкладка"

Способ создания элемента управления "Вкладка" зависит от того, используется ли элемент управления в диалоговом окне или создается в диалоговом окне.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>Использование CTabCtrl непосредственно в диалоговом окне

1. В редакторе диалоговых окон добавьте элемент управления "Вкладка" в ресурс шаблона диалогового окна. Укажите идентификатор элемента управления.

1. Используйте [Мастер добавления переменной-члена](../ide/adding-a-member-variable-visual-cpp.md) , чтобы добавить переменную члена типа [CTabCtrl](reference/ctabctrl-class.md) с помощью свойства Control. Этот элемент можно использовать для вызова `CTabCtrl` функций членов.

1. Функции обработчика сопоставляются в классе диалогового окна для любых сообщений уведомления элемента управления Tab, которые необходимо обработать. Дополнительные сведения см. [в разделе Сопоставление сообщений с функциями](reference/mapping-messages-to-functions.md).

1. В [онинитдиалог](reference/cdialog-class.md#oninitdialog)Задайте стили для `CTabCtrl` .

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Использование CTabCtrl в недиалоговом окне

1. Определите элемент управления в классе представления или окна.

1. Вызовите функцию-член [CREATE](reference/ctabctrl-class.md#create) элемента управления, возможно, в [онинитиалупдате](reference/cview-class.md#oninitialupdate), которая может быть раньше, чем функция обработчика [OnCreate](reference/cwnd-class.md#oncreate) родительского окна (если вы подклассировать элемент управления). Задайте стили для элемента управления.

После `CTabCtrl` создания объекта можно задать или очистить следующие расширенные стили:

- **TCS_EX_FLATSEPARATORS** Элемент управления "Вкладка" будет рисовать разделители между элементами вкладки. Этот расширенный стиль влияет только на элементы управления "Вкладка", которые имеют стили **TCS_BUTTONS** и **TCS_FLATBUTTONS** . По умолчанию при создании элемента управления "Вкладка" с **TCS_FLATBUTTONS** стилем задается этот расширенный стиль.

- **TCS_EX_REGISTERDROP** Элемент управления "Вкладка" создает **TCN_GETOBJECT** сообщения уведомления для запроса целевого объекта перетаскивания при перетаскивании объекта над элементами вкладки в элементе управления.

    > [!NOTE]
    >  Чтобы получить уведомление **TCN_GETOBJECT** , необходимо инициализировать библиотеки OLE с помощью вызова [афксолеинит](reference/ole-initialization.md#afxoleinit).

Эти стили можно получить и задать после создания элемента управления с соответствующими вызовами функций члена [жетекстендедстиле](reference/ctabctrl-class.md#getextendedstyle) и [сетекстендедстиле](reference/ctabctrl-class.md#setextendedstyle) .

Например, задайте стиль **TCS_EX_FLATSEPARATORS** со следующими строками кода:

[!code-cpp[NVC_MFCControlLadenDialog#33](codesnippet/cpp/creating-the-tab-control_1.cpp)]

Удалите стиль **TCS_EX_FLATSEPARATORS** из `CTabCtrl` объекта со следующими строками кода:

[!code-cpp[NVC_MFCControlLadenDialog#34](codesnippet/cpp/creating-the-tab-control_2.cpp)]

Это приведет к удалению разделителей между кнопками `CTabCtrl` объекта.

## <a name="see-also"></a>См. также раздел

[Использование CTabCtrl](using-ctabctrl.md)<br/>
[Элементы управления](controls-mfc.md)
