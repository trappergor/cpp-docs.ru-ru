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
ms.openlocfilehash: 519a376bdecc488a94eab65973e33d960ca50c8d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503025"
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
|[CPagerCtrl:: CPagerCtrl](#cpagerctrl)|Создает объект `CPagerCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPagerCtrl:: Create](#create)|Создает элемент управления страничный навигатор с указанными стилями и прикрепляет `CPagerCtrl` его к текущему объекту.|
|[CPagerCtrl:: Креатикс](#createex)|Создает элемент управления страничного навигатора с указанными расширенными стилями и прикрепляет его к текущему `CPagerCtrl` объекту.|
|[CPagerCtrl:: Форвардмаусе](#forwardmouse)|Включает или отключает перенаправление сообщений [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) в окно, содержащееся в текущем элементе управления страничного навигатора.|
|[CPagerCtrl:: Жетбкколор](#getbkcolor)|Возвращает цвет фона текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: награница](#getborder)|Возвращает размер границы текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Жетбуттонсизе](#getbuttonsize)|Получает размер кнопки текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Жетбуттонстате](#getbuttonstate)|Получает состояние указанной кнопки в текущем элементе управления страничного навигатора.|
|[CPagerCtrl:: Жетдроптаржет](#getdroptarget)|Извлекает интерфейс [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) для текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Жетскроллпос](#getscrollpos)|Возвращает расположение прокрутки текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Исбуттондепрессед](#isbuttondepressed)|Указывает, находится ли указанная кнопка текущего элемента управления страничного `pressed` навигатора в состоянии.|
|[CPagerCtrl:: Исбуттонграйед](#isbuttongrayed)|Указывает, находится ли указанная кнопка текущего элемента управления страничного `grayed` навигатора в состоянии.|
|[CPagerCtrl:: Исбуттонхот](#isbuttonhot)|Указывает, находится ли указанная кнопка текущего элемента управления страничного `hot` навигатора в состоянии.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Указывает, находится ли указанная кнопка текущего элемента управления страничного `invisible` навигатора в состоянии.|
|[CPagerCtrl:: Исбуттоннормал](#isbuttonnormal)|Указывает, находится ли указанная кнопка текущего элемента управления страничного `normal` навигатора в состоянии.|
|[CPagerCtrl:: Рекалксизе](#recalcsize)|Заставляет текущий элемент управления страничного навигатора повторно вычислить размер автономного окна.|
|[CPagerCtrl:: Сетбкколор](#setbkcolor)|Задает цвет фона для текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Сетбордер](#setborder)|Задает размер границы для текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Сетбуттонсизе](#setbuttonsize)|Задает размер кнопки для текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Сетчилд](#setchild)|Задает автономное окно для текущего элемента управления страничного навигатора.|
|[CPagerCtrl:: Сетскроллпос](#setscrollpos)|Задает расположение прокрутки для текущего элемента управления страничного навигатора.|

## <a name="remarks"></a>Примечания

Элемент управления страничного навигатора — это окно, которое содержит другое окно, которое является линейным и большим, чем содержащее его окно, и позволяет прокручивать содержимое окна на представление. В элементе управления страничного навигатора отображаются две кнопки прокрутки, которые автоматически исчезают, когда вложенное окно прокручивается до самого дальнего экстента, и в противном случае снова появляется. Можно создать элемент управления страничный навигатор, который прокручивается горизонтально или вертикально.

Например, если приложение имеет недостаточную для отображения элементов панель инструментов, ее можно назначить элементу управления страничного навигатора, и пользователи смогут прокручивать панель инструментов влево или вправо для доступа ко всем элементам. В Microsoft Internet Explorer версии 4,0 (коммктрл. dll версии 4,71) представлен элемент управления страничного навигатора.

Класс является производным от класса [CWnd.](../../mfc/reference/cwnd-class.md) `CPagerCtrl` Дополнительные сведения и иллюстрация элемента управления страничного навигатора см. в разделе [элементы управления страничного](/windows/win32/Controls/pager-controls)навигатора.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="cpagerctrl"></a>CPagerCtrl:: CPagerCtrl

Создает объект `CPagerCtrl`.

```
CPagerCtrl();
```

### <a name="remarks"></a>Примечания

Используйте метод [CPagerCtrl:: Create](#create) или [CPagerCtrl:: креатикс](#createex) , чтобы создать элемент управления страничного навигатора и присоединить `CPagerCtrl` его к объекту.

##  <a name="create"></a>CPagerCtrl:: Create

Создает элемент управления страничный навигатор с указанными стилями и прикрепляет `CPagerCtrl` его к текущему объекту.

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
|*двстиле*|окне Побитовое сочетание (или) [стилей окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стилей элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles) , применяемых к элементу управления.|
|*rect*|окне Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая содержит расположение и размер элемента управления в координатах клиента.|
|*ппарентвнд*|окне Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления. Этот параметр не может иметь значение NULL.|
|*nID*|окне Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Чтобы создать элемент управления страничного навигатора, `CPagerCtrl` объявите переменную, а затем вызовите метод [CPagerCtrl:: Create](#create) или [CPagerCtrl:: креатикс](#createex) для этой переменной.

### <a name="example"></a>Пример

В следующем примере создается элемент управления страничного навигатора, а затем используется метод [CPagerCtrl:: сетчилд](#setchild) , чтобы связать очень длинный элемент управления "Кнопка" с элементом управления страничного навигатора. Затем в примере используется метод [CPagerCtrl:: сетбуттонсизе](#setbuttonsize) для задания высоты элемента управления страничного навигатора равным 20 точкам, а метод [CPagerCtrl:: сетбордер](#setborder) задает толщину границы 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="createex"></a>CPagerCtrl:: Креатикс

Создает элемент управления страничного навигатора с указанными расширенными стилями и прикрепляет его к текущему `CPagerCtrl` объекту.

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
|*двексстиле*|окне Побитовое сочетание расширенных стилей, применяемых к элементу управления. Дополнительные сведения см. в описании параметра *двексстиле* функции [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) .|
|*двстиле*|окне Побитовое сочетание (или) [стилей окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стилей элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles) , применяемых к элементу управления.|
|*rect*|окне Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая содержит расположение и размер элемента управления в координатах клиента.|
|*ппарентвнд*|окне Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления. Этот параметр не может иметь значение NULL.|
|*nID*|окне Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Чтобы создать элемент управления страничного навигатора, `CPagerCtrl` объявите переменную, а затем вызовите метод [CPagerCtrl:: Create](#create) или [CPagerCtrl:: креатикс](#createex) для этой переменной.

##  <a name="forwardmouse"></a>CPagerCtrl:: Форвардмаусе

Включает или отключает перенаправление сообщений [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) в окно, содержащееся в текущем элементе управления страничного навигатора.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*бфорвард*|окне Значение TRUE, чтобы переслать сообщения мыши, или FALSE, чтобы не пересылать сообщения мыши.|

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse) , описанное в Windows SDK.

##  <a name="getborder"></a>CPagerCtrl:: награница

Возвращает размер границы текущего элемента управления страничного навигатора.

```
int GetBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий размер границы, измеряемый в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBORDER](/windows/win32/Controls/pgm-getborder) , описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере метод [CPagerCtrl:: «border](#getborder) » используется для получения толщины границы элемента управления страничного навигатора.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

##  <a name="getbkcolor"></a>CPagerCtrl:: Жетбкколор

Возвращает цвет фона текущего элемента управления страничного навигатора.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , содержащее текущий цвет фона элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor) , описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере метод [CPagerCtrl:: сетбкколор](#setbkcolor) используется для установки красного цвета фона элемента управления страничного навигатора, а метод [CPagerCtrl:: жетбкколор](#getbkcolor) — для подтверждения внесенного изменения.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="getbuttonsize"></a>CPagerCtrl:: Жетбуттонсизе

Получает размер кнопки текущего элемента управления страничного навигатора.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер текущей кнопки, измеряемый в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize) , описанное в Windows SDK.

Если элемент управления страничного навигатора имеет стиль PGS_HORZ, размер кнопки определяет ширину кнопок страничного навигатора, а если элемент управления страничного навигатора имеет стиль PGS_VERT, размер кнопки определяет высоту кнопок страничного навигатора. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).

##  <a name="getbuttonstate"></a>CPagerCtrl:: Жетбуттонстате

Получает состояние указанной кнопки прокрутки в текущем элементе управления страничного навигатора.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Состояние кнопки, заданной параметром *ибуттон* . Состояние имеет значение PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED или PGF_HOT. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK.

##  <a name="getdroptarget"></a>CPagerCtrl:: Жетдроптаржет

Извлекает интерфейс [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) для текущего элемента управления страничного навигатора.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IDropTarget` интерфейс для текущего элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

`IDropTarget`— один из интерфейсов, которые реализуются для поддержки операций перетаскивания в приложении.

Этот метод отправляет сообщение [PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget) , описанное в Windows SDK. Вызывающий этот метод отвечает за вызов `Release` члена интерфейса [интерфейс IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) , когда интерфейс больше не нужен.

##  <a name="getscrollpos"></a>CPagerCtrl:: Жетскроллпос

Возвращает расположение прокрутки текущего элемента управления страничного навигатора.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая положенная прокрутка, измеряемая в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETPOS](/windows/win32/Controls/pgm-getpos) , описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере метод [CPagerCtrl:: жетскроллпос](#getscrollpos) используется для получения текущей позицией прокрутки элемента управления страничного навигатора. Если элемент управления страничного навигатора еще не прокручивается до нуля, то в самой левой позиции в примере используется метод [CPagerCtrl:: сетскроллпос](#setscrollpos) , чтобы установить нулевое значение позиции прокрутки.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

##  <a name="isbuttondepressed"></a>CPagerCtrl:: Исбуттондепрессед

Указывает, находится ли заданная кнопка прокрутки текущего элемента управления страничного навигатора в состоянии нажатия.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанная кнопка находится в состоянии нажатия; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK. Затем проверяется, является ли возвращаемое состояние PGF_DEPRESSED. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

##  <a name="isbuttongrayed"></a>CPagerCtrl:: Исбуттонграйед

Указывает, находится ли заданная кнопка прокрутки текущего элемента управления страничного навигатора в неактивном состоянии.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанная кнопка находится в неактивном состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK. Затем проверяется, является ли возвращаемое состояние PGF_GRAYED. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

##  <a name="isbuttonhot"></a>CPagerCtrl:: Исбуттонхот

Указывает, находится ли заданная кнопка прокрутки текущего элемента управления страничного навигатора в активном состоянии.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанная кнопка находится в активном состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK. Затем проверяется, является ли возвращаемое состояние PGF_HOT. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

##  <a name="isbuttoninvisible"></a>CPagerCtrl:: Исбуттонинвисибле

Указывает, находится ли указанная кнопка прокрутки текущего элемента управления страничного навигатора в невидимом состоянии.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанная кнопка находится в невидимом состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Windows делает кнопку прокрутки в определенном направлении невидимой, когда вложенное окно прокручивается до самого крайнего экстента, так как нажатие кнопки больше не может привести к представлению большего количества вложенного окна.

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK. Затем проверяется, является ли возвращаемое состояние PGF_INVISIBLE. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

### <a name="example"></a>Пример

В следующем примере используется метод [CPagerCtrl:: исбуттонинвисибле](#isbuttoninvisible) , чтобы определить, видимы ли кнопки прокрутки влево и вправо.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

##  <a name="isbuttonnormal"></a>CPagerCtrl:: Исбуттоннормал

Указывает, находится ли заданная кнопка прокрутки текущего элемента управления страничного навигатора в нормальном состоянии.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттон*|окне Указывает кнопку, для которой извлекается состояние. Если стиль элемента управления страничного навигатора имеет значение PGS_HORZ, укажите PGB_TOPORLEFT для левой кнопки и PGB_BOTTOMORRIGHT для правой кнопки. Если стиль элемента управления страничного навигатора имеет значение PGS_VERT, укажите PGB_TOPORLEFT для верхней кнопки и PGB_BOTTOMORRIGHT для нижней кнопки. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанная кнопка находится в нормальном состоянии; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) , описанное в Windows SDK. Затем проверяется, является ли возвращаемое состояние PGF_NORMAL. Дополнительные сведения см. в разделе возвращаемое значение сообщения [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) .

##  <a name="recalcsize"></a>CPagerCtrl:: Рекалксизе

Заставляет текущий элемент управления страничного навигатора повторно вычислить размер автономного окна.

```
void RecalcSize();
```

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize) , описанное в Windows SDK. Следовательно, элемент управления страничного навигатора отправляет уведомление [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) для получения прокручиваемых измерений в автономном окне.

### <a name="example"></a>Пример

В следующем примере метод [CPagerCtrl:: рекалксизе](#recalcsize) используется для запроса текущего элемента управления страничного навигатора для повторного вычисления его размера.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Пример

В следующем примере [отражение сообщения](../../mfc/tn062-message-reflection-for-windows-controls.md) используется для того, чтобы разрешить элементу управления страничного навигатора повторно вычислить свой собственный размер, а не требовать от родительского диалогового окна элемента управления выполнять вычисление. Пример является производным `MyPagerCtrl` от [класса CPagerCtrl](../../mfc/reference/cpagerctrl-class.md), а затем использует схему сообщений для связи уведомления [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) с `OnCalcsize` обработчиком уведомлений. В этом примере обработчик уведомлений устанавливает для ширины и высоты элемента управления страничного навигатора фиксированные значения.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

##  <a name="setbkcolor"></a>CPagerCtrl:: Сетбкколор

Задает цвет фона для текущего элемента управления страничного навигатора.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*клрбк*|окне Значение [COLORREF](/windows/win32/gdi/colorref) , содержащее новый цвет фона элемента управления страничного навигатора.|

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , содержащее предыдущий цвет фона элемента управления страничного навигатора.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor) , описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере метод [CPagerCtrl:: сетбкколор](#setbkcolor) используется для установки красного цвета фона элемента управления страничного навигатора, а метод [CPagerCtrl:: жетбкколор](#getbkcolor) — для подтверждения внесенного изменения.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="setborder"></a>CPagerCtrl:: Сетбордер

Задает размер границы для текущего элемента управления страничного навигатора.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибордер*|окне Новый размер границы, измеряемый в пикселях. Если параметр *ибордер* имеет отрицательное значение, то размер границы устанавливается равным нулю.|

### <a name="return-value"></a>Возвращаемое значение

Размер предыдущей границы, измеряемый в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_SETBORDER](/windows/win32/Controls/pgm-setborder) , описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере создается элемент управления страничного навигатора, а затем используется метод [CPagerCtrl:: сетчилд](#setchild) , чтобы связать очень длинный элемент управления "Кнопка" с элементом управления страничного навигатора. Затем в примере используется метод [CPagerCtrl:: сетбуттонсизе](#setbuttonsize) для задания высоты элемента управления страничного навигатора равным 20 точкам, а метод [CPagerCtrl:: сетбордер](#setborder) задает толщину границы 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setbuttonsize"></a>CPagerCtrl:: Сетбуттонсизе

Задает размер кнопки для текущего элемента управления страничного навигатора.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ибуттонсизе*|окне Новый размер кнопки, измеряемый в пикселях.|

### <a name="return-value"></a>Возвращаемое значение

Размер предыдущей кнопки, измеряемый в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos) , описанное в Windows SDK.

Если элемент управления страничного навигатора имеет стиль PGS_HORZ, размер кнопки определяет ширину кнопок страничного навигатора, а если элемент управления страничного навигатора имеет стиль PGS_VERT, размер кнопки определяет высоту кнопок страничного навигатора. Размер кнопки по умолчанию составляет три четверти ширины полосы прокрутки, а минимальный размер кнопки — 12 пикселей. Дополнительные сведения см. в разделе [стили элементов управления страничного навигатора](/windows/win32/Controls/pager-control-styles).

### <a name="example"></a>Пример

В следующем примере создается элемент управления страничного навигатора, а затем используется метод [CPagerCtrl:: сетчилд](#setchild) , чтобы связать очень длинный элемент управления "Кнопка" с элементом управления страничного навигатора. Затем в примере используется метод [CPagerCtrl:: сетбуттонсизе](#setbuttonsize) для задания высоты элемента управления страничного навигатора равным 20 точкам, а метод [CPagerCtrl:: сетбордер](#setborder) задает толщину границы 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setchild"></a>CPagerCtrl:: Сетчилд

Задает автономное окно для текущего элемента управления страничного навигатора.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*хвндчилд*|окне Обработчик для содержащегося в нем окна.|

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_SETCHILD](/windows/win32/Controls/pgm-setchild) , описанное в Windows SDK.

Этот метод не изменяет родительский объект автономного окна. Он назначает только обработчику окна страничного навигатора для прокрутки. В большинстве случаев вложенное окно будет дочерним окном элемента управления страничного навигатора.

### <a name="example"></a>Пример

В следующем примере создается элемент управления страничного навигатора, а затем используется метод [CPagerCtrl:: сетчилд](#setchild) , чтобы связать очень длинный элемент управления "Кнопка" с элементом управления страничного навигатора. Затем в примере используется метод [CPagerCtrl:: сетбуттонсизе](#setbuttonsize) для задания высоты элемента управления страничного навигатора равным 20 точкам, а метод [CPagerCtrl:: сетбордер](#setborder) задает толщину границы 1 пиксель.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setscrollpos"></a>CPagerCtrl:: Сетскроллпос

Задает расположение прокрутки для текущего элемента управления страничного навигатора.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ипос*|окне Новая точка прокрутки, измеряемая в пикселях.|

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение [PGM_SETPOS](/windows/win32/Controls/pgm-setpos) , описанное в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CPagerCtrl](../../mfc/reference/cpagerctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Элементы управления страничного навигатора](/windows/win32/Controls/pager-controls)
