---
title: Класс CContainedWindowT
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 96e279e8ab3080c0239f1e41895142ba23c5a7c9
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693977"
---
# <a name="ccontainedwindowt-class"></a>Класс CContainedWindowT

Этот класс реализует окно, содержатся внутри другого объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>Параметры

*TBase*<br/>
Базовый класс для нового класса. По умолчанию используется базовый класс `CWindow`.

*TWinTraits*<br/>
Класс признаков, который определяет стили для окна. Значение по умолчанию — `CControlWinTraits`.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) является специализацией `CContainedWindowT`. Если вы хотите изменить базовый класс или признаков, используйте `CContainedWindowT` напрямую.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Конструктор. Инициализирует элементы данных, чтобы указать, какие схемы сообщений будет обрабатывать содержащееся окно сообщения.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CContainedWindowT::Create](#create)|Создает окно.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Обеспечивает обработку сообщений по умолчанию.|
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Возвращает текущее сообщение.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Регистрирует класс окна автономной окна.|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Подклассы окно.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Изменения, какие схемы сообщений используется для обработки содержащееся окно сообщения.|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Восстанавливает ранее подклассов окно.|
|[CContainedWindowT::WindowProc](#windowproc)|(Статический) Обрабатывает сообщения, отправляемые содержащееся окно.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Определяет, какие схемы сообщений будет обрабатывать содержащееся окно сообщения.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Задает имя используемого существующий класс окон, на котором будет основан новый класс окна.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Указывает исходную процедуру окна класс окна.|
|[CContainedWindowT::m_pObject](#m_pobject)|Указывает содержащего его объекта.|

## <a name="remarks"></a>Примечания

`CContainedWindowT` реализует окно, содержатся внутри другого объекта. `CContainedWindowT`в окне процедуры используется процедура сопоставить сообщение в содержащем объекте для прямых сообщений соответствующих обработчиков. При создании `CContainedWindowT` объекта, укажите, какие схемы сообщений следует использовать.

`CContainedWindowT` позволяет создать новое окно, создание надклассов существующий класс окон. `Create` Метод сначала регистрирует класс окна, который основан на существующий класс, но использует `CContainedWindowT::WindowProc`. `Create` Создает окно, в зависимости от этого нового класса. Каждый экземпляр `CContainedWindowT` можно суперкласса класс другое окно.

`CContainedWindowT` также поддерживает создание подклассов окна. `SubclassWindow` Метод прикрепляет к существующему окну `CContainedWindowT` объекта и изменяет процедура окна для `CContainedWindowT::WindowProc`. Каждый экземпляр `CContainedWindowT` можно подкласс другого окна.

> [!NOTE]
>  Для любого заданного `CContainedWindowT` объекта, вызовите `Create` или `SubclassWindow`. Не следует вызвать оба метода того же объекта.

При использовании **Добавление элемента управления на основе** параметра в мастер проектов ATL, мастер автоматически добавит `CContainedWindowT` данные-член к классу, реализующему элемент управления. В следующем примере показано, как окно автономной объявлен:

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|Дополнительные сведения о|См.|
|--------------------------------|---------|
|Создание элементов управления|[Учебник по ATL](../../atl/active-template-library-atl-tutorial.md)|
|Использование окон в ATL|[Классы окон ATL](../../atl/atl-window-classes.md)|
|Мастер проектов ATL|[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/desktop/winmsg/windows) и последующие разделы в пакете SDK для Windows|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT

Конструктор инициализирует данные-члены.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
[in] Имя существующий класс окон, на котором будет основываться содержащееся окно.

*pObject*<br/>
[in] Указатель на вмещающего объекта, который объявляет сопоставление сообщений. Класс этот объект должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] Определяет схему сообщений, которая будет обрабатывать содержащееся окно сообщения. Значение по умолчанию, 0, указывает сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.

### <a name="remarks"></a>Примечания

Если вы хотите создать новое окно через [создать](#create), необходимо передать имя существующего класса окна для *lpszClassName* параметра. Например, см. в разделе [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Обзор.

Существует три конструктора:

- Конструктор с тремя аргументами та же обычно называется.

- Конструктор с двумя аргументами использует имя класса из `TBase::GetWndClassName`.

- Конструктор без аргументов используется в том случае, если вы хотите указать аргументы в более поздней версии. Необходимо указать имя класса окна, объект-сопоставление сообщений и ИД таблицы сообщений при последующем вызове `Create`.

Если подкласс существующему окну через [SubclassWindow](#subclasswindow), *lpszClassName* не будет использоваться значение; таким образом, можно передать NULL для этого параметра.

##  <a name="create"></a>  CContainedWindowT::Create

Вызовы [RegisterWndSuperclass](#registerwndsuperclass) зарегистрировать класс окна, который основан на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc).

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
[in] Имя существующий класс окон, на котором будет основываться содержащееся окно.

*pObject*<br/>
[in] Указатель на вмещающего объекта, который объявляет сопоставление сообщений. Класс этот объект должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] Определяет схему сообщений, которая будет обрабатывать содержащееся окно сообщения. Значение по умолчанию, 0, указывает сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.

*hWndParent*<br/>
[in] Дескриптор окна родительского или владельца.

*Rect*<br/>
[in] Объект [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, указывающий положение окна. `RECT` Могут передаваться, указателем или по ссылке.

*szWindowName*<br/>
[in] Задает имя окна. Значение по умолчанию имеет значение NULL.

*dwStyle*<br/>
[in] Стиль окна. Значение по умолчанию — WS_CHILD &#124; WS_VISIBLE. Список возможных значений см. в разделе [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) в пакете Windows SDK.

*dwExStyle*<br/>
[in] Стиль окна расширенного. Значение по умолчанию — 0, то есть без расширенного стиля. Список возможных значений см. в разделе [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*MenuOrID*<br/>
[in] Для дочернего окна, окна идентификатор. Для окна верхнего уровня, дескриптор меню для окна. Значение по умолчанию — **0U**.

*lpCreateParam*<br/>
[in] Указатель на окно создания данных. Полное описание см. в описании для конечного параметра для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa).

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения дескриптор вновь созданного окна. в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Существующее имя класса окна сохраняется в [m_lpszClassName](#m_lpszclassname). `Create` Создает окно, на основании этого нового класса. Вновь созданное окно автоматически присоединяется ко `CContainedWindowT` объекта.

> [!NOTE]
>  Не вызывайте `Create` уже после вызова метода [SubclassWindow](#subclasswindow).

> [!NOTE]
>  Если используется значение 0 как значение для *MenuOrID* параметр, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.

##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc

Вызывается средой [WindowProc](#windowproc) для обработки сообщений, не обрабатываются в схеме сообщений.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*uMsg*<br/>
[in] Сообщение, отправленное окну.

*wParam*<br/>
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*<br/>
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Примечания

По умолчанию `DefWindowProc` вызовы [CallWindowProc](/windows/desktop/api/winuser/nf-winuser-callwindowproca) функцию Win32 для отправки сведений сообщение процедуре окна, указанный в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage

Возвращает текущее сообщение (`m_pCurrentMsg`).

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее сообщение, содержащийся в `MSG` структуры.

##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID

Содержит идентификатор схемы сообщений, используемые для автономной окна.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>Примечания

Эта карта сообщения должен быть объявлен в содержащем объекте.

Сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), всегда обозначается деления на ноль. Альтернативную схему сообщений, объявленных с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), идентифицируемый `msgMapID`.

`m_dwMsgMapID` сначала инициализируются конструктором и может быть изменено путем вызова [SwitchMessageMap](#switchmessagemap). Например, см. в разделе [CContainedWindowT Обзор](../../atl/reference/ccontainedwindowt-class.md).

##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName

Указывает имя существующего класса окна.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>Примечания

При создании окна, [создать](#create) регистрирует класс окна, основан на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc).

`m_lpszClassName` инициализируется с помощью конструктора. Например, см. в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.

##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc

Если содержащееся окно является подклассом, `m_pfnSuperWindowProc` указывает на исходный текст процедуры окна класса окна.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Примечания

Если окно автономной суперкласса, означающее, что она основана на класс окна, который изменяет существующий класс, `m_pfnSuperWindowProc` указывает на существующий класс окон процедуру окна.

[DefWindowProc](#defwindowproc) метод отправляет сообщения сохраняются в процедуре окна `m_pfnSuperWindowProc`.

##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject

Указывает на объект, содержащий `CContainedWindowT` объекта.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>Примечания

Этот контейнер, в которой класс должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md), объявляет схему сообщений, используемые в окне автономной.

`m_pObject` инициализируется с помощью конструктора. Например, см. в разделе [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) Обзор.

##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass

Вызывается средой [создать](#create) зарегистрировать класс окна автономной окна.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения atom, однозначно определяющий класс окна регистрируется; в противном случае — нуль.

### <a name="remarks"></a>Примечания

Этот класс окна основана на существующий класс, но использует [CContainedWindowT::WindowProc](#windowproc). Существующий класс окон имя и процедуры окна сохраняются в [m_lpszClassName](#m_lpszclassname) и [m_pfnSuperWindowProc](#m_pfnsuperwindowproc), соответственно.

##  <a name="subclasswindow"></a>  CContainedWindowT::SubclassWindow

Подклассы, идентифицируемый окна *hWnd* и присоединяет его к `CContainedWindowT` объекта.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
[in] Дескриптор окна подкласса.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно успешно подклассом; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Теперь используется окном, выведенных в подклассы [CContainedWindowT::WindowProc](#windowproc). Исходный текст процедуры окна сохраняется в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

> [!NOTE]
>  Не вызывайте `SubclassWindow` уже после вызова метода [создать](#create).

##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap

Изменения, какие схемы сообщений будет использоваться для обработки сообщений содержащееся окно.

```
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>Параметры

*dwMsgMapID*<br/>
[in] Идентификатор сопоставления сообщения. Чтобы использовать сопоставление по умолчанию сообщения, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), передать нулевое значение. Чтобы использовать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.

### <a name="remarks"></a>Примечания

Сопоставление сообщений должен быть определен в содержащего его объекта.

Изначально укажите идентификатор сопоставления сообщений в конструкторе.

##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow

Отсоединяет окно выведенных в подклассы `CContainedWindowT` объекта и восстанавливает исходный текст процедуры окна, сохраненные в [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>Параметры

*bForce*<br/>
[in] Имеет значение true, чтобы принудительно восстановить исходный текст процедуры окна даже в том случае, если процедура окна для данного `CContainedWindowT` объект не является активным. Если *bForce* имеет значение FALSE, а также процедура окна для данного `CContainedWindowT` объект не является активным, не будет восстановлен исходный текст процедуры окна.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор окна ранее подклассов. Если *bForce* имеет значение FALSE, а также процедура окна для данного `CContainedWindowT` объект не является активным, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Этот метод следует используйте только в том случае, если вы хотите восстановить исходный текст процедуры окна до уничтожения окна. В противном случае [WindowProc](#windowproc) автоматически сделает это при уничтожении окна.

##  <a name="windowproc"></a>  CContainedWindowT::WindowProc

Этот статический метод реализует процедуру окна.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
[in] Дескриптор окна.

*uMsg*<br/>
[in] Сообщение, отправленное окну.

*wParam*<br/>
[in] Дополнительные сведения, относящиеся к сообщению.

*lParam*<br/>
[in] Дополнительные сведения, относящиеся к сообщению.

### <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения.

### <a name="remarks"></a>Примечания

`WindowProc` направляет сообщения в схему сообщений, идентифицируемый [m_dwMsgMapID](#m_dwmsgmapid). При необходимости `WindowProc` вызовы [DefWindowProc](#defwindowproc) для обработки дополнительных сообщений.

## <a name="see-also"></a>См. также

[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Класс CMessageMap](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
