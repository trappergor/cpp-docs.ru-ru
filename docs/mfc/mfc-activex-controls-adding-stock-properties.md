---
title: Элементы управления ActiveX в MFC. Добавление стандартных свойств
ms.date: 11/04/2016
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
ms.openlocfilehash: 16bdfddf0c028bc6a312767844b38c58c942d56e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364666"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>Элементы управления ActiveX в MFC. Добавление стандартных свойств

Свойства запасов отличаются от пользовательских свойств `COleControl`тем, что они уже реализованы классом. `COleControl`содержит предопределенные функции членов, которые поддерживают общие свойства для управления. Некоторые общие свойства включают подпись элемента управления и передний план и фоновые цвета. Для получения информации о других свойствах акций, [см. Фондовый Свойства поддерживается Добавить собственности мастера](#_core_stock_properties_supported_by_classwizard) позже в этой статье. Записи карты отправки для свойств запасов всегда префиксированы DISP_STOCKPROP.

В этой статье описывается, как добавить свойство акций (в данном случае caption) к управлению ActiveX с помощью Add Property Wizard и объясняется полученные изменения кода. Будут рассмотрены следующие задачи:

- [Использование мастера свойств добавления для добавления акционерного свойства](#_core_using_classwizard_to_add_a_stock_property)

- [Добавление изменений мастера свойств для свойств запасов](#_core_classwizard_changes_for_stock_properties)

- [Свойства склада, поддерживаемые Мастером Свойств Добавления](#_core_stock_properties_supported_by_classwizard)

- [Свойства запасов и уведомления](#_core_stock_properties_and_notification)

- [Цветовые свойства](#_core_color_properties)

    > [!NOTE]
    >  Пользовательские элементы визуального элемента обычно имеют такие свойства, как Top, Left, Width, Height, Align, Tag, Name, TabIndex, TabStop и Parent. Контейнеры управления ActiveX, однако, отвечают за реализацию этих свойств управления и, следовательно, элементы управления ActiveX не должны поддерживать эти свойства.

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a>Использование мастера свойств добавления для добавления свойства запаса

Добавление свойств запасов требует меньше кода, чем добавление пользовательских `COleControl`свойств, поскольку поддержка свойства обрабатывается автоматически. Следующая процедура демонстрирует добавление свойства подписи к запасу в рамки управления ActiveX, а также может быть использована для добавления других свойств запасов. Замените выбранное имя недвижимости акции для подписи.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Добавление свойства субцентной подписи с помощью мастера свойств добавления

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. Из меню ярлыка, нажмите **Добавить,** а затем нажмите **Добавить свойство**.

   Это открывает [Мастер свойств добавления.](../ide/names-add-property-wizard.md)

1. В поле **имени свойства** нажмите **Подпись**.

1. Нажмите кнопку **Готово**.

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a>Добавление изменений мастера свойств для свойств складской

Поскольку `COleControl` поддерживает свойства запасов, мастер свойств Добавления никоим образом не изменяет декларацию класса; он добавляет свойство на карту отправки. Волшебник свойств Добавления добавляет следующую строку к карте диспетчеризации элемента управления, которая находится в реализации (. CPP) файл:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Следующая строка добавляется в описание интерфейса элемента управления (. IDL) файл:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Эта строка присваивает свойству caption определенный идентификатор. Обратите внимание, что свойство является обязательным, и запросит разрешение у базы данных перед изменением значения.

Это делает свойство caption доступным для пользователей вашего элемента управления. Чтобы использовать значение фондового свойства, доступ к переменной `COleControl` члена или функции члена базового класса. Для получения дополнительной информации об этих переменных членов и функциях членов смотрите следующий раздел, Stock Properties Поддерживается Мастером Свойств Добавления.

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a>Свойства фондовых при поддержке Мастера Свойств Добавления

Класс `COleControl` предоставляет девять свойств запасов. Вы можете добавить свойства, которые вы хотите, используя Add Property Wizard.

|Свойство|Отправка карты запись|Как получить доступ к значению|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE()|Значение доступно `m_sAppearance`как .|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR()|Значение доступно `GetBackColor`по телефону .|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE()|Значение доступно `m_sBorderStyle`как .|
|`Caption`|DISP_STOCKPROP_CAPTION()|Значение доступно `InternalGetText`по телефону .|
|`Enabled`|DISP_STOCKPROP_ENABLED()|Значение доступно `m_bEnabled`как .|
|`Font`|DISP_STOCKPROP_FONT()|Смотрите статью [MFC ActiveX Controls: Использование шрифтов](../mfc/mfc-activex-controls-using-fonts.md) для использования.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR()|Значение доступно `GetForeColor`по телефону .|
|`hWnd`|DISP_STOCKPROP_HWND()|Значение доступно `m_hWnd`как .|
|`Text`|DISP_STOCKPROP_TEXT()|Значение доступно `InternalGetText`по телефону . Это свойство такое же, как, `Caption`за исключением названия свойства.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|Значение доступно `m_lReadyState` как или`GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a>Фондовые Свойства и уведомления

Большинство свойств запасов имеют функции уведомлений, которые могут быть переопределены. Например, всякий `BackColor` раз, когда `OnBackColorChanged` свойство изменено, вызывается функция (функция элемента класса управления). Реализация по умолчанию `COleControl` `InvalidateControl`(в ) вызывает . Переопределить эту функцию, если вы хотите предпринять дополнительные действия в ответ на эту ситуацию.

## <a name="color-properties"></a><a name="_core_color_properties"></a>Цветовые свойства

Вы можете использовать `ForeColor` `BackColor` запас и свойства, или ваши собственные свойства цвета, при покраске управления. Чтобы использовать свойство цвета, позвоните в функцию [cOleControl::TranslateColor.](../mfc/reference/colecontrol-class.md#translatecolor) Параметры этой функции являются значение мецены цвета и дополнительной ручкой палитры. Значение возврата — это значение **COLORREF,** которое может `SetTextColor` быть `CreateSolidBrush`передано функциям GDI, таким как и .

Значения цвета для `ForeColor` запасов `BackColor` и свойств доступны, `GetForeColor` позвонив либо или функции, `GetBackColor` соответственно.

Следующий пример демонстрирует использование этих двух цветовых свойств при покраске элемента управления. Он инициирует временную переменную `CBrush` **COLORREF** и объект `ForeColor` с вызовами: `BackColor` `TranslateColor`один с использованием свойства, а другой с помощью свойства. Временный `CBrush` объект затем используется для покраски прямоугольника элемента управления, `ForeColor` а цвет текста устанавливается с помощью свойства.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Свойства](../mfc/mfc-activex-controls-properties.md)<br/>
[Элементы ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)
