---
title: Класс CWindowImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3582f3fff0ee683889e1b0403554c59835293889
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756110"
---
# <a name="cwindowimpl-class"></a>Класс CWindowImpl

Предоставляет методы для создания или создание подкласса для окна.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Параметры

*T*  
Новый класс, производный от `CWindowImpl`.

*TBase*  
Базовый класс для класса. По умолчанию является базовым классом [CWindow](../../atl/reference/cwindow-class.md).

*TWinTraits*  
Объект [класс характеристик](../../atl/understanding-window-traits.md) , определяющий стили для окна. Значение по умолчанию — `CControlWinTraits`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWindowImpl::Create](#create)|Создает окно.|

### <a name="cwindowimplbaset-methods"></a>Методы CWindowImplBaseT

|||
|-|-|
|[DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|
|[GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|
|[GetWindowProc](#getwindowproc)|Возвращает текущую процедуру окна.|
|[OnFinalMessage](#onfinalmessage)|Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).|
|[SubclassWindow](#subclasswindow)|Подклассы окно.|
|[UnsubclassWindow](#unsubclasswindow)|Восстанавливает ранее подклассов окно.|

### <a name="static-methods"></a>Статические методы

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|Возвращает статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), который управляет данными класса окна.|
|[WindowProc](#windowproc)|Обрабатывает сообщения, отправленные в окно.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает исходную процедуру окна класс окна.|

## <a name="remarks"></a>Примечания

Можно использовать `CWindowImpl` для создания окна или подкласс существующему окну. `CWindowImpl` окно процедура использует схему сообщений для направления сообщений соответствующих обработчиков.

`CWindowImpl::Create` Создает окно, на основе сведений класс окна, который управляется средой [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` содержит [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макросом, который означает, что `CWndClassInfo` регистрирует новый класс окна. Если вы хотите суперкласса существующий класс окон, являются производными от класса `CWindowImpl` и включают [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующий класс, но использует `CWindowImpl::WindowProc`. Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  Так как `CWndClassInfo` управляет данными только один класс окна, созданного посредством экземпляра каждого окна `CWindowImpl` основан на один класс.

`CWindowImpl` также поддерживает создание подклассов окна. `SubclassWindow` Метод прикрепляет к существующему окну `CWindowImpl` объекта и изменяет процедура окна для `CWindowImpl::WindowProc`. Каждый экземпляр `CWindowImpl` можно подкласс другого окна.

> [!NOTE]
>  Для любого заданного `CWindowImpl` объекта, вызовите `Create` или `SubclassWindow`. Не вызвать оба метода того же объекта.

В дополнение к `CWindowImpl`, библиотека ATL предоставляет [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) для создания окна, которое содержится в другом объекте.

Деструктор базового класса (~ `CWindowImplRoot`) гарантирует, что окно будет удален перед уничтожением объекта.

`CWindowImpl` является производным от `CWindowImplBaseT`, который является производным от `CWindowImplRoot`, который является производным от `TBase` и [CMessageMap](../../atl/reference/cmessagemap-class.md).

|Дополнительные сведения о|См.|
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

##  <a name="create"></a>  CWindowImpl::Create

Создает окно, в зависимости от нового класса окна.

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

*hWndParent*  
[in] Дескриптор окна родительского или владельца.

*Rect*  
[in] Объект [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, указывающий положение окна. `RECT` Могут передаваться, указателем или по ссылке.

*szWindowName*  
[in] Задает имя окна. Значение по умолчанию имеет значение NULL.

*dwStyle*  
[in] Стиль окна. Это значение объединяется со стилем, предоставляемый классом признаки для окна. Значение по умолчанию предоставляет признаки класса полный контроль над стиль. Список возможных значений см. в разделе [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) в пакете Windows SDK.

*dwExStyle*  
[in] Стиль окна расширенного. Это значение объединяется со стилем, предоставляемый классом признаки для окна. Значение по умолчанию предоставляет признаки класса полный контроль над стиль. Список возможных значений см. в разделе [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*MenuOrID*  
[in] Для дочернего окна, окна идентификатор. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.

*lpCreateParam*  
[in] Указатель на окно создания данных. Полное описание см. в описании для конечного параметра для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa).

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения дескриптор для созданного окна. В противном случае — значение NULL.

### <a name="remarks"></a>Примечания

`Create` Регистрирует класс окна сначала в том случае, если он еще не был зарегистрирован. Вновь созданное окно автоматически присоединяется ко `CWindowImpl` объекта.

> [!NOTE]
>  Не вызывайте `Create` уже после вызова метода [SubclassWindow](#subclasswindow).

Чтобы использовать класс окна, основанный на существующий класс окон, являются производными от класса `CWindowImpl` и включают [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос. Процедура окна существующий класс окон сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.

> [!NOTE]
>  Если используется значение 0 как значение для *MenuOrID* параметр, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.

##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc

Вызывается средой [WindowProc](#windowproc) для обработки сообщений, не обрабатываются в схеме сообщений.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Параметры

*uMsg*  
[in] Сообщение, отправленное окну.

*wParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Примечания

По умолчанию `DefWindowProc` вызовы [CallWindowProc](https://msdn.microsoft.com/library/windows/desktop/ms633571) функцию Win32 для отправки сведений сообщение процедуре окна, указанный в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

Функция без параметров автоматически извлекает необходимые параметры из текущего сообщения.

##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage

Возвращает текущее сообщение, содержащийся в `MSG` структуры.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее сообщение.

##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc

Возвращает `WindowProc`, текущую процедуру окна.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущую процедуру окна.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы заменить на собственные процедуры окна.

##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo

Вызывается средой [создать](#create) для доступа к сведениям о классе окна.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Возвращаемое значение

Статический экземпляр [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).

### <a name="remarks"></a>Примечания

По умолчанию `CWindowImpl` получает этот метод через [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макросом, который указывает новый класс окна.

Для суперкласса существующий класс окон, являются производными от класса `CWindowImpl` и включают [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос для переопределения `GetWndClassInfo`. Дополнительные сведения см. в разделе [CWindowImpl](../../atl/reference/cwindowimpl-class.md) Обзор.

Помимо использования DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS макросы, можно переопределить `GetWndClassInfo` собственной реализацией.

##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc

В зависимости от окна указывает на один из следующих процедур окна.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Примечания

|Тип окна|Процедура окна|
|--------------------|----------------------|
|Окно на основании нового класса окна, заданные с помощью [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) макрос.|[DefWindowProc](/windows/desktop/api/winuser/nf-winuser-defwindowproca) функции Win32.|
|На основе окна в класс окна, который изменяет существующий класс, заданные с помощью [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос.|Процедура окна существующий класс окон.|
|Окно, выведенных в подклассы.|Окно выведенных в подклассы исходную процедуру окна.|

[CWindowImpl::DefWindowProc](#defwindowproc) отправляет сообщения сведения, сохраненные в процедуре окна `m_pfnSuperWindowProc`.

##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage

Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор окна уничтожения.

### <a name="remarks"></a>Примечания

Реализация по умолчанию `OnFinalMessage` не выполняет никаких действий, но можно переопределить эту функцию для обработки очистки перед удалением окна. Если вы хотите автоматически удалить объект после уничтожения окна, можно вызвать **; удалить** в этой функции.

##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow

Подклассы, идентифицируемый окна *hWnd* и присоединяет его к `CWindowImpl` объекта.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор окна подкласса.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно успешно подклассом; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Теперь используется окном, выведенных в подклассы [CWindowImpl::WindowProc](#windowproc). Исходный текст процедуры окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

> [!NOTE]
>  Не вызывайте `SubclassWindow` уже после вызова метода [создать](#create).

##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow

Отсоединяет окно выведенных в подклассы `CWindowImpl` объекта и восстанавливает исходный текст процедуры окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор окна ранее подклассов.

##  <a name="windowproc"></a>  CWindowImpl::WindowProc

Эта статическая функция реализует процедуру окна.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*  
[in] Дескриптор окна.

*uMsg*  
[in] Сообщение, отправленное окну.

*wParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*  
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Примечания

`WindowProc` использует схему сообщений по умолчанию (объявлен с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) для направления сообщений соответствующих обработчиков. При необходимости `WindowProc` вызовы [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений. Если окончательное сообщение не обработано, `WindowProc` делает следующее:

- Выполняет unsubclassing в том случае, если окно было unsubclassed.

- Очищает `m_hWnd`.

- Вызовы [OnFinalMessage](#onfinalmessage) до уничтожения окна.

Можно переопределить `WindowProc` для предоставления разных механизма для обработки сообщений.

## <a name="see-also"></a>См. также

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
[Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
