---
title: "CRectTracker-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRectTracker
dev_langs:
- C++
helpviewer_keywords:
- displaying items
- CRectTracker class
- resizing items
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
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
ms.openlocfilehash: 444eab5969339cf2a3d5797807eae3dcad32a694
ms.lasthandoff: 02/24/2017

---
# <a name="crecttracker-class"></a>CRectTracker-класс
Позволяет элементу отображается, переместить и размеры различными способами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|Создает объект `CRectTracker`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|Вызывается при изменении размера прямоугольника.|  
|[CRectTracker::Draw](#draw)|Отрисовывает прямоугольник.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Вызывается при рисовании границы `CRectTracker` объекта.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Вызывается для получения маску `CRectTracker`маркеры изменения размеров элемента.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Возвращает ширину и высоту прямоугольника, включая маркеры изменения размера.|  
|[CRectTracker::HitTest](#hittest)|Возвращает текущую позицию курсора, связанные с `CRectTracker` объекта.|  
|[CRectTracker::NormalizeHit](#normalizehit)|Нормализует код проверки нажатия.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Вызывается, когда после изменения размера или перемещения прямоугольника.|  
|[CRectTracker::SetCursor](#setcursor)|Задает курсор, в зависимости от его положение над прямоугольника.|  
|[CRectTracker::Track](#track)|Позволяет пользователю управлять прямоугольника.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|Позволяет выбрать пользователя «изменяемый».|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Определяет размер маркеров изменения размера.|  
|[CRectTracker::m_nStyle](#m_nstyle)|Текущий style(s) средства отслеживания.|  
|[CRectTracker::m_rect](#m_rect)|Текущее положение прямоугольника (в пикселях).|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Определяет минимальное прямоугольника ширины и высоты.|  
  
## <a name="remarks"></a>Примечания  
 `CRectTracker`не имеет базового класса.  
  
 Хотя `CRectTracker` класс позволяет пользователю взаимодействовать с OLE-элементы с помощью графического интерфейса, его использование не ограничивается приложения с поддержкой OLE. Он может использоваться в любом интерфейс пользователя не требуется.  
  
 `CRectTracker`границы может быть сплошной или пунктирной линией. Элемент может быть заданным штриховой границей или накладывается заштрихованного шаблон для указания различных состояний элемента. Можно разместить восемь маркеров изменения размера на внешней или внутренней границы элемента. (Объяснение маркеры изменения размера в разделе [GetHandleMask](#gethandlemask).) Наконец `CRectTracker` позволяет изменить ориентацию при изменении размера элемента.  
  
 Для использования `CRectTracker`, создания `CRectTracker` и укажите, какие состояния отображения инициализируются. Затем этот интерфейс можно использовать для предоставления пользователю визуальную обратную связь от текущего состояния объекта OLE, связанные с `CRectTracker` объекта.  
  
 Дополнительные сведения об использовании `CRectTracker`, см. в статье [средства отслеживания](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRectTracker`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="a-nameadjustrecta--crecttrackeradjustrect"></a><a name="adjustrect"></a>CRectTracker::AdjustRect  
 Вызывается инфраструктурой при изменении размера прямоугольника отслеживания с помощью маркер изменения размера.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `nHandle`  
 Дескриптор, который используется индекс.  
  
 `lpRect`  
 Указатель на текущий размер прямоугольника. (Размер прямоугольника задается его высоту и ширину.)  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция позволяет ориентацию прямоугольник для изменения только если `Track` и `TrackRubberBand` вызван с Инверсия разрешено.  
  
 Переопределите эту функцию для управления корректировки прямоугольника отслеживания во время операции перетаскивания. Первый способ — настроить координатами, заданными `lpRect` перед возвратом.  
  
 Специальные функции, которые не поддерживаются напрямую `CRectTracker`, такие как привязка к сетке или keep пропорция, можно реализовать путем переопределения эта функция.  
  
##  <a name="a-namecrecttrackera--crecttrackercrecttracker"></a><a name="crecttracker"></a>CRectTracker::CRectTracker  
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
  
- **CRectTracker::solidLine** использовать сплошную линию границы прямоугольника.  
  
- **CRectTracker::dottedLine** использовать пунктирной линии для границы прямоугольника.  
  
- **CRectTracker::hatchedBorder** используют шаблон заштрихованного границы прямоугольника.  
  
- **CRectTracker::resizeInside** находятся внутри прямоугольника маркеры изменения размера.  
  
- **CRectTracker::resizeOutside** находится за пределами прямоугольника маркеры изменения размера.  
  
- **CRectTracker::hatchInside** Hatched шаблон охватывает весь прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию инициализирует `CRectTracker` объекта значениями из `lpSrcRect` и инициализирует других размеров системы по умолчанию. Если объект создается без параметров, `m_rect` и `m_nStyle` данные-члены являются неинициализированным.  
  
##  <a name="a-namedrawa--crecttrackerdraw"></a><a name="draw"></a>CRectTracker::Draw  
 Эта функция вызывается для рисования линий внешний и внутренний регион прямоугольника.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, на котором выполняется отрисовка.  
  
### <a name="remarks"></a>Примечания  
 Стиль средства отслеживания определяет, как выполняется рисование. В разделе конструктор `CRectTracker` Дополнительные сведения о доступных стилей.  
  
##  <a name="a-namedrawtrackerrecta--crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect  
 Вызывается инфраструктурой при каждом изменении позиции средства отслеживания хотя внутри `Track` или `TrackRubberBand` функции-члена.  
  
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
 Указатель окна для использования в прямоугольник отсечения.  
  
 `pDC`  
 Указатель на контекст устройства, на котором выполняется отрисовка.  
  
 `pWnd`  
 Указатель на окно, на котором будет выполняться рисование.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает метод `CDC::DrawFocusRect`, который рисует пунктирную прямоугольника.  
  
 Переопределите эту функцию для разных отзыв во время операции отслеживания.  
  
##  <a name="a-namegethandlemaska--crecttrackergethandlemask"></a><a name="gethandlemask"></a>CRectTracker::GetHandleMask  
 Платформа вызывает эту функцию-член для получения маску для прямоугольника маркеры изменения размера.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Маска `CRectTracker` маркеры изменения размеров элемента.  
  
### <a name="remarks"></a>Примечания  
 Маркеры изменения размера отображаются на углы прямоугольника и стороны и разрешить пользователю управлять форму и размер прямоугольника.  
  
 Прямоугольник имеет 8 маркеры изменения размера с номерами от 0 до 7. Каждый маркер изменения размера представленного бита в маске; значение бита равно 2 ^ *n*, где *n* номер маркер изменения размера. Биты 0-3 соответствуют угловых маркеров изменения размера, начиная с верхней левой перемещение по часовой стрелке. Бит 4 – 7 соответствуют стороне изменить размер маркеров, начиная сверху, перемещение по часовой стрелке. Маркеры изменения размера прямоугольника и соответствующие им изменять размер дескриптор числа и значения на следующем рисунке:  
  
 ![Количества маркеров изменения размера](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Реализация по умолчанию **GetHandleMask** возвращает битов маски, чтобы появились маркеры изменения размера. Если один бит включен, будет отображен соответствующий маркер изменения размера.  
  
 Переопределите эту функцию-член, чтобы скрыть или отобразить указанный маркеры изменения размера.  
  
##  <a name="a-namegettruerecta--crecttrackergettruerect"></a><a name="gettruerect"></a>CRectTracker::GetTrueRect  
 Эта функция вызывается для извлечения координат прямоугольника.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpTrueRect`  
 Указатель на `RECT` координаты структура, которая будет содержать устройства `CRectTracker` объекта.  
  
### <a name="remarks"></a>Примечания  
 Размеры прямоугольника включают высоту и ширину все маркеры изменения размера, расположенных на внешнюю границу. При возвращении, `lpTrueRect` всегда является нормализованным прямоугольником в координаты устройства.  
  
##  <a name="a-namehittesta--crecttrackerhittest"></a><a name="hittest"></a>CRectTracker::HitTest  
 Вызывайте эту функцию, чтобы узнать, является ли пользователь взял маркер изменения размера.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Точка, координаты устройства, для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение на основе перечислимого типа **CRectTracker::TrackerHit** и может иметь одно из следующих значений:  
  
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
  
##  <a name="a-namemnhandlesizea--crecttrackermnhandlesize"></a><a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize  
 Размер в точках из `CRectTracker` маркеры изменения размера.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирован системы по умолчанию.  
  
##  <a name="a-namemrecta--crecttrackermrect"></a><a name="m_rect"></a>CRectTracker::m_rect  
 Текущая позиция прямоугольника в координатах клиента (в пикселях).  
  
```  
CRect m_rect;  
```  
  
##  <a name="a-namemsizemina--crecttrackermsizemin"></a><a name="m_sizemin"></a>CRectTracker::m_sizeMin  
 Минимальный размер прямоугольника.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Примечания  
 Оба значения по умолчанию **cx** и **cy**, вычисляются на основе системы по умолчанию для ширины границы. Этот член данных используется только `AdjustRect` функции-члена.  
  
##  <a name="a-namemnstylea--crecttrackermnstyle"></a><a name="m_nstyle"></a>CRectTracker::m_nStyle  
 Текущий стиль прямоугольника.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CRectTracker::CRectTracker](#crecttracker) список возможных стилей.  
  
##  <a name="a-namenormalizehita--crecttrackernormalizehit"></a><a name="normalizehit"></a>CRectTracker::NormalizeHit  
 Эта функция вызывается для преобразования потенциально инвертированный дескриптор.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nHandle`  
 Дескриптор, выбранного пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс нормализованных дескриптор.  
  
### <a name="remarks"></a>Примечания  
 Когда `CRectTracker::Track` или `CRectTracker::TrackRubberBand` вызывается с Инверсия допускается, существует возможность прямоугольник обратные на оси x и оси y. В этом случае `HitTest` будет возвращать маркеры, которые также обратным по отношению к прямоугольника. Это подходит для рисования курсоров, поскольку отзывов зависит от положения на экране прямоугольник, а не часть структуры данных прямоугольника, который будет изменен.  
  
##  <a name="a-nameonchangedrecta--crecttrackeronchangedrect"></a><a name="onchangedrect"></a>CRectTracker::OnChangedRect  
 Вызывается инфраструктурой при каждом прямоугольник отслеживания был изменен во время вызова `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Параметры  
 *rectOld*  
 Содержит координаты старые устройства `CRectTracker` объекта.  
  
### <a name="remarks"></a>Примечания  
 Во время эта функция вызывается, все отзывы, рисуемых при помощи `DrawTrackerRect` был удален. Реализация по умолчанию этой функции не выполняет никаких действий.  
  
 Переопределите эту функцию, если требуется выполнять никаких действий, после изменения размера прямоугольника.  
  
##  <a name="a-namesetcursora--crecttrackersetcursor"></a><a name="setcursor"></a>CRectTracker::SetCursor  
 Эта функция вызывается для изменения формы курсора, когда оно находится над `CRectTracker` область объекта.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Точки окна, которое в данный момент находится курсор.  
  
 `nHitTest`  
 Результаты предыдущих попадания из `WM_SETCURSOR` сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если предыдущее соответствие по прямоугольник регистрации; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию из функции окна, который обрабатывает `WM_SETCURSOR` сообщений (обычно `OnSetCursor`).  
  
##  <a name="a-nametracka--crecttrackertrack"></a><a name="track"></a>CRectTracker::Track  
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
 Объект окна, содержащей прямоугольник.  
  
 `point`  
 Координаты устройства текущего положения мыши относительно клиентской области.  
  
 `bAllowInvert`  
 Если **TRUE**, может быть прямоугольник инвертированный вдоль оси x и оси y; в противном случае **FALSE**.  
  
 `pWndClipTo`  
 Окно, операций рисования будет обрезан по ее. Если **NULL**, `pWnd` используется как прямоугольник отсечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если нажата клавиша ESC процесс отслеживания останавливается, прямоугольник, хранящиеся в объекте отслеживания не изменяется и возвращается значение 0. При фиксации изменений, переместив указатель мыши и отпустить кнопку мыши, новое положение и размер записывается в объект отслеживания прямоугольник и возвращается ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Обычно это вызывается из функции приложения, которое обрабатывает `WM_LBUTTONDOWN` сообщений (обычно `OnLButtonDown`).  
  
 Эта функция будет захватить мышь, пока пользователь отпускает кнопку мыши, клавиши ESC или нажатии правой кнопки мыши. Обновляется, когда пользователь перемещает указатель мыши, отзывы и предложения, вызвав `DrawTrackerRect` и `OnChangedRect`.  
  
 Если `bAllowInvert` — **TRUE**, прямоугольник отслеживания могут быть инвертированы на оси x или оси y.  
  
##  <a name="a-nametrackrubberbanda--crecttrackertrackrubberband"></a><a name="trackrubberband"></a>CRectTracker::TrackRubberBand  
 Эта функция вызывается для сделать выбор изменяемого.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Объект окна, содержащей прямоугольник.  
  
 `point`  
 Координаты устройства текущего положения мыши относительно клиентской области.  
  
 `bAllowInvert`  
 Если **значение TRUE,** прямоугольник может быть инвертированный вдоль оси x и оси y; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если мышь переместилась и прямоугольник не пуста; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Обычно вызывается из функции приложения, которое обрабатывает `WM_LBUTTONDOWN` сообщений (обычно `OnLButtonDown`).  
  
 Эта функция будет захватить мышь, пока пользователь отпускает кнопку мыши, клавиши ESC или нажатии правой кнопки мыши. Обновляется, когда пользователь перемещает указатель мыши, отзывы и предложения, вызвав `DrawTrackerRect` и `OnChangedRect`.  
  
 Отслеживание выполняется с резиновой внешнего типа Выбор нижний правый маркер. Если это разрешено преобразование прямоугольника можно увеличить размер, перетащив либо вверх и влево или вниз и вправо.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TRACKER](../../visual-cpp-samples.md)   
 [Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleResizeBar](../../mfc/reference/coleresizebar-class.md)   
 [Класс CRect](../../atl-mfc-shared/reference/crect-class.md)

