---
title: Класс Квиндовимпл
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
ms.openlocfilehash: b8b633dcf4ea14e899ee00552b553476cf697689
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423186"
---
# <a name="cwindowimpl-class"></a>Класс Квиндовимпл

Предоставляет методы для создания или подкласса окна.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Новый класс, производный от `CWindowImpl`.

*тбасе*<br/>
Базовый класс класса. По умолчанию базовым классом является [CWindow](../../atl/reference/cwindow-class.md).

*твинтраитс*<br/>
[Класс](../../atl/understanding-window-traits.md) признаков, определяющий стили окна. Значение по умолчанию — `CControlWinTraits`.

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Квиндовимпл:: Create](#create)|Создает окно.|

### <a name="cwindowimplbaset-methods"></a>Методы Квиндовимплбасет

|||
|-|-|
|[дефвиндовпрок](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|
|[жеткуррентмессаже](#getcurrentmessage)|Возвращает текущее сообщение.|
|[жетвиндовпрок](#getwindowproc)|Возвращает текущую процедуру окна.|
|[онфиналмессаже](#onfinalmessage)|Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).|
|[субклассвиндов](#subclasswindow)|Подклассировать окно.|
|[унсубклассвиндов](#unsubclasswindow)|Восстанавливает ранее подклассное окно.|

### <a name="static-methods"></a>Статические методы

|||
|-|-|
|[жетвндклассинфо](#getwndclassinfo)|Возвращает статический экземпляр [квндклассинфо](../../atl/reference/cwndclassinfo-class.md), который управляет сведениями о классе окна.|
|[WindowProc](#windowproc)|Обрабатывает сообщения, отправленные в окно.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает на исходную процедуру окна класса Window.|

## <a name="remarks"></a>Remarks

`CWindowImpl` можно использовать для создания окна или подкласса существующего окна. в `CWindowImpl` оконной процедуре для направления сообщений к соответствующим обработчикам используется схема сообщений.

`CWindowImpl::Create` создает окно на основе сведений о классе окна, управляемых [квндклассинфо](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` содержит макрос [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) , то есть `CWndClassInfo` регистрирует новый класс окна. Если необходимо создать суперкласс для существующего класса окна, произнести класс от `CWindowImpl` и включить макрос [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . В этом случае `CWndClassInfo` регистрирует класс окна, основанный на существующем классе, но использует `CWindowImpl::WindowProc`. Пример:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  Поскольку `CWndClassInfo` управляет данными только для одного класса окон, каждое окно, созданное с помощью экземпляра `CWindowImpl`, основано на одном и том же классе окна.

`CWindowImpl` также поддерживает подклассы окон. Метод `SubclassWindow` присоединяет существующее окно к `CWindowImpl` объекту и изменяет процедуру окна на `CWindowImpl::WindowProc`. Каждый экземпляр `CWindowImpl` может создать подкласс для другого окна.

> [!NOTE]
>  Для любого заданного `CWindowImpl` объекта вызовите метод `Create` или `SubclassWindow`. Не вызывайте оба метода в одном объекте.

Помимо `CWindowImpl`, ATL предоставляет [кконтаинедвиндов](../../atl/reference/ccontainedwindowt-class.md) для создания окна, содержащегося в другом объекте.

Деструктор базового класса (~ `CWindowImplRoot`) гарантирует, что окно исчезнет до уничтожения объекта.

`CWindowImpl` является производным от `CWindowImplBaseT`, который является производным от `CWindowImplRoot`, который является производным от `TBase` и [кмессажемап](../../atl/reference/cmessagemap-class.md).

|Дополнительные сведения|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование Windows в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[кмессажемап](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

##  <a name="create"></a>Квиндовимпл:: Create

Создает окно на основе нового класса окна.

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

*хвндпарент*<br/>
окне Маркер родительского окна или окно владельца.

*rect*<br/>
окне Структура [Rect](/previous-versions/dd162897\(v=vs.85\)) , указывающая расположение окна. `RECT` может передаваться по указателю или по ссылке.

*сзвиндовнаме*<br/>
окне Задает имя окна. Значение по умолчанию — NULL.

*двстиле*<br/>
окне Стиль окна. Это значение сочетается со стилем, предоставленным классом признаков для окна. Значение по умолчанию предоставляет классу признаков полный контроль над стилем. Список возможных значений см. в разделе [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK.

*двексстиле*<br/>
окне Расширенный стиль окна. Это значение сочетается со стилем, предоставленным классом признаков для окна. Значение по умолчанию предоставляет классу признаков полный контроль над стилем. Список возможных значений см. в разделе [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*менуорид*<br/>
окне Для дочернего окна это идентификатор окна. Для окна верхнего уровня — маркер меню для окна. Значение по умолчанию — **0U**.

*лпкреатепарам*<br/>
окне Указатель на данные для создания окна. Полное описание см. в описании последнего параметра для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха — маркер для вновь созданного окна. В противном случае — значение NULL.

### <a name="remarks"></a>Remarks

`Create` сначала регистрирует класс окна, если он еще не зарегистрирован. Вновь созданное окно автоматически прикрепляется к объекту `CWindowImpl`.

> [!NOTE]
>  Не вызывайте `Create`, если вы уже вызвали [субклассвиндов](#subclasswindow).

Чтобы использовать класс окна, основанный на существующем классе окна, создайте класс, производный от `CWindowImpl` и включив макрос [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . Процедура окна существующего класса окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Дополнительные сведения см. в обзоре [квиндовимпл](../../atl/reference/cwindowimpl-class.md) .

> [!NOTE]
>  Если значение 0 используется в качестве значения параметра *менуорид* , его необходимо указать как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.

##  <a name="defwindowproc"></a>Квиндовимпл::D Ефвиндовпрок

Вызывается методом [WindowProc](#windowproc) для обработки сообщений, не обрабатываемых схемой сообщений.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Параметры

*Uiacp*<br/>
окне Сообщение, отправленное в окно.

*wParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Remarks

По умолчанию `DefWindowProc` вызывает функцию Win32 [каллвиндовпрок](/windows/win32/api/winuser/nf-winuser-callwindowprocw) для отправки сведений о сообщении в процедуру окна, указанную в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

Функция без параметров автоматически получает необходимые параметры из текущего сообщения.

##  <a name="getcurrentmessage"></a>Квиндовимпл:: Жеткуррентмессаже

Возвращает текущее сообщение, упакованное в структуру `MSG`.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее сообщение.

##  <a name="getwindowproc"></a>Квиндовимпл:: Жетвиндовпрок

Возвращает `WindowProc`, текущую процедуру окна.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущая процедура окна.

### <a name="remarks"></a>Remarks

Переопределите этот метод, чтобы заменить процедуру окна собственной.

##  <a name="getwndclassinfo"></a>Квиндовимпл:: Жетвндклассинфо

Вызывается методом [CREATE](#create) для доступа к сведениям о классе окна.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Возвращаемое значение

Статический экземпляр [квндклассинфо](../../atl/reference/cwndclassinfo-class.md).

### <a name="remarks"></a>Remarks

По умолчанию `CWindowImpl` получает этот метод через макрос [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) , который указывает новый класс окна.

Чтобы создать суперкласс для существующего класса окна, создайте производный класс от `CWindowImpl` и включите макрос [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) для переопределения `GetWndClassInfo`. Дополнительные сведения см. в обзоре [квиндовимпл](../../atl/reference/cwindowimpl-class.md) .

Помимо использования макросов DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS можно переопределить `GetWndClassInfo` с помощью собственной реализации.

##  <a name="m_pfnsuperwindowproc"></a>Квиндовимпл:: m_pfnSuperWindowProc

В зависимости от окна указывает на одну из следующих оконных процедур.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Remarks

|Тип окна|Процедура окна|
|--------------------|----------------------|
|Окно, основанное на новом классе окна, заданном с помощью макроса [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) .|Функция Win32 [дефвиндовпрок](/windows/win32/api/winuser/nf-winuser-defwindowprocw) .|
|Окно, основанное на классе окна, изменяющем существующий класс, заданный с помощью макроса [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) .|Оконная процедура класса существующего окна.|
|Окно с подклассом.|Исходная процедура окна подкласса.|

[Квиндовимпл::D ефвиндовпрок](#defwindowproc) отправляет сведения о сообщении в процедуру окна, сохраненную в `m_pfnSuperWindowProc`.

##  <a name="onfinalmessage"></a>Квиндовимпл:: Онфиналмессаже

Вызывается после получения последнего сообщения (обычно WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер для уничтожения окна.

### <a name="remarks"></a>Remarks

Реализация `OnFinalMessage` по умолчанию не выполняет никаких действий, но эту функцию можно переопределить для выполнения очистки перед уничтожением окна. Если вы хотите автоматически удалить объект при уничтожении окна, можно вызвать **Удаление этого объекта;** в этой функции.

##  <a name="subclasswindow"></a>Квиндовимпл:: Субклассвиндов

Подклассировать окно, идентифицируемое *HWND* , и присоединить его к объекту `CWindowImpl`.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер окна, для которого создается подкласс.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно успешно подклассировать; в противном случае — значение FALSE.

### <a name="remarks"></a>Remarks

В окне с подклассами теперь используется [квиндовимпл:: WindowProc](#windowproc). Исходная процедура окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

> [!NOTE]
>  Не вызывайте `SubclassWindow`, если вы уже вызвали [CREATE](#create).

##  <a name="unsubclasswindow"></a>Квиндовимпл:: Унсубклассвиндов

Отсоединяет окно подкласса от `CWindowImpl` объекта и восстанавливает исходную процедуру окна, сохраненную в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик для ранее подклассов окна.

##  <a name="windowproc"></a>Квиндовимпл:: WindowProc

Эта статическая функция реализует процедуру окна.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
окне Маркер окна.

*Uiacp*<br/>
окне Сообщение, отправленное в окно.

*wParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
окне Дополнительные сведения, относящиеся к конкретному сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Remarks

`WindowProc` использует схему сообщений по умолчанию (объявленную с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)), чтобы направить сообщения соответствующим обработчикам. При необходимости `WindowProc` вызывает [дефвиндовпрок](#defwindowproc) для дополнительной обработки сообщений. Если окончательное сообщение не обрабатывается, `WindowProc` выполняет следующие действия:

- Выполняет отменяющий подкласс, если окно было удалено из подкласса.

- Очищает `m_hWnd`.

- Вызывает [онфиналмессаже](#onfinalmessage) перед уничтожением окна.

Можно переопределить `WindowProc`, чтобы предоставить другой механизм обработки сообщений.

## <a name="see-also"></a>См. также раздел

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
