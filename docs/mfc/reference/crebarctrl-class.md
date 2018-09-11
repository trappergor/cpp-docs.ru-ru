---
title: Класс CReBarCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 702cc504032f7c4702dcc1b317c517d53b9cccc9
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693884"
---
# <a name="crebarctrl-class"></a>Класс CReBarCtrl
Инкапсулирует функциональность элемента управления "главная панель ", который представляет собой контейнер для дочернего окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Создает объект `CReBarCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Помещает элемент управления "Главная панель" в режим перетаскивания и вставки.|  
|[CReBarCtrl::Create](#create)|Создает элемент управления "Главная панель" и присоединяет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::CreateEx](#createex)|Создает элемент управления "Главная панель" с указанным расширенные стили Windows и присоединяет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Удаляет диапазон из элемента управления "Главная панель".|  
|[CReBarCtrl::DragMove](#dragmove)|Обновляет позицию перетаскивания в элементе управления "Главная панель" после вызова `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Завершает операцию перетаскивания и вставки элемента управления "Главная панель".|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Извлекает границы диапазона.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Получает количество делений, в данный момент в элементе управления "Главная панель".|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Извлекает сведения о полосе, указанного в элементе управления "Главная панель".|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Извлекает границы диапазона.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Получает высоту элемента управления "Главная панель".|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Извлекает сведения о элемент управления "Главная панель" и список изображений, используемые в нем.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Получает цвет фона элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Извлекает [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) структуры, связанные с элементом управления главной панели.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Получает элемент управления "Главная панель" `IDropTarget` указатель на интерфейс.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Возвращает расширенный стиль текущего элемента управления "Главная панель".|  
|[CReBarCtrl::GetImageList](#getimagelist)|Извлекает список изображений, связанный с элементом управления главной панели.|  
|[CReBarCtrl::GetPalette](#getpalette)|Извлекает текущую палитру для элемента управления "Главная панель".|  
|[CReBarCtrl::GetRect](#getrect)|Получает ограничивающий прямоугольник для заданного аппаратного контроллера управления в элементе управления "Главная панель".|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Возвращает число строк аппаратного контроллера управления в элементе управления "Главная панель".|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Получает высоту указанной строки в элементе управления "Главная панель".|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Возвращает цвет текста элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Получает дескриптор управления любой всплывающей подсказки, связанной с элементом управления главной панели.|  
|[CReBarCtrl::HitTest](#hittest)|Определяет, какая часть элемента зону главной панели в определенный момент на экране, если в этот момент существует зону главной панели.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Преобразует диапазон идентификатор (ID) индекс диапазона в элементе управления "Главная панель".|  
|[CReBarCtrl::InsertBand](#insertband)|Вставляет новый аппаратного контроллера управления в элементе управления "Главная панель".|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Изменяет размер полосы в элементе управления "Главная панель" до максимального размера.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Изменяет размер полосы в элементе управления "Главная панель" до наименьшего размера.|  
|[CReBarCtrl::MoveBand](#moveband)|Перемещает полосе из одного индекса в другую.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Программным образом помещает шеврона.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Изменяет размер полосы в элементе управления "Главная панель", чтобы его идеального размера.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Задает характеристики существующего аппаратного контроллера управления в элементе управления "Главная панель".|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Задает ширину указанного диапазона закрепленной в текущий элемент управления "Главная панель".|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Задает характеристики элемента управления "Главная панель".|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Задает цвет фона элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Задает цветовую схему для кнопок в элементе управления "Главная панель".|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для текущего элемента управления "Главная панель".|  
|[CReBarCtrl::SetImageList](#setimagelist)|Задает список изображений элемента управления "Главная панель".|  
|[CReBarCtrl::SetOwner](#setowner)|Задает окно-владелец элемента управления "Главная панель".|  
|[CReBarCtrl::SetPalette](#setpalette)|Задает палитру текущего элемента управления "Главная панель".|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Задает цвет текста элемента управления "Главная панель" по умолчанию.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Связывает элемент управления всплывающей подсказки с элементом управления главной панели.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления "Главная панель".|  
|[CReBarCtrl::ShowBand](#showband)|Показывает или скрывает заданного аппаратного контроллера управления в элементе управления "Главная панель".|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Устанавливает размер элемента управления "Главная панель" в заданном прямоугольнике.|  
  
## <a name="remarks"></a>Примечания  
 Приложение, в котором размещен элемент управления "Главная панель" назначает дочернее окно, содержащихся в элемент управления "Главная панель" зону главной панели. Дочернее окно — это обычно другой общего элемента управления.  
  
 Элементы управления "Главная панель" содержат один или несколько делений. Каждый диапазон может содержать сочетание полосу захвата, битовая карта, текстовую метку и дочернего окна. Диапазон может содержать только один из этих элементов.  
  
 Элемент управления "Главная панель" может отображать дочернее окно через указанный изображение. Можно изменять все лентами главной панели управления, за исключением тех, которые используют RBBS_FIXEDSIZE стиль. Как вы изменение положения или размера зону главной панели управления, элемент управления "Главная панель" управляет размер и положение дочернего окна, назначенные этой аппаратного контроллера управления. Чтобы изменить размер или изменить порядок полосами в элементе управления, щелкните и перетащите полосу захвата аппаратного контроллера управления.  
  
 На следующем рисунке показан элемент управления "Главная панель", который имеет три полосы:  
  
-   Диапазон 0 содержит элемент управления toolbar плоский, прозрачным.  
  
-   Диапазон 1 содержит обе кнопки прозрачный раскрывающийся список стандартных и прозрачным.  
  
-   Аппаратного контроллера управления 2 содержит поле со списком и четыре стандартных кнопок.  
  
     ![Пример меню "Главная панель"](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Главной панели управления  
 Главной панели поддержки элементов управления:  
  
-   Списки изображений.  
  
-   Обработка сообщений.  
  
-   Пользовательская прорисовка функциональные возможности.  
  
-   Используя различные стили элемента управления помимо стандартного окна стили. Список этих стилей, см. в разделе [стили элемента управления главной панели](/windows/desktop/Controls/rebar-control-styles) в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [использование CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag  
 Реализует поведение сообщение Win32 [RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag), как описано в пакете Windows SDK.  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс строки, которые влияют на операции перетаскивания и вставки.  
  
 *dwPos*  
 Значение DWORD, содержащее начальный мыши координаты. Горизонтальная координата содержится в LOWORD, и содержится в HIWORD Вертикальная координата. Если передать (DWORD) -1, элемент управления "Главная панель" будет использовать положение указателя мыши, последнее время, когда поток элемента управления называется `GetMessage` или `PeekMessage`.  
  
##  <a name="create"></a>  CReBarCtrl::Create  
 Создает элемент управления "Главная панель" и присоединяет его к `CReBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Задает сочетание стилей элемента управления "Главная панель" применен к элементу управления. См. в разделе [стили элемента управления главной панели](/windows/desktop/Controls/rebar-control-styles) в пакете SDK Windows для получения списка поддерживаемых стили.  
  
 *Rect*  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер элемента управления "Главная панель".  
  
 *pParentWnd*  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления "Главная панель". Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор элемента управления "Главная панель" элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект был создан успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Создание элемента управления "Главная панель" в два этапа:  
  
1.  Вызовите [CReBarCtrl](#crebarctrl) для создания `CReBarCtrl` объекта.  
  
2.  Вызов этой функцией-членом, которая создает элемент управления "Главная панель" Windows и присоединяет его к `CReBarCtrl` объекта.  
  
 При вызове `Create`, общие элементы управления инициализируются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CReBarCtrl::CreateEx  
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
 *dwExStyle*  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.  
  
 *dwStyle*  
 Задает сочетание стилей элемента управления "Главная панель" применен к элементу управления. Список поддерживаемых стили, см. в разделе [стили элемента управления главной панели](/windows/desktop/Controls/rebar-control-styles) в пакете Windows SDK.  
  
 *Rect*  
 Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, которое является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.  
  
##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl  
 Создает объект `CReBarCtrl`.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Пример  
  См. в примере [CReBarCtrl::Create](#create).  
  
##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand  
 Реализует поведение сообщение Win32 [RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband), как описано в пакете Windows SDK.  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс диапазона для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если удален аппаратного контроллера управления; в противном случае значение равно нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>  CReBarCtrl::DragMove  
 Реализует поведение сообщение Win32 [RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove), как описано в пакете Windows SDK.  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 *dwPos*  
 Значение DWORD, содержащее новые координаты указателя мыши. Горизонтальная координата содержится в LOWORD, и содержится в HIWORD Вертикальная координата. Если передать (DWORD) -1, элемент управления "Главная панель" будет использовать положение указателя мыши, последнее время, когда поток элемента управления называется `GetMessage` или `PeekMessage`.  
  
##  <a name="enddrag"></a>  CReBarCtrl::EndDrag  
 Реализует поведение сообщение Win32 [RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag), как описано в пакете Windows SDK.  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders  
 Реализует поведение сообщение Win32 [RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders), как описано в пакете Windows SDK.  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс, для которого требуется получить границы диапазона.  
  
 *КНР*  
 Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая будет получать границы аппаратного контроллера управления. Если элемент управления "Главная панель" имеет стиль RBS_BANDBORDERS, каждый член этой структуры получит количество пикселей, в соответствующие части аппаратного контроллера управления, составляющих границы. Если элемент управления "Главная панель" не имеет стиль RBS_BANDBORDERS, только левый элемент этой структуры получит верные сведения. Описание стили элемента управления "Главная панель", см. в разделе [стили элемента управления "Главная панель"](/windows/desktop/Controls/rebar-control-styles) в пакете Windows SDK.  
  
##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount  
 Реализует поведение сообщение Win32 [RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount), как описано в пакете Windows SDK.  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество делений, назначенный элементу управления.  
  
##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo  
 Реализует поведение сообщение Win32 [RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) как описано в пакете Windows SDK.  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, для которого будут извлекаться данные.  
  
 *prbbi*  
 Указатель на [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) структуру для получения сведения о диапазоне. Необходимо задать `cbSize` член этой структуры для `sizeof(REBARBANDINFO)` и задайте `fMask` члена к элементам, которые необходимо получить перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins  
 Извлекает границы диапазона.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Параметры  
 *pMargins*  
 Указатель на [поля](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)структуру, которая будет получать сведения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует функциональные возможности [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins) сообщения, как описано в пакете Windows SDK.  
  
##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight  
 Получает высоту панели "Главная панель".  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее высоту в пикселях, элемента управления.  
  
##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo  
 Реализует поведение сообщение Win32 [RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo), как описано в пакете Windows SDK.  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *prbi*  
 Указатель на [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) структуру, которая получает сведения элемента управления "Главная панель". Необходимо задать *cbSize* член этой структуры для `sizeof(REBARINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor  
 Реализует поведение сообщение Win32 [RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor), как описано в пакете Windows SDK.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение COLORREF, представляют текущий цвет фона по умолчанию.  
  
##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme  
 Извлекает [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) структуры для элемента управления "Главная панель".  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 *lpcs*  
 Указатель на [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) структуры, как описано в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `COLORSCHEME` Структура включает цвет выделения кнопки и цвет тени кнопки.  
  
##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget  
 Реализует поведение сообщение Win32 [RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget), как описано в пакете Windows SDK.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) интерфейс.  
  
##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle  
 Возвращает расширенные стили текущего элемента управления "Главная панель".  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание (OR) флагов, указывающих расширенные стили. Флаги: RBS_EX_SPLITTER и RBS_EX_TRANSPARENT. Дополнительные сведения см. в разделе *dwMask* параметр [CReBarCtrl::SetExtendedStyle](#setextendedstyle) метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove) сообщения, который описан в пакете Windows SDK.  
  
##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList  
 Получает `CImageList` объект, связанный с элементом управления главной панели.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Возвращает значение NULL, если список изображений не задано для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член использует сведения о размере и маска, хранящиеся в [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) структуры, как описано в пакете Windows SDK.  
  
##  <a name="getpalette"></a>  CReBarCtrl::GetPalette  
 Извлекает текущую палитру для элемента управления "Главная панель".  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, указывающий текущую палитру для элемента управления "Главная панель".  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не HPALETTE.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>  CReBarCtrl::GetRect  
 Реализует поведение сообщение Win32 [RB_GETRECT](/windows/desktop/Controls/rb-getrect), как описано в пакете Windows SDK.  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс строки в элементе управления "Главная панель".  
  
 *КНР*  
 Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, который будет получать границы зону главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount  
 Реализует поведение сообщение Win32 [RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount), как описано в пакете Windows SDK.  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение целое число без знака, представляющее число строк аппаратного контроллера управления в элементе управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight  
 Реализует поведение сообщение Win32 [RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight), как описано в пакете Windows SDK.  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uRow*  
 Отсчитываемый от нуля индекс полосы, которая будет иметь получить высоту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение целое число без знака, представляющее высоту строки, в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor  
 Реализует поведение сообщение Win32 [RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor), как описано в пакете Windows SDK.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение COLORREF, представляют текущий цвет по умолчанию.  
  
##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips  
 Реализует поведение сообщение Win32 [RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips), как описано в пакете Windows SDK.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что реализация MFC `GetToolTips` возвращает указатель на `CToolTipCtrl`, вместо того чтобы HWND.  
  
##  <a name="hittest"></a>  CReBarCtrl::HitTest  
 Реализует поведение сообщение Win32 [RB_HITTEST](/windows/desktop/Controls/rb-hittest), как описано в пакете Windows SDK.  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Параметры  
 *prbht*  
 Указатель на [RBHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo) структуры. Перед отправкой сообщения, `pt` член этой структуры должен быть инициализирован в точке, которое будет проверяться в координатах клиентской области окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс диапазона в данной точке или значение -1, если нет аппаратного контроллера управления "Главная панель" в точке.  
  
##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex  
 Реализует поведение сообщение Win32 [RB_IDTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb774496), как описано в пакете Windows SDK.  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBandID*  
 Определяемый приложением идентификатор указанного диапазона, переданный `wID` членом [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) структуры при вставке диапазона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс (с нуля) аппаратного контроллера управления, если успешно, или значение -1, в противном случае. Если повторяющийся диапазон индексов существует, возвращается первый из них.  
  
##  <a name="insertband"></a>  CReBarCtrl::InsertBand  
 Реализует поведение сообщение Win32 [RB_INSERTBAND](/windows/desktop/Controls/rb-insertband), как описано в пакете Windows SDK.  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 *uIndex*  
 Отсчитываемый от нуля индекс места вставки аппаратного контроллера управления. Если установить этот параметр в значение -1, элемент управления будет добавлен новый диапазон в последнее расположение.  
  
 *prbbi*  
 Указатель на [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) структура, определяющая диапазон для вставки. Необходимо задать *cbSize* член этой структуры для `sizeof(REBARBANDINFO)` перед вызовом этой функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand  
 Изменяет размер полосы в элементе управления "Главная панель" до максимального размера.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) с `fIdeal` присвоено значение 0, как описано в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand  
 Изменяет размер полосы в элементе управления "Главная панель" до наименьшего размера.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы свести к минимуму.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband), как описано в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>  CReBarCtrl::MoveBand  
 Реализует поведение сообщение Win32 [RB_MOVEBAND](/windows/desktop/Controls/rb-moveband), как описано в пакете Windows SDK.  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Параметры  
 *uFrom*  
 Отсчитываемый от нуля индекс перемещаемого диапазона.  
  
 *Автоподбор*  
 Отсчитываемый от нуля индекс нового положения аппаратного контроллера управления. Значение этого параметра никогда не должно быть больше, чем число полос минус один. Чтобы получить количество делений, вызовите [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron  
 Реализует поведение сообщение Win32 [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron), как описано в пакете Windows SDK.  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс диапазона которого шеврон — для распространения.  
  
 *lAppValue*  
 Определяется 32-разрядное значение. См. в разделе *lAppValue* в [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) в пакете Windows SDK.  
  
##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand  
 Изменяет размер полосы в элементе управления "Главная панель", чтобы его идеального размера.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс аппаратного контроллера управления, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) с `fIdeal` значение 1, как описано в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo  
 Реализует поведение сообщение Win32 [RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo), как описано в пакете Windows SDK.  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс диапазона для получения новых параметров.  
  
 *prbbi*  
 Указатель на [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) структура, определяющая диапазон для вставки. Необходимо задать `cbSize` член этой структуры для `sizeof(REBARBANDINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth  
 Задает ширину указанного диапазона закрепленной в текущий элемент управления "Главная панель".  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *uBand*|Отсчитываемый от нуля индекс зону главной панели.|  
|[in] *cxWidth*|Новая ширина элемента зону главной панели, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth) сообщения, который описан в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_rebar`, который используется для доступа к текущего элемента управления "Главная панель". Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает каждого зону главной панели, чтобы иметь одинаковую ширину.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo  
 Реализует поведение сообщение Win32 [RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo), как описано в пакете Windows SDK.  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Параметры  
 *prbi*  
 Указатель на [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) структуру, содержащую сведения о задаваемых. Необходимо задать `cbSize` член этой структуры для `sizeof(REBARINFO)` перед отправкой этого сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor  
 Реализует поведение сообщение Win32 [RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor), как описано в пакете Windows SDK.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 *Среда CLR*  
 Значение COLORREF, представляющий новый цвет фона по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](/windows/desktop/gdi/colorref) значение, которое представляет предыдущий цвет фона по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 См. Дополнительные сведения о времени для задания фонового цвета и как задать значение по умолчанию.  
  
##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme  
 Задает цветовую схему для кнопок в элементе управления "Главная панель".  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 *lpcs*  
 Указатель на [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) структуры, как описано в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 `COLORSCHEME` Структура включает цвет выделения кнопки и цвет тени кнопки.  
  
##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle  
 Задает расширенные стили для текущего элемента управления "Главная панель".  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *dwMask*|Побитовое сочетание (OR) флагов, определяющих, какие флаги в *dwStyleEx* применить параметр. Используйте один или несколько из следующих значений:<br /><br /> RBS_EX_SPLITTER: По умолчанию отображать разделителя внизу в режиме по горизонтали, а справа в режиме по вертикали.<br /><br /> RBS_EX_TRANSPARENT: Пересылать [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) родительское окно.|  
|[in] *dwStyleEx*|Побитовое сочетание (OR) флагов, которые определяют стили для применения. Чтобы задать стиль, укажите флаг, используемый в *dwMask* параметра. Чтобы сбросить стиль, укажите двоичный нуль.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий расширенный стиль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle) сообщения, который описан в пакете Windows SDK.  
  
##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList  
 Назначает списка изображений в элемент управления "Главная панель".  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 *pImageList*  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, содержащий список изображений, чтобы назначить элементу управления "Главная панель".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="setowner"></a>  CReBarCtrl::SetOwner  
 Реализует поведение сообщение Win32 [RB_SETPARENT](/windows/desktop/Controls/rb-setparent), как описано в пакете Windows SDK.  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указатель на `CWnd` для которого устанавливается как владелец элемента управления "Главная панель".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является текущим владельцем элемента управления "Главная панель".  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует указатели на `CWnd` объектов для текущей и выбранной владелец элемента управления "Главная панель", а не обрабатывает для windows.  
  
> [!NOTE]
>  Эта функция-член не изменяет фактическое родителя, который был задан при создании элемента управления; Вместо этого он отправляет сообщения уведомления окна, указанную вами.  
  
##  <a name="setpalette"></a>  CReBarCtrl::SetPalette  
 Реализует поведение сообщение Win32 [RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette), как описано в пакете Windows SDK.  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Параметры  
 *hPal*  
 HPALETTE, указывающее новую палитру, которую будет использовать элемент управления "Главная панель".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, указывающий палитры предыдущего элемента управления "Главная панель".  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не HPALETTE.  
  
##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor  
 Реализует поведение сообщение Win32 [RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor), как описано в пакете Windows SDK.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 *Среда CLR*  
 Цвет значение COLORREF, представляющий новый текст в `CReBarCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [COLORREF](/windows/desktop/gdi/colorref) значение, представляющее цвет текста предыдущих связан с `CReBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Он предназначен для поддержки гибкости цвет текста в элементе управления "Главная панель".  
  
##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips  
 Связывает элемент управления всплывающей подсказки с элементом управления главной панели.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pToolTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта  
  
### <a name="remarks"></a>Примечания  
 Вы должны уничтожить `CToolTipCtrl` объекта, когда вы закончите с ним.  
  
##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme  
 Задает визуальный стиль элемента управления "Главная панель".  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 *pszSubAppName*  
 Указатель на строку Юникода, которая содержит визуальный стиль "Главная панель" для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует функциональные возможности [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme) сообщения, как описано в пакете Windows SDK.  
  
##  <a name="showband"></a>  CReBarCtrl::ShowBand  
 Реализует поведение сообщение Win32 [RB_SHOWBAND](/windows/desktop/Controls/rb-showband), как описано в пакете Windows SDK.  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *uBand*  
 Отсчитываемый от нуля индекс строки в элементе управления "Главная панель".  
  
 *fShow*  
 Указывает, если диапазон должны быть отображены или скрыты. Если это значение равно TRUE, будут показаны аппаратного контроллера управления. В противном случае диапазон будет скрыта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect  
 Реализует поведение сообщение Win32 [RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect), как описано в пакете Windows SDK.  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 *Rect*  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) , указывающий прямоугольник, который следует задавать элемент управления "Главная панель".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CRect` объект в качестве параметра, а не `RECT` структуры.  
  
## <a name="see-also"></a>См. также  
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


