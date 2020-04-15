---
title: Класс CWindowImpl
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::CWindowImpl::DefWindowProc
- ATLWIN/ATL::CWindowImpl::GetCurrentMessage
- ATLWIN/ATL::CWindowImpl::GetWindowProc
- ATLWIN/ATL::CWindowImpl::OnFinalMessage
- ATLWIN/ATL::CWindowImpl::SubclassWindow
- ATLWIN/ATL::CWindowImpl::UnsubclassWindow
- ATLWIN/ATL::CWindowImpl::GetWndClassInfo
- ATLWIN/ATL::CWindowImpl::WindowProc
- ATLWIN/ATL::CWindowImpl::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: d7f7f7363eb123181bd6e0389663810346094cba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330297"
---
# <a name="cwindowimpl-class"></a>Класс CWindowImpl

Предоставляет методы создания или подкласса окна.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш новый класс, `CWindowImpl`полученный из .

*TBase*<br/>
Базовый класс вашего класса. По умолчанию базовым классом является [CWindow](../../atl/reference/cwindow-class.md).

*TWinTraits*<br/>
[Класс признаков,](../../atl/understanding-window-traits.md) определяющий стили для вашего окна. Значение по умолчанию — `CControlWinTraits`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWindowImpl::Создание](#create)|Создает окно.|

### <a name="cwindowimplbaset-methods"></a>Методы CWindowImplBaseT

|||
|-|-|
|[DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|
|[GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|
|[GetWindowProc](#getwindowproc)|Возвращает текущую процедуру окна.|
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).|
|[ПодклассОкно](#subclasswindow)|Подклассы окна.|
|[НеподклассОк](#unsubclasswindow)|Восстанавливает ранее подклассифицированное окно.|

### <a name="static-methods"></a>Статические методы

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|Возвращает статический экземпляр [CWndClassInfo,](../../atl/reference/cwndclassinfo-class.md)который управляет информацией о классе окон.|
|[Windowproc](#windowproc)|Обрабатывает сообщения, отправленные в окно.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает на оригинальную процедуру окна класса окон.|

## <a name="remarks"></a>Remarks

Можно использовать `CWindowImpl` для создания окна или подкласса существующего окна. процедура `CWindowImpl` окна использует карту сообщений для направления сообщений соответствующим обработчикам.

`CWindowImpl::Create`создает окно на основе информации о классе окон, которая управляется [CWndClassInfo.](../../atl/reference/cwndclassinfo-class.md) `CWindowImpl`содержит [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макрос, `CWndClassInfo` что означает регистрацию нового класса окон. Если вы хотите классифицировать существующий класс `CWindowImpl` окон, получите свой класс из и включите [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. В этом `CWndClassInfo` случае регистрирует класс окон, основанный на существующем классе, но использует. `CWindowImpl::WindowProc` Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
> Поскольку `CWndClassInfo` управление информацией только для одного класса окон, `CWindowImpl` каждое окно, созданное через экземпляр, основано на одном и том же классе окон.

`CWindowImpl`также поддерживает подклассок окон. Метод `SubclassWindow` прикрепляет существующее `CWindowImpl` окно к объекту `CWindowImpl::WindowProc`и изменяет процедуру окна на. Каждый `CWindowImpl` экземпляр может подклассифицировать другое окно.

> [!NOTE]
> Для любого `CWindowImpl` данного `Create` `SubclassWindow`объекта позвоните или . Не ссылайтесь на оба метода на одном объекте.

В дополнение `CWindowImpl`к, ATL предоставляет [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) для создания окна, которое содержится в другом объекте.

Деструктор базового класса `CWindowImplRoot`(яп. ) гарантирует, что окно исчезло до того, как объект будет уничтожен.

`CWindowImpl`производит `CWindowImplBaseT`ся , `CWindowImplRoot`который происходит от `TBase` , который вытекает из и [CMessageMap](../../atl/reference/cmessagemap-class.md).

|Дополнительные сведения|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="cwindowimplcreate"></a><a name="create"></a>CWindowImpl::Создание

Создает окно на основе нового класса окон.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
(в) Ручка к окну родителя или владельца.

*rect*<br/>
(в) Структура [RECT,](/previous-versions/dd162897\(v=vs.85\)) определяющая положение окна. Может `RECT` быть передан указателем или ссылкой.

*szWindowName*<br/>
(в) Определяет название окна. Значение по умолчанию — NULL.

*dwStyle*<br/>
(в) Стиль окна. Это значение сочетается со стилем, предоставленным классом черт для окна. Значение по умолчанию дает классу признаков полный контроль над стилем. Список возможных значений можно узнать в [SDK](/windows/win32/api/winuser/nf-winuser-createwindoww) Windows.

*dwExStyle*<br/>
(в) Расширенный стиль окна. Это значение сочетается со стилем, предоставленным классом черт для окна. Значение по умолчанию дает классу признаков полный контроль над стилем. Список возможных значений можно узнать в [SDK Windows.](/windows/win32/api/winuser/nf-winuser-createwindowexw)

*Менорид*<br/>
(в) Для окна ребенка идентификатор окна. Для окна верхнего уровня ручка меню для окна. Значение по умолчанию **0U**.

*lpСоздатьПарам*<br/>
(в) Указатель на данные создания окон. Для полного описания смотрите описание окончательного параметра [для CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, ручка к вновь созданному окну. В противном случае — значение NULL.

### <a name="remarks"></a>Remarks

`Create`сначала регистрирует класс окна, если он еще не зарегистрирован. Новое окно автоматически прикрепляется `CWindowImpl` к объекту.

> [!NOTE]
> Не звоните, `Create` если вы уже позвонили [подклассу Window.](#subclasswindow)

Чтобы использовать класс окон, основанный на существующем классе `CWindowImpl` окон, вывешможно из класса и включите [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. Процедура существующего класса окон сохраняется в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc) Для получения дополнительной информации смотрите обзор [CWindowImpl.](../../atl/reference/cwindowimpl-class.md)

> [!NOTE]
> Если 0 используется в качестве значения для параметра *MenuOrID,* оно должно быть указано как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.

## <a name="cwindowimpldefwindowproc"></a><a name="defwindowproc"></a>CWindowImpl::DefWindowProc

Вызывается [WindowProc](#windowproc) для обработки сообщений, не обрабатываемых на карте сообщений.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Параметры

*uMsg*<br/>
(в) Сообщение, отправленное в окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщений.

### <a name="remarks"></a>Remarks

По умолчанию вызывает функцию `DefWindowProc` [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 для отправки информации о сообщении в процедуру окна, указанную в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

Функция без каких-либо параметров автоматически извлекает необходимые параметры из текущего сообщения.

## <a name="cwindowimplgetcurrentmessage"></a><a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage

Возвращает текущее сообщение, упакованное в структуру. `MSG`

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее сообщение.

## <a name="cwindowimplgetwindowproc"></a><a name="getwindowproc"></a>CWindowImpl::GetWindowProc

Возвращает, `WindowProc`текущая процедура окна.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущая процедура окна.

### <a name="remarks"></a>Remarks

Переопределить этот метод, чтобы заменить процедуру окна с вашей собственной.

## <a name="cwindowimplgetwndclassinfo"></a><a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo

Вызывается [путем создания](#create) для доступа к информации класса окна.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Возвращаемое значение

Статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).

### <a name="remarks"></a>Remarks

По умолчанию, `CWindowImpl` получает этот метод через [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макрос, который определяет новый класс окна.

Чтобы превзойти существующий класс окон, `CWindowImpl` вывешйте свой `GetWndClassInfo`класс и включите [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос для переопределения. Для получения дополнительной информации смотрите обзор [CWindowImpl.](../../atl/reference/cwindowimpl-class.md)

Помимо использования DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS макросов, вы можете переопределить `GetWndClassInfo` с вашей собственной реализации.

## <a name="cwindowimplm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc

В зависимости от окна, указывает на одну из следующих процедур окна.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Remarks

|Тип окна|Процедура окна|
|--------------------|----------------------|
|Окно, основанное на новом классе окон, указанном в [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макрос.|Функция [DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32.|
|Окно, основанное на классе окон, изменяя существующий класс, указанный в [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макроса.|Процедура окна существующего класса окон.|
|Подклассифицированное окно.|Оригинальная процедура окна подклассифицированного окна.|

[CWindowImpl::DefWindowProc](#defwindowproc) отправляет информацию о сообщениях `m_pfnSuperWindowProc`в сохраненную процедуру окна.

## <a name="cwindowimplonfinalmessage"></a><a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage

Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к разрушенной окну.

### <a name="remarks"></a>Remarks

Реализация по `OnFinalMessage` умолчанию ничего не делает, но вы можете переопределить эту функцию для обработки очистки перед уничтожением окна. Если вы хотите автоматически удалить объект при уничтожении окна, вы можете **вызвать удалить это;** в этой функции.

## <a name="cwindowimplsubclasswindow"></a><a name="subclasswindow"></a>CWindowImpl::SubclassWindow

Подклассы окна, идентифицированного *hWnd,* `CWindowImpl` и прикрепляет его к объекту.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к подклассу окна.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно успешно подклассифицировано; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Подклассное окно теперь использует [CWindowImpl::WindowProc](#windowproc). Оригинальная процедура окна сохраняется в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

> [!NOTE]
> Не звоните, `SubclassWindow` если вы уже позвонили [Создать](#create).

## <a name="cwindowimplunsubclasswindow"></a><a name="unsubclasswindow"></a>CWindowImpl::НеподклассОк

Отсоединяет подклассифицированное окно от `CWindowImpl` объекта и восстанавливает исходную процедуру окна, сохраненную в [m_pfnSuperWindowProc.](#m_pfnsuperwindowproc)

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к окну ранее подклассифицирована.

## <a name="cwindowimplwindowproc"></a><a name="windowproc"></a>CWindowImpl::WindowProc

Эта статическая функция реализует процедуру окна.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
(в) Ручка к окну.

*uMsg*<br/>
(в) Сообщение, отправленное в окно.

*wParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

*lParam*<br/>
(в) Дополнительная информация, соомнее сообщения.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщений.

### <a name="remarks"></a>Remarks

`WindowProc`использует карту сообщений по умолчанию (объявленную с [BEGIN_MSG_MAP)](message-map-macros-atl.md#begin_msg_map)для направления сообщений соответствующим обработчикам. При необходимости звоните `WindowProc` в [DefWindowProc](#defwindowproc) для дополнительной обработки сообщений. Если окончательное сообщение не `WindowProc` обработано, следует:

- Выполняет отослаивание, если окно было неклассифицировано.

- Очищает `m_hWnd`.

- Вызовы [OnFinalMessage](#onfinalmessage) перед тем, как окно будет уничтожено.

Можно переопределить, `WindowProc` чтобы обеспечить другой механизм обработки сообщений.

## <a name="see-also"></a>См. также раздел

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
