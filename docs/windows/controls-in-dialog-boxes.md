---
title: Элементы управления "диалоговое окно" (C++) | Документация Майкрософт
ms.date: 02/15/2019
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: 449e60e968916f7741422ca2766375ad29afd062
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505713"
---
# <a name="dialog-box-controls-c"></a>Элементы управления "диалоговое окно" (C++)

Добавить элементы управления в диалоговое окно можно с помощью вкладки **Редактор диалоговых** окон [окна Панель элементов](/visualstudio/ide/reference/toolbox) , которая позволяет выбрать нужный элемент управления и перетащить его в диалоговое окно. По умолчанию окно **панели элементов** имеет значение автоматическое скрытие. Он отображается в виде вкладки в левом поле решения, если **Редактор диалоговых окон** открыт. Однако окно **панели элементов** можно закрепить в положении, нажав кнопку **Автоматическое скрытие** в правом верхнем углу окна. Дополнительные сведения об управлении поведением этого окна см. в разделе [Управление окнами](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Самый быстрый способ добавить элементы управления в диалоговое окно, изменить положение существующих элементов управления или переместить элементы управления из одного диалогового окна в другое заключается в использовании метода перетаскивания. Расположение элемента управления выделяются пунктирной линией до тех пор, пока оно не будет перенесено в диалоговое окно. При добавлении элемента управления в диалоговое окно с методом перетаскивания элементу управления присваивается стандартная высота, соответствующая этому типу элемента управления.

Когда вы добавляете элемент управления в диалоговое окно или перемещаете его, его окончательное размещение может быть определено направляющими или полями или включенным режимом сетки макета.

После добавления элемента управления в диалоговое окно можно изменить свойства, такие как заголовок, в [окне Свойства](/visualstudio/ide/reference/properties-window). Можно также выбрать несколько элементов управления и изменить их свойства одновременно.

Дополнительные сведения о **редакторе диалоговых окон**см. в статьях [Добавление, изменение и удаление элементов управления](adding-editing-or-deleting-controls.md), [элементов управления макетом](../windows/arrangement-of-controls-on-dialog-boxes.md)и [Определение доступа и значений](../windows/defining-mnemonics-access-keys.md).

Дополнительные сведения о элементах управления и диалоговых окнах см. в разделе [классы элементов управления](../mfc/control-classes.md), [классы диалоговых окон](../mfc/dialog-box-classes.md)и [стили полосы прокрутки](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

Стандартные элементы управления, доступные на **панели элементов** с событиями по умолчанию:

|Имя элемента управления|Событие по умолчанию|
|---|---|
|[Элемент управления Button](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Элемент управления "Флажок"](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Элемент управления "Поле со списком"](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Элемент управления "Поле ввода"](../mfc/reference/cedit-class.md)|EN_CHANGE|
|Группа|(неприменимо)|
|[Элемент управления "список"](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Элемент управления "Переключатель"](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Элемент управления "Надпись"](../mfc/reference/cstatic-class.md)|(неприменимо)|
|[Элемент управления "Рисунок"](../mfc/reference/cpictureholder-class.md)|(неприменимо)|
|[Элемент управления Rich Edit 2.0](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[Элемент управления "Полоса прокрутки"](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> Дополнительные сведения об использовании элемента управления **richedit 1,0** с MFC см. в разделе [использование элемента управления RichEdit 1,0 с](./adding-editing-or-deleting-controls.md) [примерами элементов управления MFC и Rich Edit](../mfc/rich-edit-control-examples.md).

[Стандартные элементы управления Windows](../mfc/controls-mfc.md) , доступные на **панели элементов** для обеспечения расширенной функциональности:

|Имя элемента управления|Событие по умолчанию|
|---|---|
|[Ползунок - элемент управления](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Spin control](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[Progress control](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Элемент управления "Сочетание клавиш"](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[Элемент управления "Список"](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[Элемент управления "Дерево"](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[Элемент управления табуляции](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[Элемент управления "Анимация"](../mfc/using-an-animation-control.md)|ACN_START|
|[Элемент выбора даты и времени](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[Элемент управления "Календарь месяца"](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[Элемент управления "IP-адрес"](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[Элемент управления "Расширенное поле со списком"](../mfc/creating-an-extended-combo-box-control.md)||
|Пользовательский элемент управления|TTN_GETDISPINFO|

## <a name="custom-controls"></a>Пользовательские элементы управления

**Редактор диалоговых окон** позволяет использовать существующие настраиваемые или пользовательские элементы управления в шаблоне диалогового окна.

> [!NOTE]
> В этом смысле пользовательские элементы управления не следует путать с элементами управления ActiveX. Элементы управления ActiveX иногда называются пользовательскими элементами управления OLE. Кроме того, не путайте эти элементы управления с элементами управления, рисуемыми владельцем в Windows.

Эта функция предназначена для использования элементов управления, отличных от предоставляемых Windows. Во время выполнения элемент управления связывается с классом окна (а не с классом C++). Более распространенный способ выполнения этой же задачи заключается в установке любого элемента управления, например статического элемента управления, в диалоговом окне. Затем во время выполнения в функции [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog) удалите этот элемент управления и замените его своим пользовательским элементом управления.

> [!NOTE]
> Это старая методика. Сегодня рекомендуется в большинстве случаев написать элемент управления ActiveX или подкласс общего элемента управления Windows.

Для этих пользовательских элементов управления существует ограничение:

- Задание расположения в диалоговом окне.

- Введите заголовок.

- Определение имени класса Windows элемента управления, так как код приложения должен зарегистрировать элемент управления по этому имени.

- Введите 32-разрядное шестнадцатеричное значение, устанавливающее стиль элемента управления.

- Задание расширенного стиля.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также раздел

[Редактор диалоговых окон](../windows/dialog-editor.md)

<!--
[Adding Event Handlers for Dialog Box Controls](./adding-editing-or-deleting-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/adding-a-member-variable-visual-cpp.md#dialog-box-controls-and-variable-types)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->
