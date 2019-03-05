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
ms.openlocfilehash: a6d5d3becfd1c1ee4a032c74eb116ede82c42bc4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260274"
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
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Создает объект `CProgressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CProgressCtrl::Create](#create)|Создает элемент управления хода выполнения и присоединяет его к `CProgressCtrl` объекта.|
|[CProgressCtrl::CreateEx](#createex)|Создает элемент управления хода выполнения с указанной расширенные стили Windows и присоединяет его к `CProgressCtrl` объекта.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|Получает цвет индикатора индикатор хода выполнения для текущего индикатора.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Получает цвет фона индикатора хода выполнения на текущем компьютере.|
|[CProgressCtrl::GetPos](#getpos)|Получает текущую позицию индикатора хода выполнения.|
|[CProgressCtrl::GetRange](#getrange)|Получает нижний и верхний пределы диапазона индикатора.|
|[CProgressCtrl::GetState](#getstate)|Получает состояние текущего индикатора.|
|[CProgressCtrl::GetStep](#getstep)|Возвращает шаг приращения индикатор хода выполнения из текущего индикатора.|
|[CProgressCtrl::OffsetPos](#offsetpos)|Перемещает текущую позицию индикатора на заданную величину и перерисовывает строке, чтобы отразить новое место.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|Задает цвет индикатора индикатор хода выполнения в текущего индикатора.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|Задает цвет фона для индикатора выполнения.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Отключает режим бегущей строки или отключить для текущего индикатора.|
|[CProgressCtrl::SetPos](#setpos)|Задает текущую позицию для управления индикатором выполнения и перерисовывает строке, чтобы отразить новое место.|
|[CProgressCtrl::SetRange](#setrange)|Задает минимальный и максимальный диапазоны для управления индикатором выполнения и перерисовывает строке, чтобы отразить новые диапазоны.|
|[CProgressCtrl::SetState](#setstate)|Задает состояние текущего элемента управления "Индикатор выполнения".|
|[CProgressCtrl::SetStep](#setstep)|Задает шаг приращения для управления индикатором выполнения.|
|[CProgressCtrl::StepIt](#stepit)|Перемещает текущую позицию для управления индикатором выполнения путем увеличения шага (см. в разделе [SetStep](#setstep)) и перерисовывает строке, чтобы отразить новое место.|

## <a name="remarks"></a>Примечания

Управления индикатором выполнения — это окно, в который приложение может использовать для отображения хода выполнения длительной операции. Он состоит из прямоугольника, который постепенно заполняется, слева, справа, в системе цвет выделения мере выполнения операции.

Индикатор выполнения имеет диапазон и текущее положение. Диапазон представляет общее время выполнения операции, а текущая позиция ход выполнения работ по завершению операции внесенные приложения. Процедура окна использует диапазон и текущее положение, чтобы определить процент индикатор хода выполнения для заливки цветом выделения. Так как диапазон и текущее положение значения выражаются в виде целых чисел со знаком, возможный диапазон из текущей позиции значений — от -2147483648 2 147 483 647 включительно.

Дополнительные сведения об использовании `CProgressCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CProgressCtrl](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl

Создает объект `CProgressCtrl`.

```
CProgressCtrl();
```

### <a name="remarks"></a>Примечания

После построения `CProgressCtrl` , вызовите `CProgressCtrl::Create` для создания индикатора.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>  CProgressCtrl::Create

Создает элемент управления хода выполнения и присоединяет его к `CProgressCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль окна хода выполнения. Применить любое сочетание stylesdescribed окно в [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) в пакете SDK для Windows, кроме следующих индикатора выполнения стили элемента управления, к элементу управления:

- PBS_VERTICAL отображает сведения о выполнении вертикально, сверху вниз. Без этого флага индикатор выполнения отображается горизонтально, слева направо.

- Отображает PBS_SMOOTH постепенного, плавное заполнение индикатора. Без этого флага элемент управления будет заполнить блоки.

*rect*<br/>
Задает размер и положение окна хода выполнения. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. Так как элемент управления должен быть дочернего окна, указанной координаты указываются относительно клиентской области *pParentWnd*.

*pParentWnd*<br/>
Указывает ход родительскому окну элемента управления, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления панель хода выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если `CProgressCtrl` объект успешно создан; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При создании `CProgressCtrl` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CProgressCtrl` объекта, а затем вызвать `Create`, который создает индикатора.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>  CProgressCtrl::CreateEx

Создает элемент управления (дочернего окна) и связывает его с `CProgressCtrl` объекта.

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
Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*dwStyle*<br/>
Задает стиль окна хода выполнения. Применить любое сочетание стилей окна, описанные в [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) в пакете Windows SDK.

*rect*<br/>
Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor

Получает цвет индикатора индикатор хода выполнения для текущего индикатора.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет текущий индикатор хода выполнения, представленное в виде [COLORREF](/windows/desktop/gdi/colorref) значение или CLR_DEFAULT, если цвет по умолчанию является цвет панели индикатор хода выполнения.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETBARCOLOR](/windows/desktop/Controls/pbm-getbarcolor) сообщения, который описан в пакете Windows SDK.

##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor

Получает цвет фона индикатора хода выполнения на текущем компьютере.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет фона текущего индикатора хода выполнения, представленное в виде [COLORREF](/windows/desktop/gdi/colorref) значение.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETBKCOLOR](/windows/desktop/Controls/pbm-getbkcolor) сообщения, который описан в пакете Windows SDK.

##  <a name="getpos"></a>  CProgressCtrl::GetPos

Извлекает текущее положение индикатора выполнения.

```
int GetPos();
```

### <a name="return-value"></a>Возвращаемое значение

Положение индикатора.

### <a name="remarks"></a>Примечания

Положение индикатора не физическое расположение на экране, но вместо между верхней и нижней диапазона указывается в [SetRange](#setrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>  CProgressCtrl::GetRange

Получает текущий нижняя и верхняя границы, то диапазон индикатора.

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Параметры

*nLower*<br/>
Ссылка на целое число, получать нижнюю границу индикатора.

*nUpper*<br/>
Ссылка на целое число, получение верхнее предельное значение индикатора.

### <a name="remarks"></a>Примечания

Эта функция копирует значения нижний и верхний пределы целых чисел, ссылается *nLower* и *nUpper*, соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>  CProgressCtrl::GetState

Получает состояние текущего индикатора.

```
int GetState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Состояние текущего индикатора, который является одним из следующих значений:

|Значение|Регион|
|-----------|-----------|
|PBST_NORMAL|Выполняется|
|PBST_ERROR|Error|
|PBST_PAUSED|Приостановлено|

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETSTATE](/windows/desktop/Controls/pbm-getstate) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода извлекает состояние текущего индикатора.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>  CProgressCtrl::GetStep

Возвращает шаг приращения индикатор хода выполнения из текущего индикатора.

```
int GetStep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Шаг увеличения индикатора хода выполнения.

### <a name="remarks"></a>Примечания

Шаг приращения, — это величина, на которую вызов [CProgressCtrl::StepIt](#stepit) увеличивает текущее положение индикатора выполнения.

Этот метод отправляет [PBM_GETSTEP](/windows/desktop/Controls/pbm-getstep) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода извлекает шаг шаг текущего индикатора.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos

Перемещает индикатор текущей позиции элемента управления приращения, заданные *nPos* и перерисовывает строке, чтобы отразить новое место.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Сумма, чтобы переместить позицию.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция заголовка индикатора.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor

Задает цвет индикатора индикатор хода выполнения в текущего индикатора.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*clrBar*|[in] Объект [COLORREF](/windows/desktop/gdi/colorref) значение, которое указывает новый цвет индикатора индикатор хода выполнения. Укажите CLR_DEFAULT заставить индикатор хода выполнения использовать цвета по умолчанию.|

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет индикатора индикатор хода выполнения, представленное в виде [COLORREF](/windows/desktop/gdi/colorref) значение или CLR_DEFAULT, если цвет по умолчанию цвет индикатора индикатор хода выполнения.

### <a name="remarks"></a>Примечания

`SetBarColor` Метод задает индикатор выполнения только если цвет Windows Vista [темы](/windows/desktop/Controls/visual-styles-overview) не действует.

Этот метод отправляет [PBM_SETBARCOLOR](/windows/desktop/Controls/pbm-setbarcolor) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода изменяется цвет индикатора хода выполнения на красный, зеленый, синий или значение по умолчанию.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor

Задает цвет фона для индикатора выполнения.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Параметры

*clrNew*<br/>
Значение COLORREF, которое указывает новый цвет фона. Укажите значение CLR_DEFAULT, используемое по умолчанию цвет фона для индикатора выполнения.

### <a name="return-value"></a>Возвращаемое значение

[COLORREF](/windows/desktop/gdi/colorref) значение, указывающее предыдущий цвет фона, то есть CLR_DEFAULT, если цвет фона цвет по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee

Отключает режим бегущей строки или отключить для текущего индикатора.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*fMarqueeMode*|[in] Значение true, чтобы включить режим бегущей строки Вкл "или" значение FALSE, чтобы отключить режим бегущей строки.|
|*nInterval*|[in] Время в миллисекундах между обновлениями анимации области выделения.|

### <a name="return-value"></a>Возвращаемое значение

Этот метод всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Когда включен режим бегущей строки, анимированный индикатор хода выполнения и прокручивает элемент управления, такие как вход на бегущую строку.

Этот метод отправляет [PBM_SETMARQUEE](/windows/desktop/Controls/pbm-setmarquee) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода запускает и останавливает бегущей строки, прокрутка анимации.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>  CProgressCtrl::SetPos

Задает сведения о ходе панели текущее положение элемента управления в соответствии с *nPos* и перерисовывает строке, чтобы отразить новое место.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Новое положение индикатора.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция заголовка индикатора.

### <a name="remarks"></a>Примечания

Положение индикатора не физическое расположение на экране, но вместо между верхней и нижней диапазона указывается в [SetRange](#setrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>  CProgressCtrl::SetRange

Задает верхний и нижний пределы индикатора выполнения элемента управления диапазона и перерисовывает строке, чтобы отразить новые диапазоны.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Параметры

*nLower*<br/>
Указывает нижний предел диапазона (по умолчанию равно нулю).

*nUpper*<br/>
Указывает верхний предел диапазона (по умолчанию — 100).

### <a name="remarks"></a>Примечания

Функция-член `SetRange32` задает 32-разрядным диапазоном для элемента управления хода выполнения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>  CProgressCtrl::SetState

Задает состояние текущего элемента управления "Индикатор выполнения".

```
int SetState(int iState);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*iState*|[in] Состояние, устанавливаемое для индикатора. Необходимо использовать одно из следующих значений.<br /><br /> -PBST_NORMAL - выполняется<br />-PBST_ERROR - ошибка<br />-PBST_PAUSED - приостановлена|

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние текущего элемента управления "Индикатор выполнения".

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_SETSTATE](/windows/desktop/Controls/pbm-setstate) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода позволяет задать состояние текущего индикатора выполнения: "Приостановлено" или "Выполняется".

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>  CProgressCtrl::SetStep

Задает шаг приращения для управления индикатором выполнения.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Параметры

*nStep*<br/>
Новый шаг приращения.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий шаг приращения.

### <a name="remarks"></a>Примечания

Шаг приращения, — это величина, на которую вызов `CProgressCtrl::StepIt` хода выполнения увеличивается строки в текущей позиции.

Шаг инкремента по умолчанию — 10.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>  CProgressCtrl::StepIt

Перемещает текущую позицию для управления индикатором выполнения шаг приращения и перерисовывает строке, чтобы отразить новое место.

```
int StepIt();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция заголовка индикатора.

### <a name="remarks"></a>Примечания

Шаг приращения задается `CProgressCtrl::SetStep` функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>См. также

[Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
