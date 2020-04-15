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
ms.openlocfilehash: 0aaeb1b6de0febfd5fc0d41cbcc7bad41c607af4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330677"
---
# <a name="cstockpropimpl-class"></a>Класс CStockPropImpl

Этот класс предоставляет методы поддержки значений фондового свойства.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

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
Класс реализации управления и вытекающих `CStockPropImpl`из .

*ИнтерфейсИмя*<br/>
Двойной интерфейс, обнажающий свойства запасов.

*пиид*<br/>
Указатель на IID `InterfaceName`.

*плибид*<br/>
Указатель на LIBID библиотеки типа, содержащий `InterfaceName`определение .

*wMajor*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*wMinor*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*<br/>
Класс используется для управления информацией типа для *T.* Значение по `CComTypeInfoHolder`умолчанию .

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[get_Appearance](#get_appearance)|Вызовите этот метод, чтобы получить стиль краски, используемый элементом управления, например, плоский или 3D.|
|[get_AutoSize](#get_autosize)|Вызовите этот метод, чтобы получить статус флага, который указывает, если элемент управления не может быть любого другого размера.|
|[get_BackColor](#get_backcolor)|Вызовите этот метод, чтобы получить цвет фона элемента управления.|
|[get_BackStyle](#get_backstyle)|Вызовите этот метод, чтобы получить фоновый стиль элемента управления, прозрачный или непрозрачный.|
|[get_BorderColor](#get_bordercolor)|Вызовите этот метод, чтобы получить цвет границы элемента управления.|
|[get_BorderStyle](#get_borderstyle)|Вызовите этот метод, чтобы получить пограничный стиль управления.|
|[get_BorderVisible](#get_bordervisible)|Вызовите этот метод, чтобы получить статус флага, который указывает, если граница элемента управления видна или нет.|
|[get_BorderWidth](#get_borderwidth)|Вызовите этот метод, чтобы получить ширину (в пикселях) границы элемента управления.|
|[get_Caption](#get_caption)|Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.|
|[get_DrawMode](#get_drawmode)|Вызовите этот метод, чтобы получить режим рисования элемента управления, например, XOR Pen или invert Colors.|
|[get_DrawStyle](#get_drawstyle)|Вызовите этот метод, чтобы получить стиль рисования элемента управления, например, твердый, пунктирный или пунктирный.|
|[get_DrawWidth](#get_drawwidth)|Вызовите этот метод, чтобы получить ширину чертежа (в пикселях), используемую методами рисования элемента управления.|
|[get_Enabled](#get_enabled)|Вызовите этот метод, чтобы получить статус флага, который указывает, включен ли элемент управления.|
|[get_FillColor](#get_fillcolor)|Вызовите этот метод, чтобы получить цвет заполнения элемента управления.|
|[get_FillStyle](#get_fillstyle)|Вызовите этот метод, чтобы получить стиль заполнения элемента управления, например, твердый, прозрачный или кросс-хэтч.|
|[get_Font](#get_font)|Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.|
|[get_ForeColor](#get_forecolor)|Вызовите этот метод, чтобы получить цвет переднего плана управления.|
|[get_HWND](#get_hwnd)|Вызовите этот метод, чтобы получить ручку окна, связанную с управлением.|
|[get_MouseIcon](#get_mouseicon)|Вызовите этот метод, чтобы получить свойства изображения графических (значок, бит-карта или метафил), которые будут отображаться, когда мышь находится над управлением.|
|[get_MousePointer](#get_mousepointer)|Вызовите этот метод, чтобы получить тип указателя мыши отображается, когда мышь находится над управлением, например, стрелка, крест, или песочные часы.|
|[get_Picture](#get_picture)|Вызовите этот метод, чтобы получить указатель на свойства изображения графических (значок, бит-карта, или метафайл), которые будут отображаться.|
|[get_ReadyState](#get_readystate)|Вызовите этот метод, чтобы получить готовое состояние элемента управления, например, загрузка или загрузка.|
|[get_TabStop](#get_tabstop)|Вызовите этот метод, чтобы получить флаг, который указывает, если элемент управления является остановкой вкладки или нет.|
|[get_Text](#get_text)|Вызовите этот метод, чтобы получить текст, который отображается с помощью элемента управления.|
|[получитьдействительный](#get_valid)|Вызовите этот метод, чтобы получить статус флага, который указывает, является ли элемент управления действительным или нет.|
|[get_Window](#get_window)|Вызовите этот метод, чтобы получить ручку окна, связанную с управлением. Идентичен [CStockPropImpl::get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Вызовите этот метод, чтобы установить стиль краски, используемый элементом управления, например, плоский или 3D.|
|[put_AutoSize](#put_autosize)|Вызовите этот метод, чтобы установить значение флага, которое указывает, если элемент управления не может быть любого другого размера.|
|[put_BackColor](#put_backcolor)|Вызовите этот метод, чтобы установить цвет фона элемента управления.|
|[put_BackStyle](#put_backstyle)|Вызовите этот метод, чтобы установить фоновый стиль элемента управления.|
|[put_BorderColor](#put_bordercolor)|Вызовите этот метод, чтобы установить цвет границы элемента управления.|
|[put_BorderStyle](#put_borderstyle)|Вызовите этот метод, чтобы установить пограничный стиль управления.|
|[put_BorderVisible](#put_bordervisible)|Вызовите этот метод, чтобы установить значение флага, которое указывает, видна граница элемента управления или нет.|
|[put_BorderWidth](#put_borderwidth)|Вызовите этот метод, чтобы установить ширину границы элемента управления.|
|[put_Caption](#put_caption)|Вызовите этот метод, чтобы настроить текст для отображения с помощью элемента управления.|
|[put_DrawMode](#put_drawmode)|Вызовите этот метод, чтобы установить режим рисования элемента управления, например, XOR Pen или invert Colors.|
|[put_DrawStyle](#put_drawstyle)|Вызовите этот метод, чтобы установить стиль рисования элемента управления, например, твердый, пунктирный или пунктирный.|
|[put_DrawWidth](#put_drawwidth)|Вызовите этот метод, чтобы установить ширину (в пикселях), используемую методами рисования элемента управления.|
|[put_Enabled](#put_enabled)|Вызов иметод, чтобы установить флаг, указывающий, включен ли элемент управления.|
|[put_FillColor](#put_fillcolor)|Вызовите этот метод, чтобы установить цвет заполнения элемента управления.|
|[put_FillStyle](#put_fillstyle)|Вызовите этот метод, чтобы установить стиль заполнения элемента управления, например, твердый, прозрачный или кросс-хэтч.|
|[put_Font](#put_font)|Вызовите этот метод, чтобы установить свойства шрифта элемента управления.|
|[put_ForeColor](#put_forecolor)|Вызовите этот метод, чтобы установить цвет переднего плана управления.|
|[put_HWND](#put_hwnd)|Этот метод возвращает E_FAIL.|
|[put_MouseIcon](#put_mouseicon)|Вызовите этот метод, чтобы настроить свойства изображения изображения графических (значок, бит-карта или метафилия), которые будут отображаться, когда мышь находится над управлением.|
|[put_MousePointer](#put_mousepointer)|Вызовите этот метод, чтобы установить тип указателя мыши отображается, когда мышь находится над управлением, например, стрелка, крест, или песочные часы.|
|[put_Picture](#put_picture)|Вызовите этот метод, чтобы настроить свойства изображения графического (значок, бит-карта или метафилия) для отображения.|
|[put_ReadyState](#put_readystate)|Вызовите этот метод, чтобы установить готовое состояние элемента управления, например, загрузку или загрузку.|
|[put_TabStop](#put_tabstop)|Вызовите этот метод, чтобы установить значение флага, которое указывает, если элемент управления является остановкой вкладки или нет.|
|[put_Text](#put_text)|Вызовите этот метод, чтобы настроить текст, который отображается с помощью элемента управления.|
|[putvalid](#put_valid)|Вызовите этот метод, чтобы установить флаг, указывающий, является ли элемент управления действительным или нет.|
|[put_Window](#put_window)|Этот метод называется [CStockPropImpl: :put-HWND](#put_hwnd), который возвращает E_FAIL.|
|[putref_Font](#putref_font)|Вызовите этот метод, чтобы установить свойства шрифта элемента управления с учетом количества.|
|[putref_MouseIcon](#putref_mouseicon)|Вызовите этот метод, чтобы установить свойства изображения графического (значок, бит-карта или метафилия), которые будут отображаться, когда мышь находится над управлением, с эталонным числом.|
|[putref_Picture](#putref_picture)|Вызовите этот метод, чтобы настроить свойства изображения графического (значок, бит-карта или метафилия), которые будут отображаться, с учетом подсчета.|

## <a name="remarks"></a>Remarks

`CStockPropImpl`обеспечивает **положить** и **получить** методы для каждого фондового свойства. Эти методы обеспечивают код, необходимый для установки или получения члена данных, связанного с каждым свойством, а также для уведомления и синхронизации с контейнером при изменении свойств.

Visual Studio обеспечивает поддержку фондовых свойств через своих мастеров. Для получения дополнительной информации о добавлении свойств запасов в элемент управления, [см.](../../atl/active-template-library-atl-tutorial.md)

Для обратной `CStockPropImpl` совместимости, `get_Window` а `put_Window` также подвергает `get_HWND` и `put_HWND`методы, которые просто вызова и , соответственно. Реализация `put_HWND` возврата по умолчанию E_FAIL, так как HWND должен быть свойством только для чтения.

Следующие свойства также имеют **цельную** реализацию:

- Шрифт

- MouseIcon

- Рисунок

Те же три свойства запасов требуют, `CComPtr` чтобы соответствующий член данных был типа или какой-либо другой класс, который обеспечивает правильный подсчет ссылок интерфейса с помощью оператора назначения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a>CStockPropImpl::get_Appearance

Вызовите этот метод, чтобы получить стиль краски, используемый элементом управления, например, плоский или 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Параметры

*pnВнешний*<br/>
Переменная, которая получает стиль краски управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a>CStockPropImpl::get_AutoSize

Вызовите этот метод, чтобы получить статус флага, который указывает, если элемент управления не может быть любого другого размера.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Параметры

*pbAutoSize*<br/>
Переменная, получившая статус флага. TRUE указывает на то, что элемент управления не может быть любого другого размера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a>CStockPropImpl::get_BackColor

Вызовите этот метод, чтобы получить цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Параметры

*pclrBackColor*<br/>
Переменная, которая получает фоновый цвет элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a>CStockPropImpl::get_BackStyle

Вызовите этот метод, чтобы получить фоновый стиль элемента управления, прозрачный или непрозрачный.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Параметры

*pnBackStyle*<br/>
Переменная, которая получает фоновый стиль элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a>CStockPropImpl::get_BorderColor

Вызовите этот метод, чтобы получить цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Параметры

*pclrBorderColor*<br/>
Переменная, которая получает пограничный цвет контрольного управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a>CStockPropImpl::get_BorderStyle

Вызовите этот метод, чтобы получить пограничный стиль управления.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Параметры

*pnBorderStyle*<br/>
Переменная, которая получает пограничный стиль контроля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a>CStockPropImpl::get_BorderVisible

Вызовите этот метод, чтобы получить статус флага, который указывает, если граница элемента управления видна или нет.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Параметры

*pbBorderVisible*<br/>
Переменная, получившая статус флага. TRUE указывает на то, что граница контроля видна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a>CStockPropImpl::get_BorderWidth

Вызовите этот метод, чтобы получить ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Параметры

*pnBorderWidth*<br/>
Переменная, которая получает ширину границы контроля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_caption"></a><a name="get_caption"></a>CStockPropImpl::get_Caption

Вызовите этот метод, чтобы получить текст, указанный в заголовке объекта.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Параметры

*pbstrCaption*<br/>
Текст, который будет отображаться с помощью элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a>CStockPropImpl::get_DrawMode

Вызовите этот метод, чтобы получить режим рисования элемента управления, например, XOR Pen или invert Colors.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Параметры

*pnDrawMode*<br/>
Переменная, которая получает режим рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a>CStockPropImpl::get_DrawStyle

Вызовите этот метод, чтобы получить стиль рисования элемента управления, например, твердый, пунктирный или пунктирный.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*pnDrawStyle*<br/>
Переменная, которая получает стиль рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a>CStockPropImpl::get_DrawWidth

Вызовите этот метод, чтобы получить ширину чертежа (в пикселях), используемую методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Параметры

*pnDrawШирин*<br/>
Переменная, которая получает значение ширины элемента управления, в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a>CStockPropImpl::get_Enabled

Вызовите этот метод, чтобы получить статус флага, который указывает, включен ли элемент управления.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Параметры

*pbEnabled*<br/>
Переменная, получившая статус флага. TRUE указывает на то, что элемент управления включен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a>CStockPropImpl::get_FillColor

Вызовите этот метод, чтобы получить цвет заполнения элемента управления.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Параметры

*pclrFillColor*<br/>
Переменная, которая получает цвет заполнения элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a>CStockPropImpl::get_FillStyle

Вызовите этот метод, чтобы получить стиль заполнения элемента управления, например, твердый, прозрачный или перекрестный.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Параметры

*pnFillStyle*<br/>
Переменная, которая получает стиль заполнения элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_font"></a><a name="get_font"></a>CStockPropImpl::get_Font

Вызовите этот метод, чтобы получить указатель на свойства шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Параметры

*ppФон*<br/>
Переменная, которая получает указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a>CStockPropImpl::get_ForeColor

Вызовите этот метод, чтобы получить цвет переднего плана управления.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Параметры

*pclrForeColor*<br/>
Переменная, которая получает цвет переднего плана управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a>CStockPropImpl::get_HWND

Вызовите этот метод, чтобы получить ручку окна, связанную с управлением.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*phWnd*<br/>
Ручка окна, связанная с управлением.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a>CStockPropImpl::get_MouseIcon

Вызовите этот метод, чтобы получить свойства изображения графических (значок, бит-карта или метафил), которые будут отображаться, когда мышь находится над управлением.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*ppPicture*<br/>
Переменная, которая получает указатель на свойства изображения графического.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a>CStockPropImpl::get_MousePointer

Вызовите этот метод, чтобы получить тип указателя мыши отображается, когда мышь находится над управлением, например, стрелка, крест, или песочные часы.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Параметры

*pnMousePointer*<br/>
Переменная, которая получает тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_picture"></a><a name="get_picture"></a>CStockPropImpl::get_Picture

Вызовите этот метод, чтобы получить указатель на свойства изображения графических (значок, бит-карта, или метафайл), которые будут отображаться.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Параметры

*ppPicture*<br/>
Переменная, которая получает указатель на свойства изображения. Более подробную информацию можно узнать [на примере IPictureDisp.](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a>CStockPropImpl::get_ReadyState

Вызовите этот метод, чтобы получить готовое состояние элемента управления, например, загрузка или загрузка.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Параметры

*pnReadyState*<br/>
Переменная, которая получает готовое состояние элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a>CStockPropImpl::get_TabStop

Вызовите этот метод, чтобы получить статус флага, который указывает, если элемент управления является остановкой вкладки или нет.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Параметры

*pbTabStop*<br/>
Переменная, получившая статус флага. TRUE указывает на то, что элемент управления является остановкой вкладок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_text"></a><a name="get_text"></a>CStockPropImpl::get_Text

Вызовите этот метод, чтобы получить текст, который отображается с помощью элемента управления.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Параметры

*pbstrText*<br/>
Текст, отображаемый с помощью элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a>CStockPropImpl::getvalid

Вызовите этот метод, чтобы получить статус флага, который указывает, является ли элемент управления действительным или нет.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Параметры

*pbValid*<br/>
Переменная, получившая статус флага. TRUE указывает, что элемент управления действителен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplget_window"></a><a name="get_window"></a>CStockPropImpl::get_Window

Вызовите этот метод, чтобы получить ручку окна, связанную с управлением. Идентичен [CStockPropImpl::get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Параметры

*phWnd*<br/>
Ручка окна, связанная с управлением.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a>CStockPropImpl::put

Вызовите этот метод, чтобы установить стиль краски, используемый элементом управления, например, плоский или 3D.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Параметры

*nПоявление*<br/>
Новый стиль краски, который будет использоваться элементом управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a>CStockPropImpl::put-AutoSize

Вызовите этот метод, чтобы установить значение флага, которое указывает, если элемент управления не может быть любого другого размера.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Параметры

*bAutoSize*<br/>
ПРАВДА, если элемент управления не может быть любого другого размера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a>CStockPropImpl::put-BackColor

Вызовите этот метод, чтобы установить цвет фона элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Параметры

*clrBackColor*<br/>
Новый цвет фона управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a>CStockPropImpl::put-BackStyle

Вызовите этот метод, чтобы установить фоновый стиль элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Параметры

*nBackStyle*<br/>
Новый стиль фона управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a>CStockPropImpl::put-BorderColor

Вызовите этот метод, чтобы установить цвет границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Параметры

*clrBorderColor*<br/>
Новый цвет границы. Тип данных OLE_COLOR внутренне представлен как целый 32-битный целый ряд.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a>CStockPropImpl::put-BorderStyle

Вызовите этот метод, чтобы установить пограничный стиль управления.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Параметры

*nBorderStyle*<br/>
Новый пограничный стиль.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a>CStockPropImpl::put-BorderVisible

Вызовите этот метод, чтобы установить значение флага, которое указывает, видна граница элемента управления или нет.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Параметры

*bBorderVisible*<br/>
ПРАВДА, если граница должна быть видимой.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a>CStockPropImpl::put-BorderWidth

Вызовите этот метод, чтобы установить ширину границы элемента управления.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Параметры

*nBorderWidth*<br/>
Новая ширина границы контроля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_caption"></a><a name="put_caption"></a>CStockPropImpL::put-caption

Вызовите этот метод, чтобы настроить текст для отображения с помощью элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Параметры

*bstrCaption*<br/>
Текст, который будет отображаться с помощью элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a>CStockPropImpl::put-DrawMode

Вызовите этот метод, чтобы установить режим рисования элемента управления, например, XOR Pen или invert Colors.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Параметры

*nDrawMode*<br/>
Новый режим рисования для управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a>CStockPropImpl::put-DrawStyle

Вызовите этот метод, чтобы установить стиль рисования элемента управления, например, твердый, пунктирный или пунктирный.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Параметры

*nDrawStyle*<br/>
Новый стиль рисования для управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a>CStockPropImpl::put-DrawWidth

Вызовите этот метод, чтобы установить ширину (в пикселях), используемую методами рисования элемента управления.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Параметры

*nDrawWidth*<br/>
Новая ширина, используемая методами рисования элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a>CStockPropImpl::put

Вызовите этот метод, чтобы установить значение флага, которое указывает, включен ли элемент управления.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*bВСтои*<br/>
TRUE, если элемент управления включен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a>CStockPropImpl::put-FillColor

Вызовите этот метод, чтобы установить цвет заполнения элемента управления.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Параметры

*clrFillColor*<br/>
Новый цвет заполнения для управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a>CStockPropImpl::put-FillStyle

Вызовите этот метод, чтобы установить стиль заполнения элемента управления, например, твердый, прозрачный или кросс-хэтч.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Параметры

*nFillStyle*<br/>
Новый стиль заполнения для управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_font"></a><a name="put_font"></a>CStockPropImpl::put-Font

Вызовите этот метод, чтобы установить свойства шрифта элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a>CStockPropImpl::put-ForeColor

Вызовите этот метод, чтобы установить цвет переднего плана управления.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Параметры

*clrForeColor*<br/>
Новый цвет переднего плана управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a>CStockPropImpl::put-HWND

Этот метод возвращает E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_FAIL.

### <a name="remarks"></a>Remarks

Ручка окна является значением только для чтения.

## <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a>CStockPropImpl::put-MouseIcon

Вызовите этот метод, чтобы настроить свойства изображения изображения графических (значок, бит-карта или метафилия), которые будут отображаться, когда мышь находится над управлением.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойства изображения изображения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a>CStockPropImpl::put-MousePointer

Вызовите этот метод, чтобы установить тип указателя мыши отображается, когда мышь находится над управлением, например, стрелка, крест, или песочные часы.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Параметры

*nMousePointer*<br/>
Тип указателя мыши.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_picture"></a><a name="put_picture"></a>CStockPropImpl::put

Вызовите этот метод, чтобы настроить свойства изображения графического (значок, бит-карта или метафилия) для отображения.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойства изображения. Более подробную информацию можно узнать [на примере IPictureDisp.](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a>CStockPropImpl::put-ReadyStateState

Вызовите этот метод, чтобы установить готовое состояние элемента управления, например, загрузку или загрузку.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Параметры

*nReadyState*<br/>
Контроль готов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a>CStockPropImpl::put-TabStop

Вызов иметод, чтобы установить флаг, указывающий, если элемент управления является остановкой вкладки или нет.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Параметры

*bTabStop*<br/>
ПРАВДА, если контроль является остановить вкладку.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_text"></a><a name="put_text"></a>CStockPropImpl::put-Текст

Вызовите этот метод, чтобы настроить текст, который отображается с помощью элемента управления.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*bstrText*<br/>
Текст, отображаемый с помощью элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplputvalid"></a><a name="put_valid"></a>CStockPropImpl::putvalid

Вызовите этот метод, чтобы установить флаг, указывающий, является ли элемент управления действительным или нет.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Параметры

*bValid*<br/>
ПРАВДА, если элемент управления действителен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="cstockpropimplput_window"></a><a name="put_window"></a>CStockPropImpl::pут-окно

Этот метод называется [CStockPropImpl: :put-HWND](#put_hwnd), который возвращает E_FAIL.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Дескриптор окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_FAIL.

### <a name="remarks"></a>Remarks

Ручка окна является значением только для чтения.

## <a name="cstockpropimplputref_font"></a><a name="putref_font"></a>CStockPropImpl::putref-Font

Вызовите этот метод, чтобы установить свойства шрифта элемента управления с учетом количества.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на свойства шрифта элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Так же, как [CStockPropImpl: :put -Font](#put_font), но с ссылкой кол.

## <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a>CStockPropImpl::putref-MouseIcon

Вызовите этот метод, чтобы установить свойства изображения графического (значок, бит-карта или метафилия), которые будут отображаться, когда мышь находится над управлением, с эталонным числом.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойства изображения изображения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Так же, как [CStockPropImpl: :pут-Мысикон ,](#put_mouseicon)но с ссылкой рассчитывать.

## <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a>CStockPropImpl::putref

Вызовите этот метод, чтобы настроить свойства изображения графического (значок, бит-карта или метафилия), которые будут отображаться, с учетом подсчета.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Параметры

*pPicture*<br/>
Указатель на свойства изображения. Более подробную информацию можно узнать [на примере IPictureDisp.](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Так же, как [CStockPropImpl: :pут -Картинка](#put_picture), но с ссылкой кол.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl класс](../../atl/reference/idispatchimpl-class.md)
