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
ms.openlocfilehash: 27fed55ac8a5fc8b95f81c1bfd2c6edb3da6227d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502247"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>Элементы управления ActiveX в MFC. Добавление стандартных свойств

Свойства акции отличаются от пользовательских свойств тем, что они уже реализуются классом `COleControl` . `COleControl` содержит стандартные функции элементов, поддерживающие общие свойства элемента управления. Некоторые общие свойства включают заголовок элемента управления, а также цвет переднего плана и фона. Сведения о других свойствах хранения см. в разделе [свойства хранения, поддерживаемые мастером добавления свойств](#_core_stock_properties_supported_by_classwizard) далее в этой статье. Записи о диспетчеризации для стандартных свойств всегда имеют префикс DISP_STOCKPROP.

В этой статье описывается добавление свойства акции (в данном случае, заголовка) к элементу управления ActiveX с помощью мастера добавления свойств и объясняется результат изменений в коде. Будут рассмотрены следующие задачи:

- [Добавление свойства акции с помощью мастера добавления свойств](#_core_using_classwizard_to_add_a_stock_property)

- [Изменения в мастере добавления свойств для стандартных свойств](#_core_classwizard_changes_for_stock_properties)

- [Стандартные свойства, поддерживаемые мастером добавления свойств](#_core_stock_properties_supported_by_classwizard)

- [Свойства и уведомления на бирже](#_core_stock_properties_and_notification)

- [Свойства цвета](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic пользовательские элементы управления обычно имеют такие свойства, как верх, слева, ширина, высота, выровняйте, тег, имя, TabIndex, TabStop и родитель. Однако контейнеры элементов управления ActiveX отвечают за реализацию этих свойств элемента управления, поэтому элементы управления ActiveX не должны поддерживать эти свойства.

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a> Добавление свойства акции с помощью мастера добавления свойств

Добавление свойств хранения требует меньше кода, чем добавление пользовательских свойств, так как поддержка свойства осуществляется автоматически с помощью `COleControl` . В следующей процедуре показано добавление свойства "заголовок акции" в платформу элементов управления ActiveX и его также можно использовать для добавления других свойств хранения. Подставьте имя выбранного свойства на бумаге для заголовка.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Добавление свойства «заголовок акции» с помощью мастера добавления свойства

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить свойство**.

   Откроется [Мастер добавления свойств](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard).

1. В поле **имя свойства** щелкните **заголовок**.

1. Нажмите кнопку **Готово**.

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a> Изменения в мастере добавления свойств для стандартных свойств

Так как `COleControl` поддерживает стандартные свойства, мастер добавления свойств не изменяет объявление класса каким-либо образом; он добавляет свойство в карту диспетчеризации. Мастер добавления свойств добавляет следующую строку в карту диспетчеризации элемента управления, которая находится в реализации (. Файл CPP):

[!code-cpp[NVC_MFC_AxUI#22](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Следующая строка добавляется в описание интерфейса элемента управления (. IDL-файл:

[!code-cpp[NVC_MFC_AxUI#23](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Эта строка присваивает свойству Caption конкретный идентификатор. Обратите внимание, что свойство доступно для привязки и будет запрашивать разрешение из базы данных перед изменением значения.

Это делает свойство Caption доступным для пользователей элемента управления. Чтобы использовать значение свойства акции, необходимо получить доступ к переменной или функции-члену `COleControl` базового класса. Дополнительные сведения об этих переменных и функциях членов см. в следующем разделе, «акции», поддерживаемые мастером добавления свойств.

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a> Стандартные свойства, поддерживаемые мастером добавления свойств

`COleControl`Класс предоставляет девять стандартных свойств. Вы можете добавить нужные свойства с помощью мастера добавления свойств.

|Свойство|Запись схемы диспетчеризации|Доступ к значению|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE ()|Значение доступно как `m_sAppearance` .|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR ()|Значение, доступное при вызове метода `GetBackColor` .|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE ()|Значение доступно как `m_sBorderStyle` .|
|`Caption`|DISP_STOCKPROP_CAPTION ()|Значение, доступное при вызове метода `InternalGetText` .|
|`Enabled`|DISP_STOCKPROP_ENABLED ()|Значение доступно как `m_bEnabled` .|
|`Font`|DISP_STOCKPROP_FONT ()|См. статью [элементы управления ActiveX в MFC: использование шрифтов](mfc-activex-controls-using-fonts.md) для использования.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR ()|Значение, доступное при вызове метода `GetForeColor` .|
|`hWnd`|DISP_STOCKPROP_HWND ()|Значение доступно как `m_hWnd` .|
|`Text`|DISP_STOCKPROP_TEXT ()|Значение, доступное при вызове метода `InternalGetText` . Это свойство аналогично `Caption` , за исключением имени свойства.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE ()|Значение доступно как `m_lReadyState` или `GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a> Свойства и уведомления на бирже

Большинство стандартных свойств имеют функции уведомления, которые могут быть переопределены. Например, при каждом `BackColor` изменении свойства `OnBackColorChanged` вызывается функция (функция-член класса Control). Реализация по умолчанию (in `COleControl` ) вызывает `InvalidateControl` . Переопределите эту функцию, если требуется выполнить дополнительные действия в ответ на эту ситуацию.

## <a name="color-properties"></a><a name="_core_color_properties"></a> Свойства цвета

`ForeColor` `BackColor` При рисовании элемента управления можно использовать акции и свойства, а также собственные свойства пользовательского цвета. Чтобы использовать свойство Color, вызовите функцию-член [COleControl:: транслатеколор](reference/colecontrol-class.md#translatecolor) . Параметры этой функции являются значением свойства Color и необязательным маркером палитры. Возвращаемое значение — это значение **COLORREF** , которое может быть передано в функции GDI, такие как `SetTextColor` и `CreateSolidBrush` .

Доступ к значениям цветов для запасов `ForeColor` и `BackColor` свойств осуществляется путем вызова либо `GetForeColor` `GetBackColor` функции, соответственно.

В следующем примере демонстрируется использование этих двух свойств цвета при рисовании элемента управления. Он инициализирует временную переменную **COLORREF** и `CBrush` объект с вызовами `TranslateColor` : один использует `ForeColor` свойство, а другое — с помощью `BackColor` Свойства. `CBrush`Затем для рисования прямоугольника элемента управления используется временный объект, а цвет текста задается с помощью `ForeColor` Свойства.

[!code-cpp[NVC_MFC_AxUI#24](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Элементы управления ActiveX в MFC](mfc-activex-controls.md)<br/>
[Элементы управления ActiveX в MFC: свойства](mfc-activex-controls-properties.md)<br/>
[Элементы управления ActiveX в MFC: методы](mfc-activex-controls-methods.md)<br/>
[Класс COleControl](reference/colecontrol-class.md)
