---
title: CRectTracker-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eff57e1fde0af6e794c2c47db7d1e31daf545715
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="crecttracker-class"></a>CRectTracker-класс
Позволяет элементу отображаются, перемещать и изменять размер различными способами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|Создает объект `CRectTracker`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|Вызывается, когда размер прямоугольника.|  
|[CRectTracker::Draw](#draw)|Отрисовывает прямоугольник.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Вызывается при рисовании границы `CRectTracker` объекта.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Вызывается для получения маски `CRectTracker` маркеры изменения размеров элемента.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Возвращает ширину и высоту прямоугольника и маркеров изменения размера.|  
|[CRectTracker::HitTest](#hittest)|Возвращает текущую позицию курсора, связанные с `CRectTracker` объекта.|  
|[CRectTracker::NormalizeHit](#normalizehit)|Нормализует код проверки нажатия.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Вызывается, когда после изменения размера или перемещения прямоугольника.|  
|[CRectTracker::SetCursor](#setcursor)|Задает курсор, в зависимости от его положение по прямоугольника.|  
|[CRectTracker::Track](#track)|Позволяет пользователю управлять прямоугольника.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|Позволяет пользователю «эластичное» выделение.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Определяет размер маркеров изменения размера.|  
|[CRectTracker::m_nStyle](#m_nstyle)|Текущий style(s) средство отслеживания.|  
|[CRectTracker::m_rect](#m_rect)|Текущая позиция (в пикселях) прямоугольника.|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Определяет минимальное прямоугольников ширины и высоты.|  
  
## <a name="remarks"></a>Примечания  
 `CRectTracker` не имеет базового класса.  
  
 Несмотря на то что `CRectTracker` класс предназначена для взаимодействия с OLE-элементы с помощью графического интерфейса пользователя, его использование не ограничено для приложений с поддержкой OLE. Он может использоваться в любом интерфейс пользователя не требуется.  
  
 `CRectTracker` границы могут быть сплошной или пунктирными линиями. Элемент может быть заданному штриховой границей или накладывается заштрихованного шаблон для указания различных состояний элемента. Можно поместить восемь маркеров изменения размера на внешней или внутренней границы элемента. (Описание маркеры изменения размера, в разделе [GetHandleMask](#gethandlemask).) Наконец `CRectTracker` позволяет изменение ориентации элемента при изменении размера.  
  
 Для использования `CRectTracker`, создания `CRectTracker` и укажите, какие состояния отображения инициализируются. Затем этот интерфейс можно использовать для предоставления пользователю визуальную обратную связь на текущее состояние объекта OLE, связанные с `CRectTracker` объекта.  
  
 Дополнительные сведения об использовании `CRectTracker`, см. в статье [средства отслеживания](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRectTracker`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="adjustrect"></a>  CRectTracker::AdjustRect  
 Вызывается платформой при изменении размеров прямоугольника отслеживания с помощью маркер изменения размера.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `nHandle`  
 Дескриптор, который используется индекс.  
  
 `lpRect`  
 Указатель на текущий размер прямоугольника. (Размер прямоугольника определяется его высота и ширина.)  
  
### <a name="remarks"></a>Примечания  
 Поведение по умолчанию эта функция позволяет ориентации прямоугольника для изменения только если `Track` и `TrackRubberBand` вызван с Инверсия разрешено.  
  
 Переопределите эту функцию для управления корректировки прямоугольника отслеживания во время операции перетаскивания. Первый способ — настроить координатами, заданными `lpRect` перед возвратом.  
  
 Специальные функции, которые не поддерживаются напрямую `CRectTracker`, такие как сетку привязки или сохранять--пропорции, можно реализовать путем переопределения этой функции.  
  
##  <a name="crecttracker"></a>  CRectTracker::CRectTracker  
 Создает и инициализирует `CRectTracker` объекта.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpSrcRect`  
 Координаты объекта rectangle.  
  
 `nStyle`  
 Задает стиль `CRectTracker` объекта. Поддерживаются следующие стили:  
  
- **CRectTracker::solidLine** использовать сплошной линии для границы прямоугольника.  
  
- **CRectTracker::dottedLine** использовать пунктирной линии для границы прямоугольника.  
  
- **CRectTracker::hatchedBorder** используют заштрихованного шаблон для границы прямоугольника.  
  
- **CRectTracker::resizeInside** находятся внутри прямоугольника маркеры изменения размера.  
  
- **CRectTracker::resizeOutside** расположен вне прямоугольника маркеры изменения размера.  
  
- **CRectTracker::hatchInside** Hatched шаблон охватывает весь прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию инициализирует `CRectTracker` со значениями из `lpSrcRect` и инициализирует других размеров параметры системы по умолчанию. Если объект создается без параметров, `m_rect` и `m_nStyle` данные-члены не инициализированы.  
  
##  <a name="draw"></a>  CRectTracker::Draw  
 Эта функция вызывается для рисования внешней линий и внутренняя область прямоугольника.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, на котором выполняется отрисовка.  
  
### <a name="remarks"></a>Примечания  
 Стиль окна инспектора определяет, как выполняется рисование. В разделе конструктор для `CRectTracker` Дополнительные сведения о доступных стилей.  
  
##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect  
 Вызывается платформой при каждом изменении позиции инспектор while внутри `Track` или `TrackRubberBand` функции-члена.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указатель на `RECT` , содержащий прямоугольника для рисования.  
  
 `pWndClipTo`  
 Указатель на окно для использования в прямоугольной обрезки.  
  
 `pDC`  
 Указатель на контекст устройства, на котором выполняется отрисовка.  
  
 `pWnd`  
 Указатель на окно, на котором будет выполняться рисование.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает метод `CDC::DrawFocusRect`, который рисует прямоугольник пунктирная.  
  
 Переопределите эту функцию для предоставления отзывов различных во время операции отслеживания.  
  
##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask  
 Платформа вызывает эту функцию-член для извлечения маску для прямоугольника маркеры изменения размера.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Маска `CRectTracker` маркеры изменения размеров элемента.  
  
### <a name="remarks"></a>Примечания  
 Маркеры изменения размера появляются на сторонах углов прямоугольника и разрешить пользователю контролировать форму и размер прямоугольника.  
  
 Прямоугольник имеет 8 маркеры изменения размера с номерами от 0 до 7. Каждый маркер изменения размера представленного бита в маске; значение бита равно 2 ^ *n*, где *n* номер маркер изменения размера. Биты 0-3 соответствуют маркеры изменения размера угла, начиная с верхней левой перемещение по часовой стрелке. Бит 4-7 соответствуют стороне изменить размер маркеров, начиная сверху стрелке. На следующем рисунке показано маркеры изменения размера прямоугольника и соответствующие им изменить дескриптор числа и значения:  
  
 ![Числа маркера изменения размера](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Реализация по умолчанию **GetHandleMask** возвращает значение маски битов, чтобы появились маркеры изменения размера. Если один бит включен, отображается соответствующий маркер изменения размера.  
  
 Переопределите эту функцию-член, чтобы скрыть или отобразить выбранный маркеры изменения размера.  
  
##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect  
 Вызывайте эту функцию для извлечения координат прямоугольника.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpTrueRect`  
 Указатель на `RECT` координаты структура, которая будет содержать устройство `CRectTracker` объекта.  
  
### <a name="remarks"></a>Примечания  
 Размеры прямоугольника включают высоту и ширину все маркеры изменения размера, расположенных на внешней границы. При возвращении, `lpTrueRect` всегда представляет собой нормализованное прямоугольник в координатах устройства.  
  
##  <a name="hittest"></a>  CRectTracker::HitTest  
 Вызывайте эту функцию, чтобы узнать, является ли пользователь захвачено маркер изменения размера.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Точка в координатах устройства, для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение зависит от перечисляемого типа **CRectTracker::TrackerHit** и может иметь одно из следующих значений:  
  
- **CRectTracker::hitNothing** -1  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize  
 Размер в пикселях от `CRectTracker` маркеры изменения размера.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирован системы по умолчанию.  
  
##  <a name="m_rect"></a>  CRectTracker::m_rect  
 Текущая позиция прямоугольника в клиентские координаты (в пикселях).  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin  
 Минимальный размер прямоугольника.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Примечания  
 Оба значения по умолчанию **cx** и **cy**, вычисляются на основе системы по умолчанию для ширины границы. Этот член данных используется только `AdjustRect` функции-члена.  
  
##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle  
 Текущий стиль прямоугольника.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CRectTracker::CRectTracker](#crecttracker) список возможных стилей.  
  
##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit  
 Вызовите эту функцию для преобразования потенциально инвертированный дескриптор.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nHandle`  
 Дескриптор, выбранных пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс нормализованный дескриптор.  
  
### <a name="remarks"></a>Примечания  
 Когда `CRectTracker::Track` или `CRectTracker::TrackRubberBand` вызывается с Инверсия допускается, существует возможность прямоугольник обратные на оси x и оси y. В этом случае `HitTest` будет возвращать маркеры, которые также обратным по отношению к прямоугольника. Это не подходит для рисования курсоров, так как отзывы зависит от позиции экрана прямоугольника, а не часть структуры данных прямоугольник, который будет изменен.  
  
##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect  
 Вызывается платформой при каждом прямоугольнике отслеживания был изменен во время вызова `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Параметры  
 *rectOld*  
 Содержит координаты старое устройство `CRectTracker` объекта.  
  
### <a name="remarks"></a>Примечания  
 Во время вызова этой функции, все отзывы, нарисованных при помощи `DrawTrackerRect` был удален. Реализация по умолчанию этой функции не выполняет никаких действий.  
  
 Переопределите эту функцию, если вы хотите выполнить действия после был изменен размер прямоугольника.  
  
##  <a name="setcursor"></a>  CRectTracker::SetCursor  
 Эта функция вызывается для изменения формы курсора, когда оно находится над `CRectTracker` области объекта.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Точки окна, которое в данный момент находится курсор.  
  
 `nHitTest`  
 Результаты предыдущей проверки нажатия из `WM_SETCURSOR` сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если предыдущее соответствие по протоколу прямоугольник регистрации; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию из внутри функции окна, который обрабатывает `WM_SETCURSOR` сообщений (обычно `OnSetCursor`).  
  
##  <a name="track"></a>  CRectTracker::Track  
 Эта функция вызывается для отображения пользовательского интерфейса для изменения размеров прямоугольника.  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Объект window, содержащей прямоугольник.  
  
 `point`  
 Устройство координаты текущего положения мыши относительно клиентской области.  
  
 `bAllowInvert`  
 Если **TRUE**, прямоугольник может быть инвертированный вдоль оси x и оси y; в противном случае **FALSE**.  
  
 `pWndClipTo`  
 Окно, в котором операций рисования будет обрезан по ее. Если **NULL**, `pWnd` используется в качестве отсекающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если нажата клавиша ESC, остановить процесс отслеживания, прямоугольник, хранящиеся в объекте отслеживания не изменяется и возвращается значение 0. При фиксации изменений с мышью и, не отпуская кнопку мыши, новое положение и размер записывается в средство отслеживания прямоугольник и возвращается ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Обычно это вызывается из внутри функции приложения, которые обрабатывают `WM_LBUTTONDOWN` сообщений (обычно `OnLButtonDown`).  
  
 Эта функция будет захватить мышь, пока пользователь отпускает левую кнопку мыши, клавиши ESC или нажатии правой кнопки мыши. Обновляется, когда пользователь перемещает указатель мыши, обратную связь путем вызова `DrawTrackerRect` и `OnChangedRect`.  
  
 Если `bAllowInvert` — **TRUE**, прямоугольник отслеживания могут быть инвертированы на оси x или оси y.  
  
##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand  
 Вызовите эту функцию, чтобы сделать выбор эластичное.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Объект window, содержащей прямоугольник.  
  
 `point`  
 Устройство координаты текущего положения мыши относительно клиентской области.  
  
 `bAllowInvert`  
 Если **задано значение TRUE,** прямоугольник может быть инвертированный вдоль оси x и оси y; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если мышь перемещена и прямоугольника, не является пустой; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Обычно она вызывается из внутри функции приложения, которые обрабатывают `WM_LBUTTONDOWN` сообщений (обычно `OnLButtonDown`).  
  
 Эта функция будет захватить мышь, пока пользователь отпускает левую кнопку мыши, клавиши ESC или нажатии правой кнопки мыши. Обновляется, когда пользователь перемещает указатель мыши, обратную связь путем вызова `DrawTrackerRect` и `OnChangedRect`.  
  
 Отслеживание выполняется с выбора эластичные внешнего типа из нижнего правого дескриптора. Если разрешается обращение, прямоугольник можно изменять, перетаскивая либо вверх и влево или вниз и вправо.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC ОТСЛЕЖИВАНИЯ](../../visual-cpp-samples.md)   
 [Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleResizeBar](../../mfc/reference/coleresizebar-class.md)   
 [Класс CRect](../../atl-mfc-shared/reference/crect-class.md)
