---
title: "CReBarCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
dev_langs:
- C++
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 592493a9eb554f0bdeecd291fdbe3ceb54c599c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crebarctrl-class"></a>CReBarCtrl-класс
Инкапсулирует функциональность элемента управления "главная панель ", который представляет собой контейнер для дочернего окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Создает объект `CReBarCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Помещает элемент управления главной панели в режим перетаскивания и вставки.|  
|[CReBarCtrl::Create](#create)|Создает контейнер элементов управления и прикрепляет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::CreateEx](#createex)|Создает элемент управления главной панели с указанным расширенные стили Windows и прикрепляет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Удаляет диапазон с элементом управления главной панели.|  
|[CReBarCtrl::DragMove](#dragmove)|Обновляет позицию перетаскивания в элементе управления "Главная панель" после вызова `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Завершает операцию перетаскивания и вставки элемента управления главной панели.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Возвращает границы диапазона.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Получает количество делений, в данный момент в элементе управления главной панели.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Извлекает сведения о полосе, указанного в элементах управления главной панели.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Получает поля полосе.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Получает высоту элемента управления главной панели.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Извлекает сведения о главной панели управления и список изображений, используемые в нем.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Возвращает цвет фона элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Извлекает [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структур, связанных с элементом управления главной панели.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Возвращает элемент управления главной панели `IDropTarget` указатель на интерфейс.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Возвращает расширенный стиль текущего элемента управления главной панели.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Извлекает список изображений, связанных с элементом управления главной панели.|  
|[CReBarCtrl::GetPalette](#getpalette)|Извлекает текущую палитру управления главной панели.|  
|[CReBarCtrl::GetRect](#getrect)|Возвращает ограничивающий прямоугольник для заданного диапазона в элементах управления главной панели.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Возвращает число строк аппаратного контроллера управления в элементе управления главной панели.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Получает высоту указанной строки в элемент управления главной панели.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Возвращает цвет текста элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор управления любой всплывающей подсказки, связанный с элементом управления главной панели.|  
|[CReBarCtrl::HitTest](#hittest)|Определяет, какая часть области главной панели в момент на экране, если на данный момент существует области главной панели.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Преобразует внешнего идентификатора (ID) индекс диапазона в элементах управления главной панели.|  
|[CReBarCtrl::InsertBand](#insertband)|Вставляет новый аппаратного контроллера управления в элементе управления главной панели.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Изменяет размер диапазона в элементах управления главной панели до максимального размера.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Изменяет размер диапазона в элементах управления главной панели до наименьшего размера.|  
|[CReBarCtrl::MoveBand](#moveband)|Перемещает диапазон из одного индекса в другую.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Шеврон программным образом помещает в стек.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Изменяет размер диапазона в элементе управления главной панели, чтобы его идеального размера.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Задает характеристики существующего диапазона в элементах управления главной панели.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Задает ширину указанной полосы закрепленной в текущий элемент управления главной панели.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Задает характеристики элементом управления главной панели.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Задает цвет фона элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Задает цветовую схему для кнопок на элементах управления главной панели.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для текущего элемента управления главной панели.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Задает список изображений элемента управления главной панели.|  
|[CReBarCtrl::SetOwner](#setowner)|Задает элемент управления главной панели окна-владельца.|  
|[CReBarCtrl::SetPalette](#setpalette)|Задает текущую палитру управления главной панели.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Задает цвет текста элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Связывает всплывающая подсказка с элементом управления главной панели.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления главной панели.|  
|[CReBarCtrl::ShowBand](#showband)|Показывает или скрывает заданного диапазона в элементах управления главной панели.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Устанавливает размер элемента управления главной панели в заданном прямоугольнике.|  
  
## <a name="remarks"></a>Примечания  
 Приложения, в которой находится элемент управления главной панели назначает дочернее окно содержится элементом управления главной панели для аппаратного контроллера управления главной панели. Дочернее окно является обычно другой стандартного элемента управления.  
  
 Элементы управления главной панели содержит зоны один или несколько. Каждый диапазон может содержать сочетание полосу захвата, битовая карта, текстовую метку и дочернего окна. Диапазон может содержать только один из этих элементов.  
  
 Элемент управления главной панели можно отобразить дочернее окно по указанным фоновый рисунок. Можно изменять все лентами главной панели управления, за исключением тех, которые использовать **RBBS_FIXEDSIZE** стиля. Как переместить или изменить размер области главной панели управления, элемент управления главной панели управляет размер и положение дочернего окна, назначенный этой аппаратного контроллера управления. Чтобы изменить размер или изменить порядок полосами в элементе управления, щелкните и перетащите полосы захвата.  
  
 На следующей иллюстрации элемент управления главной панели, который имеет три полосы.  
  
-   Диапазон 0 содержит элемент управления toolbar плоский, прозрачный.  
  
-   Диапазон 1 содержит обе кнопки прозрачный раскрывающийся список стандартных, так и прозрачный.  
  
-   Полоса 2 содержит поле со списком и четыре стандартных кнопок.  
  
     ![Пример меню главной панели](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Элемент управления главной панели  
 Главной панели поддержки элементов управления:  
  
-   Списки изображений.  
  
-   Обработка сообщений.  
  
-   Пользовательская прорисовка функциональные возможности.  
  
-   Различные стили элемента управления, кроме стандартного окна стилей. Список этих стилей см. в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в Windows SDK.  
  
 Дополнительные сведения см. в разделе [использование CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="begindrag"></a>CReBarCtrl::BeginDrag  
 Реализует поведение сообщения Win32 [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429), как описано в Windows SDK.  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, которые влияют на операции перетаскивания и вставки.  
  
 `dwPos`  
 Объект `DWORD` значение, которое содержит начальные координаты мыши. Горизонтальная координата содержится в LOWORD и содержится в HIWORD Вертикальная координата. Если передать `(DWORD)-1`, элемент управления главной панели будет использовать позицию указателя мыши последнего элемента управления потоком, который называется **GetMessage** или **PeekMessage**.  
  
##  <a name="create"></a>CReBarCtrl::Create  
 Создает контейнер элементов управления и прикрепляет его к `CReBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стилей элемента управления главной панели, применяемых к элементу управления. В разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в Windows SDK для получения списка поддерживаемых стили.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер элемента управления главной панели.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления главной панели. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления главной панели управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создание элемента управления главной панели в два этапа:  
  
1.  Вызовите [CReBarCtrl](#crebarctrl) для создания `CReBarCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает элемент управления главной панели Windows и прикрепляет его к `CReBarCtrl` объекта.  
  
 При вызове **создать**, инициализируются стандартных элементов управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CReBarCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CReBarCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `dwStyle`  
 Задает сочетание стилей элемента управления главной панели, применяемых к элементу управления. Список поддерживаемых стили см. в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в Windows SDK.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl  
 Создает объект `CReBarCtrl`.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CReBarCtrl::Create](#create).  
  
##  <a name="deleteband"></a>CReBarCtrl::DeleteBand  
 Реализует поведение сообщения Win32 [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431), как описано в Windows SDK.  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диапазон удален успешно. в противном случае значение равно нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>CReBarCtrl::DragMove  
 Реализует поведение сообщения Win32 [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx), как описано в Windows SDK.  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `dwPos`  
 Объект `DWORD` значение, содержащее новые координаты мыши. Горизонтальная координата содержится в LOWORD и содержится в HIWORD Вертикальная координата. Если передать `(DWORD)-1`, элемент управления главной панели будет использовать позицию указателя мыши последнего элемента управления потоком, который называется **GetMessage** или **PeekMessage**.  
  
##  <a name="enddrag"></a>CReBarCtrl::EndDrag  
 Реализует поведение сообщения Win32 [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435), как описано в Windows SDK.  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>CReBarCtrl::GetBandBorders  
 Реализует поведение сообщения Win32 [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437), как описано в Windows SDK.  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, для которого будет извлекаться границы.  
  
 `prc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, который получит границы диапазона. Если для элемента управления главной панели **RBS_BANDBORDERS** стиля, каждый член этой структуры будет получать количество пикселей, на стороне соответствующего диапазона, составляющих границы. Если элемент управления "Главная панель" не имеет **RBS_BANDBORDERS** стиля только левой членом этой структуры получает недопустимые данные. Описание стили элемента управления главной панели см. в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в Windows SDK.  
  
##  <a name="getbandcount"></a>CReBarCtrl::GetBandCount  
 Реализует поведение сообщения Win32 [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439), как описано в Windows SDK.  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество диапазонов, которые назначены элементу управления.  
  
##  <a name="getbandinfo"></a>CReBarCtrl::GetBandInfo  
 Реализует поведение сообщения Win32 [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) как описано в Windows SDK.  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, для которого будут извлекаться данные.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуру для получения сведений о аппаратного контроллера. Необходимо задать `cbSize` структуры для `sizeof(REBARBANDINFO)` и задайте **fMask** элемента с элементами, которые необходимо получить перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="getbandmargins"></a>CReBarCtrl::GetBandMargins  
 Возвращает границы диапазона.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Параметры  
 *pMargins*  
 Указатель на [поля](http://msdn.microsoft.com/library/windows/desktop/bb773244)структуру, которая будет получать данные.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) сообщения, как описано в Windows SDK.  
  
##  <a name="getbarheight"></a>CReBarCtrl::GetBarHeight  
 Получает высоту строки главной панели.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее высоту в пикселях элемента управления.  
  
##  <a name="getbarinfo"></a>CReBarCtrl::GetBarInfo  
 Реализует поведение сообщения Win32 [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457), как описано в Windows SDK.  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `prbi`  
 Указатель на [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуру, которая будет получать данные управления главной панели. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="getbkcolor"></a>CReBarCtrl::GetBkColor  
 Реализует поведение сообщения Win32 [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459), как описано в Windows SDK.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет фона по умолчанию.  
  
##  <a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme  
 Извлекает [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуру для управления главной панели.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуры, как описано в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **COLORSCHEME** структура включает в себя цвет выделения кнопки и кнопки цвет тени.  
  
##  <a name="getdroptarget"></a>CReBarCtrl::GetDropTarget  
 Реализует поведение сообщения Win32 [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463), как описано в Windows SDK.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса.  
  
##  <a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle  
 Возвращает расширенные стили текущего элемента управления главной панели.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание (OR) флагов, указывающих расширенные стили. Возможные флаги `RBS_EX_SPLITTER` и `RBS_EX_TRANSPARENT`. Дополнительные сведения см. в разделе `dwMask` параметр [CReBarCtrl::SetExtendedStyle](#setextendedstyle) метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) сообщение, которое описано в Windows SDK.  
  
##  <a name="getimagelist"></a>CReBarCtrl::GetImageList  
 Возвращает `CImageList` объект, связанный с элементом управления главной панели.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Возвращает **NULL** Если список изображений не задано для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член использует сведения о размере и маска, хранящиеся в [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуры, как описано в Windows SDK.  
  
##  <a name="getpalette"></a>CReBarCtrl::GetPalette  
 Извлекает текущую палитру управления главной панели.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, указывающий текущую палитру управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не исключение `HPALETTE`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>CReBarCtrl::GetRect  
 Реализует поведение сообщения Win32 [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469), как описано в Windows SDK.  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона в элементе управления главной панели.  
  
 `prc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, который получит границы области главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>CReBarCtrl::GetRowCount  
 Реализует поведение сообщения Win32 [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471), как описано в Windows SDK.  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** значение, представляющее число строк аппаратного контроллера управления в элементе управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>CReBarCtrl::GetRowHeight  
 Реализует поведение сообщения Win32 [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473), как описано в Windows SDK.  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uRow*  
 Отсчитываемый от нуля индекс, которого будут получены Высота полосы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** значение, представляющее высоту строки, в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>CReBarCtrl::GetTextColor  
 Реализует поведение сообщения Win32 [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475), как описано в Windows SDK.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет по умолчанию.  
  
##  <a name="gettooltips"></a>CReBarCtrl::GetToolTips  
 Реализует поведение сообщения Win32 [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477), как описано в Windows SDK.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что реализация MFC `GetToolTips` возвращает указатель на `CToolTipCtrl`, а не исключение `HWND`.  
  
##  <a name="hittest"></a>CReBarCtrl::HitTest  
 Реализует поведение сообщения Win32 [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494), как описано в Windows SDK.  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Параметры  
 *prbht*  
 Указатель на [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) структуры. Перед отправкой сообщения, **pt** член этой структуры должен быть инициализирован в точке, которая будет тестироваться в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс аппаратного контроллера управления в заданной точке или -1, если в точке без полос главной панели.  
  
##  <a name="idtoindex"></a>CReBarCtrl::IDToIndex  
 Реализует поведение сообщения Win32 [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496), как описано в Windows SDK.  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBandID*  
 Переданный идентификатор указанного диапазона, определяемые приложением **wID** членом [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуры при вставке диапазона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс (с нуля) диапазона, в случае успешного выполнения или -1, в противном случае. Если существуют повторяющиеся диапазон индексов, возвращается первый.  
  
##  <a name="insertband"></a>CReBarCtrl::InsertBand  
 Реализует поведение сообщения Win32 [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498), как описано в Windows SDK.  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 *uIndex*  
 Отсчитываемый от нуля индекс места вставки аппаратного контроллера управления. Если этот параметр имеет значение -1, элемент управления добавит новый диапазон от последней позиции.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структура, определяющая аппаратного контроллера управления для вставки. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARBANDINFO)` перед вызовом этой функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>CReBarCtrl::MaximizeBand  
 Изменяет размер диапазона в элементах управления главной панели до максимального размера.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) с `fIdeal` присваивается значение 0, как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>CReBarCtrl::MinimizeBand  
 Изменяет размер диапазона в элементах управления главной панели до наименьшего размера.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы свести к минимуму.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщения Win32 [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>CReBarCtrl::MoveBand  
 Реализует поведение сообщения Win32 [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504), как описано в Windows SDK.  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Параметры  
 *uFrom*  
 Отсчитываемый от нуля индекс аппаратного контроллера управления для перемещения.  
  
 *Автоподбор*  
 Отсчитываемый от нуля индекс позиции нового аппаратного контроллера управления. Значение этого параметра никогда не должно быть больше, чем число полос минус 1. Чтобы получить количество делений, вызовите [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="pushchevron"></a>CReBarCtrl::PushChevron  
 Реализует поведение сообщения Win32 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506), как описано в Windows SDK.  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона которого шеврона — для распространения.  
  
 `lAppValue`  
 Определяется 32-разрядное значение. В разделе `lAppValue` в [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) в Windows SDK.  
  
##  <a name="restoreband"></a>CReBarCtrl::RestoreBand  
 Изменяет размер диапазона в элементе управления главной панели, чтобы его идеального размера.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщения Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) с `fIdeal` равно 1, как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>CReBarCtrl::SetBandInfo  
 Реализует поведение сообщения Win32 [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508), как описано в Windows SDK.  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс аппаратного контроллера управления для получения новых параметров.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структура, определяющая аппаратного контроллера управления для вставки. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARBANDINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>CReBarCtrl::SetBandWidth  
 Задает ширину указанной полосы закрепленной в текущий элемент управления главной панели.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `uBand`|Отсчитываемый от нуля индекс области главной панели.|  
|[in] `cxWidth`|Новая ширина области главной панели, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_rebar`, который используется для доступа к текущего элемента управления главной панели. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается каждой зоны главной панели, чтобы иметь одинаковую ширину.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>CReBarCtrl::SetBarInfo  
 Реализует поведение сообщения Win32 [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513), как описано в Windows SDK.  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Параметры  
 `prbi`  
 Указатель на [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуру, содержащую сведения о задаваемых. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARINFO)` перед отправкой этого сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>CReBarCtrl::SetBkColor  
 Реализует поведение сообщения Win32 [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515), как описано в Windows SDK.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 **COLORREF** значение, представляющее новый цвет фона по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее предыдущий цвет фона по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 См. Дополнительные сведения о необходимости задать цвет фона и как задать значение по умолчанию.  
  
##  <a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme  
 Задает цветовую схему для кнопок на элементах управления главной панели.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуры, как описано в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 **COLORSCHEME** структура включает в себя цвет выделения кнопки и кнопки цвет тени.  
  
##  <a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle  
 Задает расширенные стили для текущего элемента управления главной панели.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `dwMask`|Побитовое сочетание (OR) флагов, указывающих, какие флаги в `dwStyleEx` применить параметр. Используйте один или несколько из следующих значений:<br /><br /> RBS_EX_SPLITTER: По умолчанию отображаться разделитель в нижней в горизонтальном режиме, а справа в вертикальной режиме.<br /><br /> RBS_EX_TRANSPARENT: Пересылать [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) сообщение родительского окна.|  
|[in] `dwStyleEx`|Побитовое сочетание (OR) флагов, определяющих стили для применения. Чтобы задать стиль, укажите флаг, используемый в `dwMask` параметра. Чтобы сбросить стиля, укажите двоичный нуль.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий расширенный стиль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) сообщение, которое описано в Windows SDK.  
  
##  <a name="setimagelist"></a>CReBarCtrl::SetImageList  
 Назначает списка изображений с элементом управления главной панели.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, содержащий список изображений для назначения элемента управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="setowner"></a>CReBarCtrl::SetOwner  
 Реализует поведение сообщения Win32 [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522), как описано в Windows SDK.  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на `CWnd` объекта, чтобы задать в качестве владельца элемента управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является текущим владельцем элемента управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует указатели на `CWnd` объектов для текущей и выбранной владельцу элемента управления главной панели, а не обрабатывает для windows.  
  
> [!NOTE]
>  Эта функция-член не изменяет фактическое родителя, который был задан при создании элемента управления; Вместо этого он отправляет сообщения уведомления окно, которое можно указать.  
  
##  <a name="setpalette"></a>CReBarCtrl::SetPalette  
 Реализует поведение сообщения Win32 [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520), как описано в Windows SDK.  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Параметры  
 *hPal*  
 `HPALETTE` , Указывающее новую палитру, которую будет использовать элемент управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, указывающий палитры предыдущего элемента управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не исключение `HPALETTE`.  
  
##  <a name="settextcolor"></a>CReBarCtrl::SetTextColor  
 Реализует поведение сообщения Win32 [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524), как описано в Windows SDK.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** цветов значение, представляющее новый текст `CReBarCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее на предыдущий цвет текста, связан с `CReBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Он предоставляется для поддержки гибкости цвет текста в элементе управления главной панели.  
  
##  <a name="settooltips"></a>CReBarCtrl::SetToolTips  
 Связывает всплывающая подсказка с элементом управления главной панели.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pToolTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта  
  
### <a name="remarks"></a>Примечания  
 Требуется уничтожить `CToolTipCtrl` объекта, когда вы завершили работу с ним.  
  
##  <a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme  
 Задает визуальный стиль элемента управления главной панели.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль главной панели, чтобы задать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) сообщения, как описано в Windows SDK.  
  
##  <a name="showband"></a>CReBarCtrl::ShowBand  
 Реализует поведение сообщения Win32 [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532), как описано в Windows SDK.  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона в элементе управления главной панели.  
  
 *fShow*  
 Указывает, если диапазон должны быть отображены или скрыты. Если это значение равно **TRUE**, отображается соответствующий диапазон. В противном случае диапазон будет скрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="sizetorect"></a>CReBarCtrl::SizeToRect  
 Реализует поведение сообщения Win32 [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534), как описано в Windows SDK.  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, который указывает на прямоугольник, который следует задавать управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CRect` объект в качестве параметра, а не `RECT` структуры.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


