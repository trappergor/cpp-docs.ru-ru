---
title: Класс CScrollView
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: d60082092bd42fbe220eee08953ad5fda0ff0a85
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774157"
---
# <a name="cscrollview-class"></a>Класс CScrollView

Объект [CView](../../mfc/reference/cview-class.md) с возможностями прокрутки.

## <a name="syntax"></a>Синтаксис

```
class CScrollView : public CView
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|Создает объект `CScrollView`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|Указывает, имеет ли представление прокрутки горизонтальные и вертикальные полосы прокрутки.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|Заполняет область представления за пределами области прокрутки.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Получает текущую позицию прокрутки в единицах устройства.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Получает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления. Размеры, доступны в единицах устройства.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Получает текущую позицию прокрутки в логических единицах.|
|[CScrollView::GetTotalSize](#gettotalsize)|Получает общий размер представления прокрутки в логических единицах.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|В результате размер представления для диктовки размер фрейма.|
|[CScrollView::ScrollToPosition](#scrolltoposition)|Прокручивает представление на определенный момент, указанный в логических единицах.|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Помещает представление прокрутки в режиме масштабирования ширины.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Задает режим сопоставления представление прокрутки, общий размер и суммы горизонтальной и вертикальной прокрутки.|

## <a name="remarks"></a>Примечания

Можно обрабатывать прокрутка самостоятельно в любой класс, производный от стандартного `CView` путем переопределения размещенный сообщение [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) функций-членов. Но `CScrollView` добавляет следующие возможности для его `CView` возможности:

- Он управляет, размеры окна и окна просмотра и режимы сопоставления.

- Он автоматически прокручивается в ответ на сообщения полосы прокрутки.

- Он автоматически прокручивается в ответ на сообщения от клавиатуры, мыши непрокручиваемых или Поворачивайте колесико.

Чтобы автоматически перейти в ответ на сообщения с помощью клавиатуры, добавьте сообщение WM_KEYDOWN и тестирования для VK_DOWN, VK_PREV и вызов [SetScrollPos](/windows/desktop/api/winuser/nf-winuser-setscrollpos).

Колесико мыши, прокрутка самостоятельно путем переопределения размещенный сообщения можно обрабатывать [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) и [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) функций-членов. Как и для `CScrollView`, эти функции-члены поддерживают рекомендуемые поведение для [WM_MOUSEWHEEL](/windows/desktop/inputdev/wm-mousewheel), сообщением о повороте колеса.

Чтобы воспользоваться преимуществами автоматическую прокрутку, являются производными от класса представления `CScrollView` вместо из `CView`. Когда сначала создается представление, чтобы вычислить размер прокручиваемой представления, в зависимости от размера документа, вызов `SetScrollSizes` функции-члена из переопределенный либо [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) или [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Необходимо написать собственный код, чтобы запросить размер документа. Например, см. в разделе [пример Scribble](../../overview/visual-cpp-samples.md).)

Вызов `SetScrollSizes` функция-член задает режим сопоставления представления, общее размеры представления и суммы для прокрутки по горизонтали и вертикали. Все размеры, доступны в логических единицах. Логический размер представления обычно вычисляется на основе данных, хранящимся в документе, но в некоторых случаях может потребоваться указать фиксированный размер. Примеры обоих подходов, см. в разделе [CScrollView::SetScrollSizes](#setscrollsizes).

Укажите сумму для прокрутки по горизонтали и вертикали в логических единицах. По умолчанию, если пользователь нажимает кнопку стрелки панель прокрутки за пределами полосы прокрутки `CScrollView` прокручивает «страница». Если пользователь щелкает стрелку прокрутки на любом конце полосы прокрутки, `CScrollView` прокручивает «строка». По умолчанию страницы составляет 1/10, от общего размера представления; строки — 1/10 размер страницы. Переопределить значения по умолчанию, передав размеров в `SetScrollSizes` функция-член. Например можно задать размер по горизонтали для определенной части ширину общий размер и размер по вертикали, чтобы высота строки с использованием текущего шрифта.

Вместо прокрутки, `CScrollView` можно автоматически масштабировать представлении, чтобы текущий размер окна. В этом режиме, содержит представление полосы прокрутки и логического представления вытягивается или сужается точно по размеру клиентской области окна. Чтобы использовать эти возможности масштабирования ширины, вызовите [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Вызвать либо метод `SetScaleToFitSize` или `SetScrollSizes`, но не оба.)

Прежде чем `OnDraw` вызывается функция-член класса производным представлением, `CScrollView` автоматически прибавляет к дате начала координат окна просмотра для `CPaintDC` объект контекста устройства, он передает `OnDraw`.

Для настройки начала координат окна просмотра для прокрутки окна, `CScrollView` переопределяет [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Этот параметр для автоматического `CPaintDC` контекста устройства, `CScrollView` передает `OnDraw`, но необходимо вызвать `CScrollView::OnPrepareDC` самостоятельно для любые другие контексты устройств вы используете, таких как `CClientDC`. Можно переопределить `CScrollView::OnPrepareDC` задать пера, цвет фона и другие атрибуты рисования, но вызывают базовый класс для масштабирования.

В трех местах относительно представления, могут отображаться полосы прокрутки, как показано в следующих случаях.

- Стандартный стиль окна полос прокрутки можно задать для представления, используя WS_HSCROLL и WS_VSCROLL[стили Windows](../../mfc/reference/styles-used-by-mfc.md#window-styles).

- Элементы управления полосы прокрутки можно также добавить рамку, содержащую представление, в этом случае платформа перенаправляет сообщения WM_HSCROLL и WM_VSCROLL с окном фрейма к текущему активному представлению.

- Платформа также перенаправляет прокрутите сообщения от `CSplitterWnd` разделителя в область текущего активного разделителя (представления). При помещении в [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) с полосами прокрутки общего `CScrollView` объект будет использовать общий те из них, а не создавать свои собственные.

Дополнительные сведения об использовании `CScrollView`, см. в разделе [архитектуры Document/View](../../mfc/document-view-architecture.md) и [производным представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars

Вызывайте эту функцию члена, чтобы определить наличие горизонтальные и вертикальные полосы прокрутки представления.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Параметры

*bHasHorzBar*<br/>
Указывает, что приложение имеет горизонтальную полосу прокрутки.

*bHasVertBar*<br/>
Указывает, что приложение имеет вертикальную полосу прокрутки.

##  <a name="cscrollview"></a>  CScrollView::CScrollView

Создает объект `CScrollView`.

```
CScrollView();
```

### <a name="remarks"></a>Примечания

Следует вызвать `SetScrollSizes` или `SetScaleToFitSize` перед прокрутки представления можно использовать.

##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect

Вызовите `FillOutsideRect` для заполнения области, представления, появляющийся вне области прокрутки.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
Контекст устройства, в котором будет заполняться, которую требуется выполнить.

*pBrush*<br/>
Кисть, с которым должен быть заполнен области.

### <a name="remarks"></a>Примечания

Используйте `FillOutsideRect` в режиме прокрутки `OnEraseBkgnd` функция обработчика, чтобы предотвратить чрезмерное фона перерисовки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition

Вызовите `GetDeviceScrollPosition` при необходимости текущие горизонтальные и вертикальные положения прокрутки полей в полосы прокрутки.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальные и вертикальные позиций (в единицах устройства) поля прокрутки `CPoint` объекта.

### <a name="remarks"></a>Примечания

Эта пара координат соответствует расположению в документе, к которому прокрутил в левом верхнем углу представления. Это полезно для смещения позиций устройство мыши для прокрутки представления позиций устройства.

`GetDeviceScrollPosition` Возвращает значения в единицах устройства. Логические устройства, используйте `GetScrollPosition` вместо этого.

##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes` Получает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Параметры

*nMapMode*<br/>
Возвращает текущий режим сопоставления для этого представления. Список возможных значений см. в разделе `SetScrollSizes`.

*sizeTotal*<br/>
Возвращает текущий общий размер представления прокрутки в единицах устройства.

*sizePage*<br/>
Возвращает суммы текущего горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки полосы прокрутки. `cx` Член содержит горизонтальный сдвиг. `cy` Член содержит вертикальный сдвиг.

*sizeLine*<br/>
Возвращает суммы текущего горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки прокрутки. `cx` Член содержит горизонтальный сдвиг. `cy` Член содержит вертикальный сдвиг.

### <a name="remarks"></a>Примечания

Размеры, доступны в единицах устройства. Эта функция-член вызывается редко.

##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition

Вызовите `GetScrollPosition` при необходимости текущие горизонтальные и вертикальные положения прокрутки полей в полосы прокрутки.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальные и вертикальные позиций (в логических единицах) поля прокрутки `CPoint` объекта.

### <a name="remarks"></a>Примечания

Эта пара координат соответствует расположению в документе, к которому прокрутил в левом верхнем углу представления.

`GetScrollPosition` Возвращает значения в логических единицах. Единицы устройства, используйте `GetDeviceScrollPosition` вместо этого.

##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize

Вызовите `GetTotalSize` для получения текущих размерах горизонтальной и вертикальной прокрутки представления.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Общий размер представления прокрутки в логических единицах. Размер по горизонтали находится в `cx` членом `CSize` возвращаемое значение. Вертикальный размер становится в `cy` член.

##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit

Вызовите `ResizeParentToFit` для размеры представления определяют размер окном фрейма.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bShrinkOnly*<br/>
Тип изменения размера для выполнения. Значение по умолчанию — TRUE, сжимает фрейм окна, при необходимости. Полосы прокрутки по-прежнему будет отображаться для больших представлений или небольшой фреймов. Значение FALSE приводит к смещению представления всегда для того изменить размер окна фрейма, точно. Это может быть несколько опасно, так как фрейм окна удалось получить помещается внутри окна многодокументного интерфейса (MDI) кадра или экрана.

### <a name="remarks"></a>Примечания

Это рекомендуется только для представлений в кадр дочерних MDI-окон. Используйте `ResizeParentToFit` в `OnInitialUpdate` функция обработчика производного `CScrollView` класса. Пример того, эта функция-член, см. в разделе [CScrollView::SetScrollSizes](#setscrollsizes).

`ResizeParentToFit` предполагается, что размер окна представление установлена. Если размер окна представление не было задано при `ResizeParentToFit` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом `ResizeParentToFit`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition

Вызовите `ScrollToPosition` выполнить прокрутку в определенный момент в представлении.

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Точка для прокрутки, в логических единицах. `x` Член должен быть положительным (больше или равно 0, вплоть до общего размера представления). То же самое касается `y` члена, если режим сопоставления указан режим MM_TEXT. `y` Член имеет отрицательное значение в сопоставление режимах, отличных от режим MM_TEXT.

### <a name="remarks"></a>Примечания

Представление прокручивается, чтобы эта точка находится в левом верхнем углу окна. Эта функция-член не должен вызываться, если представление масштабируется по размерам.

##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize

Вызовите `SetScaleToFitSize` при необходимости автоматически масштабировать размер окна просмотра текущего размера окна.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Параметры

*sizeTotal*<br/>
Горизонтальные и вертикальные размеры, к которым это представление является масштабировать. Представление прокрутки размер измеряется в логических единицах. Размер по горизонтали, содержащийся в `cx` член. Размер по вертикали, содержащийся в `cy` член. Оба `cx` и `cy` должно быть больше или равно 0.

### <a name="remarks"></a>Примечания

С помощью полосы прокрутки только часть логического представления могут быть видны в любое время. Но с возможностью масштабирования ширины, представление имеет полосы прокрутки, а логическое представление вытягивается или сужается точно по размеру клиентской области окна. При изменении размера окна, представления рисует его данные в новый масштабе, в зависимости от размера окна.

Обычно будет размещен вызов `SetScaleToFitSize` в переопределении представления `OnInitialUpdate` функция-член. Если не требуется автоматического масштабирования, вызовите `SetScrollSizes` вместо этого функция-член.

`SetScaleToFitSize` можно использовать для реализации операции «Масштаб по размеру». Используйте `SetScrollSizes` для повторной инициализации прокрутки.

`SetScaleToFitSize` предполагается, что размер окна представление установлена. Если размер окна представление не было задано при `SetScaleToFitSize` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом `SetScaleToFitSize`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes

Вызовите `SetScrollSizes` при представлении будет обновляться.

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Параметры

*nMapMode*<br/>
Режим сопоставления, чтобы задать для этого представления. Возможные значения:

|Режим сопоставления|Логическое устройство|Расширения по оси y —...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 пиксель|Вниз|
|MM_HIMETRIC|0,01 мм|Вверх|
|MM_TWIPS|1/1440 в|Вверх|
|MM_HIENGLISH|0,001 дюйма|Вверх|
|MM_LOMETRIC|0,1 мм|Вверх|
|MM_LOENGLISH|0,01 дюйма|Вверх|

Все эти режимы определяются Windows. Два режима сопоставления стандартных MM_ISOTROPIC и MM_ANISOTROPIC, не используются для `CScrollView`. Библиотека классов предоставляет `SetScaleToFitSize` функция-член для масштабирования представления размера окна. Столбец 3 в таблице выше описывает ориентацию координат.

*sizeTotal*<br/>
Общий размер представления. `cx` Член содержит области по горизонтали. `cy` Член содержит протяженности по вертикали представления. Размеры: в логических единицах. Оба `cx` и `cy` должно быть больше или равно 0.

*sizePage*<br/>
Суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки полосы прокрутки. `cx` Член содержит горизонтальный сдвиг. `cy` Член содержит вертикальный сдвиг.

*sizeLine*<br/>
Суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки прокрутки. `cx` Член содержит горизонтальный сдвиг. `cy` Член содержит вертикальный сдвиг.

### <a name="remarks"></a>Примечания

Вызовите его в переопределении `OnUpdate` функция-член для настройки прокрутки характеристики, когда, например, изначально отображается документа или изменении размера.

Обычно будет получать сведения о размере из этого представления документа, вызвав функцию-член документа, может быть вызван `GetMyDocSize`, предоставляемого с документа производного класса. В следующем коде показано этот подход:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Кроме того иногда может потребоваться установить фиксированный размер, как показано в следующем коде:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

В любом из режимов сопоставления Windows за исключением MM_ISOTROPIC или MM_ANISOTROPIC, необходимо установить режим сопоставления. Если вы хотите использовать режим неограниченного сопоставления, вызвать `SetScaleToFitSize` функция-член вместо `SetScrollSizes`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)
