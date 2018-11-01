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
ms.openlocfilehash: 2ffe37059eb6ab81eb9dd67243ba125766b92dfc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467305"
---
# <a name="cwndclassinfo-class"></a>Класс CWndClassInfo

Этот класс предоставляет методы для регистрации сведений о для класса окна.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWndClassInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|[Регистрация](#register)|Регистрирует класс окна.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_atom](#m_atom)|Уникально идентифицирует класс зарегистрированных окна.|
|[m_bSystemCursor](#m_bsystemcursor)|Указывает, ссылается ли ресурса курсора в системе курсор или курсор, содержащиеся в ресурсе модуля.|
|[m_lpszCursorID](#m_lpszcursorid)|Задает имя ресурса курсора.|
|[m_lpszOrigName](#m_lpszorigname)|Содержит имя существующего класса окна.|
|[m_szAutoName](#m_szautoname)|Содержит ATL созданное имя класса окна.|
|[m_wc](#m_wc)|Хранит сведения о классе окна в `WNDCLASSEX` структуры.|
|[pWndProc](#pwndproc)|Указывает процедуру окна существующий класс окон.|

## <a name="remarks"></a>Примечания

`CWndClassInfo` Управляет данными класса окна. Как правило, используется `CWndClassInfo` посредством одного из трех макросы, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX или DECLARE_WND_SUPERCLASS, как описано в следующей таблице:

|Макрос|Описание|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` Регистрирует сведения для нового класса окна.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` Регистрирует сведения для нового класса окна, включая параметры класса.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` Регистрирует сведения для класса окна, который основан на существующий класс, но использует другую процедуру окна. Этот прием называется создание надклассов.|

По умолчанию [CWindowImpl](../../atl/reference/cwindowimpl-class.md) включает в себя `DECLARE_WND_CLASS` макрос для создания окна на основании нового класса окна. DECLARE_WND_CLASS содержит стили по умолчанию и цвет фона для элемента управления. Если вы хотите указать стиль и цвет фона самостоятельно, являются производными от класса `CWindowImpl` и включить макрос DECLARE_WND_CLASS_EX в определении класса.

Если вы хотите создать окно, в зависимости от существующий класс окон, являются производными от класса `CWindowImpl` и включить макрос DECLARE_WND_SUPERCLASS в определении класса. Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

Дополнительные сведения о классах окна см. в разделе [классы окон](/windows/desktop/winmsg/window-classes) в пакете Windows SDK.

Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="m_atom"></a>  CWndClassInfo::m_atom

Содержит уникальный идентификатор для класса зарегистрированного окна.

```
ATOM m_atom;
```

##  <a name="m_bsystemcursor"></a>  CWndClassInfo::m_bSystemCursor

Значение TRUE, если курсор системный ресурс загружается при регистрации класса окна.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>Примечания

В противном случае будет загружен ресурс курсора, содержащиеся в модуле.

`CWndClassInfo` использует `m_bSystemCursor` только тогда, когда [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) указан макрос. В этом случае `m_bSystemCursor` устанавливается равным TRUE. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.

##  <a name="m_lpszcursorid"></a>  CWndClassInfo::m_lpszCursorID

Задает имя ресурса курсора или идентификатор ресурса в младшее слово и ноль в старшее слово.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>Примечания

При регистрации класса окна, дескриптор курсора определяется `m_lpszCursorID` извлекается и хранятся в [m_wc](#m_wc).

`CWndClassInfo` использует `m_lpszCursorID` только тогда, когда [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) указан макрос. В этом случае `m_lpszCursorID` инициализируется IDC_ARROW. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.

##  <a name="m_lpszorigname"></a>  CWndClassInfo::m_lpszOrigName

Содержит имя существующего класса окна.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` использует `m_lpszOrigName` только при включении [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макроса в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна на основе класса с именем, `m_lpszOrigName`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.

##  <a name="m_szautoname"></a>  CWndClassInfo::m_szAutoName

Содержит имя класса окна.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` использует `m_szAutoName` только в том случае, если передается значение NULL `WndClassName` параметр [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) или [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . ATL создают имя при регистрации класса окна.

##  <a name="m_wc"></a>  CWndClassInfo::m_wc

Хранит сведения о классе окна в [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577) структуры.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>Примечания

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос, `m_wc` содержит сведения о новый класс окна.

Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `m_wc` содержит сведения о суперклассе — класс окна, который основан на существующий класс, но использует другую процедуру окна. [m_lpszOrigName](#m_lpszorigname) и [pWndProc](#pwndproc) сохранить имя существующий класс окон и процедуру окна, соответственно.

##  <a name="pwndproc"></a>  CWndClassInfo::pWndProc

Указывает процедуру окна существующий класс окон.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>Примечания

`CWndClassInfo` использует `pWndProc` только при включении [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макроса в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующий класс, но использует другую процедуру окна. Процедура окна существующий класс окон сохраняется в `pWndProc`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.

##  <a name="register"></a>  CWndClassInfo::Register

Вызывается средой [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) зарегистрировать класс окна, если он еще не был зарегистрирован.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>Параметры

*pProc*<br/>
[out] Указывает исходную процедуру существующий класс окон.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения atom, однозначно определяющий класс окна зарегистрирован. В противном случае — 0.

### <a name="remarks"></a>Примечания

Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос, `Register` регистрирует новый класс окна. В этом случае *pProc* параметр не используется.

Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `Register` регистрирует суперкласса — класс окна, который основан на существующий класс, но использует другую процедуру окна. Процедура окна существующий класс окон возвращается в *pProc*.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)