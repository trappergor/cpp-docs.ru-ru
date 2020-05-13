---
title: Класс CWndClassInfo
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 01706bf61c3b977c28998325ece68724cfbc7452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330335"
---
# <a name="cwndclassinfo-class"></a>Класс CWndClassInfo

Этот класс предоставляет методы регистрации информации для класса окон.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CWndClassInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[Регистрация](#register)|Регистрирует класс окон.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_atom](#m_atom)|Уникально идентифицирует зарегистрированный класс окон.|
|[m_bSystemCursor](#m_bsystemcursor)|Определяет, относится ли ресурс курсора к системного курсору или к курсору, содержащемуся в ресурсе модуля.|
|[m_lpszCursorID](#m_lpszcursorid)|Упогоняет название ресурса курсора.|
|[m_lpszOrigName](#m_lpszorigname)|Содержит имя существующего класса окон.|
|[m_szAutoName](#m_szautoname)|Содержит сгенерированное ATL имя класса окон.|
|[m_wc](#m_wc)|Поддерживает информацию о `WNDCLASSEX` классе окон в структуре.|
|[pWndProc](#pwndproc)|Указывает на процедуру окна существующего класса окон.|

## <a name="remarks"></a>Remarks

`CWndClassInfo`управляет информацией класса окон. Как правило, вы используете `CWndClassInfo` один из трех макросов, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX или DECLARE_WND_SUPERCLASS, как описано в следующей таблице:

|Макрос|Описание|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`регистрирует информацию для нового класса окон.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`регистрирует информацию для нового класса окон, включая параметры класса.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`регистрирует информацию для класса окон, которая основана на существующем классе, но использует другую процедуру окна. Этот метод называется суперклассированием.|

По умолчанию [CWindowImpl](../../atl/reference/cwindowimpl-class.md) включает `DECLARE_WND_CLASS` макрос для создания окна на основе нового класса окон. DECLARE_WND_CLASS предоставляет стили по умолчанию и цвет фона для управления. Если вы хотите указать стиль и цвет фона самостоятельно, получите свой класс из `CWindowImpl` и включите DECLARE_WND_CLASS_EX макрос в определение класса.

Если требуется создать окно на основе существующего класса `CWindowImpl` окон, вывемите свой класс и включите DECLARE_WND_SUPERCLASS макрос в определение класса. Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Для получения дополнительной информации [Window Classes](/windows/win32/winmsg/window-classes) о классах окон см.

Для получения дополнительной информации об использовании [ATL Window Classes](../../atl/atl-window-classes.md)окон в ATL, см.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a>CWndClassInfo::m_atom

Содержит уникальный идентификатор для зарегистрированного класса окон.

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor

Если true, ресурс системного курсора будет загружен при регистрации класса окон.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Remarks

В противном случае ресурс курсора, содержащийся в модуле, будет загружен.

`CWndClassInfo`использует `m_bSystemCursor` только тогда, когда [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl)](../../atl/reference/cwindowimpl-class.md)или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос указан. В этом `m_bSystemCursor` случае, инициализирована к TRUE. Для получения дополнительной информации смотрите обзор [CWndClassInfo.](../../atl/reference/cwndclassinfo-class.md)

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID

Укажите либо название ресурса курсора, либо идентификатор ресурса в слове с низким уровнем порядка и ноль в слове высокого порядка.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Remarks

Когда класс окон зарегистрирован, ручка к курсору, идентифицированному `m_lpszCursorID` по способу, извлекается и хранится [m_wc.](#m_wc)

`CWndClassInfo`использует `m_lpszCursorID` только тогда, когда [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl)](../../atl/reference/cwindowimpl-class.md)или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос указан. В этом `m_lpszCursorID` случае инициализирован до IDC_ARROW. Для получения дополнительной информации смотрите обзор [CWndClassInfo.](../../atl/reference/cwndclassinfo-class.md)

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName

Содержит имя существующего класса окон.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Remarks

`CWndClassInfo`использует `m_lpszOrigName` только тогда, когда вы включаете [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос в определении класса. В этом `CWndClassInfo` случае регистрирует класс окон на основе `m_lpszOrigName`класса, названного . Для получения дополнительной информации смотрите обзор [CWndClassInfo.](../../atl/reference/cwndclassinfo-class.md)

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName

Сохраняет название класса окон.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Remarks

`CWndClassInfo`использует `m_szAutoName` только в том `WndClassName` случае, если NULL передается по параметру [для DECLARE_WND_CLASS,](window-class-macros.md#declare_wnd_class) [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) или [DECLARE_WND_SUPERCLASS.](window-class-macros.md#declare_wnd_superclass) ATL будет строить имя, когда класс окна зарегистрирован.

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a>CWndClassInfo::m_wc

Поддерживает информацию о классе окон в структуре [WNDCLASSEX.](/windows/win32/api/winuser/ns-winuser-wndclassexw)

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Remarks

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl)](../../atl/reference/cwindowimpl-class.md)или [макрос DECLARE_WND_CLASS_EX,](window-class-macros.md#declare_wnd_class_ex) `m_wc` содержит информацию о новом классе окон.

Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `m_wc` содержит информацию о суперклассе - классе окон, который основан на существующем классе, но использует другую процедуру окна. [m_lpszOrigName](#m_lpszorigname) и [pWndProc](#pwndproc) сохраняют имя и процедуру окна существующего класса окон соответственно.

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc

Указывает на процедуру окна существующего класса окон.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Remarks

`CWndClassInfo`использует `pWndProc` только тогда, когда вы включаете [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос в определении класса. В этом `CWndClassInfo` случае регистрирует класс окон, основанный на существующем классе, но использующийся другую процедуру окна. Процедура существующего класса окон сохраняется `pWndProc`в . Для получения дополнительной информации смотрите обзор [CWndClassInfo.](../../atl/reference/cwndclassinfo-class.md)

## <a name="cwndclassinforegister"></a><a name="register"></a>CWndClassInfo:Регистрация

Вызывается [CWindowImpl::Создать](../../atl/reference/cwindowimpl-class.md#create) для регистрации класса окна, если он еще не зарегистрирован.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Параметры

*pProc*<br/>
(ваут) Определяет исходную процедуру окна существующего класса окон.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха атом, который однозначно идентифицирует зарегистрированный класс окон. В противном случае флагу присваивается значение 0.

### <a name="remarks"></a>Remarks

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl)](../../atl/reference/cwindowimpl-class.md)или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос, `Register` регистрирует новый класс окон. В этом случае параметр *pProc* не используется.

Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `Register` регистрирует суперкласс - класс окон, основанный на существующем классе, но использующийся другую процедуру окна. Процедура окна существующего окна класса возвращается в *pProc.*

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
