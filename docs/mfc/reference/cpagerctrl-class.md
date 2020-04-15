---
title: Класс CPagerCtrl
ms.date: 11/04/2016
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
ms.openlocfilehash: b2c4f1ac99735953f4832226b840ced4ea4c509a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376967"
---
# <a name="cpagerctrl-class"></a>Класс CPagerCtrl

Класс `CPagerCtrl` создается элемент управления страничного навигатора Windows, который может выполнить прокрутку и отобразить содержащееся окно, которое не помещается в содержащее его окно.

## <a name="syntax"></a>Синтаксис

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Формирует объект `CPagerCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPagerCtrl::Создание](#create)|Создает управление пейджером с указанными стилями `CPagerCtrl` и прикрепляет его к текущему объекту.|
|[CPagerCtrl::CreateEx](#createex)|Создает управление пейджером с указанными расширенными `CPagerCtrl` стилями и прикрепляет его к текущему объекту.|
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Позволяет или отстраняет пересылку [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) сообщений в окно, содержащееся в текущем элементе управления пейджера.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|Извлекает фоновый цвет текущего элемента управления пейджера.|
|[CPagerCtrl::GetBorder](#getborder)|Извлекает размер границы текущего элемента управления пейджера.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Извлекает размер кнопки текущего элемента управления пейджером.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Извлекает состояние указанной кнопки в текущем управлении пейджером.|
|[CPagerCtrl:GetDropTarget](#getdroptarget)|Извлекает интерфейс [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) для текущего управления пейджером.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Извлекает положение прокрутки текущего элемента управления пейджера.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Указывает, находится ли указанная кнопка `pressed` текущего управления пейджером в состоянии.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Указывает, находится ли указанная кнопка `grayed` текущего управления пейджером в состоянии.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Указывает, находится ли указанная кнопка `hot` текущего управления пейджером в состоянии.|
|[CPagerCtrl::IsButtonНевидимый](#isbuttoninvisible)|Указывает, находится ли указанная кнопка `invisible` текущего управления пейджером в состоянии.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Указывает, находится ли указанная кнопка `normal` текущего управления пейджером в состоянии.|
|[CPagerCtrl::RecalcSize](#recalcsize)|Вызывает перерасчет текущего элемента управления пейджером с размером содержащегося окна.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|Устанавливает фоновый цвет текущего элемента управления пейджером.|
|[CPagerCtrl::SetBorder](#setborder)|Устанавливает размер границы текущего элемента управления пейджером.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Устанавливает размер кнопки текущего управления пейджером.|
|[CPagerCtrl:SetChild](#setchild)|Устанавливает содержащееся окно для текущего элемента управления пейджером.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Устанавливает положение прокрутки текущего элемента управления пейджером.|

## <a name="remarks"></a>Remarks

Управление пейджером — это окно, которое содержит другое окно, которое является линейным и больше, чем содержащее окно, и позволяет прокручивать содержащееся окно в поле зрения. Управление пейджером отображает две кнопки прокрутки, которые автоматически исчезают, когда содержащееся окно прокручивается в дальней степени, и вновь появляется в противном случае. Можно создать элемент управления пейджера, который прокручивается горизонтально или вертикально.

Например, если в приложении есть панель инструментов, которая недостаточно широка, чтобы показать все его элементы, можно назначить панель инструментов элементу управления пейджером, и пользователи смогут прокрутить панель инструментов влево или вправо, чтобы получить доступ ко всем элементам. Microsoft Internet Explorer Version 4.0 (commctrl.dll версия 4.71) вводит управление пейджером.

Класс `CPagerCtrl` происходит от класса [CWnd.](../../mfc/reference/cwnd-class.md) Для получения дополнительной информации и иллюстрации [Pager Controls](/windows/win32/Controls/pager-controls)управления пейджером см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cpagerctrlcpagerctrl"></a><a name="cpagerctrl"></a>CPagerCtrl::CPagerCtrl

Формирует объект `CPagerCtrl`.

```
CPagerCtrl();
```

### <a name="remarks"></a>Remarks

Используйте [CPagerCtrl::Создать](#create) или [CPagerCtrl::CreateEx](#createex) метод для создания управления `CPagerCtrl` пейджером и прикрепить его к объекту.

## <a name="cpagerctrlcreate"></a><a name="create"></a>CPagerCtrl::Создание

Создает управление пейджером с указанными стилями `CPagerCtrl` и прикрепляет его к текущему объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwStyle*|(в) Битовая комбинация (ИЛИ) [стилей окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стилей управления пейджером,](/windows/win32/Controls/pager-control-styles) которые должны быть применены к управлению.|
|*rect*|(в) Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) содержащую положение и размер элемента управления в координатах клиента.|
|*pParentWnd*|(в) Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента управления. Значение этого параметра не может быть равно NULL.|
|*nID*|(в) Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Чтобы создать элемент управления пейджером, объявить переменную, `CPagerCtrl` а затем позвоните в [CPagerCtrl:::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод на этой переменной.

### <a name="example"></a>Пример

Следующий пример создает управление пейджером, а затем использует [cPagerCtrl::SetChild](#setchild) метод связать очень длинный элемент управления кнопками с управлением пейджера. В примере используется метод [CPagerCtrl::SetButtonSize](#setbuttonsize) для установки высоты управления пейджером до 20 пикселей, а [метод CPagerCtrl: SetBorder](#setborder) установил толщину границы до 1 пикселя.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlcreateex"></a><a name="createex"></a>CPagerCtrl::CreateEx

Создает управление пейджером с указанными расширенными `CPagerCtrl` стилями и прикрепляет его к текущему объекту.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwExStyle*|(в) Битовая комбинация расширенных стилей, которые должны быть применены к управлению. Для получения дополнительной *dwExStyle* информации см. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)|
|*dwStyle*|(в) Битовая комбинация (ИЛИ) [стилей окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стилей управления пейджером,](/windows/win32/Controls/pager-control-styles) которые должны быть применены к управлению.|
|*rect*|(в) Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) содержащую положение и размер элемента управления в координатах клиента.|
|*pParentWnd*|(в) Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента управления. Значение этого параметра не может быть равно NULL.|
|*nID*|(в) Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Чтобы создать элемент управления пейджером, объявить переменную, `CPagerCtrl` а затем позвоните в [CPagerCtrl:::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод на этой переменной.

## <a name="cpagerctrlforwardmouse"></a><a name="forwardmouse"></a>CPagerCtrl::ForwardMouse

Позволяет или отстраняет пересылку [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) сообщений в окно, содержащееся в текущем элементе управления пейджера.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bForward*|(в) TRUE для переадресов сообщений мыши, или FALSE, чтобы не пересылать сообщения мыши.|

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse) сообщение, которое описано в SDK Windows.

## <a name="cpagerctrlgetborder"></a><a name="getborder"></a>CPagerCtrl::GetBorder

Извлекает размер границы текущего элемента управления пейджера.

```
int GetBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер границы, измеряемый в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBORDER](/windows/win32/Controls/pgm-getborder) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::GetBorder](#getborder) для получения толщины границы управления пейджером.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

## <a name="cpagerctrlgetbkcolor"></a><a name="getbkcolor"></a>CPagerCtrl::GetBkColor

Извлекает фоновый цвет текущего элемента управления пейджера.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) содержащее текущий фоновый цвет элемента управления пейджером.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::SetBkColor](#setbkcolor) для установки фонового цвета управления пейджера на красный цвет, и метод [CPagerCtrl::GetBkColor,](#getbkcolor) чтобы подтвердить, что изменение было сделано.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CPagerCtrl::GetButtonSize

Извлекает размер кнопки текущего элемента управления пейджером.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер кнопки, измеряемый в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize) сообщение, которое описано в SDK Windows.

Если управление пейджером имеет PGS_HORZ стиль, размер кнопки определяет ширину кнопок пейджера, а если управление пейджером имеет PGS_VERT стиль, размер кнопки определяет высоту кнопок пейджера. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.

## <a name="cpagerctrlgetbuttonstate"></a><a name="getbuttonstate"></a>CPagerCtrl::GetButtonState

Извлекает состояние указанной кнопки прокрутки в текущем элементе управления пейджером.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

Состояние кнопки, указанной параметром *iButton.* Государство либо PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, либо PGF_DEPRESSED, либо PGF_HOT. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows.

## <a name="cpagerctrlgetdroptarget"></a><a name="getdroptarget"></a>CPagerCtrl:GetDropTarget

Извлекает интерфейс [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) для текущего управления пейджером.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IDropTarget` интерфейс для текущего управления пейджером.

### <a name="remarks"></a>Remarks

`IDropTarget`является одним из интерфейсов, которые вы реализуете для поддержки операций перетаскивания в приложении.

Этот метод отправляет [PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget) сообщение, которое описано в SDK Windows. Звонящее в этом методе `Release` отвечает за вызов участника интерфейса [IDropTarget,](/windows/win32/api/oleidl/nn-oleidl-idroptarget) когда интерфейс больше не нужен.

## <a name="cpagerctrlgetscrollpos"></a><a name="getscrollpos"></a>CPagerCtrl::GetScrollPos

Извлекает положение прокрутки текущего элемента управления пейджера.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее положение прокрутки, измеренное в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETPOS](/windows/win32/Controls/pgm-getpos) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::GetScrollPos](#getscrollpos) для получения текущего положения прокрутки элемента управления пейджером. Если элемент управления пейджера еще не прокрутен до нуля, то в левом положении используется метод [CPagerCtrl::SetScrollPos](#setscrollpos) для установки позиции прокрутки до нуля.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

## <a name="cpagerctrlisbuttondepressed"></a><a name="isbuttondepressed"></a>CPagerCtrl::IsButtonDepressed

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления пейджером в нажатом состоянии.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанная кнопка находится в нажатом состоянии; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows. Затем он проверяет, является ли состояние, которое возвращается, PGF_DEPRESSED. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

## <a name="cpagerctrlisbuttongrayed"></a><a name="isbuttongrayed"></a>CPagerCtrl::IsButtonGrayed

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления пейджером в сером состоянии.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанная кнопка находится в сером состоянии; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows. Затем он проверяет, является ли состояние, которое возвращается, PGF_GRAYED. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

## <a name="cpagerctrlisbuttonhot"></a><a name="isbuttonhot"></a>CPagerCtrl::IsButtonHot

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления пейджером в горячем состоянии.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанная кнопка находится в горячем состоянии; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows. Затем он проверяет, является ли состояние, которое возвращается, PGF_HOT. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

## <a name="cpagerctrlisbuttoninvisible"></a><a name="isbuttoninvisible"></a>CPagerCtrl::IsButtonНевидимый

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления пейджером в невидимом состоянии.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанная кнопка находится в невидимом состоянии; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Windows делает кнопку прокрутки в определенном направлении невидимой, когда содержащееся окно прокручивается в дальней степени, потому что нажатие кнопки дальше не может привести в поле зрения больше содержащегося окна.

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows. Затем он проверяет, является ли состояние, которое возвращается, PGF_INVISIBLE. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) для определения того, видны ли кнопки управления пейджером левой и правой прокрутки.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

## <a name="cpagerctrlisbuttonnormal"></a><a name="isbuttonnormal"></a>CPagerCtrl::IsButtonNormal

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления пейджером в нормальном состоянии.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|(в) Указывает кнопку, для которой находится состояние. Если стиль управления пейджером PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль управления пейджером PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанная кнопка находится в нормальном состоянии; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщение, которое описано в SDK Windows. Затем он проверяет, является ли состояние, которое возвращается, PGF_NORMAL. Для получения дополнительной информации смотрите раздел «Значение [возврата» PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) сообщения.

## <a name="cpagerctrlrecalcsize"></a><a name="recalcsize"></a>CPagerCtrl::RecalcSize

Вызывает перерасчет текущего элемента управления пейджером с размером содержащегося окна.

```
void RecalcSize();
```

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize) сообщение, которое описано в SDK Windows. Следовательно, управление пейджером отправляет [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) уведомление для получения прокрутки размеров содержащегося окна.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::RecalcSize](#recalcsize) для запроса текущего элемента управления пейджера для пересчета его размера.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Пример

В следующем примере используется [отражение сообщений,](../../mfc/tn062-message-reflection-for-windows-controls.md) чтобы позволить управлению пейджера пересчитать свой собственный размер вместо того, чтобы требовать родительского диалога элемента управления для выполнения вычисления. Пример выводит `MyPagerCtrl` класс из [класса CPagerCtrl,](../../mfc/reference/cpagerctrl-class.md)затем использует карту сообщений, `OnCalcsize` чтобы связать уведомление [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) с обработчиком уведомлений. В этом примере обработчик уведомлений устанавливает ширину и высоту управления пейджером на фиксированные значения.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

## <a name="cpagerctrlsetbkcolor"></a><a name="setbkcolor"></a>CPagerCtrl::SetBkColor

Устанавливает фоновый цвет текущего элемента управления пейджером.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*clrBk*|(в) Значение [COLORREF,](/windows/win32/gdi/colorref) содержащее новый фоновый цвет управления пейджером.|

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) содержащее предыдущий фоновый цвет управления пейджером.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl::SetBkColor](#setbkcolor) для установки фонового цвета управления пейджера на красный цвет, и метод [CPagerCtrl::GetBkColor,](#getbkcolor) чтобы подтвердить, что изменение было сделано.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlsetborder"></a><a name="setborder"></a>CPagerCtrl::SetBorder

Устанавливает размер границы текущего элемента управления пейджером.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iBorder*|(в) Новый размер границы, измеряемый в пикселях. Если параметр *iBorder* отрицательный, размер границы устанавливается до нуля.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер границы, измеряемый в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_SETBORDER](/windows/win32/Controls/pgm-setborder) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример создает управление пейджером, а затем использует [cPagerCtrl::SetChild](#setchild) метод связать очень длинный элемент управления кнопками с управлением пейджера. В примере используется метод [CPagerCtrl::SetButtonSize](#setbuttonsize) для установки высоты управления пейджером до 20 пикселей, а [метод CPagerCtrl: SetBorder](#setborder) установил толщину границы до 1 пикселя.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CPagerCtrl::SetButtonSize

Устанавливает размер кнопки текущего управления пейджером.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButtonSize*|(в) Новый размер кнопки, измеряемый в пикселях.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер кнопки, измеряемый в пикселях.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos) сообщение, которое описано в SDK Windows.

Если управление пейджером имеет PGS_HORZ стиль, размер кнопки определяет ширину кнопок пейджера, а если управление пейджером имеет PGS_VERT стиль, размер кнопки определяет высоту кнопок пейджера. Размер кнопки по умолчанию составляет три четверти ширины панели прокрутки, а минимальный размер кнопки — 12 пикселей. Для получения дополнительной [Pager Control Styles](/windows/win32/Controls/pager-control-styles)информации см.

### <a name="example"></a>Пример

Следующий пример создает управление пейджером, а затем использует [cPagerCtrl::SetChild](#setchild) метод связать очень длинный элемент управления кнопками с управлением пейджера. В примере используется метод [CPagerCtrl::SetButtonSize](#setbuttonsize) для установки высоты управления пейджером до 20 пикселей, а [метод CPagerCtrl: SetBorder](#setborder) установил толщину границы до 1 пикселя.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetchild"></a><a name="setchild"></a>CPagerCtrl:SetChild

Устанавливает содержащееся окно для текущего элемента управления пейджером.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*hwndChild*|(в) Ручка к окну, чтобы содержаться.|

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_SETCHILD](/windows/win32/Controls/pgm-setchild) сообщение, которое описано в SDK Windows.

Этот метод не изменяет родительский, содержащийся в окне; он только назначает ручку окна к управлению pager для прокрутки. В большинстве случаев содержащееся окно будет детским окном управления пейджером.

### <a name="example"></a>Пример

Следующий пример создает управление пейджером, а затем использует [cPagerCtrl::SetChild](#setchild) метод связать очень длинный элемент управления кнопками с управлением пейджера. В примере используется метод [CPagerCtrl::SetButtonSize](#setbuttonsize) для установки высоты управления пейджером до 20 пикселей, а [метод CPagerCtrl: SetBorder](#setborder) установил толщину границы до 1 пикселя.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetscrollpos"></a><a name="setscrollpos"></a>CPagerCtrl::SetScrollPos

Устанавливает положение прокрутки текущего элемента управления пейджером.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Ipos*|(в) Новое положение прокрутки, измеренное в пикселях.|

### <a name="remarks"></a>Remarks

Этот метод отправляет [PGM_SETPOS](/windows/win32/Controls/pgm-setpos) сообщение, которое описано в SDK Windows.

## <a name="see-also"></a>См. также раздел

[Класс CPagerCtrl](../../mfc/reference/cpagerctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Контроль Пейджера](/windows/win32/Controls/pager-controls)
