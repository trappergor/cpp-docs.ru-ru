---
title: Добавление элемента управления в диалоговое окно (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
helpviewer_keywords:
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
ms.openlocfilehash: 92b644769bcbe2649d00ba68437bd474ee06dfcc
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293628"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>Добавление элемента управления в диалоговое окно (C++)

**Редактор диалоговых окон** отображается вкладка [окно панели элементов](/visualstudio/ide/reference/toolbox) при работе **диалоговое окно** редактора. Добавление элементов управления в новое диалоговое окно, перетащите элементы управления из **элементов** в диалоговое окно, вы создаете. Затем можно изменить местонахождение элементов управления или их размеры и форму.

Стандартные элементы управления в **элементов** являются:

- [Элемент управления Button](../mfc/reference/cbutton-class.md)

- [Элемент управления "флажок"](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Поле со списком](../mfc/reference/ccombobox-class.md)

- [Изменение элемента управления](../mfc/reference/cedit-class.md)

- Группа

- [Окно списка](../mfc/reference/clistbox-class.md)

- [Управления "переключатель"](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Статический элемент управления текст](../mfc/reference/cstatic-class.md)

- [Управления изображения](../mfc/reference/cpictureholder-class.md)

- [Элемент управления Rich Edit 2.0](../mfc/using-cricheditctrl.md)

- [Полосы прокрутки](../mfc/reference/cscrollbar-class.md)

[Стандартных элементов управления Windows](../mfc/controls-mfc.md) в **элементов** предоставить расширенные функциональные возможности в приложении. В их число входят следующее.

- [Элемент управления "ползунок"](../mfc/slider-control-styles.md)

- [Элемент управления "Счетчик"](../mfc/using-cspinbuttonctrl.md)

- [Элемент управления хода выполнения](../mfc/styles-for-the-progress-control.md)

- ["Горячий" ключа управления](../mfc/using-a-hot-key-control.md)

- [Управления "список"](../mfc/list-control-and-list-view.md)

- [Дерево](../mfc/tree-control-styles.md)

- [Набор вкладок](../mfc/tab-controls-and-property-sheets.md)

- [Анимация элемента управления](../mfc/using-an-animation-control.md)

- [Элемент управления даты средство выбора времени](../mfc/creating-the-date-and-time-picker-control.md)

- [Элемент управления месячного календаря](../mfc/month-calendar-control-examples.md)

- [IP-адрес управления](../mfc/reference/cipaddressctrl-class.md)

- [Расширенного элемента управления списком](../mfc/creating-an-extended-combo-box-control.md)

- [Пользовательский элемент управления](custom-controls-in-the-dialog-editor.md)

Можно добавить пользовательские элементы управления в диалоговое окно, выбрав **пользовательский элемент управления** значок в **элементов** и перетащив его в диалоговое окно. Чтобы добавить **Syslink** управления, добавьте пользовательский элемент управления, а затем изменить элемент управления **класс** свойства **Syslink**. Это приведет к свойства для обновления и Показать **Syslink** свойства элемента управления. Сведения об оболочках MFC см. в разделе [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

Кроме того, вы можете [Добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Вы также можете настроить **элементов** окно, чтобы упростить работу. Дополнительные сведения см. в разделе [Использование панели элементов](/visualstudio/ide/using-the-toolbox).

Дополнительные сведения об использовании **RichEdit 1.0** управления с MFC, см. в разделе [использование элемента управления RichEdit 1.0 с MFC](../windows/using-the-richedit-1-0-control-with-mfc.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-add-a-control-to-a-dialog-box"></a>Добавление элемента управления в диалоговое окно

1. Убедитесь, что диалоговое окно с вкладками открыто как текущий документ в окне редактора. Если диалоговое окно не является текущим документом, вы не увидите **вкладка диалогового окна редактора** в **элементов**.

1. На **редактор диалоговых окон** вкладке [окно панели элементов](/visualstudio/ide/reference/toolbox), выберите нужный элемент управления, затем:

   - Выберите диалоговое окно, в расположении, где вы хотите поместить элемент управления. Элемент управления выглядит, где вы выбрали.

       \- или -

   - Перетаскивание элемента управления с **элементов** окно в расположение в диалоговом окне.

       \- или -

   - Дважды щелкните элемент управления **элементов** (отображается в диалоговом окне), а затем изменить положение элемента управления в расположение, вы предпочитаете.

## <a name="to-add-multiple-controls"></a>Чтобы добавить несколько элементов управления

1. Удерживая нажатой **Ctrl** ключа, выберите элемент управления в [окно панели элементов](/visualstudio/ide/reference/toolbox).

1. Выпуск **Ctrl** ключа и диалоговое окно выбора столько раз, сколько вы хотите добавить конкретного элемента управления.

1. Нажмите клавишу **Esc** остановить размещения элементов управления.

## <a name="to-size-a-control-while-you-add-it"></a>Чтобы изменить размер элемента управления при его добавлении

1. Выберите элемент управления в [окно панели элементов](/visualstudio/ide/reference/toolbox).

1. Поместите курсор (которая отображается как перекрестие) место верхнего левого угла нового элемента управления в диалоговом окне.

1. Выберите и удерживайте кнопку мыши, чтобы закрепить в левом верхнем углу элемента управления в диалоговом окне, а затем перетащите курсор вправо и вниз до нужного размера элемента управления.

   > [!NOTE]
   > Фактически можно привязать любой из четырех углов рисуемого элемента управления. Эта процедура в качестве примера использован верхнего левого угла.

1. Отпустите кнопку мыши. В диалоговом окне, в заданный размер сопоставляет элемент управления.

   > [!TIP]
   > Можно изменить размер элемента управления после перетаскивания диалоговом окне, перемещая маркеры на границы элемента управления. Дополнительные сведения см. в разделе [изменения размера отдельных элементов управления](../windows/sizing-individual-controls.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Добавление обработчиков событий для элементов управления диалоговых окон](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Элементы управления "Диалоговое окно" и типы переменных](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)<br/>
[Классы элементов управления](../mfc/control-classes.md)<br/>
[Классы диалоговых окон](../mfc/dialog-box-classes.md)<br/>
[Стили полосы прокрутки](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[Примеры элементов управления "Rich Edit"](../mfc/rich-edit-control-examples.md)<br/>
