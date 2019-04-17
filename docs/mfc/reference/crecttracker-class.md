---
title: CRectTracker-класс
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 9c54cdfecfa6c4ff0eef7e16003ab2097553953d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775690"
---
# <a name="crecttracker-class"></a>CRectTracker-класс

Позволяет элементу отображается, перемещать и изменении размера различными способами.

## <a name="syntax"></a>Синтаксис

```
class CRectTracker
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|Создает объект `CRectTracker`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CRectTracker::AdjustRect](#adjustrect)|Вызывается, когда изменяются размеры прямоугольника.|
|[CRectTracker::Draw](#draw)|Отрисовывает прямоугольник.|
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Вызывается при рисовании границы `CRectTracker` объекта.|
|[CRectTracker::GetHandleMask](#gethandlemask)|Вызывается для получения маска `CRectTracker` маркеры изменения размера элемента.|
|[CRectTracker::GetTrueRect](#gettruerect)|Возвращает ширину и высоту прямоугольника, включая маркеры изменения размера.|
|[CRectTracker::HitTest](#hittest)|Возвращает текущее положение курсора, связанные с `CRectTracker` объекта.|
|[CRectTracker::NormalizeHit](#normalizehit)|Нормализует код проверки нажатия.|
|[CRectTracker::OnChangedRect](#onchangedrect)|Вызывается, когда после изменения размера или перемещения прямоугольника.|
|[CRectTracker::SetCursor](#setcursor)|Задает курсор, в зависимости от его положение над прямоугольника.|
|[CRectTracker::Track](#track)|Позволяет пользователю управлять прямоугольника.|
|[CRectTracker::TrackRubberBand](#trackrubberband)|Позволяет выбрать пользователю «изменяемый».|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Определяет размер маркеров изменения размера.|
|[CRectTracker::m_nStyle](#m_nstyle)|Текущий style(s) средства отслеживания.|
|[CRectTracker::m_rect](#m_rect)|Текущая позиция (в пикселях) прямоугольника.|
|[CRectTracker::m_sizeMin](#m_sizemin)|Определяет минимальный прямоугольник шириной и высотой.|

## <a name="remarks"></a>Примечания

`CRectTracker` не имеет базового класса.

Несмотря на то что `CRectTracker` класс позволяет пользователю взаимодействовать с элементами OLE с помощью графического интерфейса, его использование не ограничено для приложений с поддержкой OLE. Он может использоваться в любом необходим такой пользовательский интерфейс.

`CRectTracker` может быть сплошной или пунктирными линиями. Элемент может быть учитывая штриховой границей или накладывается заштрихованный шаблон для указания различных состояний элемента. Можно разместить восемь маркеров изменения размера на внешней или внутренней границы элемента. (Объяснение маркеры изменения размера, см. в разделе [GetHandleMask](#gethandlemask).) Наконец `CRectTracker` позволяет изменение ориентации элемента при изменении размера.

Чтобы использовать `CRectTracker`, создания `CRectTracker` и укажите, какие состояния отображения инициализируются. Затем этот интерфейс можно использовать для предоставления пользователю визуальную обратную связь от текущего состояния объекта OLE, связанный с `CRectTracker` объекта.

Дополнительные сведения об использовании `CRectTracker`, см. в статье [Трекеры](../../mfc/trackers.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CRectTracker`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="adjustrect"></a>  CRectTracker::AdjustRect

Вызывается платформой при изменении размеров прямоугольника отслеживания с помощью маркера изменения размера.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*nHandle*<br/>
Дескриптор, используемый индекс.

*lpRect*<br/>
Указатель на текущий размер прямоугольника. (Размер прямоугольника определяется его высоту и ширину.)

### <a name="remarks"></a>Примечания

По умолчанию эта функция позволяет ориентации прямоугольника изменить только тогда, когда `Track` и `TrackRubberBand` вызываются с Инверсия разрешено.

Переопределите эту функцию для управления коррекции прямоугольника отслеживания во время операции перетаскивания. Первый способ — настроить координатами, заданными *lpRect* перед возвратом.

Специальные возможности, которые не поддерживаются непосредственно `CRectTracker`, такие как привязки к сетке или сохранять--пропорции, можно реализовать путем переопределения этой функции.

##  <a name="crecttracker"></a>  CRectTracker::CRectTracker

Создает и инициализирует `CRectTracker` объекта.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*lpSrcRect*<br/>
Координаты объекта прямоугольника.

*nStyle*<br/>
Задает стиль `CRectTracker` объекта. Поддерживаются следующие стили:

- `CRectTracker::solidLine` Используйте сплошной линии для границы прямоугольника.

- `CRectTracker::dottedLine` Используйте пунктирной линии для границы прямоугольника.

- `CRectTracker::hatchedBorder` Используйте заштрихованный шаблон для границы прямоугольника.

- `CRectTracker::resizeInside` Маркеры, расположенные внутри прямоугольника изменения размера.

- `CRectTracker::resizeOutside` Маркеры, расположенные за пределами прямоугольника изменения размера.

- `CRectTracker::hatchInside` Hatched шаблон охватывает весь прямоугольник.

### <a name="remarks"></a>Примечания

Инициализирует конструктор по умолчанию `CRectTracker` объекта значениями из *lpSrcRect* и инициализирует других размеров параметры системы по умолчанию. Если объект создается без параметров `m_rect` и `m_nStyle` данные-члены не инициализированы.

##  <a name="draw"></a>  CRectTracker::Draw

Эта функция используется для рисования внешней линии и внутренняя область прямоугольника.

```
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, на котором выполняется отрисовка.

### <a name="remarks"></a>Примечания

Стиль объекта отслеживания определяет, как выполняется рисование. См. в разделе конструктор `CRectTracker` Дополнительные сведения о доступных стили.

##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect

Вызывается платформой при каждом изменении позиции объекта отслеживания while внутри `Track` или `TrackRubberBand` функция-член.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указатель на `RECT` , содержащий прямоугольника для рисования.

*pWndClipTo*<br/>
Указатель на окно для использования в прямоугольник обрезки.

*pDC*<br/>
Указатель на контекст устройства, на котором выполняется отрисовка.

*pWnd*<br/>
Указатель на окно, на котором будет выполняться рисование.

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает метод `CDC::DrawFocusRect`, который рисует пунктирный прямоугольник.

Переопределите эту функцию для предоставления различных отзывов во время операции отслеживания.

##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask

Платформа вызывает эту функцию-член для извлечения маски для прямоугольника маркеры изменения размера.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маска `CRectTracker` маркеры изменения размера элемента.

### <a name="remarks"></a>Примечания

Маркеры изменения размера появляются на сторонах углов прямоугольника и разрешить пользователю контролировать форму и размер прямоугольника.

Прямоугольник имеет 8 маркеров изменения размера с номерами от 0 до 7. Каждый маркер изменения размера представленный бита в маске; значение бита равно 2 ^ *n*, где *n* — номер маркер изменения размера. Биты 0-3 соответствуют угловые маркеры изменения размера, начиная с верхней левой перемещение по часовой стрелке. Бит 4 – 7 соответствуют на стороне изменить размер маркеров, начиная сверху перемещение по часовой стрелке. На следующем рисунке показано маркеры изменения размера прямоугольника и соответствующие им изменения размера дескриптор числа и значения:

![Количества маркеров изменения размера](../../mfc/reference/media/vc35dp1.gif "числа маркера изменения размера")

Реализация по умолчанию `GetHandleMask` возвращает маске биты, чтобы появились маркеры изменения размера. Если один бит включен, будет отображен соответствующий маркер изменения размера.

Переопределите эту функцию-член, чтобы скрыть или отобразить указанный маркеры изменения размера.

##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect

Вызывайте эту функцию для извлечения координат прямоугольника.

```
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Параметры

*lpTrueRect*<br/>
Указатель на `RECT` координаты структуры, которая будет содержать устройство `CRectTracker` объекта.

### <a name="remarks"></a>Примечания

Размеры прямоугольника включают высоту и ширину любые маркеры изменения размера, расположенных на внешней границы. При возвращении, *lpTrueRect* всегда представляет собой нормализованное прямоугольник в координатах устройства.

##  <a name="hittest"></a>  CRectTracker::HitTest

Вызывайте эту функцию, чтобы узнать, является ли пользователь взял маркер изменения размера.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Параметры

*point*<br/>
Точка, в координатах устройства, для тестирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение зависит от перечисляемым типом `CRectTracker::TrackerHit` и может иметь одно из следующих значений:

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 1

- `CRectTracker::hitBottomRight` 2

- `CRectTracker::hitBottomLeft` 3

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` 5

- `CRectTracker::hitBottom` 6

- `CRectTracker::hitLeft` 7

- `CRectTracker::hitMiddle` 8

##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize

Размер в пикселях от `CRectTracker` маркеры изменения размера.

```
int m_nHandleSize;
```

### <a name="remarks"></a>Примечания

Инициализировать с помощью системы по умолчанию.

##  <a name="m_rect"></a>  CRectTracker::m_rect

Текущая позиция прямоугольника в координатах клиентской области окна (в пикселях).

```
CRect m_rect;
```

##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin

Минимальный размер прямоугольника.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Примечания

Оба значения по умолчанию `cx` и `cy`, вычисляются на основе системы по умолчанию для ширины границы. Этот элемент данных будет использоваться только службами `AdjustRect` функция-член.

##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle

Текущий стиль прямоугольника.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Примечания

См. в разделе [CRectTracker::CRectTracker](#crecttracker) список возможных стилей.

##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit

Вызывайте эту функцию, чтобы преобразовать потенциально инвертированный дескриптор.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Параметры

*nHandle*<br/>
Дескриптор, выбранного пользователем.

### <a name="return-value"></a>Возвращаемое значение

Индекс дескриптора, нормализованный.

### <a name="remarks"></a>Примечания

Когда `CRectTracker::Track` или `CRectTracker::TrackRubberBand` вызывается с Инверсия разрешено, это возможно для прямоугольника следует Инвертировать на оси x и оси y. В этом случае `HitTest` будет возвращать маркеры, которые также инвертированы по отношению к прямоугольника. Это не подходит для рисования курсоров, поскольку отзывов зависит от координаты положения прямоугольника, а не часть структуре данных прямоугольник, который будет изменен.

##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect

Вызывается платформой, каждый раз, когда средство отслеживания прямоугольник был изменен во время вызова `Track`.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Параметры

*rectOld*<br/>
Содержит старый координаты устройства `CRectTracker` объекта.

### <a name="remarks"></a>Примечания

Во время вызова этой функции, все отзывы, нарисованных при помощи `DrawTrackerRect` был удален. Реализация по умолчанию этой функции не выполняет никаких действий.

Переопределите эту функцию, если вы хотите выполнять любые действия, после изменения размера прямоугольника.

##  <a name="setcursor"></a>  CRectTracker::SetCursor

Вызывайте эту функцию, чтобы изменить форму курсора, когда оно находится над `CRectTracker` объекта области.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, которое в данный момент находится курсор.

*nHitTest*<br/>
Результаты предыдущей проверки нажатия, из WM_SETCURSOR сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если предыдущее соответствие по прямоугольником tracker. в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию из внутри функции окна, который обрабатывает сообщение WM_SETCURSOR (обычно `OnSetCursor`).

##  <a name="track"></a>  CRectTracker::Track

Вызывайте эту функцию для отображения пользовательского интерфейса для изменения размеров прямоугольника.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащей прямоугольник.

*point*<br/>
Координаты устройства текущее положение указателя мыши относительно клиентской области.

*bAllowInvert*<br/>
Значение TRUE, если прямоугольник могут быть инвертированы вдоль оси x или y; в противном случае — значение FALSE.

*pWndClipTo*<br/>
Окно, операций рисования будет обрезана. Если значение равно NULL, *pWnd* используется в качестве прямоугольник отсечения.

### <a name="return-value"></a>Возвращаемое значение

Если нажата клавиша ESC, процесс отслеживания будет прерван, прямоугольник, хранящихся в средство отслеживания не изменяется и возвращается значение 0. При фиксации изменений, переместив указатель мыши и отпустить кнопку мыши, новая позиция и размер записывается в средство отслеживания прямоугольник и возвращается ненулевое значение.

### <a name="remarks"></a>Примечания

Это обычно вызываются из тела функции приложения, которое обрабатывает `WM_LBUTTONDOWN` сообщение (обычно `OnLButtonDown`).

Эта функция будет захвата мыши, пока пользователь отпускает левую кнопку мыши, нажимает клавишу ESC или нажимает правую кнопку мыши. Когда пользователь перемещает указатель мыши, отзыв обновляется путем вызова `DrawTrackerRect` и `OnChangedRect`.

Если *bAllowInvert* имеет значение TRUE, прямоугольник отслеживания могут быть инвертированы по оси x или оси y.

##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand

Вызывайте эту функцию, чтобы сделать выбор эластичного.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащей прямоугольник.

*point*<br/>
Координаты устройства текущее положение указателя мыши относительно клиентской области.

*bAllowInvert*<br/>
Значение TRUE, если прямоугольник могут быть инвертированы вдоль оси x или y; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если мышь перемещена и прямоугольник не является пустой; в противном случае 0.

### <a name="remarks"></a>Примечания

Обычно он вызывается из внутри функции приложения, которое обрабатывает сообщение WM_LBUTTONDOWN (обычно `OnLButtonDown`).

Эта функция будет захвата мыши, пока пользователь отпускает левую кнопку мыши, нажимает клавишу ESC или нажимает правую кнопку мыши. Когда пользователь перемещает указатель мыши, отзыв обновляется путем вызова `DrawTrackerRect` и `OnChangedRect`.

Отслеживание выполняется с набором резиновый внешнего типа из дескриптора нижний правый. Если разрешено обращение, прямоугольник можно изменять, перетаскивая либо вверх и влево или вниз и вправо.

## <a name="see-also"></a>См. также

[Пример MFC TRACKER](../../overview/visual-cpp-samples.md)<br/>
[Пример MFC ФУНКЦИЙ](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleResizeBar](../../mfc/reference/coleresizebar-class.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)
