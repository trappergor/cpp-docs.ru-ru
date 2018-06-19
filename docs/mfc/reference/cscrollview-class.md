---
title: Класс CScrollView | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ffdb26c5766a0ff7cbada511c9bc9c82ebfd93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375546"
---
# <a name="cscrollview-class"></a>Класс CScrollView
Объект [CView](../../mfc/reference/cview-class.md) с возможностями прокрутки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CScrollView : public CView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollView::CScrollView](#cscrollview)|Создает объект `CScrollView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](#checkscrollbars)|Указывает, имеет ли представление прокрутки горизонтальные и вертикальные полосы прокрутки.|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|Заполняет область представления за пределами области прокрутки.|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Получает текущую позицию прокрутки в единицы устройства.|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Возвращает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления. Размеры: в единицы устройства.|  
|[CScrollView::GetScrollPosition](#getscrollposition)|Получает текущую позицию прокрутки в логических единицах.|  
|[CScrollView::GetTotalSize](#gettotalsize)|Возвращает общий размер представления прокрутки в логических единицах.|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|В результате размер представления для диктовки размер фрейма.|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|Прокручивает представление до определенного момента, указанного в логических единицах.|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Помещает представление прокрутки в режиме масштабирования ширины.|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|Задает режим сопоставления представлений прокрутки, общий размер и суммы вертикальной и горизонтальной прокрутки.|  
  
## <a name="remarks"></a>Примечания  
 Можно обработать стандартный прокрутки самостоятельно в класс, производный от `CView` путем переопределения сообщения сопоставлены [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) функции-члены. Но `CScrollView` добавляет следующие возможности для его `CView` возможности:  
  
-   Он управляет размеры окна и окна просмотра и режимы сопоставления.  
  
-   Он автоматически прокручивается в ответ на сообщения полосы прокрутки.  
  
-   Он автоматически прокручивается в ответ на сообщения с клавиатуры, мыши непрокручиваемых или Поворачивайте колесико мыши.  
  
 Чтобы автоматически перейти в ответ на сообщения с помощью клавиатуры, добавить сообщение WM_KEYDOWN и тестирования для VK_DOWN, VK_PREV и вызова [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Можно обработать прокрутки самостоятельно путем переопределения сопоставить сообщение колесика мыши [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) и [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) функции-члены. Как и для `CScrollView`, эти функции-члены поддерживают рекомендуемые поведения при [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), сообщение поворота колесика.  
  
 Чтобы воспользоваться преимуществами автоматическая прокрутка, являются производными класса представления из `CScrollView` вместо из `CView`. При представлении сначала создается, если требуется вычислить размер прокручиваемой представления, исходя из размера документа, вызов `SetScrollSizes` функции-члена из переопределенный либо [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) или [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Необходимо написать собственный код, чтобы запросить размер документа. Пример см. в разделе [пример Scribble](../../visual-cpp-samples.md).)  
  
 Вызов `SetScrollSizes` функция-член устанавливает режим представления сопоставления, размеры общее представление прокрутки и суммы для прокрутки по горизонтали и вертикали. Все размеры, в логических единицах. Логический размер представления обычно вычисляется по данным, хранящимся в документе, но в некоторых случаях может потребоваться указать фиксированный размер. Примеры обоих подходов см. в разделе [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 Необходимо указать суммы для прокрутки по горизонтали и вертикали в логических единицах. По умолчанию, если пользователь нажимает кнопку стрелки панель прокрутки вне полосы прокрутки `CScrollView` прокручивает «страница». При нажатии стрелок прокрутки на любом конце полоса прокрутки `CScrollView` прокручивает «линия». По умолчанию размер страницы равен 1/10 общий размер представления. Строка является 1/10 размер страницы. Переопределить значения по умолчанию, передав размеров в `SetScrollSizes` функции-члена. Например можно задать размер по горизонтали для определенной части ширину общий размер и размер по вертикали, чтобы высота строки в текущего шрифта.  
  
 Вместо прокрутки, `CScrollView` можно автоматически масштабировать представлении, чтобы размер текущего окна. В этом режиме представления не имеют полос прокрутки и логическое представление растянуть или сжать точно по размеру клиентской области окна. Для использования этой возможности масштабирования ширины вызвать [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Вызвать либо метод `SetScaleToFitSize` или `SetScrollSizes`, но не оба.)  
  
 Прежде чем `OnDraw` вызывается функция-член класса производным представлением, `CScrollView` автоматически корректирует просмотра точку отсчета для `CPaintDC` объект контекста устройства, он передает `OnDraw`.  
  
 Для настройки начала координат окна просмотра для прокрутки окна `CScrollView` переопределяет [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Этот параметр для автоматического `CPaintDC` контекста устройства, `CScrollView` передает `OnDraw`, но необходимо вызвать **CScrollView::OnPrepareDC** самостоятельно для любого другого контекста устройства можно использовать, например `CClientDC`. Можно переопределить **CScrollView::OnPrepareDC** задать пера, цвет фона и другие атрибуты рисования, но вызывают базовый класс для масштабирования.  
  
 В трех местах относительно представления, могут отображаться полосы прокрутки, как показано в следующих случаях.  
  
-   Можно задать стандартный стиль окна полосы прокрутки для представления с помощью **WS_HSCROLL** и **WS_VSCROLL**[стили Windows](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
-   Полоса прокрутки элементов управления можно также добавить фрейм, содержащий представление, в котором регистр платформа перенаправляет `WM_HSCROLL` и `WM_VSCROLL` сообщений от фрейма окна для активного представления.  
  
-   Платформа также пересылает прокрутите сообщения от `CSplitterWnd` splitter-элемент управления в область текущего активного разделителей (представления). При помещении в [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) с полосами прокрутки общего `CScrollView` объекта будет использовать общий из них, а не создавать свои собственные.  
  
 Дополнительные сведения об использовании `CScrollView`, в разделе [архитектуры Document/View](../../mfc/document-view-architecture.md) и [производный представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars  
 Вызовите эту функцию-член для определения наличия горизонтальные и вертикальные полосы прокрутки представления.  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *bHasHorzBar*  
 Указывает, что приложение имеет горизонтальной полосы прокрутки.  
  
 *bHasVertBar*  
 Указывает, что приложение имеет вертикальную полосу прокрутки.  
  
##  <a name="cscrollview"></a>  CScrollView::CScrollView  
 Создает объект `CScrollView`.  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>Примечания  
 Следует вызвать `SetScrollSizes` или `SetScaleToFitSize` перед прокрутки представления можно использовать.  
  
##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect  
 Вызовите `FillOutsideRect` для заполнения области представление, которое отображается вне области прокрутки.  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Контекст устройства, в котором будет выполняться заполнение.  
  
 `pBrush`  
 Кисть, с которым должен быть заполнен области.  
  
### <a name="remarks"></a>Примечания  
 Используйте `FillOutsideRect` в представление прокрутки `OnEraseBkgnd` функции обработчика, чтобы предотвратить чрезмерное фона перерисовка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition  
 Вызовите `GetDeviceScrollPosition` при необходимости текущей горизонтальной и вертикальной позиции прокрутки полей в полосы прокрутки.  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальные и вертикальные позиций (в единицах устройства) поля прокрутки `CPoint` объекта.  
  
### <a name="remarks"></a>Примечания  
 Расположение в документе, к которому прокручивается левом верхнем углу представления соответствует этой парой координат. Это полезно для смещения позиций устройство мыши для представлений прокрутки положения устройства.  
  
 `GetDeviceScrollPosition` Возвращает значения в единицы устройства. Логические устройства, используйте `GetScrollPosition` вместо него.  
  
##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes` Возвращает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления.  
  
```  
void GetDeviceScrollSizes(
    int& nMapMode,  
    SIZE& sizeTotal,  
    SIZE& sizePage,  
    SIZE& sizeLine) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nMapMode`  
 Возвращает текущий режим сопоставления для этого представления. Список возможных значений см. в разделе `SetScrollSizes`.  
  
 `sizeTotal`  
 Возвращает текущий размер общее представление прокрутки в единицы устройства.  
  
 `sizePage`  
 Возвращает суммы текущего горизонтальной и вертикальной прокрутки в каждом направлении в ответ на мыши щелкните стрелки полосы прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит вертикальный интервал.  
  
 `sizeLine`  
 Возвращает суммы текущего горизонтальной и вертикальной прокрутки в каждом направлении в ответ на мышь, нажмите кнопку в стрелок прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит вертикальный интервал.  
  
### <a name="remarks"></a>Примечания  
 Размеры: в единицы устройства. Эта функция-член вызывается редко.  
  
##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition  
 Вызовите `GetScrollPosition` при необходимости текущей горизонтальной и вертикальной позиции прокрутки полей в полосы прокрутки.  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальные и вертикальные позиций (в логических единицах) поля прокрутки `CPoint` объекта.  
  
### <a name="remarks"></a>Примечания  
 Расположение в документе, к которому прокручивается левом верхнем углу представления соответствует этой парой координат.  
  
 `GetScrollPosition` Возвращает значения в логических единицах. Единицы устройства, используйте `GetDeviceScrollPosition` вместо него.  
  
##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize  
 Вызовите `GetTotalSize` для получения текущие размеры горизонтальной и вертикальной прокрутки представления.  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Общий размер представление прокрутки в логических единицах. Размер по горизонтали находится в **cx** членом `CSize` возвращаемое значение. Вертикальный размер находится в **cy** член.  
  
##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit  
 Вызовите `ResizeParentToFit` позволяет размер представления определяют размер окном фрейма.  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bShrinkOnly*  
 Тип изменения размера для выполнения. Значение по умолчанию **TRUE**, сжимает окно фрейма, при необходимости. Полосы прокрутки по-прежнему будет отображаться для представления больших или небольшой фреймов. Значение **FALSE** вызывает представления всегда точно размера окна фрейма. Это может быть несколько опасно, поскольку фрейм окна давало помещается внутри несколько фреймового окна многодокументного интерфейса (MDI) или экрана.  
  
### <a name="remarks"></a>Примечания  
 Это рекомендуется только для представлений в дочерние окна фрейма MDI. Используйте `ResizeParentToFit` в `OnInitialUpdate` функция обработчика производного `CScrollView` класса. Пример эта функция-член, в разделе [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 `ResizeParentToFit` предполагается, что размер окна представления установлена. Если размер окна представления не было задано при `ResizeParentToFit` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом метода `ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition  
 Вызовите `ScrollToPosition` для прокрутки до определенного момента в представлении.  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Точка для прокрутки, в логических единицах. **x** член должен иметь положительное значение (больше или равно 0, вплоть до общего размера представления). То же самое справедливо для **y** член в режиме сопоставления `MM_TEXT`. **y** член имеет отрицательное значение в сопоставление режимов, отличный от `MM_TEXT`.  
  
### <a name="remarks"></a>Примечания  
 Представление будет прокрутки, чтобы эта точка находится в левом верхнем углу окна. Эта функция-член не должен вызываться, если представление масштабируется по размерам.  
  
##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize  
 Вызовите `SetScaleToFitSize` при необходимости автоматически масштабировать размер окна просмотра текущего размера окна.  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>Параметры  
 `sizeTotal`  
 Горизонтальные и вертикальные размеры, для которых представление не масштабировать. Размер представления прокрутки измеряется в логических единицах. Размер по горизонтали, содержащихся в **cx** член. Вертикальный размер содержится в **cy** член. Оба **cx** и **cy** должно быть больше или равно 0.  
  
### <a name="remarks"></a>Примечания  
 С полосами прокрутки только части логического представления могут быть видны в любое время. Но с возможностью масштабирования ширины полосы прокрутки не имеет представление и логическое представление растянуть или сжать точно по размеру клиентской области окна. При изменении размера окна, представления рисует свои данные в новый масштаб, в зависимости от размера окна.  
  
 Обычно будет разместить вызова `SetScaleToFitSize` в переопределении представления `OnInitialUpdate` функции-члена. Если требуется запретить автоматическое масштабирование, вызовите `SetScrollSizes` вместо этого функция-член.  
  
 `SetScaleToFitSize` можно использовать для реализации операции «Масштаб по размеру». Используйте `SetScrollSizes` для повторной инициализации прокрутки.  
  
 `SetScaleToFitSize` предполагается, что размер окна представления установлена. Если размер окна представления не было задано при `SetScaleToFitSize` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом метода `SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes  
 Вызовите `SetScrollSizes` при представлении сейчас будет обновляться.  
  
```  
void SetScrollSizes(
    int nMapMode,  
    SIZE sizeTotal,  
    const SIZE& sizePage = sizeDefault,  
    const SIZE& sizeLine = sizeDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `nMapMode`  
 Режим сопоставления, чтобы задать для этого представления. Возможные допустимые значения приведены ниже.  
  
|Режим сопоставления|Логическое устройство|Оси y — Extends...|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 пиксель|Вниз|  
|`MM_HIMETRIC`|0,01 мм|Вверх|  
|`MM_TWIPS`|1/1440 в|Вверх|  
|`MM_HIENGLISH`|0,001 дюйма|Вверх|  
|`MM_LOMETRIC`|0,1 мм|Вверх|  
|`MM_LOENGLISH`|0,01 дюйма|Вверх|  
  
 Все эти режимы определяются операционной системой Windows. Два режима сопоставления стандартных `MM_ISOTROPIC` и `MM_ANISOTROPIC`, не используются для `CScrollView`. Библиотека классов предоставляет `SetScaleToFitSize` функции-члена для масштабирования представления для размера окна. Столбец 3 в таблице выше описывает ориентацию координат.  
  
 `sizeTotal`  
 Общий размер представление прокрутки. **Cx** член содержит горизонтальной экстента. **Cy** член содержит верхнюю границу. Размеры: в логических единицах. Оба **cx** и **cy** должно быть больше или равно 0.  
  
 `sizePage`  
 Суммы горизонтальной и вертикальной прокрутки в каждом направлении в ответ на мыши щелкните стрелки полосы прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит вертикальный интервал.  
  
 `sizeLine`  
 Суммы горизонтальной и вертикальной прокрутки в каждом направлении в ответ на мыши щелкните стрелок прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит вертикальный интервал.  
  
### <a name="remarks"></a>Примечания  
 Вызовите его в переопределении `OnUpdate` функции-члена для настройки характеристик прокрутки, когда, например, изначально отображается документа или изменении размера.  
  
 Как правило, будут получены из представления связанный документ сведения о размере путем вызова функции-члена документа, может быть вызван `GetMyDocSize`, указываемое с документа производного класса. В следующем коде показано этот подход:  
  
 [!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 Кроме того иногда может потребоваться установить фиксированный размер, как показано в следующем коде:  
  
 [!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 В любом из режимов сопоставления Windows, за исключением того, необходимо задать режим сопоставления `MM_ISOTROPIC` или `MM_ANISOTROPIC`. Если вы хотите использовать режим сопоставления без ограничений, вызовите `SetScaleToFitSize` вместо функции-члена `SetScrollSizes`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)
