---
title: "Класс CScrollView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CScrollView class
- views, scrolling
- scrolling views
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0dc937a9559306ff527779c45af9fdb62cf602df
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollview-class"></a>Класс CScrollView
Объект [CView](../../mfc/reference/cview-class.md) с возможностями прокрутки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CScrollView : public CView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollView::CScrollView](#cscrollview)|Создает объект `CScrollView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](#checkscrollbars)|Указывает, имеет ли представление прокрутки горизонтальные и вертикальные полосы прокрутки.|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|Заполняет область представления за пределами области прокрутки.|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Возвращает текущую позицию прокрутки в единицы устройства.|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Возвращает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления. Размеры указаны в единицы устройства.|  
|[CScrollView::GetScrollPosition](#getscrollposition)|Возвращает текущую позицию прокрутки в логических единицах.|  
|[CScrollView::GetTotalSize](#gettotalsize)|Возвращает общий размер представление прокрутки в логических единицах.|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|В результате размер представления для диктовки размер фрейма.|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|Прокручивает представление на определенный момент, указанный в логических единицах.|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Переводит представление прокрутки в режиме масштабирования ширины.|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|Задает режим сопоставления представления с прокруткой, общий размер и суммы вертикальной и горизонтальной прокрутки.|  
  
## <a name="remarks"></a>Примечания  
 Можно обработать самостоятельно прокрутку в класс, производный от стандартного `CView` путем переопределения сообщения сопоставлены [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) функции-члены. Но `CScrollView` добавляет следующие функции к ее `CView` возможности:  
  
-   Он управляет размеры окна и окна просмотра и режимы сопоставления.  
  
-   Он автоматически прокручивается в ответ на сообщения полосы прокрутки.  
  
-   Он автоматически прокручивается в ответ на сообщения от клавиатуры, мыши без прокрутки или Поворачивайте колесико мыши.  
  
 Чтобы автоматически перейти в ответ на сообщения с клавиатуры, добавьте сообщение WM_KEYDOWN и тестирования для VK_DOWN, VK_PREV и вызвать [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Можно обработать прокрутка самостоятельно путем переопределения сопоставить сообщение колесика мыши [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) и [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) функции-члены. Как для `CScrollView`, рекомендуемые действия для поддержки этих функций-членов [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), сообщение поворота колесика.  
  
 Чтобы воспользоваться преимуществами автоматическую прокрутку, сформируйте класс представления из `CScrollView` вместо из `CView`. При представлении сначала создается, если требуется вычислить размер представления прокрутки, исходя из размера документа, вызов `SetScrollSizes` функции-члена из переопределение метода либо [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) или [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Необходимо написать собственный код для запроса размера документа. Например, в разделе [примера Scribble](../../visual-cpp-samples.md).)  
  
 Вызов `SetScrollSizes` функция-член задает режим сопоставления, размеры общее представление прокрутки и суммы для прокрутки по горизонтали и вертикали. Все размеры указаны в логических единицах. Обычно размер логического представления вычисляется из данных, хранящихся в документе, но в некоторых случаях может потребоваться указать фиксированный размер. Примеры этих двух подходов см. [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 Укажите сумму для прокрутки по горизонтали и вертикали в логических единицах. По умолчанию, если пользователь нажимает кнопку стрелки панель прокрутки вне полосы прокрутки `CScrollView` прокручивает «страница». При нажатии стрелки прокрутки на любом конце полосу прокрутки `CScrollView` прокручивает «строка». По умолчанию страницы составляет 1/10 общий размер представления. Строка является 1/10 размер страницы. Переопределить значения по умолчанию, передав размеров в `SetScrollSizes` функции-члена. Например можно задать размер по горизонтали для определенной части ширину общий размер и размер по вертикали, чтобы высота строки текущим шрифтом.  
  
 Вместо прокрутки, `CScrollView` можно автоматически масштабировать представление текущего размера окна. В этом режиме представления не имеют полос прокрутки и логическое представление является растягивается или сжимается точно по размеру клиентской области окна. Чтобы использовать эти возможности масштабирования ширины, вызовите [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Вызова какого-либо `SetScaleToFitSize` или `SetScrollSizes`, но не оба.)  
  
 Прежде чем `OnDraw` вызывается функция-член класса производным представлением, `CScrollView` автоматически корректирует источником просмотра `CPaintDC` объект контекста устройства, он передает `OnDraw`.  
  
 Для настройки начала координат окна просмотра для прокрутки окна `CScrollView` переопределяет [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Этот параметр для автоматического `CPaintDC` контекста устройства, `CScrollView` передает `OnDraw`, но необходимо вызвать **CScrollView::OnPrepareDC** самостоятельно для контекстов устройство используется, например `CClientDC`. Можно переопределить **CScrollView::OnPrepareDC** задать пера, цвет фона и другие атрибуты рисования, но вызывают базовый класс для масштабирования.  
  
 Полосы прокрутки могут находиться в трех местах относительно представления, как показано в следующих случаях:  
  
-   Стандартный стиль окна полосы прокрутки можно задать для представления с помощью **WS_HSCROLL** и **WS_VSCROLL**[стили Windows](../../mfc/reference/window-styles.md).  
  
-   Элементы управления полосы прокрутки можно также добавить кадр, содержащий представление, в котором пересылает случае платформа `WM_HSCROLL` и `WM_VSCROLL` сообщений от фрейма окна для активного представления.  
  
-   Платформа также пересылает прокрутите сообщения от `CSplitterWnd` разделителя для активного разделенной области (представление). При помещении в [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) с полосами прокрутки общего `CScrollView` объекта будет использовать общие из них, а не создавать собственный.  
  
 Дополнительные сведения об использовании `CScrollView`, в разделе [архитектуры документ/представление](../../mfc/document-view-architecture.md) и [производный представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="checkscrollbars"></a>CScrollView::CheckScrollBars  
 Вызовите эту функцию-член для определения горизонтальные и вертикальные полосы прокрутки представления.  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *bHasHorzBar*  
 Указывает, что приложение имеет горизонтальную полосу прокрутки.  
  
 *bHasVertBar*  
 Указывает, что приложение имеет вертикальную полосу прокрутки.  
  
##  <a name="cscrollview"></a>CScrollView::CScrollView  
 Создает объект `CScrollView`.  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>Примечания  
 Следует вызвать `SetScrollSizes` или `SetScaleToFitSize` перед прокрутки пригодна для представления.  
  
##  <a name="filloutsiderect"></a>CScrollView::FillOutsideRect  
 Вызов `FillOutsideRect` для заполнения области представления, которое отображается вне области прокрутки.  
  
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
 Используйте `FillOutsideRect` в представление прокрутки `OnEraseBkgnd` функция обработчика для предотвращения чрезмерного фонового обновления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#164;](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="getdevicescrollposition"></a>CScrollView::GetDeviceScrollPosition  
 Вызов `GetDeviceScrollPosition` при необходимости текущей горизонтальной и вертикальной позиции прокрутки полей в полосы прокрутки.  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальные и вертикальные позиций (в единицах устройства) поля прокрутки `CPoint` объекта.  
  
### <a name="remarks"></a>Примечания  
 Место в документе, в который прокручивается в левый верхний угол представления соответствует этой парой координат. Это полезно для смещения позиций устройство мыши для представления с прокруткой устройства позиций.  
  
 `GetDeviceScrollPosition`Возвращает значения в единицах устройства. Логические устройства, используйте `GetScrollPosition` вместо.  
  
##  <a name="getdevicescrollsizes"></a>CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes`Возвращает текущий режим сопоставления, общий размер и размеры страниц и прокрутки представления.  
  
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
 Возвращает текущий суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки полосы прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит сумму вертикальной.  
  
 `sizeLine`  
 Возвращает текущий суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит сумму вертикальной.  
  
### <a name="remarks"></a>Примечания  
 Размеры указаны в единицы устройства. Эта функция-член вызывается редко.  
  
##  <a name="getscrollposition"></a>CScrollView::GetScrollPosition  
 Вызов `GetScrollPosition` при необходимости текущей горизонтальной и вертикальной позиции прокрутки полей в полосы прокрутки.  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальное и вертикальное положение (в логических единицах) поля прокрутки `CPoint` объекта.  
  
### <a name="remarks"></a>Примечания  
 Место в документе, в который прокручивается в левый верхний угол представления соответствует этой парой координат.  
  
 `GetScrollPosition`Возвращает значения в логических единицах. Единицы устройства, используйте `GetDeviceScrollPosition` вместо.  
  
##  <a name="gettotalsize"></a>CScrollView::GetTotalSize  
 Вызов `GetTotalSize` для получения текущего горизонтального и вертикального размеров представление прокрутки.  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Общий размер представление прокрутки в логических единицах. Размер по горизонтали находится в **cx** членом `CSize` возвращаемое значение. Вертикальный размер становится в **cy** член.  
  
##  <a name="resizeparenttofit"></a>CScrollView::ResizeParentToFit  
 Вызов `ResizeParentToFit` позволяет размер представления определяют размер его рамки окна.  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bShrinkOnly*  
 Тип изменения размера для выполнения. Значение по умолчанию **TRUE**, сжимает фрейме окна при необходимости. Для представления больших или небольших кадров windows по-прежнему появятся полосы прокрутки. Значение **FALSE** в представлении всегда точно размера окна фрейма. Это может быть несколько опасно, так как окно области может получить помещается внутри нескольких фреймового окна многодокументного интерфейса (MDI) или экрана.  
  
### <a name="remarks"></a>Примечания  
 Это рекомендуется только для представлений в кадр дочерние MDI-окна. Используйте `ResizeParentToFit` в `OnInitialUpdate` функция обработчика производный `CScrollView` класса. Пример эта функция-член, в разделе [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 `ResizeParentToFit`предполагается, что размер окна задан. Если размер окна представление не было задано при `ResizeParentToFit` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом метода `ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView&#165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="scrolltoposition"></a>CScrollView::ScrollToPosition  
 Вызов `ScrollToPosition` для прокрутки на определенный момент в представлении.  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Точка для прокрутки, в логических единицах. **x** член должен иметь положительное значение (больше или равно 0, до общего размера представления). То же самое верно для **y** член в режиме сопоставления `MM_TEXT`. **y** член имеет отрицательное значение в сопоставление режимов, отличных от `MM_TEXT`.  
  
### <a name="remarks"></a>Примечания  
 Представление будет прокручиваться, чтобы эта точка находится в верхнем левом углу окна. Эта функция-член не должен вызываться, если представление масштабируется по размерам.  
  
##  <a name="setscaletofitsize"></a>CScrollView::SetScaleToFitSize  
 Вызовите `SetScaleToFitSize` , если необходимо автоматически масштабировать размер окна просмотра текущего размера окна.  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>Параметры  
 `sizeTotal`  
 Горизонтальные и вертикальные размеры, к которым это масштабирование. Размер представления с прокруткой измеряется в логических единицах. Размер по горизонтали, содержащихся в **cx** член. Размер по вертикали, содержащихся в **cy** член. Оба **cx** и **cy** должно быть больше или равно 0.  
  
### <a name="remarks"></a>Примечания  
 С помощью полосы прокрутки часть логическое представление может отображаться в любой момент. Но с возможностью масштабирования ширины представления не имеют полос прокрутки и логическое представление является растягивается или сжимается точно по размеру клиентской области окна. При изменении размера окна представления рисует свои данные в новый масштаб, в зависимости от размера окна.  
  
 Обычно поместим вызов `SetScaleToFitSize` в переопределении представления `OnInitialUpdate` функции-члена. Если не требуется автоматическое масштабирование, вызовите `SetScrollSizes` вместо этого функция-член.  
  
 `SetScaleToFitSize`можно использовать для реализации операции «Масштаб по размеру». Используйте `SetScrollSizes` для повторной инициализации прокрутки.  
  
 `SetScaleToFitSize`предполагается, что размер окна задан. Если размер окна представление не было задано при `SetScaleToFitSize` является именем, вы получите утверждения. Чтобы убедиться, что этого не происходит, сделать следующий вызов перед вызовом метода `SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView&#165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="setscrollsizes"></a>CScrollView::SetScrollSizes  
 Вызов `SetScrollSizes` при представлении скоро будет обновляться.  
  
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
  
|Режим сопоставления|Логическое устройство|Расширяет оси y —...|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 пиксель|Вниз|  
|`MM_HIMETRIC`|0,01 мм|Вверх|  
|`MM_TWIPS`|1-1440 в|Вверх|  
|`MM_HIENGLISH`|0,001 дюйма|Вверх|  
|`MM_LOMETRIC`|0,1 мм|Вверх|  
|`MM_LOENGLISH`|0,01 дюйма|Вверх|  
  
 Все эти режимы определяются Windows. Два режима сопоставления стандартных `MM_ISOTROPIC` и `MM_ANISOTROPIC`, не используются для `CScrollView`. Библиотека классов предоставляет `SetScaleToFitSize` функции-члена для масштабирования до размера окна представления. Три столбца в таблице выше описывает ориентацию координат.  
  
 `sizeTotal`  
 Общий размер представления с прокруткой. **Cx** член содержит горизонтальной экстент. **Cy** член содержит верхнюю границу. Размеры указаны в логических единицах. Оба **cx** и **cy** должно быть больше или равно 0.  
  
 `sizePage`  
 Суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки полосы прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит сумму вертикальной.  
  
 `sizeLine`  
 Суммы горизонтальной и вертикальной прокрутки в каждом направлении, в ответ на мыши щелкните стрелки прокрутки. **Cx** член содержит сумму горизонтальной. **Cy** член содержит сумму вертикальной.  
  
### <a name="remarks"></a>Примечания  
 Вызовите его в переопределении `OnUpdate` функции-члена для настройки прокрутки характеристики, когда, например, изначально отображается документа или изменении размера.  
  
 Обычно будет получать сведения о размере из представления связанных документов, вызвав функцию-член документа, может быть вызван `GetMyDocSize`, поставляемого с документа производного класса. В следующем коде показано этот подход:  
  
 [!code-cpp[NVC_MFCDocView&#166;](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 Кроме того иногда может потребоваться установить фиксированный размер, как показано в следующем коде:  
  
 [!code-cpp[NVC_MFCDocView&167;](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 Необходимо установить режим сопоставления для всех режимов сопоставления Windows за исключением `MM_ISOTROPIC` или `MM_ANISOTROPIC`. Если вы хотите использовать режим неограниченного сопоставления, вызвать `SetScaleToFitSize` вместо функции-члена `SetScrollSizes`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#168;](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#169;](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)

