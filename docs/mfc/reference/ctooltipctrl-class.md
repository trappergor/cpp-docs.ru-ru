---
title: Класс CToolTipCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ac89d58b6043089f6c0d0045189116d2799f517
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069221"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

Инкапсулирует функциональность элемента управления "всплывающая подсказка" — небольшого всплывающего окна, в котором отображается одна строка текста, описывающая назначение инструмента в приложении.

## <a name="syntax"></a>Синтаксис

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Создает объект `CToolTipCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CToolTipCtrl::Activate](#activate)|Активирует и деактивирует всплывающая подсказка.|
|[CToolTipCtrl::AddTool](#addtool)|Регистрирует средство управления всплывающей подсказки.|
|[CToolTipCtrl::AdjustRect](#adjustrect)|Преобразует между текст элемента управления всплывающей подсказки элемента отображения прямоугольника и его прямоугольной области окна.|
|[CToolTipCtrl::Create](#create)|Создает элемент управления всплывающей подсказки и присоединяет его к `CToolTipCtrl` объекта.|
|[CToolTipCtrl::CreateEx](#createex)|Создает элемент управления всплывающей подсказки с указанным расширенные стили Windows и присоединяет его к `CToolTipCtrl` объекта.|
|[CToolTipCtrl::DelTool](#deltool)|Удаляет инструмент из всплывающая подсказка.|
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Извлекает размер подсказки.|
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Получает сведения, такие как размер, положение и текст окна всплывающей подсказки, отображающий текущего элемента управления всплывающей подсказки.|
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Получает начальный, всплывающее окно и reshow длительности, которые в настоящее время заданы для средства элемента управления подсказки.|
|[CToolTipCtrl::GetMargin](#getmargin)|Извлекает верхней, левую, нижнюю и правого полей, которые заданы для подсказки.|
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Получает максимальную ширину окна подсказки средство.|
|[CToolTipCtrl::GetText](#gettext)|Извлекает текст, который поддерживает элемент управления всплывающей подсказки для инструмента.|
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Получает цвет фона в окно подсказки.|
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Возвращает цвет текста в окно подсказки.|
|[CToolTipCtrl::GetTitle](#gettitle)|Извлекает заголовок текущего элемента управления всплывающей подсказки.|
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Извлекает количество средств, поддерживаемых элементом управления всплывающей подсказки.|
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Извлекает сведения о это средство, поддерживает элемент управления всплывающей подсказки.|
|[CToolTipCtrl::HitTest](#hittest)|Проверяет точку, чтобы определить, является ли оно в ограничивающий прямоугольник данного средства. Если Да, извлекает сведения об этом средстве.|
|[CToolTipCtrl::Pop](#pop)|Удаляет отображаемые подсказки из представления.|
|[CToolTipCtrl::Popup](#popup)|Вызывает текущего элемента управления всплывающей подсказки для отображения в координатах последнего сообщения мыши.|
|[CToolTipCtrl::RelayEvent](#relayevent)|Передает сообщение мыши элементом управления всплывающей подсказки для обработки.|
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Задает начальное всплывающем окне и reshow длительности для элемента управления всплывающей подсказки.|
|[CToolTipCtrl::SetMargin](#setmargin)|Задает верхней, левую, нижнюю и правого полей для подсказки.|
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Задает максимальную ширину окна подсказки средство.|
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Задает цвет фона в окно подсказки.|
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Задает цвет текста в окно подсказки.|
|[CToolTipCtrl::SetTitle](#settitle)|Добавляет стандартный значок и название строку во всплывающей подсказке.|
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Задает сведения, которые поддерживает всплывающей подсказки для инструмента.|
|[CToolTipCtrl::SetToolRect](#settoolrect)|Задает новый ограничивающий прямоугольник для средства.|
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль окно подсказки.|
|[CToolTipCtrl::Update](#update)|Вызывает перерисовку текущего инструмента.|
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Задает текст подсказки для инструмента.|

## <a name="remarks"></a>Примечания

«Средство» — либо это окно, такие как дочернего окна элемента управления или определяемые приложением прямоугольная область в клиентской области окна. Во всплывающей подсказке будет скрыт в большинстве случаев, отображаются, только когда пользователь помещает курсор над инструментом и оставляет его примерно половина во-вторых. Подсказка появляется рядом с курсором и исчезает, когда пользователь нажимает кнопку мыши или перемещает курсор средство.

`CToolTipCtrl` предоставляет функциональные возможности для управления начального времени и длительности всплывающей подсказки, ширина полей, окружающий текст подсказки, ширину самой окно подсказки и цвет фона и текста всплывающей подсказки. Единый всплывающая подсказка может предоставить сведения для более одного средства.

`CToolTipCtrl` Класс предоставляет функциональные возможности Windows распространенных всплывающая подсказка. Этот элемент управления (и, следовательно `CToolTipCtrl` класс) доступны только для программ, работающих в версиях Windows 95/98 и Windows NT 3.51 и более поздних версиях.

Дополнительные сведения о включении всплывающие подсказки, см. в разделе [всплывающие подсказки в Windows не являющиеся производными CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

Дополнительные сведения об использовании `CToolTipCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CToolTipCtrl](../../mfc/using-ctooltipctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="activate"></a>  CToolTipCtrl::Activate

Вызывайте эту функцию, чтобы активировать или деактивировать элемент управления всплывающей подсказки.

```
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Указывает, является ли всплывающая подсказка для быть активируется или деактивируется.

### <a name="remarks"></a>Примечания

Если *bActivate* имеет значение TRUE, элемент управления активирован; Если значение равно FALSE, он будет отключена.

Когда всплывающая подсказка включен, данные подсказки отображается при прохождении курсора над инструментом, который регистрируется с помощью элемента управления; Если оно неактивно, данные подсказки не отображается, даже если курсор находится над инструментом.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="addtool"></a>  CToolTipCtrl::AddTool

Регистрирует средство управления всплывающей подсказки.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDText*<br/>
Идентификатор строкового ресурса, содержащий текст для средства.

*lpRectTool*<br/>
Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, содержащую средство координаты ограничивающего прямоугольника. Координаты указываются относительно левого верхнего угла клиентской области окна, идентифицируемый *pWnd*.

*nIDTool*<br/>
Идентификатор средства.

*lpszText*<br/>
Указатель на текст для средства. Если этот параметр содержит значение LPSTR_TEXTCALLBACK, сообщений уведомления TTN_NEEDTEXT перейдите к родительского окна, *pWnd* указывает.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

*LpRectTool* и *nIDTool* параметры должны быть допустимыми, или если *lpRectTool* имеет значение NULL, *nIDTool* должно быть равно 0.

Элемент управления всплывающей подсказки можно связать с более чем одним средством. Эта функция вызывается для регистрации средством управления всплывающей подсказки, так что сведениями, хранящимися в подсказке отображается в том случае, когда курсор находится в средстве.

> [!NOTE]
>  Не удается задать всплывающую подсказку в статический элемент управления с помощью `AddTool`.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect

Преобразует между текст всплывающей подсказки элемента управления отображения прямоугольника и его прямоугольной области окна.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, которая содержит прямоугольник окна подсказки средство или прямоугольник отображаемого текста.

*bLarger*<br/>
Если значение равно TRUE, *lprc* используется для указания прямоугольник отображения текста, и он получает соответствующий прямоугольной области окна. Если значение равно FALSE, *lprc* используется для указания прямоугольника окна, и он получает соответствующий прямоугольник отображения текста.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если прямоугольник успешно корректируется; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член вычисляет прямоугольник отображения текста элемента управления всплывающей подсказки элемента из его прямоугольной области окна или прямоугольной области окна подсказки средства, необходимые для отображения прямоугольника отображения указанный текст.

Эта функция-член реализует поведение сообщение Win32 [TTM_ADJUSTRECT](/windows/desktop/Controls/ttm-adjustrect), как описано в пакете Windows SDK.

##  <a name="create"></a>  CToolTipCtrl::Create

Создает элемент управления всплывающей подсказки и присоединяет его к `CToolTipCtrl` объекта.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указывает родительского окна управления всплывающей подсказки, обычно `CDialog`. Он не должен иметь значение NULL.

*dwStyle*<br/>
Задает стиль управления всплывающей подсказки. См. в разделе **"Примечания"** Дополнительные сведения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CToolTipCtrl` объект создано успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

При создании `CToolTipCtrl` в два этапа. Во-первых, вызовите конструктор для создания `CToolTipCtrl` объекта, а затем вызвать `Create` для создания всплывающая подсказка и присоединить его к `CToolTipCtrl` объекта.

*DwStyle* параметр может быть любое сочетание [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Кроме того, элемент управления всплывающей подсказки имеет два стиля данного класса: TTS_ALWAYSTIP и TTS_NOPREFIX.

|Стиль|Значение|
|-----------|-------------|
|TTS_ALWAYSTIP|Указывает, что подсказка будет отображаться при прохождении курсора над инструментом, независимо от того, окно-владелец управления всплывающей подсказки, является ли активным или неактивным. Без этого стиля всплывающая подсказка появляется при активном окно владелец, но не в том случае, если оно неактивно.|
|TTS_NOPREFIX|Этот стиль предотвращает удаление символ амперсанда (&) из строки. Если элемент управления всплывающей подсказки не имеет стиль TTS_NOPREFIX, система автоматически удаляет знаки амперсанда, что позволяет приложению использовать ту же строку, как элемент меню, а также как текст в элемент управления всплывающей подсказки.|

Всплывающая подсказка имеет WS_POPUP и WS_EX_TOOLWINDOW стили окна, независимо от их при создании элемента управления.

Чтобы создать элемент управления всплывающей подсказки с windows, расширенные стили, вызовите [CToolTipCtrl::CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="createex"></a>  CToolTipCtrl::CreateEx

Создает элемент управления (дочернего окна) и связать его с `CToolTipCtrl` объекта.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*dwStyle*<br/>
Задает стиль управления всплывающей подсказки. См. в разделе **"Примечания"** раздел [создать](#create) Дополнительные сведения.

*dwStyleEx*<br/>
Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, при успешном выполнении в противном случае 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо `Create` применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl

Создает объект `CToolTipCtrl`.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать `Create` после создания объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

##  <a name="deltool"></a>  CToolTipCtrl::DelTool

Удаляет заданные средство *pWnd* и *nIDTool* из коллекции средств, поддерживаемых элементом управления всплывающей подсказки.

```
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDTool*<br/>
Идентификатор средства.

##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize

Извлекает размер подсказки.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*lpToolInfo*<br/>
Указатель на всплывающей подсказки [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) структуры.

### <a name="return-value"></a>Возвращаемое значение

Размер подсказки.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETBUBBLESIZE](/windows/desktop/Controls/ttm-getbubblesize), как описано в пакете Windows SDK.

##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool

Получает сведения, такие как размер, положение и текст окна всплывающей подсказки, отображаемый элементом управления всплывающей подсказки текущей.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpToolInfo*|[out] Указатель на [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) структуры, который получает сведения о текущем окне всплывающей подсказки.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если эти сведения поступают успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_GETCURRENTTOOL](/windows/desktop/Controls/ttm-getcurrenttool) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода извлекает сведения о текущем окне всплывающей подсказки.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime

Получает начальный всплывающем окне и reshow длительности в настоящий момент настроен элемент управления всплывающей подсказки.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Параметры

*dwDuration*<br/>
Флаг, указывающий, какие значения длительности будут извлекаться. Этот параметр может принимать одно из следующих значений:

- Получить TTDT_AUTOPOP продолжительность времени, средство окно подсказок по остается видимым, если указатель мыши останавливается в ограничивающий прямоугольник для средства.

- Получить TTDT_INITIAL отображается продолжительность времени хранения указатель мыши должен оставаться в границах внутри ограничивающего прямоугольника инструмента перед окно подсказки.

- Получить TTDT_RESHOW продолжительность времени, необходимое для окна подсказки последующих инструментов в виде указателя перемещает из одного средства в другую.

### <a name="return-value"></a>Возвращаемое значение

Время истечения указанной задержки в миллисекундах

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETDELAYTIME](/windows/desktop/Controls/ttm-getdelaytime), как описано в пакете Windows SDK.

##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin

Извлекает верхней, левую, нижнюю и правого полей для подсказки.

```
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Адрес `RECT` структуру, которая будет получать данные поля. Члены [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры не определяют ограничивающего прямоугольника. Для этого сообщения элементы структуры интерпретируются следующим образом:

|Член|Представление|
|------------|--------------------|
|`top`|Расстояние между верхней границы и верхним краем текста подсказки, в пикселях.|
|`left`|Расстояние между левой границей и левый конец текст подсказки, в пикселях.|
|`bottom`|Расстояние между нижней границей и нижней части текст подсказки, в пикселях.|
|`right`|Расстояние между правой границей и правом конце текст подсказки, в пикселях.|

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETMARGIN](/windows/desktop/Controls/ttm-getmargin), как описано в пакете Windows SDK.

##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth

Получает максимальную ширину окна подсказки средство.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная ширина для подсказки.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETMAXTIPWIDTH](/windows/desktop/Controls/ttm-getmaxtipwidth), как описано в пакете Windows SDK.

##  <a name="gettext"></a>  CToolTipCtrl::GetText

Извлекает текст, который поддерживает элемент управления всплывающей подсказки для инструмента.

```
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
Ссылка на `CString` объект, который получает текст данного средства.

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDTool*<br/>
Идентификатор средства.

### <a name="remarks"></a>Примечания

*PWnd* и *nIDTool* параметры определяют средство. Если этот инструмент предварительно был зарегистрирован с элементом управления всплывающей подсказки посредством предыдущего вызова `CToolTipCtrl::AddTool`, объект, упоминаемый в *str* присваивается текст этого средства.

##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor

Получает цвет фона в окно подсказки.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, представляющее цвет фона.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETTIPBKCOLOR](/windows/desktop/Controls/ttm-gettipbkcolor), как описано в пакете Windows SDK.

##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor

Возвращает цвет текста в окно подсказки.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, представляющее цвет текста.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_GETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-gettiptextcolor), как описано в пакете Windows SDK.

##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle

Извлекает заголовок текущего элемента управления всплывающей подсказки.

```
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pttgt*|[out] Указатель на [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) структуру, содержащую сведения об элементе управления ToolTip. При возвращении данного метода *pszTitle* членом [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) структура указывает на текст заголовка.|

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_GETTITLE](/windows/desktop/Controls/ttm-gettitle) сообщения, который описан в пакете Windows SDK.

##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount

Извлекает количество средств, зарегистрированной элементом управления всплывающей подсказки.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество средств, зарегистрированных с элементом управления всплывающей подсказки.

##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo

Извлекает сведения о это средство, поддерживает элемент управления всплывающей подсказки.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Параметры

*ToolInfo*<br/>
Ссылка на `TOOLINFO` объект, который получает текст данного средства.

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDTool*<br/>
Идентификатор средства.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`hwnd` И `uId` членами [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) ссылается структура *CToolInfo* идентификации средство. Если этот инструмент был зарегистрирован с элементом управления всплывающей подсказки посредством предыдущего вызова `AddTool`, `TOOLINFO` структура заполняется информацию об этом инструменте.

##  <a name="hittest"></a>  CToolTipCtrl::HitTest

Проверяет точку, чтобы определить, является ли оно в ограничивающий прямоугольник данного средства и если да, получить информацию об этом инструменте.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее средство.

*pt*<br/>
Указатель на `CPoint` объект, содержащий координаты точки проверяется.

*lpToolInfo*<br/>
Указатель на [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) структуру, содержащую сведения об этом средстве.

### <a name="return-value"></a>Возвращаемое значение

Ненулевым, если точку, указанную сведения проверки нажатия в ограничивающий прямоугольник данного средства; в противном случае 0.

### <a name="remarks"></a>Примечания

Если эта функция возвращает ненулевое значение, структура указывает *lpToolInfo* заполняется сведения о средстве, в которой прямоугольник находится точка.

`TTHITTESTINFO` Структура определена следующим образом:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Указывает дескриптор этого средства.

- `pt`

   Задает координаты точки, если точка находится в инструменте ограничивающий прямоугольник.

- `ti`

   Сведения о средстве. Дополнительные сведения о `TOOLINFO` структуры, см. в разделе [CToolTipCtrl::GetToolInfo](#gettoolinfo).

##  <a name="pop"></a>  CToolTipCtrl::Pop

Удаляет отображаемые подсказки из представления.

```
void Pop();
```

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_POP](/windows/desktop/Controls/ttm-pop), как описано в пакете Windows SDK.

##  <a name="popup"></a>  CToolTipCtrl::Popup

Вызывает текущего элемента управления всплывающей подсказки для отображения в координатах последнего сообщения мыши.

```
void Popup();
```

### <a name="remarks"></a>Примечания

Этот метод отправляет [TTM_POPUP](/windows/desktop/Controls/ttm-popup) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода отображает окно всплывающей подсказки.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent

Передает сообщение мыши элементом управления всплывающей подсказки для обработки.

```
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*lpMsg*<br/>
Указатель на [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, содержащую сообщения для ретрансляции.

### <a name="remarks"></a>Примечания

Всплывающая подсказка обрабатывает только следующие сообщения, отправляемые на него по `RelayEvent`:

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime

Задает время задержки для элемента управления всплывающей подсказки.

```
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Параметры

*nDelay*<br/>
Задает время задержки в миллисекундах.

*dwDuration*<br/>
Флаг, указывающий, какие значения длительности будут извлекаться. См. в разделе [CToolTipCtrl::GetDelayTime](#getdelaytime) описание допустимых значений.

*iTime*<br/>
Время истечения указанной задержки в миллисекундах.

### <a name="remarks"></a>Примечания

Задержка — это продолжительность времени хранения курсор должен оставаться на средство, прежде чем появится окно подсказки. Время задержки по умолчанию — 500 миллисекунд.

##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin

Задает верхней, левую, нижнюю и правого полей для подсказки.

```
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Параметры

*lprc*<br/>
Адрес `RECT` структуру, содержащую сведения margin устанавливаемое значение. Члены `RECT` структуры не определяют ограничивающего прямоугольника. См. в разделе [CToolTipCtrl::GetMargin](#getmargin) описание поля данных.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_SETMARGIN](/windows/desktop/Controls/ttm-setmargin), как описано в пакете Windows SDK.

##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth

Задает максимальную ширину окна подсказки средство.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Параметры

*iWidth*<br/>
Ширина окна подсказки максимальное средство устанавливаемое значение.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий ширина максимальное tip.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_SETMAXTIPWIDTH](/windows/desktop/Controls/ttm-setmaxtipwidth), как описано в пакете Windows SDK.

##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor

Задает цвет фона в окно подсказки.

```
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Среда CLR*<br/>
Новый цвет фона.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_SETTIPBKCOLOR](/windows/desktop/Controls/ttm-settipbkcolor), как описано в пакете Windows SDK.

##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor

Задает цвет текста в окно подсказки.

```
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Среда CLR*<br/>
Новый цвет текста.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_SETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-settiptextcolor), как описано в пакете Windows SDK.

##  <a name="settitle"></a>  CToolTipCtrl::SetTitle

Добавляет стандартный значок и название строку во всплывающей подсказке.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Параметры

*uIcon*<br/>
См. в разделе *значок* в [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle) в пакете Windows SDK.

*lpstrTitle*<br/>
Указатель на строку заголовка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle), как описано в пакете Windows SDK.

##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo

Задает сведения, которые поддерживает всплывающей подсказки для инструмента.

```
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Параметры

*lpToolInfo*<br/>
Указатель на [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) структуру, которая определяет сведения для задания.

##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect

Задает новый ограничивающий прямоугольник для средства.

```
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDTool*<br/>
Идентификатор средства.

*lpRect*<br/>
Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, указав новый ограничивающий прямоугольник.

##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme

Задает визуальный стиль окно подсказки.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*pszSubAppName*<br/>
Указатель на строку Юникода, которая содержит визуальный стиль для задания.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не используется.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [TTM_SETWINDOWTHEME](/windows/desktop/Controls/ttm-setwindowtheme) сообщения, как описано в пакете Windows SDK.

##  <a name="update"></a>  CToolTipCtrl::Update

Вызывает перерисовку текущего инструмента.

```
void Update();
```

##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText

Обновляет текст подсказки для данного элемента управления средств.

```
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текст для средства.

*pWnd*<br/>
Указатель на окно, содержащее средство.

*nIDTool*<br/>
Идентификатор средства.

*nIDText*<br/>
Идентификатор строкового ресурса, содержащий текст для средства.

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBar](../../mfc/reference/ctoolbar-class.md)
