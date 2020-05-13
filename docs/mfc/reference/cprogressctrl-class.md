---
title: Класс CProgressCtrl
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: c9e94e334318b32efcf8c9de681a78349ab12151
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751135"
---
# <a name="cprogressctrl-class"></a>Класс CProgressCtrl

Предоставляет функциональные возможности стандартного элемента управления "индикатор выполнения" Windows.

## <a name="syntax"></a>Синтаксис

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Формирует объект `CProgressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CProgressCtrl::Создание](#create)|Создает элемент управления панели прогресса и `CProgressCtrl` прикрепляет его к объекту.|
|[CProgressCtrl::CreateEx](#createex)|Создает элемент управления прогрессом с указанными расширенными `CProgressCtrl` стилями Windows и прикрепляет его к объекту.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|Получает цвет панели индикатора прогресса для текущего управления баром прогресса.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Получает цвет фона текущего бара прогресса.|
|[CProgressCtrl:GetPos](#getpos)|Получает текущее положение бара прогресса.|
|[CProgressCtrl:GetRange](#getrange)|Получает нижние и верхние пределы диапазона контроля панели прогресса.|
|[CProgressCtrl::GetState](#getstate)|Получает состояние текущего управления панели прогресса.|
|[CProgressCtrl:GetStep](#getstep)|Извлекает шаг приращения для панели прогресса текущего элемента управления панели прогресса.|
|[CProgressCtrl::OffsetPos](#offsetpos)|Продвигает текущее положение управления панели прогресса за счет указанного приращения и перерисовывает планку, чтобы отразить новое положение.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|Устанавливает цвет панели индикатора прогресса в текущем элементе управления панели прогресса.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|Устанавливает цвет фона для панели прогресса.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Включает режим шатра или выключается для текущего управления баром прогресса.|
|[CProgressCtrl:SetPos](#setpos)|Устанавливает текущее положение для управления панелью прогресса и перерисовывает панель, чтобы отразить новое положение.|
|[CProgressCtrl:SetRange](#setrange)|Устанавливает минимальные и максимальные диапазоны для управления панелью прогресса и перерисовывает планку, чтобы отразить новые диапазоны.|
|[CProgressCtrl::SetState](#setstate)|Задает состояние текущего элемента управления "Индикатор выполнения".|
|[CProgressCtrl::SetStep](#setstep)|Определяет шаг приращения для контроля панели прогресса.|
|[CProgressCtrl::StepIt](#stepit)|Продвигает текущее положение для управления панелью прогресса шагом (см. [SetStep)](#setstep)и перерисовывает планку, чтобы отразить новое положение.|

## <a name="remarks"></a>Remarks

Управление панелью прогресса — это окно, которое приложение может использовать для указания хода длительной операции. Он состоит из прямоугольника, который постепенно заполняется, слева направо, с системой выделить цвет, как операция прогрессирует.

Контроль панели прогресса имеет диапазон и текущее положение. Диапазон представляет общую продолжительность операции, а текущее положение представляет прогресс, достигнутый приложением к завершению операции. Процедура окна использует диапазон и текущее положение для определения процента панели прогресса для заполнения цветом выделения. Поскольку значения диапазона и текущих значений положения выражены в виде подписанных рядов, возможный диапазон текущих значений позиции составляет от -2 147 483 648 до 2 147 483 647 включительно.

Для получения дополнительной `CProgressCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CProgressCtrl](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl

Формирует объект `CProgressCtrl`.

```
CProgressCtrl();
```

### <a name="remarks"></a>Remarks

После построения `CProgressCtrl` объекта `CProgressCtrl::Create` вызов для создания элемента управления панели прогресса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a>CProgressCtrl::Создание

Создает элемент управления панели прогресса и `CProgressCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления панелью прогресса. Примените к элементу управления любую комбинацию стилей окон, описанных в [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK, в дополнение к следующим стилям управления панелью прогресса:

- PBS_VERTICAL отображает информацию о ходе работы вертикально, сверху вниз. Без этого флага панель прогресса отображается горизонтально, слева направо.

- PBS_SMOOTH отображает постепенное, плавное заполнение контроля панели прогресса. Без этого флага элемент управления будет заполняться блоками.

*rect*<br/>
Определяет размер и положение панели прогресса. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect) Поскольку элемент управления должен быть окном ребенка, указанные координаты относительно области клиента *pParentWnd.*

*pParentWnd*<br/>
Определяет родительское окно родительского элемента панели `CDialog`хода, обычно . Она не должна быть NULL.

*nID*<br/>
Определяет идентификатор панели прогресса.

### <a name="return-value"></a>Возвращаемое значение

TRUE, `CProgressCtrl` если объект успешно создан; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вы строите `CProgressCtrl` объект в два этапа. Сначала позвоните в конструктор, `CProgressCtrl` который создает объект, а затем вызов `Create`, который создает управление панели прогресса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a>CProgressCtrl::CreateEx

Создает элемент управления (детское окно) и `CProgressCtrl` связывает его с объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет стиль управления панелью прогресса. Примените любую комбинацию оконных стилей, описанных в [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a>CProgressCtrl::GetBarColor

Получает цвет панели индикатора прогресса для текущего управления баром прогресса.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет текущей панели прогресса, представленный как значение [COLORREF,](/windows/win32/gdi/colorref) или CLR_DEFAULT, если цвет панели индикатора прогресса является цветом по умолчанию.

### <a name="remarks"></a>Remarks

Этот метод отправляет [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) сообщение, которое описано в SDK Windows.

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a>CProgressCtrl::GetBkColor

Получает цвет фона текущего бара прогресса.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет фона текущего бара прогресса, представленный как значение [COLORREF.](/windows/win32/gdi/colorref)

### <a name="remarks"></a>Remarks

Этот метод отправляет [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) сообщение, которое описано в SDK Windows.

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a>CProgressCtrl:GetPos

Извлекает текущее положение панели прогресса.

```
int GetPos();
```

### <a name="return-value"></a>Возвращаемое значение

Положение контроля панели прогресса.

### <a name="remarks"></a>Remarks

Положение управления панелью прогресса не является физическим расположением на экране, а находится между верхним и нижним диапазоном, указанным в [SetRange.](#setrange)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a>CProgressCtrl:GetRange

Получает текущие нижние и верхние пределы или диапазон контроля панели прогресса.

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Параметры

*nLower*<br/>
Ссылка на ряд, получающий нижний предел контроля панели прогресса.

*nУппер*<br/>
Ссылка на ряд, получающий верхний предел контроля панели прогресса.

### <a name="remarks"></a>Remarks

Эта функция копирует значения нижних и верхних пределов для рядов, на которые ссылаются *nLower* и *nUpper*, соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a>CProgressCtrl::GetState

Получает состояние текущего управления панели прогресса.

```
int GetState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Состояние текущего элемента управления панели прогресса, которое является одним из следующих значений:

|Значение|Состояние|
|-----------|-----------|
|PBST_NORMAL|Выполняется|
|PBST_ERROR|Error|
|PBST_PAUSED|Пауза|

### <a name="remarks"></a>Remarks

Этот метод отправляет [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода извлекает состояние текущего элемента управления панели прогресса.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a>CProgressCtrl:GetStep

Извлекает шаг приращения для панели прогресса текущего элемента управления панели прогресса.

```
int GetStep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Шаг приращения панели прогресса.

### <a name="remarks"></a>Remarks

Шаг приращения — это сумма, на которую вызывает вызов [в CProgressCtrl::StepIt](#stepit) увеличивает текущее положение панели прогресса.

Этот метод отправляет [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода получает шаг приращение текущего элемента управления панели прогресса.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a>CProgressCtrl::OffsetPos

Продвигает текущее положение управления панели прогресса по приращению, указанному *nPos,* и перерисовывает панель, чтобы отразить новое положение.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Сумма для продвижения позиции.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция контроля панели прогресса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a>CProgressCtrl::SetBarColor

Устанавливает цвет панели индикатора прогресса в текущем элементе управления панели прогресса.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*clrBar*|(в) Значение [COLORREF,](/windows/win32/gdi/colorref) которое определяет новый цвет панели индикаторов прогресса. Укажите CLR_DEFAULT, чтобы заставить панель прогресса использовать свой цвет по умолчанию.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет панели индикатора прогресса, представленный как значение [COLORREF,](/windows/win32/gdi/colorref) или CLR_DEFAULT если цвет омрачивания панели индикатора является цветом по умолчанию.

### <a name="remarks"></a>Remarks

Метод `SetBarColor` устанавливает цвет панели прогресса только в том случае, если [тема](/windows/win32/Controls/visual-styles-overview) Windows Vista не действует.

Этот метод отправляет [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода изменяет цвет панели прогресса на красный, зеленый, синий или по умолчанию.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a>CProgressCtrl::SetBkColor

Устанавливает цвет фона для панели прогресса.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Параметры

*clrNew*<br/>
Значение COLORREF, которое определяет новый цвет фона. Укажите значение CLR_DEFAULT для использования фонового цвета по умолчанию для панели прогресса.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) с указанием предыдущего фонового цвета или CLR_DEFAULT, если цвет фона является цветом по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a>CProgressCtrl::SetMarquee

Включает режим шатра или выключается для текущего управления баром прогресса.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*fMarqueeMode*|(в) ПРАВДА включить режим шатер, или FALSE, чтобы включить режим шатер выключен.|
|*nИнтервал*|(в) Время в миллисекундах между обновлениями анимации шатера.|

### <a name="return-value"></a>Возвращаемое значение

Этот метод всегда возвращает TRUE.

### <a name="remarks"></a>Remarks

Когда режим шатер включен, прогресс бар анимирован и прокручивается, как знак на театре шатер.

Этот метод отправляет [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода запускает и останавливает анимацию прокрутки шатера.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a>CProgressCtrl:SetPos

Устанавливает текущее положение панели прогресса в том виде, в каком это указывает *nPos,* и перерисовывает панель, чтобы отразить новое положение.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Новая позиция управления панели прогресса.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция контроля панели прогресса.

### <a name="remarks"></a>Remarks

Положение управления панелью прогресса не является физическим расположением на экране, а находится между верхним и нижним диапазоном, указанным в [SetRange.](#setrange)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a>CProgressCtrl:SetRange

Устанавливает верхние и нижние пределы диапазона управления прогрессом и перерисовывает планку, чтобы отразить новые диапазоны.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Параметры

*nLower*<br/>
Определяет нижний предел диапазона (по умолчанию равен нулю).

*nУппер*<br/>
Определяет верхний предел диапазона (по умолчанию 100).

### <a name="remarks"></a>Remarks

Функция `SetRange32` члена устанавливает диапазон 32-битного диапазона для управления прогрессом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a>CProgressCtrl::SetState

Задает состояние текущего элемента управления "Индикатор выполнения".

```
int SetState(int iState);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iState*|(в) Состояние, устанавливаево планку прогресса. Используйте одно из следующих значений:<br /><br /> - PBST_NORMAL - В процессе<br />- PBST_ERROR - Ошибка<br />- PBST_PAUSED - Пауза|

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние текущего элемента управления "Индикатор выполнения".

### <a name="remarks"></a>Remarks

Этот метод отправляет [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода позволяет задать состояние текущего индикатора выполнения: "Приостановлено" или "Выполняется".

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a>CProgressCtrl::SetStep

Определяет шаг приращения для контроля панели прогресса.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Параметры

*nStep*<br/>
Новый шаг приращения.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий шаг приращения.

### <a name="remarks"></a>Remarks

Шаг приращения — это сумма, на которую вызов `CProgressCtrl::StepIt` увеличивает текущее положение панели прогресса.

Приравщение шага по умолчанию составляет 10.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a>CProgressCtrl::StepIt

Продвигает текущее положение для управления панелью прогресса шагом и перерисовывает планку, чтобы отразить новое положение.

```
int StepIt();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция контроля панели прогресса.

### <a name="remarks"></a>Remarks

Шаг приращения устанавливается функцией `CProgressCtrl::SetStep` члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
