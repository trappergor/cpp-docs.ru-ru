---
title: Класс CStockPropImpl
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 246e2a26db6adde0fec06523c1b8db09c5f552f3
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221071"
---
# <a name="cstockpropimpl-class"></a>Класс CStockPropImpl

Этот класс предоставляет методы для поддержки стандартных свойств значения.

> [!IMPORTANT]
> Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <
    class T, 
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Реализация элемента управления и наследование от класса `CStockPropImpl`.

*Имя интерфейса*<br/>
Сдвоенный интерфейс, предоставление доступа к свойствам акций.

*piid*<br/>
Указатель на идентификатор IID `InterfaceName`.

*plibid*<br/>
Указатель на идентификатор LIBID библиотеки типов, содержащие определение `InterfaceName`.

*wMajor*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*wMinor*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*<br/>
Класс, используемый для управления сведения о типе *T*. Значение по умолчанию — `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[get_Appearance](#get_appearance)|Этот метод используется для получения стиль рисования, используемые элементом управления, например, фиксированная или 3D.|
|[get_AutoSize](#get_autosize)|Вызовите этот метод, чтобы получить состояние флага, указывающее, если элемент управления не может быть любой другой размер.|
|[get_BackColor](#get_backcolor)|Вызовите этот метод, чтобы получить цвет фона элемента управления.|
|[get_BackStyle](#get_backstyle)|Этот метод используется для получения стиль фона элемента управления, либо прозрачный или непрозрачный.|
|[get_BorderColor](#get_bordercolor)|Вызовите этот метод, чтобы получить цвет границы элемента управления.|
|[get_BorderStyle](#get_borderstyle)|Этот метод используется для получения стиль границы элемента управления.|
|[get_BorderVisible](#get_bordervisible)|Вызовите этот метод, чтобы получить состояние флага, указывающее границы элемента управления является видимым или нет.|
|[get_BorderWidth](#get_borderwidth)|Этот метод используется для получения ширину (в пикселях) границы элемента управления.|
|[get_Caption](#get_caption)|Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.|
|[get_DrawMode](#get_drawmode)|Этот метод используется для получения элемента управления режим рисования, например, XOR пера или обратить цвета.|
|[get_DrawStyle](#get_drawstyle)|Этот метод для получения стиль рисования элемента управления, например, сплошная, пунктирная или пунктирная.|
|[get_DrawWidth](#get_drawwidth)|Этот метод используется для получения ширину (в пикселях) используемый методами рисования элемента управления.|
|[get_Enabled](#get_enabled)|Вызовите этот метод, чтобы получить состояние флага, указывающее, активирован ли элемент управления.|
|[get_FillColor](#get_fillcolor)|Этот метод используется для получения цвета заливки элемента управления.|
|[get_FillStyle](#get_fillstyle)|Этот метод для получения стиль заливки элемента управления, например, сплошная, прозрачным или клетчатого.|
|[get_Font](#get_font)|Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.|
|[get_ForeColor](#get_forecolor)|Вызовите этот метод, чтобы получить цвет переднего плана элемента управления.|
|[get_HWND](#get_hwnd)|Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления.|
|[get_MouseIcon](#get_mouseicon)|Этот метод используется для получения свойства рисунка рисунок (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления.|
|[get_MousePointer](#get_mousepointer)|Вызовите этот метод для получения типа указатель, отображаемый, когда указатель мыши находится над элементом управления, например, стрелку, крест или песочные часы.|
|[get_Picture](#get_picture)|Вызовите этот метод, чтобы получить указатель на свойствах изображения рисунка (значок, растровое изображение или метафайла) для отображения.|
|[get_ReadyState](#get_readystate)|Этот метод для получения состояния готовности элемента управления, например, загружается или загружается.|
|[get_TabStop](#get_tabstop)|Вызовите этот метод, чтобы получить флаг, указывающий, является ли элемент управления табуляции.|
|[get_Text](#get_text)|Вызовите этот метод, чтобы получить текст, отображаемый с элементом управления.|
|[getvalid](#get_valid)|Вызовите этот метод, чтобы получить состояние флага, указывающее, является ли элемент управления допустимым.|
|[get_Window](#get_window)|Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления. Идентичен [CStockPropImpl::get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Вызовите этот метод, чтобы задать стиль рисования, используемые элементом управления, например, фиксированная или 3D.|
|[put_AutoSize](#put_autosize)|Этот метод используется для задания значения флага, указывающее, если элемент управления не может быть любой другой размер.|
|[put_BackColor](#put_backcolor)|Вызовите этот метод, чтобы задать цвет фона элемента управления.|
|[put_BackStyle](#put_backstyle)|Этот метод используется для задания стиля фона элемента управления.|
|[put_BorderColor](#put_bordercolor)|Вызовите этот метод, чтобы задать цвет границы элемента управления.|
|[put_BorderStyle](#put_borderstyle)|Вызовите этот метод, чтобы задать стиль границы элемента управления.|
|[put_BorderVisible](#put_bordervisible)|Этот метод используется для задания значения флага, указывающее границы элемента управления является видимым или нет.|
|[put_BorderWidth](#put_borderwidth)|Вызовите этот метод, чтобы задать ширину границы элемента управления.|
|[put_Caption](#put_caption)|Этот метод используется для задания текста, отображаемого с помощью элемента управления.|
|[put_DrawMode](#put_drawmode)|Вызовите этот метод для установки элемента управления режим рисования, например, XOR пера или обратить цвета.|
|[put_DrawStyle](#put_drawstyle)|Вызовите этот метод, чтобы задать стиль рисования элемента управления, например, сплошная, пунктирная или пунктирная.|
|[put_DrawWidth](#put_drawwidth)|Вызовите этот метод, чтобы задать ширину (в пикселях), используемый методами рисования элемента управления.|
|[put_Enabled](#put_enabled)|Вызовите этот метод, чтобы задать флаг, указывающий, включена ли элемент управления.|
|[put_FillColor](#put_fillcolor)|Этот метод используется для задания цвета заливки элемента управления.|
|[put_FillStyle](#put_fillstyle)|Этот метод требуется задать стиль заливки элемента управления, например, сплошная, прозрачным или клетчатого.|
|[put_Font](#put_font)|Этот метод используется для задания свойств шрифта элемента управления.|
|[put_ForeColor](#put_forecolor)|Вызовите этот метод, чтобы задать цвет переднего плана элемента управления.|
|[put_HWND](#put_hwnd)|Этот метод вернет значение E_FAIL.|
|[put_MouseIcon](#put_mouseicon)|Этот метод используется для задания свойств изображения рисунка (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления.|
|[put_MousePointer](#put_mousepointer)|Вызовите этот метод, чтобы задать тип указателя мыши, отображаемый, когда указатель мыши находится над элементом управления, например, стрелку, крест или песочные часы.|
|[put_Picture](#put_picture)|Этот метод используется для задания свойств рисунок (значок, растровое изображение или метафайла) для отображения графики.|
|[put_ReadyState](#put_readystate)|Этот метод для задания состояния готовности элемента управления, например, загружается или загружается.|
|[put_TabStop](#put_tabstop)|Этот метод используется для задания значения флага, указывающее, является ли элемент управления табуляции.|
|[put_Text](#put_text)|Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.|
|[putvalid](#put_valid)|Вызовите этот метод, чтобы задать флаг, указывающий, если элемент управления является допустимым, или нет.|
|[put_Window](#put_window)|Этот метод вызывает метод [CStockPropImpl::put_HWND](#put_hwnd), который возвращает E_FAIL.|
|[putref_Font](#putref_font)|Этот метод используется для задания свойств шрифта элемента управления, с помощью счетчика ссылок.|
|[putref_MouseIcon](#putref_mouseicon)|Этот метод для задания свойств изображения рисунка (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления, с помощью счетчика ссылок.|
|[putref_Picture](#putref_picture)|Этот метод для задания свойств изображения рисунка (значок, растровое изображение или метафайла) для отображения, с помощью счетчика ссылок.|

## <a name="remarks"></a>Примечания

`CStockPropImpl` предоставляет **поместить** и **получить** методы для каждого стандартного свойства. Эти методы предоставляют код, необходимый для установки или получения данных элемент, связанный с каждого свойства, а также для уведомления и синхронизировать с контейнером при изменении любого свойства.

Visual Studio поддерживает стандартные свойства через ее мастера. Дополнительные сведения о Добавление стандартных свойств для элемента управления, см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md).

Для обеспечения обратной совместимости `CStockPropImpl` также предоставляет `get_Window` и `put_Window` методы, которые просто вызовите `get_HWND` и `put_HWND`, соответственно. Реализация по умолчанию `put_HWND` вернет значение E_FAIL, поскольку HWND должен быть доступным только для чтения.

Следующие свойства также имеют **putref** реализации:

- Шрифт

- MouseIcon

- Рисунок

Те же три свойства акций требуют их соответствующий член данных типа `CComPtr` или другой класс, предоставляющий ссылку на правильный интерфейс инвентаризации с помощью оператора присваивания.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="get_appearance"></a>  CStockPropImpl::get_Appearance

Этот метод используется для получения стиль рисования, используемые элементом управления, например, фиксированная или 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Параметры

*pnAppearance*<br/>
Переменная, которая получает стиль рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_autosize"></a>  CStockPropImpl::get_AutoSize

Вызовите этот метод, чтобы получить состояние флага, указывающее, если элемент управления не может быть любой другой размер.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Параметры

*pbAutoSize*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления не может быть любой другой размер.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_backcolor"></a>  CStockPropImpl::get_BackColor

Вызовите этот метод, чтобы получить цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Параметры

*pclrBackColor*<br/>
Переменная, которая получает цвет фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_backstyle"></a>  CStockPropImpl::get_BackStyle

Этот метод используется для получения стиль фона элемента управления, либо прозрачный или непрозрачный.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Параметры

*pnBackStyle*<br/>
Переменная, которая получает стиль фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_bordercolor"></a>  CStockPropImpl::get_BorderColor

Вызовите этот метод, чтобы получить цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Параметры

*pclrBorderColor*<br/>
Переменная, которая получает цвет границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_borderstyle"></a>  CStockPropImpl::get_BorderStyle

Этот метод используется для получения стиль границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Параметры

*pnBorderStyle*<br/>
Переменная, которая получает стиль границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_bordervisible"></a>  CStockPropImpl::get_BorderVisible

Вызовите этот метод, чтобы получить состояние флага, указывающее границы элемента управления является видимым или нет.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Параметры

*pbBorderVisible*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что границы элемента управления является видимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_borderwidth"></a>  CStockPropImpl::get_BorderWidth

Этот метод используется для получения ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Параметры

*pnBorderWidth*<br/>
Переменная, которая получает ширину границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_caption"></a>  CStockPropImpl::get_Caption

Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Параметры

*pbstrCaption*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_drawmode"></a>  CStockPropImpl::get_DrawMode

Этот метод используется для получения элемента управления режим рисования, например, XOR пера или обратить цвета.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Параметры

*pnDrawMode*<br/>
Переменная, которая получает режим рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_drawstyle"></a>  CStockPropImpl::get_DrawStyle

Этот метод для получения стиль рисования элемента управления, например, сплошная, пунктирная или пунктирная.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*pnDrawStyle*<br/>
Переменная, которая получает стиль рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_drawwidth"></a>  CStockPropImpl::get_DrawWidth

Этот метод используется для получения ширину (в пикселях) используемый методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Параметры

*pnDrawWidth*<br/>
Переменная, которая получает значение ширины элемента управления, в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_enabled"></a>  CStockPropImpl::get_Enabled

Вызовите этот метод, чтобы получить состояние флага, указывающее, активирован ли элемент управления.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Параметры

*pbEnabled*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления включен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_fillcolor"></a>  CStockPropImpl::get_FillColor

Этот метод используется для получения цвета заливки элемента управления.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Параметры

*pclrFillColor*<br/>
Переменная, которая получает цвета заливки элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_fillstyle"></a>  CStockPropImpl::get_FillStyle

Этот метод для получения стиль заливки элемента управления, например, сплошная, прозрачным или crosshatched.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Параметры

*pnFillStyle*<br/>
Переменная, которая получает стиль заливки элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_font"></a>  CStockPropImpl::get_Font

Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Параметры

*ppFont*<br/>
Переменная, которая получает указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_forecolor"></a>  CStockPropImpl::get_ForeColor

Вызовите этот метод, чтобы получить цвет переднего плана элемента управления.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Параметры

*pclrForeColor*<br/>
Переменная, которая получает основной цвет элементов управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_hwnd"></a>  CStockPropImpl::get_HWND

Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*phWnd*<br/>
Дескриптор окна, связанный с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_mouseicon"></a>  CStockPropImpl::get_MouseIcon

Этот метод используется для получения свойства рисунка рисунок (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*ppPicture*<br/>
Переменная, которая получает указатель на свойствах изображения рисунка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_mousepointer"></a>  CStockPropImpl::get_MousePointer

Вызовите этот метод для получения типа указатель, отображаемый, когда указатель мыши находится над элементом управления, например, стрелку, крест или песочные часы.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Параметры

*pnMousePointer*<br/>
Переменная, которая получает тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_picture"></a>  CStockPropImpl::get_Picture

Вызовите этот метод, чтобы получить указатель на свойствах изображения рисунка (значок, растровое изображение или метафайла) для отображения.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*ppPicture*<br/>
Переменная, которая получает указатель на свойствах изображения. См. в разделе [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) для получения дополнительных сведений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_readystate"></a>  CStockPropImpl::get_ReadyState

Этот метод для получения состояния готовности элемента управления, например, загружается или загружается.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Параметры

*pnReadyState*<br/>
Переменная, которая получает состояние готовности элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_tabstop"></a>  CStockPropImpl::get_TabStop

Вызовите этот метод, чтобы получить состояние флага, указывающее, является ли элемент управления табуляции.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Параметры

*pbTabStop*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления является позицией табуляции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_text"></a>  CStockPropImpl::get_Text

Вызовите этот метод, чтобы получить текст, отображаемый с элементом управления.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Параметры

*pbstrText*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_valid"></a>  CStockPropImpl::getvalid

Вызовите этот метод, чтобы получить состояние флага, указывающее, является ли элемент управления допустимым.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Параметры

*pbValid*<br/>
Переменная, которая получает состояние флага. Значение TRUE указывает, что элемент управления является допустимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="get_window"></a>  CStockPropImpl::get_Window

Вызовите этот метод, чтобы получить дескриптор окна, связанный с элементом управления. Идентичен [CStockPropImpl::get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*phWnd*<br/>
Дескриптор окна, связанный с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_appearance"></a>  CStockPropImpl::put_Appearance

Вызовите этот метод, чтобы задать стиль рисования, используемые элементом управления, например, фиксированная или 3D.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Параметры

*nAppearance*<br/>
Новый стиль рисования для использования элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_autosize"></a>  CStockPropImpl::put_AutoSize

Этот метод используется для задания значения флага, указывающее, если элемент управления не может быть любой другой размер.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Параметры

*bAutoSize*<br/>
Значение TRUE, если элемент управления не может быть любой другой размер.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_backcolor"></a>  CStockPropImpl::put_BackColor

Вызовите этот метод, чтобы задать цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Параметры

*clrBackColor*<br/>
Новый цвет фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_backstyle"></a>  CStockPropImpl::put_BackStyle

Этот метод используется для задания стиля фона элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Параметры

*nBackStyle*<br/>
Новый стиль фона элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_bordercolor"></a>  CStockPropImpl::put_BorderColor

Вызовите этот метод, чтобы задать цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Параметры

*clrBorderColor*<br/>
Новый цвет границы. Тип данных OLE_COLOR внутренне представлено как 32-разрядных длинное целое число.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_borderstyle"></a>  CStockPropImpl::put_BorderStyle

Вызовите этот метод, чтобы задать стиль границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Параметры

*nBorderStyle*<br/>
Новый стиль границы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_bordervisible"></a>  CStockPropImpl::put_BorderVisible

Этот метод используется для задания значения флага, указывающее границы элемента управления является видимым или нет.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Параметры

*bBorderVisible*<br/>
Значение TRUE, если граница является видимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_borderwidth"></a>  CStockPropImpl::put_BorderWidth

Вызовите этот метод, чтобы задать ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Параметры

*nBorderWidth*<br/>
Новая ширина границы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_caption"></a>  CStockPropImpl::put_Caption

Этот метод используется для задания текста, отображаемого с помощью элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Параметры

*bstrCaption*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_drawmode"></a>  CStockPropImpl::put_DrawMode

Вызовите этот метод для установки элемента управления режим рисования, например, XOR пера или обратить цвета.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Параметры

*nDrawMode*<br/>
Новый режим рисования для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_drawstyle"></a>  CStockPropImpl::put_DrawStyle

Вызовите этот метод, чтобы задать стиль рисования элемента управления, например, сплошная, пунктирная или пунктирная.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*nDrawStyle*<br/>
Новый стиль рисования для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_drawwidth"></a>  CStockPropImpl::put_DrawWidth

Вызовите этот метод, чтобы задать ширину (в пикселях), используемый методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Параметры

*nDrawWidth*<br/>
Новое значение ширины для использования элементом управления графические методы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_enabled"></a>  CStockPropImpl::put_Enabled

Этот метод используется для задания значения флага, указывающее, активирован ли элемент управления.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*bEnabled*<br/>
Значение TRUE, если включен элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_fillcolor"></a>  CStockPropImpl::put_FillColor

Этот метод используется для задания цвета заливки элемента управления.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Параметры

*clrFillColor*<br/>
Новый цвет заливки для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_fillstyle"></a>  CStockPropImpl::put_FillStyle

Этот метод требуется задать стиль заливки элемента управления, например, сплошная, прозрачным или клетчатого.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Параметры

*nFillStyle*<br/>
Новый стиль заливки для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_font"></a>  CStockPropImpl::put_Font

Этот метод используется для задания свойств шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_forecolor"></a>  CStockPropImpl::put_ForeColor

Вызовите этот метод, чтобы задать цвет переднего плана элемента управления.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Параметры

*clrForeColor*<br/>
Новый цвет переднего плана элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_hwnd"></a>  CStockPropImpl::put_HWND

Этот метод вернет значение E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_FAIL.

### <a name="remarks"></a>Примечания

Дескриптор окна является значение, доступное только для чтения.

##  <a name="put_mouseicon"></a>  CStockPropImpl::put_MouseIcon

Этот метод используется для задания свойств изображения рисунка (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойствах изображения рисунка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_mousepointer"></a>  CStockPropImpl::put_MousePointer

Вызовите этот метод, чтобы задать тип указателя мыши, отображаемый, когда указатель мыши находится над элементом управления, например, стрелку, крест или песочные часы.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Параметры

*nMousePointer*<br/>
Тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_picture"></a>  CStockPropImpl::put_Picture

Этот метод используется для задания свойств рисунок (значок, растровое изображение или метафайла) для отображения графики.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойствах изображения. См. в разделе [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) для получения дополнительных сведений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_readystate"></a>  CStockPropImpl::put_ReadyState

Этот метод для задания состояния готовности элемента управления, например, загружается или загружается.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Параметры

*nReadyState*<br/>
Состояние готовности элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_tabstop"></a>  CStockPropImpl::put_TabStop

Вызовите этот метод, чтобы задать флаг, указывающий, является ли элемент управления табуляции.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Параметры

*bTabStop*<br/>
Значение TRUE, если элемент управления является позицией табуляции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_text"></a>  CStockPropImpl::put_Text

Вызовите этот метод, чтобы задать текст, отображаемый с элементом управления.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*bstrText*<br/>
Текст, отображаемый с элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_valid"></a>  CStockPropImpl::putvalid

Вызовите этот метод, чтобы задать флаг, указывающий, если элемент управления является допустимым, или нет.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Параметры

*bValid*<br/>
Значение TRUE, если элемент управления является допустимым.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="put_window"></a>  CStockPropImpl::put_Window

Этот метод вызывает метод [CStockPropImpl::put_HWND](#put_hwnd), который возвращает E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Дескриптор окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_FAIL.

### <a name="remarks"></a>Примечания

Дескриптор окна является значение, доступное только для чтения.

##  <a name="putref_font"></a>  CStockPropImpl::putref_Font

Этот метод используется для задания свойств шрифта элемента управления, с помощью счетчика ссылок.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Так же, как [CStockPropImpl::put_Font](#put_font), но с подсчет ссылок.

##  <a name="putref_mouseicon"></a>  CStockPropImpl::putref_MouseIcon

Этот метод для задания свойств изображения рисунка (значок, растровое изображение или метафайла), отображаемый, когда указатель мыши находится над элементом управления, с помощью счетчика ссылок.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойствах изображения рисунка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Так же, как [CStockPropImpl::put_MouseIcon](#put_mouseicon), но с подсчет ссылок.

##  <a name="putref_picture"></a>  CStockPropImpl::putref_Picture

Этот метод для задания свойств изображения рисунка (значок, растровое изображение или метафайла) для отображения, с помощью счетчика ссылок.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойствах изображения. См. в разделе [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) для получения дополнительных сведений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Так же, как [CStockPropImpl::put_Picture](#put_picture), но с подсчет ссылок.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)
