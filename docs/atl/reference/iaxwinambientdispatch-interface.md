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
ms.openlocfilehash: f143b2c58159d1bb0812152c68d3c31153d4570d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467435"
---
# <a name="iaxwinambientdispatch-interface"></a>Интерфейс IAxWinAmbientDispatch

Этот интерфейс предоставляет методы для определения характеристик размещаемого элемента управления или контейнера.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.|
|[get_BackColor](#get_backcolor)|`BackColor` Свойство задает цвет фона окружения контейнера.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.|
|[get_Font](#get_font)|`Font` Свойство задает шрифт окружения контейнера.|
|[get_ForeColor](#get_forecolor)|`ForeColor` Свойство задает цвет переднего плана окружения контейнера.|
|[get_LocaleID](#get_localeid)|`LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам с маркерами захвата.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам hatched.|
|[get_UserMode](#get_usermode)|`UserMode` Свойство задает режим работы окружения пользователя контейнера.|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.|
|[put_BackColor](#put_backcolor)|`BackColor` Свойство задает цвет фона окружения контейнера.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.|
|[put_Font](#put_font)|`Font` Свойство задает шрифт окружения контейнера.|
|[put_ForeColor](#put_forecolor)|`ForeColor` Свойство задает цвет переднего плана окружения контейнера.|
|[put_LocaleID](#put_localeid)|`LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.|
|[put_UserMode](#put_usermode)|`UserMode` Свойство задает режим работы окружения пользователя контейнера.|

## <a name="remarks"></a>Примечания

Этот интерфейс предоставляется элементом управления ActiveX библиотеки ATL, размещение объектов. Вызывайте методы на этом интерфейсе для задания свойства окружающей среды, доступные для размещаемого элемента управления или для указания других аспектов поведения контейнера. В дополнение к свойств, предоставляемых `IAxWinAmbientDispatch`, использовать [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) будет пытаться загрузить сведения о типе о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, который содержит код.

При связывании ATL90.dll, **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна в несколько форм, как показано в следующей таблице.

|Тип определения|Файл|
|---------------------|----------|
|IDL|atliface.IDL|
|Библиотеки типов|ATL.dll|
|C++|насколько (также входит в ATLBase.h)|

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*pbAllowContextMenu*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

`AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Параметры

*pbAllowShowUI*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

`AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Параметры

*pbAllowWindowless*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

`BackColor` Свойство задает цвет фона окружения контейнера.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Параметры

*pclrBackground*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение по умолчанию этого свойства (в зависимости от родительского окна хоста является ли диалоговое окно или нет).

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*pbDisplayAsDefault*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*pdwDocHostDoubleClickFlags*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT как значение по умолчанию этого свойства.

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

`DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*pdwDocHostFlags*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER как значение по умолчанию этого свойства.

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

`Font` Свойство задает шрифт окружения контейнера.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
[out] Адрес `IFontDisp` указатель на интерфейс, используемый для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

`ForeColor` Свойство задает цвет переднего плана окружения контейнера.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Параметры

*pclrForeground*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует системный цвет окна как значение по умолчанию этого свойства.

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

`LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Параметры

*plcidLocaleID*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.

С помощью этого метода можно обнаружить окружения локальный идентификатор, то есть LocaleID программы управления, используется. Зная код языка, можно вызвать код для загрузки заголовков зависящих от языкового стандарта, текст сообщения об ошибке, и так далее из файла ресурсов или вспомогательной библиотеке DLL.

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

`MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Параметры

*pbMessageReflect*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

`OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*pbstrOptionKeyPath*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам с маркерами захвата.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Параметры

*pbShowGrabHandles*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

ATL узла объекта реализация всегда возвращает значение VARIANT_FALSE в качестве значения этого свойства.

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

`ShowHatching` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам hatched.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Параметры

*pbShowHatching*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

ATL узла объекта реализация всегда возвращает значение VARIANT_FALSE в качестве значения этого свойства.

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

`UserMode` Свойство задает режим работы окружения пользователя контейнера.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Параметры

*pbUserMode*<br/>
[out] Адрес переменной для получения текущего значения этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

`AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Параметры

*bAllowContextMenu*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

`AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Параметры

*bAllowShowUI*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

`AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Параметры

*bAllowWindowless*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

`BackColor` Свойство задает цвет фона окружения контейнера.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Параметры

*clrBackground*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение по умолчанию этого свойства (в зависимости от родительского окна хоста является ли диалоговое окно или нет).

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*bDisplayAsDefault*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Параметры

*dwDocHostDoubleClickFlags*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT как значение по умолчанию этого свойства.

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

`DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Параметры

*dwDocHostFlags*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER как значение по умолчанию этого свойства.

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

`Font` Свойство задает шрифт окружения контейнера.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

`ForeColor` Свойство задает цвет переднего плана окружения контейнера.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Параметры

*clrForeground*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует системный цвет окна как значение по умолчанию этого свойства.

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

`LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Параметры

*lcidLocaleID*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

`MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Параметры

*bMessageReflect*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

`OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Параметры

*bstrOptionKeyPath*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode` Свойство задает режим работы окружения пользователя контейнера.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Параметры

*bUserMode*<br/>
[in] Новое значение этого свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.

## <a name="see-also"></a>См. также

[Интерфейс IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[Интерфейс IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

