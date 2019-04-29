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
ms.openlocfilehash: 648bc17f0f130b831aa619b90ed13ba6be35b4d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373249"
---
# <a name="cpagerctrl-class"></a>Класс CPagerCtrl

Класс `CPagerCtrl` создается элемент управления страничного навигатора Windows, который может выполнить прокрутку и отобразить содержащееся окно, которое не помещается в содержащее его окно.

## <a name="syntax"></a>Синтаксис

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Создает объект `CPagerCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPagerCtrl::Create](#create)|Создает элемент управления страничного навигатора с указанными стилями и присоединяет его к текущему `CPagerCtrl` объекта.|
|[CPagerCtrl::CreateEx](#createex)|Создает элемент управления страничного навигатора с указанным расширенные стили и присоединяет его к текущему `CPagerCtrl` объекта.|
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Включает или отключает переадресации [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) сообщения окна, которое содержится в текущего элемента управления страничного навигатора.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|Получает цвет фона текущего элемента управления страничного навигатора.|
|[CPagerCtrl::GetBorder](#getborder)|Получает размер границы текущего элемента управления страничного навигатора.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Извлекает размер кнопок текущего элемента управления страничного навигатора.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Возвращает состояние элемента текущего элемента управления страничного навигатора в указанную кнопку.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Извлекает [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) интерфейс для текущего элемента управления страничного навигатора.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Возвращает позицию прокрутки текущего элемента управления страничного навигатора.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Указывает, является ли указанный кнопка текущего элемента управления страничного навигатора в `pressed` состояние.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Указывает, является ли указанный кнопка текущего элемента управления страничного навигатора в `grayed` состояние.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Указывает, является ли указанный кнопка текущего элемента управления страничного навигатора в `hot` состояние.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Указывает, является ли указанный кнопка текущего элемента управления страничного навигатора в `invisible` состояние.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Указывает, является ли указанный кнопка текущего элемента управления страничного навигатора в `normal` состояние.|
|[CPagerCtrl::RecalcSize](#recalcsize)|Вызывает текущего элемента управления страничного навигатора для пересчета размер окна автономной.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|Задает цвет фона текущего элемента управления страничного навигатора.|
|[CPagerCtrl::SetBorder](#setborder)|Задает размер границы текущего элемента управления страничного навигатора.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Задает размер кнопок текущего элемента управления страничного навигатора.|
|[CPagerCtrl::SetChild](#setchild)|Задает содержащееся окно текущего элемента управления страничного навигатора.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Задает позицию прокрутки текущего элемента управления страничного навигатора.|

## <a name="remarks"></a>Примечания

Элемент управления страничного навигатора — окно, содержащее еще одно окно, имеет линейную и больше содержащего его окна и позволяет выполнять прокрутку и отобразить содержащееся окно. Страничный навигатор отображает две кнопки прокрутки, которые автоматически исчезают, когда с автономной прокручивать окно в его выбирается самый дальний степени и в противном случае на экране. Можно создать элемент управления страничного навигатора, который прокручивается горизонтально или вертикально.

Например если приложение имеет панель инструментов, которая не является достаточно широким, чтобы показать все элементы, можно назначить панели инструментов управления страничного навигатора, и пользователи смогут выполнять прокрутку панели инструментов, чтобы влево или вправо для доступа к все элементы. Microsoft Internet Explorer версии 4.0 (версия commctrl.dll 4.71) представляет элемент управления страничного навигатора.

`CPagerCtrl` Класс является производным от [CWnd](../../mfc/reference/cwnd-class.md) класса. Дополнительные сведения и пример элемента управления страничного навигатора, см. в разделе [элементов управления Pager](/windows/desktop/Controls/pager-controls).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl

Создает объект `CPagerCtrl`.

```
CPagerCtrl();
```

### <a name="remarks"></a>Примечания

Используйте [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для создания элемента управления страничного навигатора и присоединить его к `CPagerCtrl` объекта.

##  <a name="create"></a>  CPagerCtrl::Create

Создает элемент управления страничного навигатора с указанными стилями и присоединяет его к текущему `CPagerCtrl` объекта.

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
|*dwStyle*|[in] Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles) для применения к элементу управления.|
|*rect*|[in] Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, содержащая положение и размер элемента управления в координатах клиентской области окна.|
|*pParentWnd*|[in] Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления. Этот параметр не может иметь значение NULL.|
|*nID*|[in] Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Чтобы создать элемент управления страничного навигатора, объявите `CPagerCtrl` переменной, затем вызвать [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для этой переменной.

### <a name="example"></a>Пример

Следующий пример создает управления страничного навигатора, а затем использует [CPagerCtrl::SetChild](#setchild) метод должен быть сопоставлен очень много кнопки управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="createex"></a>  CPagerCtrl::CreateEx

Создает элемент управления страничного навигатора с указанным расширенные стили и присоединяет его к текущему `CPagerCtrl` объекта.

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
|*dwExStyle*|[in] Побитовое сочетание расширенные стили для применения к элементу управления. Дополнительные сведения см. в разделе *dwExStyle* параметр [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) функции.|
|*dwStyle*|[in] Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles) для применения к элементу управления.|
|*rect*|[in] Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, содержащая положение и размер элемента управления в координатах клиентской области окна.|
|*pParentWnd*|[in] Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления. Этот параметр не может иметь значение NULL.|
|*nID*|[in] Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Чтобы создать элемент управления страничного навигатора, объявите `CPagerCtrl` переменной, затем вызвать [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для этой переменной.

##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse

Включает или отключает переадресации [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) сообщения окна, которое содержится в текущего элемента управления страничного навигатора.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bForward*|[in] Значение true, чтобы сообщения мыши вперед, или FALSE не перенаправлять сообщения мыши.|

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_FORWARDMOUSE](/windows/desktop/Controls/pgm-forwardmouse) сообщения, который описан в пакете Windows SDK.

##  <a name="getborder"></a>  CPagerCtrl::GetBorder

Получает размер границы текущего элемента управления страничного навигатора.

```
int GetBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер границы, измеряется в пикселах.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBORDER](/windows/desktop/Controls/pgm-getborder) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::GetBorder](#getborder) метод для извлечения толщины границы для элемента управления страничного навигатора.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor

Получает цвет фона текущего элемента управления страничного навигатора.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, содержащее текущий цвет фона элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBKCOLOR](/windows/desktop/Controls/pgm-getbkcolor) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::SetBkColor](#setbkcolor) метод, чтобы задать цвет фона элемента управления страничного навигатора на красный и [CPagerCtrl::GetBkColor](#getbkcolor) метод, чтобы убедиться, что была изменена.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize

Извлекает размер кнопок текущего элемента управления страничного навигатора.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер кнопок, измеряется в пикселах.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSIZE](/windows/desktop/Controls/pgm-getbuttonsize) сообщения, который описан в пакете Windows SDK.

Если для элемента управления страничного навигатора PGS_HORZ стиль, размер кнопок определяет ширину кнопок страничного навигатора и если для элемента управления страничного навигатора PGS_VERT стиль, размер кнопок определяет высоту кнопок страничного навигатора. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).

##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState

Возвращает состояние элемента указанную кнопку прокрутки в текущего элемента управления страничного навигатора.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Состояние кнопки, определяемой параметром *iButton* параметра. Состояние — либо PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED или PGF_HOT. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK.

##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget

Извлекает [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) интерфейс для текущего элемента управления страничного навигатора.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IDropTarget` интерфейс для текущего элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

`IDropTarget` является одним из интерфейсы, реализуемые для поддержки операций перетаскивания и вставки в приложении.

Этот метод отправляет [PGM_GETDROPTARGET](/windows/desktop/Controls/pgm-getdroptarget) сообщения, который описан в пакете Windows SDK. Объект, вызывающий этот метод отвечает за вызов метода `Release` членом [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) интерфейс интерфейс больше не используется.

##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos

Возвращает позицию прокрутки текущего элемента управления страничного навигатора.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

В текущую позицию прокрутки, измеряется в пикселах.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETPOS](/windows/desktop/Controls/pgm-getpos) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::GetScrollPos](#getscrollpos) метод для извлечения в текущую позицию прокрутки элемента управления страничного навигатора. Если элемент управления страничного навигатора не прокручивается до нуля, самую левую позицию, в примере используется [CPagerCtrl::SetScrollPos](#setscrollpos) способ присваивается нулевое значение позиции прокрутки.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed

Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в нажатом состоянии.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанную кнопку в нажатом состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK. Затем он проверяет, является ли состояние, которое возвращается PGF_DEPRESSED. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed

Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в состоянии затененный.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанный кнопка находится в состоянии затененный; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK. Затем он проверяет, является ли состояние, которое возвращается PGF_GRAYED. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot

Указывает, находится ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в активном состоянии.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанную кнопку в активном состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK. Затем он проверяет, является ли состояние, которое возвращается PGF_HOT. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible

Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в состоянии невидимым.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанный кнопка находится в состоянии невидимым; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Windows делает кнопки прокрутки в определенном направлении невидимым когда содержащееся окно прокручена его выбирается самый дальний экстент, так как дополнительные кнопки не удается подключить несколько содержащееся окно в представление.

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK. Затем он проверяет, является ли состояние, которое возвращается PGF_INVISIBLE. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) метод для определения ли элемент управления страничного навигатора левым и элемента отображаются кнопки прокрутки вправо.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal

Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в обычном состоянии.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButton*|[in] Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора PGS_HORZ, укажите для левой кнопки мыши и PGB_BOTTOMORRIGHT PGB_TOPORLEFT для правой кнопки. Если стиль элемента управления страничного навигатора PGS_VERT, укажите PGB_TOPORLEFT кнопка сверху и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанную кнопку в обычном состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения, который описан в пакете Windows SDK. Затем он проверяет, является ли состояние, которое возвращается PGF_NORMAL. Дополнительные сведения см. в разделе возвращают значение [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) сообщения.

##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize

Вызывает текущего элемента управления страничного навигатора для пересчета размер окна автономной.

```
void RecalcSize();
```

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_RECALCSIZE](/windows/desktop/Controls/pgm-recalcsize) сообщения, который описан в пакете Windows SDK. Следовательно, элемент управления страничного навигатора отправляет [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) уведомление, чтобы получить размеры прокрутки окна автономной.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::RecalcSize](#recalcsize) метод для запроса к пересчету его размера текущего элемента управления страничного навигатора.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Пример

В следующем примере используется [сообщений отражения](../../mfc/tn062-message-reflection-for-windows-controls.md) включить элемент управления страничного навигатора, чтобы повторно вычислить собственный размер не требует диалоговое окно родительского элемента управления для выполнения вычисления. В примере является производным `MyPagerCtrl` класса из [класс CPagerCtrl](../../mfc/reference/cpagerctrl-class.md), затем использует схему сообщений для привязки [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) уведомление с `OnCalcsize` обработчика уведомлений. В этом примере обработчик уведомления задает ширину и высоту элемента управления страничного навигатора для фиксированных значений.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor

Задает цвет фона текущего элемента управления страничного навигатора.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*clrBk*|[in] Объект [COLORREF](/windows/desktop/gdi/colorref) значение, содержащее новый цвет фона элемента управления страничного навигатора.|

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, содержащее предыдущий цвет фона элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_SETBKCOLOR](/windows/desktop/Controls/pgm-setbkcolor) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере используется [CPagerCtrl::SetBkColor](#setbkcolor) метод, чтобы задать цвет фона элемента управления страничного навигатора на красный и [CPagerCtrl::GetBkColor](#getbkcolor) метод, чтобы убедиться, что была изменена.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="setborder"></a>  CPagerCtrl::SetBorder

Задает размер границы текущего элемента управления страничного навигатора.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iBorder*|[in] Новый размер границы, измеряется в пикселах. Если *iBorder* параметр имеет отрицательное значение, размер границы, равным нулю.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер границы, измеряется в пикселах.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_SETBORDER](/windows/desktop/Controls/pgm-setborder) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

Следующий пример создает управления страничного навигатора, а затем использует [CPagerCtrl::SetChild](#setchild) метод должен быть сопоставлен очень много кнопки управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize

Задает размер кнопок текущего элемента управления страничного навигатора.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iButtonSize*|[in] Новый размер кнопок, измеряется в пикселах.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер кнопки, измеряется в пикселах.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_SETBUTTONSIZE](/windows/desktop/Controls/pgm-setpos) сообщения, который описан в пакете Windows SDK.

Если для элемента управления страничного навигатора PGS_HORZ стиль, размер кнопок определяет ширину кнопок страничного навигатора и если для элемента управления страничного навигатора PGS_VERT стиль, размер кнопок определяет высоту кнопок страничного навигатора. Размер кнопок по умолчанию — три четверти ширина полосы прокрутки, а размер кнопок минимальное — 12 пикселов. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](/windows/desktop/Controls/pager-control-styles).

### <a name="example"></a>Пример

Следующий пример создает управления страничного навигатора, а затем использует [CPagerCtrl::SetChild](#setchild) метод должен быть сопоставлен очень много кнопки управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setchild"></a>  CPagerCtrl::SetChild

Задает содержащееся окно текущего элемента управления страничного навигатора.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*hwndChild*|[in] Дескриптор окна, которые должны содержаться.|

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_SETCHILD](/windows/desktop/Controls/pgm-setchild) сообщения, который описан в пакете Windows SDK.

Этот метод не изменяет родительский автономной окна. только элемент управления страничного навигатора для прокрутки назначает дескриптор окна. В большинстве случаев содержащееся окно будет дочернего окна элемента управления страничного навигатора.

### <a name="example"></a>Пример

Следующий пример создает управления страничного навигатора, а затем использует [CPagerCtrl::SetChild](#setchild) метод должен быть сопоставлен очень много кнопки управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos

Задает позицию прокрутки текущего элемента управления страничного навигатора.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iPos*|[in] Новая позиция прокрутки, измеряется в пикселах.|

### <a name="remarks"></a>Примечания

Этот метод отправляет [PGM_SETPOS](/windows/desktop/Controls/pgm-setpos) сообщения, который описан в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Класс CPagerCtrl](../../mfc/reference/cpagerctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Элементы управления страничного навигатора](/windows/desktop/Controls/pager-controls)
