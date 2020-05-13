---
title: Класс IAtlMemgr
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: fcecf716e9d865b1b8590a733216576e0da4c2fb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746012"
---
# <a name="iatlmemmgr-class"></a>Класс IAtlMemgr

Этот класс представляет интерфейс для менеджера памяти.

## <a name="syntax"></a>Синтаксис

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Выделить](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[Бесплатный](#free)|Вызовите этот метод, чтобы освободить блок памяти.|
|[GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти.|
|[Перераспределить](#reallocate)|Вызовите этот метод, чтобы перераспределить блок памяти.|

## <a name="remarks"></a>Remarks

Этот интерфейс реализован [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), или [CWin32Heap](../../atl/reference/cwin32heap-class.md).

> [!NOTE]
> Локальные и глобальные функции кучи медленнее, чем другие функции управления памятью, и не предоставляют столько функций. Таким образом, новые приложения должны использовать [функции кучи.](/windows/win32/Memory/heap-functions) Они доступны в классе [CWin32Heap.](../../atl/reference/cwin32heap-class.md)

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a>IAtlMemMgr:Распределение

Вызовите этот метод, чтобы выделить блок памяти.

```cpp
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Remarks

Позвоните [iAtlMemMgr::Free](#free) или [IAtlMemMgr::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

### <a name="example"></a>Пример

Например, [см.](../../atl/reference/iatlmemmgr-class.md)

## <a name="iatlmemmgrfree"></a><a name="free"></a>IAtlMemMgr::Бесплатно

Вызовите этот метод, чтобы освободить блок памяти.

```cpp
void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

### <a name="remarks"></a>Remarks

Используйте этот метод, чтобы освободить память, полученную [IAtlMemMgr::Выделение](#allocate) или [IAtlMemMgr::Reallocate](#reallocate).

### <a name="example"></a>Пример

Например, [см.](../../atl/reference/iatlmemmgr-class.md)

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a>IAtlMemMgr:GetSize

Вызовите этот метод, чтобы получить размер выделенного блока памяти.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер блока памяти в байтах.

### <a name="example"></a>Пример

Например, [см.](../../atl/reference/iatlmemmgr-class.md)

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a>IAtlMemMgr::Перераспределить

Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.

```cpp
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

*nБайт*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Remarks

Позвоните [iAtlMemMgr::Free](#free) или [IAtlMemMgr::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

Концептуально этот метод освобождает существующую память и выделяет новый блок памяти. В действительности существующая память может быть расширена или иным образом использована повторно.

### <a name="example"></a>Пример

Например, [см.](../../atl/reference/iatlmemmgr-class.md)

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

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch

Этот метод называется в дополнение к интерфейсу эмбиента по умолчанию с пользовательским интерфейсом.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatch*<br/>
Указатель на новый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Когда `SetAmbientDispatch` вызовуется с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любых свойств или методов, запрошенных размещаемым элементом управления, если эти свойства еще не предоставлены [IAxWinAmbientDispatch.](../../atl/reference/iaxwinambientdispatch-interface.md)

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::AttachControl

Прикрепляет существующий (и ранее инициализированный) элемент управления к объекту-хоста с помощью окна, идентифицированного *hWnd.*

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Параметры

*pUnkControl*<br/>
(в) Указатель на `IUnknown` интерфейс элемента управления, который должен быть прикреплен к объекту-хозяину.

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::CreateControl

Создает элемент управления, инициализирует его и размещает в окне, идентифицированном *hWnd.*

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Параметры

*lpTricsData*<br/>
(в) Строка, идентифицирующая элемент управления для создания. Может быть CLSID (должен включать скобки), ProgID, URL, или сырья HTML (прификсированной **MSHTML:**).

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

*pStream*<br/>
(в) Указатель интерфейса для потока, содержащего данные инициализации для управления. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Это окно будет подклассифицировано объектом-хоста, разоблачающим этот интерфейс, чтобы сообщения могли быть отражены в элементе управления, а другие элементы контейнера работали.

Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).

Чтобы создать лицензированный элемент управления [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)ActiveX, см.

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [IAxWinHostWindow::CreateControl](#createcontrol).

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>Параметры

*lpTricsData*<br/>
(в) Строка, идентифицирующая элемент управления для создания. Может быть CLSID (должны включать скобки), ProgID, URL, или сырья HTML (прикреплительно с **MSHTML:**).

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

*pStream*<br/>
(в) Указатель интерфейса для потока, содержащего данные инициализации для управления. Может иметь значение NULL.

*ppUnk*<br/>
(ваут) Адрес указателя, который получит `IUnknown` интерфейс созданного элемента управления. Может иметь значение NULL.

*riidAdvise*<br/>
(в) Идентификатор интерфейса исходящего интерфейса на содержащемся объекте. Может быть IID_NULL.

*punkAdvise*<br/>
(в) Указатель на `IUnknown` интерфейс объекта раковины, который будет подключен к точке `iidSink`соединения на указанном объекте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

В `CreateControl` отличие `CreateControlEx` от метода, также позволяет получать указатель интерфейса к вновь созданному элементу управления и настраивать опускание событий для получения событий, выпущенных элементом управления.

Чтобы создать лицензированный элемент управления [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)ActiveX, см.

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::ЗапросКонтроль

Возвращает указанный указатель интерфейса, предоставляемый размещенным элементом управления.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
(в) Идентификатор интерфейса на запрашиваемом элементе управления.

*ppvObject*<br/>
(ваут) Адрес указателя, который получит указанный интерфейс созданного элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch

Устанавливает внешний дисинтерфейс, который доступен для содержащегося элементов управления через [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
(в) Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinhostWindow::SetExternalUIHandler

Вызовите эту функцию, чтобы установить внешний `CAxWindow` интерфейс [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) для объекта.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
(в) Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Эта функция используется элементами управления веб-браузером, которые задавают `IDocHostUIHandlerDispatch` запрос на сайт узла для интерфейса.

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHostWindowLic:CreateControlLic

Создает лицензированный элемент управления, инициализирует его и `hWnd`размещает в окне, идентифицированном .

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*bstrLic*<br/>
(в) BSTR, содержащий ключ лицензии для управления.

### <a name="remarks"></a>Remarks

Смотрите [IAxWinHostWindow::CreateControl](#createcontrol) для описания оставшихся параметров и значения возврата.

Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `IAxWinHostWindowLic::CreateControlLic`

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [IAxWinHostWindow::CreateControl](#createcontrol).

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*bstrLic*<br/>
(в) BSTR, содержащий ключ лицензии для управления.

### <a name="remarks"></a>Remarks

Смотрите [IAxWinHostWindow::CreateControlEx](#createcontrolex) для описания оставшихся параметров и значения возврата.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `IAxWinHostWindowLic::CreateControlLicEx`

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
