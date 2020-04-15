---
title: Интерфейс IAxWinAmbientDispatch
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: 6a4f5322d957b1e978bd123db3b4796be6b300da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330011"
---
# <a name="iaxwinambientdispatch-interface"></a>Интерфейс IAxWinAmbientDispatch

Этот интерфейс предоставляет методы для определения характеристик размещаемого управления или контейнера.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|Свойство `AllowContextMenu` определяет, разрешено ли размещенное элементы управления отображать свое собственное контекстное меню.|
|[get_AllowShowUI](#get_allowshowui)|Свойство `AllowShowUI` определяет, разрешено ли размещаемое управление отображать свой собственный пользовательский интерфейс.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|Свойство `AllowWindowlessActivation` определяет, будет ли контейнер позволит активации без окон.|
|[get_BackColor](#get_backcolor)|Свойство `BackColor` определяет цвет окружающего фона контейнера.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault`является свойством окружающего, что позволяет элементуправления, чтобы узнать, если это контроль по умолчанию.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|Свойство `DocHostDoubleClickFlags` определяет операцию, которая должна быть проведена в ответ на двойной клик.|
|[get_DocHostFlags](#get_dochostflags)|Свойство `DocHostFlags` определяет возможности пользовательского интерфейса объекта-хоста.|
|[get_Font](#get_font)|Свойство `Font` определяет окружающий шрифт контейнера.|
|[get_ForeColor](#get_forecolor)|Свойство `ForeColor` определяет цвет переднего плана окружающего значения контейнера.|
|[get_LocaleID](#get_localeid)|Свойство `LocaleID` указывает идентификатор окружающего места контейнера.|
|[get_MessageReflect](#get_messagereflect)|Свойство `MessageReflect` окружающего определяет, будет ли контейнер отражать сообщения в размещенный элемент управления.|
|[get_OptionKeyPath](#get_optionkeypath)|Свойство `OptionKeyPath` определяет ключевой путь реестра к настройкам пользователя.|
|[get_ShowGrabHandles](#get_showgrabhandles)|Свойство `ShowGrabHandles` окружающего может элемент управления узнать, следует ли ему рисовать с помощью ручки захвата.|
|[get_ShowHatching](#get_showhatching)|Свойство `ShowHatching` окружающего может контролировать, чтобы узнать, если он должен рисовать себя вылупился.|
|[get_UserMode](#get_usermode)|Свойство `UserMode` определяет режим окружающего пользователя контейнера.|
|[put_AllowContextMenu](#put_allowcontextmenu)|Свойство `AllowContextMenu` определяет, разрешено ли размещенное элементы управления отображать свое собственное контекстное меню.|
|[put_AllowShowUI](#put_allowshowui)|Свойство `AllowShowUI` определяет, разрешено ли размещаемое управление отображать свой собственный пользовательский интерфейс.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|Свойство `AllowWindowlessActivation` определяет, будет ли контейнер позволит активации без окон.|
|[put_BackColor](#put_backcolor)|Свойство `BackColor` определяет цвет окружающего фона контейнера.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault`является свойством окружающего, что позволяет элементуправления, чтобы узнать, если это контроль по умолчанию.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|Свойство `DocHostDoubleClickFlags` определяет операцию, которая должна быть проведена в ответ на двойной клик.|
|[put_DocHostFlags](#put_dochostflags)|Свойство `DocHostFlags` определяет возможности пользовательского интерфейса объекта-хоста.|
|[put_Font](#put_font)|Свойство `Font` определяет окружающий шрифт контейнера.|
|[put_ForeColor](#put_forecolor)|Свойство `ForeColor` определяет цвет переднего плана окружающего значения контейнера.|
|[put_LocaleID](#put_localeid)|Свойство `LocaleID` указывает идентификатор окружающего места контейнера.|
|[put_MessageReflect](#put_messagereflect)|Свойство `MessageReflect` окружающего определяет, будет ли контейнер отражать сообщения в размещенный элемент управления.|
|[put_OptionKeyPath](#put_optionkeypath)|Свойство `OptionKeyPath` определяет ключевой путь реестра к настройкам пользователя.|
|[put_UserMode](#put_usermode)|Свойство `UserMode` определяет режим окружающего пользователя контейнера.|

## <a name="remarks"></a>Remarks

Этот интерфейс подвергается ATL в ActiveX управления хостингобъектов. Вызовите методы на этом интерфейсе, чтобы установить свойства окружающего, доступные для размещаемого управления, или указать другие аспекты поведения контейнера. Для дополнения `IAxWinAmbientDispatch`свойств, предоставляемых, используйте [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).

<xref:System.Windows.Forms.AxHost>будет пытаться загрузить `IAxWinAmbientDispatch` информацию о типе типа о и `IAxWinAmbientDispatchEx` из typelib, который содержит код.

Если вы ссылаетесь на ATL90.dll, **AXHost** загрузит информацию типа из typelib в DLL.

Более подробную информацию можно узнать [о хостинге ActiveX Controls с помощью ATL AXHost.](../../atl/hosting-activex-controls-using-atl-axhost.md)

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в ряде форм, как показано в таблице ниже.

|Тип определения|Файл|
|---------------------|----------|
|Idl|atliface.idl|
|Тип библиотеки|Atl.dll|
|C++|atliface.h (также включен в ATLBase.h)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu

Свойство `AllowContextMenu` определяет, разрешено ли размещенное элементы управления отображать свое собственное контекстное меню.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*pbAllowКонтекстМеню*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI

Свойство `AllowShowUI` определяет, разрешено ли размещаемое управление отображать свой собственный пользовательский интерфейс.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Параметры

*pbAllowShowUI*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation

Свойство `AllowWindowlessActivation` определяет, будет ли контейнер позволит активации без окон.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Параметры

*pbAllowWindowless*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor

Свойство `BackColor` определяет цвет окружающего фона контейнера.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Параметры

*pclrBackground*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта используется COLOR_BTNFACE или COLOR_WINDOW в качестве значения этого свойства по умолчанию (в зависимости от того, является ли родительский момент окна узла диалогом или нет).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault`является свойством окружающего, что позволяет элементуправления, чтобы узнать, если это контроль по умолчанию.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*pbDisplayAsDefault*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

Свойство `DocHostDoubleClickFlags` определяет операцию, которая должна быть проведена в ответ на двойной клик.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*pdwDocHostDoubleClickFlags*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует DOCHOSTUIDBLCLK_DEFAULT в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags

Свойство `DocHostFlags` определяет возможности пользовательского интерфейса объекта-хоста.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*pdwDocHostFlags*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта используется DOCHOSTUIFLAG_NO3DBORDER в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a>IAxWinAmbientDispatch::get_Font

Свойство `Font` определяет окружающий шрифт контейнера.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
(ваут) Адрес указателя `IFontDisp` интерфейса, используемого для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта-хоста ATL использует шрифт GUI по умолчанию или системный шрифт в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor

Свойство `ForeColor` определяет цвет переднего плана окружающего значения контейнера.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Параметры

*pclrForeground*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта-хоста ATL использует цвет текста окна системы в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID

Свойство `LocaleID` указывает идентификатор окружающего места контейнера.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Параметры

*plcidLocaleID*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта узла ATL использует местоление пользователя по умолчанию в качестве значения этого свойства по умолчанию.

С помощью этого метода вы можете обнаружить Ambient LocalID, то есть, LocaleID программы вашего управления используется дюйма После того как вы знаете LocaleID, вы можете вызвать код для загрузки локально-специфических субтитров, текстовых сообщений об ошибке и так далее из файла ресурсов или спутникового DLL.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect

Свойство `MessageReflect` окружающего определяет, будет ли контейнер отражать сообщения в размещенный элемент управления.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Параметры

*pbMessageОтражение*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath

Свойство `OptionKeyPath` определяет ключевой путь реестра к настройкам пользователя.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*pbstrOptionKeyPath*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles

Свойство `ShowGrabHandles` окружающего может элемент управления узнать, следует ли ему рисовать с помощью ручки захвата.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Параметры

*pbShowGrabРучки*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта всегда возвращает VARIANT_FALSE как стоимость этого свойства.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching

Свойство `ShowHatching` окружающего может контролировать, чтобы узнать, если он должен рисовать себя вылупился.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Параметры

*pbShowHatching*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта всегда возвращает VARIANT_FALSE как стоимость этого свойства.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode

Свойство `UserMode` определяет режим окружающего пользователя контейнера.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Параметры

*pbUserMode*<br/>
(ваут) Адрес переменной для получения текущей стоимости этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put-AllowContextMenu

Свойство `AllowContextMenu` определяет, разрешено ли размещенное элементы управления отображать свое собственное контекстное меню.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*bAllowContextMenu*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a>IAxWinAmbientDispatch::put-AllowShowUI

Свойство `AllowShowUI` определяет, разрешено ли размещаемое управление отображать свой собственный пользовательский интерфейс.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Параметры

*bAllowShowUI*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put-AllowWindowlessActivation

Свойство `AllowWindowlessActivation` определяет, будет ли контейнер позволит активации без окон.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Параметры

*bAllowWindowless*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a>IAxWinAmbientDispatch::put-BackColor

Свойство `BackColor` определяет цвет окружающего фона контейнера.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Параметры

*clrBackground*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта используется COLOR_BTNFACE или COLOR_WINDOW в качестве значения этого свойства по умолчанию (в зависимости от того, является ли родительский момент окна узла диалогом или нет).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put-DisplayAsDefault

`DisplayAsDefault`является свойством окружающего, что позволяет элементуправления, чтобы узнать, если это контроль по умолчанию.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*bDisplayAsDefault*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_FALSE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put-DocHostDoubleClickFlags

Свойство `DocHostDoubleClickFlags` определяет операцию, которая должна быть проведена в ответ на двойной клик.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*dwDocHostDoubleClickFlags*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует DOCHOSTUIDBLCLK_DEFAULT в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a>IAxWinAmbientDispatch::put-DocHostFlags

Свойство `DocHostFlags` определяет возможности пользовательского интерфейса объекта-хоста.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*dwDocHostFlags*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта используется DOCHOSTUIFLAG_NO3DBORDER в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a>IAxWinAmbientDispatch::put-Font

Свойство `Font` определяет окружающий шрифт контейнера.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта-хоста ATL использует шрифт GUI по умолчанию или системный шрифт в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a>IAxWinAmbientDispatch: :put-ForeColor

Свойство `ForeColor` определяет цвет переднего плана окружающего значения контейнера.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Параметры

*clrForeground*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта-хоста ATL использует цвет текста окна системы в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a>IAxWinAmbientDispatch::put-LocaleID

Свойство `LocaleID` указывает идентификатор окружающего места контейнера.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Параметры

*lcidLocaleID*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта узла ATL использует местоление пользователя по умолчанию в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a>IAxWinAmbientDispatch::put

Свойство `MessageReflect` окружающего определяет, будет ли контейнер отражать сообщения в размещенный элемент управления.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Параметры

*bMessageОтражение*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a>IAxWinAmbientDispatch: :put-OptionKeyPath

Свойство `OptionKeyPath` определяет ключевой путь реестра к настройкам пользователя.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*bstrOptionKeyPath*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a>IAxWinAmbientDispatch::put-UserMode

Свойство `UserMode` определяет режим окружающего пользователя контейнера.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Параметры

*bUserMode*<br/>
(в) Новая стоимость этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Реализация объекта atL-объекта использует VARIANT_TRUE в качестве значения этого свойства по умолчанию.

## <a name="see-also"></a>См. также раздел

[Интерфейс IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[Интерфейс IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::КвиторХост](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
