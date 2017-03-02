---
title: "CReBarCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- rebar controls, CReBarCtrl class
- CReBarCtrl class
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
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
ms.openlocfilehash: c1da4de2897c74e9cb25bc060033f4bd43159174
ms.lasthandoff: 02/24/2017

---
# <a name="crebarctrl-class"></a>CReBarCtrl-класс
Инкапсулирует функциональность элемента управления "главная панель ", который представляет собой контейнер для дочернего окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Создает объект `CReBarCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Помещает элемент управления главной панели в режиме и перетащите.|  
|[CReBarCtrl::Create](#create)|Создает элемент управления главной панели и присоединяет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::CreateEx](#createex)|Создает элемент управления главной панели с указанным расширенные стили Windows и присоединяет его к `CReBarCtrl` объекта.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Удаляет диапазон с элементом управления главной панели.|  
|[CReBarCtrl::DragMove](#dragmove)|Обновляет перетащите позицию в элементе управления "Главная панель" после вызова `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Завершает работу и перетащите элемент управления главной панели.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Получает границы диапазона.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Извлекает число полосами в данный момент в элементе управления главной панели.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Извлекает сведения о указанного диапазона в элементах управления главной панели.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Получает поля полосе.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Получает высоту элемента управления главной панели.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Извлекает сведения о главной панели управления и список изображений, которые он использует.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Получает цвет фона элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Извлекает [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуры, связанный с элементом управления главной панели.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Возвращает элемент управления главной панели `IDropTarget` указатель на интерфейс.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Получает расширенный стиль текущего элемента управления главной панели.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Получает список изображений, связанных с элементом управления главной панели.|  
|[CReBarCtrl::GetPalette](#getpalette)|Получает текущую палитру управления главной панели.|  
|[CReBarCtrl::GetRect](#getrect)|Возвращает ограничивающий прямоугольник для заданного диапазона в элементах управления главной панели.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Получает число строк внешнего управления главной панели.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Получает высоту указанной строки в элементах управления главной панели.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Возвращает цвет текста элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Получает дескриптор для любого управления всплывающей подсказки, связанный с элементом управления главной панели.|  
|[CReBarCtrl::HitTest](#hittest)|Определяет, какая часть области главной панели в определенный момент на экране, если в этот момент существует области главной панели.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Преобразует диапазон идентификатор (ID) индекс диапазона в элементах управления главной панели.|  
|[CReBarCtrl::InsertBand](#insertband)|Вставляет новую группу в элементах управления главной панели.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Изменяет размер диапазона в элементах управления главной панели до максимального размера.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Изменяет размер диапазона в элементах управления главной панели до наименьшего размера.|  
|[CReBarCtrl::MoveBand](#moveband)|Перемещает диапазон из одного индекса в другую.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Программно помещает шеврона.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Изменяет размер диапазона в элементах управления главной панели идеальный размер.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Задает характеристики существующей внешней в элементах управления главной панели.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Задает указанный диапазон закрепленной в текущий элемент управления главной панели.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Задает характеристики контейнер элементов управления.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Задает цвет фона элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Задает цветовую схему для кнопок элемента управления главной панели.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили текущего элемента управления главной панели.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Задает список изображений элемента управления главной панели.|  
|[CReBarCtrl::SetOwner](#setowner)|Задает элемент управления главной панели окна-владельца.|  
|[CReBarCtrl::SetPalette](#setpalette)|Задает текущую палитру управления главной панели.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Задает цвет текста элемента управления главной панели по умолчанию.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Связывает управления всплывающей подсказки с элементом управления главной панели.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления главной панели.|  
|[CReBarCtrl::ShowBand](#showband)|Показывает или скрывает заданного диапазона в элементах управления главной панели.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Помещает элемент управления главной панели в заданном прямоугольнике.|  
  
## <a name="remarks"></a>Примечания  
 Приложения, в которой находится элемент управления "Главная панель" назначает дочернего окна, содержащихся в контейнер элементов управления в области главной панели. Дочернее окно является обычно другой общий элемент управления.  
  
 Элементы управления главной панели содержит один или несколько полосы. Каждый диапазон может содержать сочетание полосу захвата, точечный рисунок, текстовую метку и дочернего окна. Диапазон может содержать только один из этих элементов.  
  
 Контейнер элементов управления можно отобразить дочернее окно по указанным фоновый рисунок. Можно изменять все лентами главной панели управления, за исключением тех, которые используют **RBBS_FIXEDSIZE** стиль. Как изменение положения или размера области главной панели управления, элемент управления главной панели управляет размер и положение дочернего окна, назначенные этой внешней. Чтобы изменить размер или изменить порядок полосами в элементе управления, щелкните и перетащите полосы захвата.  
  
 На следующем рисунке показано контейнер элементов управления, который имеет три полосы:  
  
-   Диапазон 0 содержит элемент управления toolbar плоский, прозрачным.  
  
-   Диапазон 1 содержит обе кнопки прозрачный раскрывающийся список стандартных и прозрачной.  
  
-   Полоса 2 содержит поле со списком и четыре стандартных кнопок.  
  
     ![Пример меню "Главная панель"](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Элемент управления главной панели  
 Главной панели поддержка элементов управления:  
  
-   Списки изображений.  
  
-   Обработка сообщений.  
  
-   Пользовательская прорисовка функциональные возможности.  
  
-   Различные стили элемента управления помимо стандартного окна стили. Список этих стилей см. в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [CReBarCtrl с помощью](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namebegindraga--crebarctrlbegindrag"></a><a name="begindrag"></a>CReBarCtrl::BeginDrag  
 Реализует поведение сообщение Win32 [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс полосы, которая влияет на операции и перетаскивания.  
  
 `dwPos`  
 A `DWORD` значение, которое содержит начальные координаты мыши. Горизонтальная координата содержится в LOWORD и содержится в HIWORD Вертикальная координата. Если передать `(DWORD)-1`, контейнер элементов управления будет использоваться позиция мыши последнего элемента управления потоком, который называется **GetMessage** или **PeekMessage**.  
  
##  <a name="a-namecreatea--crebarctrlcreate"></a><a name="create"></a>CReBarCtrl::Create  
 Создает элемент управления главной панели и присоединяет его к `CReBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стилей элемента управления главной панели, примененный к элементу управления. В разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список поддерживаемых стили.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер элемента управления главной панели.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления главной панели. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления главной панели управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создайте контейнер элементов управления в два этапа:  
  
1.  Вызов [CReBarCtrl](#crebarctrl) для создания `CReBarCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает контейнер элементов управления Windows и присоединяет его к `CReBarCtrl` объекта.  
  
 При вызове **создать**, общие элементы управления инициализируются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#3;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--crebarctrlcreateex"></a><a name="createex"></a>CReBarCtrl::CreateEx  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает сочетание стилей элемента управления главной панели, примененный к элементу управления. Список поддерживаемых стили см [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namecrebarctrla--crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl  
 Создает объект `CReBarCtrl`.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Пример  
  В примере показано [CReBarCtrl::Create](#create).  
  
##  <a name="a-namedeletebanda--crebarctrldeleteband"></a><a name="deleteband"></a>CReBarCtrl::DeleteBand  
 Реализует поведение сообщение Win32 [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс удаляемого диапазона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если удалена диапазона; в противном случае — нуль.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#4;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="a-namedragmovea--crebarctrldragmove"></a><a name="dragmove"></a>CReBarCtrl::DragMove  
 Реализует поведение сообщение Win32 [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `dwPos`  
 A `DWORD` значение, содержащее новые координаты курсора. Горизонтальная координата содержится в LOWORD и содержится в HIWORD Вертикальная координата. Если передать `(DWORD)-1`, контейнер элементов управления будет использоваться позиция мыши последнего элемента управления потоком, который называется **GetMessage** или **PeekMessage**.  
  
##  <a name="a-nameenddraga--crebarctrlenddrag"></a><a name="enddrag"></a>CReBarCtrl::EndDrag  
 Реализует поведение сообщение Win32 [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void EndDrag();
```  
  
##  <a name="a-namegetbandbordersa--crebarctrlgetbandborders"></a><a name="getbandborders"></a>CReBarCtrl::GetBandBorders  
 Реализует поведение сообщение Win32 [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона, для которого будет извлекаться границы.  
  
 `prc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, получит границы диапазона. Если для элемента управления "Главная панель" **RBS_BANDBORDERS** стиль, каждый член этой структуры будет получать количество пикселей, на стороне соответствующего диапазона, составляющих границы. Если элемент управления "Главная панель" не имеет **RBS_BANDBORDERS** стиля только левой член этой структуры получает допустимые данные. Описание стили элемента управления главной панели, в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbandcounta--crebarctrlgetbandcount"></a><a name="getbandcount"></a>CReBarCtrl::GetBandCount  
 Реализует поведение сообщение Win32 [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество делений, назначенный элементу управления.  
  
##  <a name="a-namegetbandinfoa--crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>CReBarCtrl::GetBandInfo  
 Реализует поведение сообщение Win32 [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона, для которого будут извлекаться данные.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуру для получения сведения о диапазоне. Необходимо задать `cbSize` структуры для `sizeof(REBARBANDINFO)` и **fMask** элемента для элементов, которые необходимо получить перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namegetbandmarginsa--crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>CReBarCtrl::GetBandMargins  
 Получает поля диапазона.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Параметры  
 *pMargins*  
 Указатель на [поля](http://msdn.microsoft.com/library/windows/desktop/bb773244)структуру, которая будет получать данные.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbarheighta--crebarctrlgetbarheight"></a><a name="getbarheight"></a>CReBarCtrl::GetBarHeight  
 Получает высоту панели главной панели.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее высоту в точках управления.  
  
##  <a name="a-namegetbarinfoa--crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>CReBarCtrl::GetBarInfo  
 Реализует поведение сообщение Win32 [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `prbi`  
 Указатель на [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуру, которая будет получать данные управления главной панели. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namegetbkcolora--crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>CReBarCtrl::GetBkColor  
 Реализует поведение сообщение Win32 [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет фона по умолчанию.  
  
##  <a name="a-namegetcolorschemea--crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme  
 Извлекает [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуру для управления главной панели.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 **COLORSCHEME** структура включает кнопку цвет выделения и кнопку Цвет тени.  
  
##  <a name="a-namegetdroptargeta--crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>CReBarCtrl::GetDropTarget  
 Реализует поведение сообщение Win32 [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса.  
  
##  <a name="a-namegetextendedstylea--crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle  
 Возвращает расширенные стили текущего элемента управления главной панели.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание (или) флагов, указывающих расширенные стили. Флаги, `RBS_EX_SPLITTER` и `RBS_EX_TRANSPARENT`. Дополнительные сведения см. в разделе `dwMask` параметр [CReBarCtrl::SetExtendedStyle](#setextendedstyle) метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--crebarctrlgetimagelist"></a><a name="getimagelist"></a>CReBarCtrl::GetImageList  
 Возвращает `CImageList` объект, связанный с элементом управления главной панели.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Возвращает **NULL** Если список изображений не задано для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член использует сведения о размере и маска, хранящиеся в [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpalettea--crebarctrlgetpalette"></a><a name="getpalette"></a>CReBarCtrl::GetPalette  
 Получает текущую палитру управления главной панели.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, указывающий текущую палитру управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не `HPALETTE`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#5;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="a-namegetrecta--crebarctrlgetrect"></a><a name="getrect"></a>CReBarCtrl::GetRect  
 Реализует поведение сообщение Win32 [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона в элементе управления главной панели.  
  
 `prc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, получит границы области главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl №&6;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="a-namegetrowcounta--crebarctrlgetrowcount"></a><a name="getrowcount"></a>CReBarCtrl::GetRowCount  
 Реализует поведение сообщение Win32 [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** значение, представляющее номер строки внешнего элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="a-namegetrowheighta--crebarctrlgetrowheight"></a><a name="getrowheight"></a>CReBarCtrl::GetRowHeight  
 Реализует поведение сообщение Win32 [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uRow*  
 Отсчитываемый от нуля индекс полосы, которая будет иметь высоту, извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** значение, представляющее высоту строк, в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl №&8;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="a-namegettextcolora--crebarctrlgettextcolor"></a><a name="gettextcolor"></a>CReBarCtrl::GetTextColor  
 Реализует поведение сообщение Win32 [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, которое представляет текущий цвет текста по умолчанию.  
  
##  <a name="a-namegettooltipsa--crebarctrlgettooltips"></a><a name="gettooltips"></a>CReBarCtrl::GetToolTips  
 Реализует поведение сообщение Win32 [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что реализация MFC `GetToolTips` возвращает указатель на `CToolTipCtrl`, а не `HWND`.  
  
##  <a name="a-namehittesta--crebarctrlhittest"></a><a name="hittest"></a>CReBarCtrl::HitTest  
 Реализует поведение сообщение Win32 [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Параметры  
 *prbht*  
 Указатель на [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) структуры. Перед отправкой сообщения, **pt** член этой структуры должен быть инициализирован до точки, которое будет проверяться в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс диапазона на определенный момент или -1, если в точке без полос главной панели.  
  
##  <a name="a-nameidtoindexa--crebarctrlidtoindex"></a><a name="idtoindex"></a>CReBarCtrl::IDToIndex  
 Реализует поведение сообщение Win32 [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *uBandID*  
 Переданный идентификатор указанного диапазона, определяемые приложением **wID** членом [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуры при вставке диапазона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс (с нуля) диапазона, в случае успешного выполнения или значение -1, в противном случае. Если существуют повторяющиеся внешнего индексов, возвращается первый из них.  
  
##  <a name="a-nameinsertbanda--crebarctrlinsertband"></a><a name="insertband"></a>CReBarCtrl::InsertBand  
 Реализует поведение сообщение Win32 [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 *uIndex*  
 Отсчитываемый от нуля индекс места вставки полосе. Если этот параметр равен -1, элемент управления будет добавлен новый диапазон в последнее расположение.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структура, определяющая диапазона для вставки. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARBANDINFO)` перед вызовом этой функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl №&9;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="a-namemaximizebanda--crebarctrlmaximizeband"></a><a name="maximizeband"></a>CReBarCtrl::MaximizeBand  
 Изменяет размер диапазона в элементах управления главной панели до максимального размера.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) с `fIdeal` значение 0, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="a-nameminimizebanda--crebarctrlminimizeband"></a><a name="minimizeband"></a>CReBarCtrl::MinimizeBand  
 Изменяет размер диапазона в элементах управления главной панели до наименьшего размера.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона, чтобы свести к минимуму.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&11;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="a-namemovebanda--crebarctrlmoveband"></a><a name="moveband"></a>CReBarCtrl::MoveBand  
 Реализует поведение сообщение Win32 [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Параметры  
 *uFrom*  
 Отсчитываемый от нуля индекс перемещаемого диапазона.  
  
 *Автоподбор*  
 Отсчитываемый от нуля индекс новое положение диапазона. Значение этого параметра никогда не должно быть больше, чем число полос минус один. Чтобы получить количество делений, вызовите [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namepushchevrona--crebarctrlpushchevron"></a><a name="pushchevron"></a>CReBarCtrl::PushChevron  
 Реализует поведение сообщение Win32 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона которого шеврона — будет перемещен.  
  
 `lAppValue`  
 Определяется 32-разрядное значение. В разделе `lAppValue` в [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namerestorebanda--crebarctrlrestoreband"></a><a name="restoreband"></a>CReBarCtrl::RestoreBand  
 Изменяет размер диапазона в элементах управления главной панели идеальный размер.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона, чтобы развернуть.  
  
### <a name="remarks"></a>Примечания  
 Реализует поведение сообщение Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) с `fIdeal` равным 1, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="a-namesetbandinfoa--crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>CReBarCtrl::SetBandInfo  
 Реализует поведение сообщение Win32 [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона для получения новых параметров.  
  
 `prbbi`  
 Указатель на [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структура, определяющая диапазона для вставки. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARBANDINFO)` перед отправкой этого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#13;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="a-namesetbandwidtha--crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>CReBarCtrl::SetBandWidth  
 Задает указанный диапазон закрепленной в текущий элемент управления главной панели.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uBand`|Отсчитываемый от нуля индекс области главной панели.|  
|[in] `cxWidth`|Новая ширина области главной панели, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_rebar`, который используется для доступа к текущим элементом управления главной панели. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается каждой области главной панели, чтобы иметь одинаковую ширину.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="a-namesetbarinfoa--crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>CReBarCtrl::SetBarInfo  
 Реализует поведение сообщение Win32 [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Параметры  
 `prbi`  
 Указатель на [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) структуру, содержащую сведения, чтобы задать. Необходимо задать `cbSize` членом этой структуры `sizeof(REBARINFO)` перед отправкой этого сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#14;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="a-namesetbkcolora--crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>CReBarCtrl::SetBkColor  
 Реализует поведение сообщение Win32 [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 **COLORREF** значение, которое представляет новый цвет фона по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее на предыдущий цвет фона по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 См. Дополнительные сведения о времени для задания цвета фона и как задать значение по умолчанию.  
  
##  <a name="a-namesetcolorschemea--crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme  
 Задает цветовую схему для кнопок элемента управления главной панели.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 **COLORSCHEME** структура включает кнопку цвет выделения и кнопку Цвет тени.  
  
##  <a name="a-namesetextendedstylea--crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle  
 Задает расширенные стили текущего элемента управления главной панели.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwMask`|Побитовое сочетание (или) флаги, указывающие, какие флаги в `dwStyleEx` применить параметр. Используйте один или несколько из следующих значений:<br /><br /> RBS_EX_SPLITTER: По умолчанию, показывают разделитель внизу в горизонтальном режиме и справа в вертикальное отображение.<br /><br /> RBS_EX_TRANSPARENT: Пересылка [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) сообщение родительского окна.|  
|[in] `dwStyleEx`|Побитовое сочетание (или) флагов, определяющих стили вступили в силу. Чтобы задать стиль, укажите флаг, используемый в `dwMask` параметр. Чтобы сбросить параметры стиля, укажите двоичного нуля.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий расширенный стиль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--crebarctrlsetimagelist"></a><a name="setimagelist"></a>CReBarCtrl::SetImageList  
 Назначает списка изображений с элементом управления главной панели.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, содержащий список изображений для назначения элемента управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namesetownera--crebarctrlsetowner"></a><a name="setowner"></a>CReBarCtrl::SetOwner  
 Реализует поведение сообщение Win32 [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на `CWnd` объект, чтобы задать в качестве владельца элемента управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является текущим владельцем элемента управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует указатели на `CWnd` объектов для текущей и выбранной владельца элемента управления главной панели, а не обрабатывает к windows.  
  
> [!NOTE]
>  Эта функция-член не изменяет фактическое родителя, который был установлен при создании элемента управления; Вместо этого он отправляет сообщения уведомления окно, которое можно указать.  
  
##  <a name="a-namesetpalettea--crebarctrlsetpalette"></a><a name="setpalette"></a>CReBarCtrl::SetPalette  
 Реализует поведение сообщение Win32 [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Параметры  
 *hPal*  
 `HPALETTE` , Указывающее новую палитру, используемую управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CPalette](../../mfc/reference/cpalette-class.md) объект, задающий предыдущего палитры элемента управления главной панели.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CPalette` объект в качестве возвращаемого значения, а не `HPALETTE`.  
  
##  <a name="a-namesettextcolora--crebarctrlsettextcolor"></a><a name="settextcolor"></a>CReBarCtrl::SetTextColor  
 Реализует поведение сообщение Win32 [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** значение, представляющее текст новый цвет в `CReBarCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) на предыдущий цвет текста, представляющее связанный с `CReBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Он обеспечивает поддержку гибкость цвет текста в элементе управления главной панели.  
  
##  <a name="a-namesettooltipsa--crebarctrlsettooltips"></a><a name="settooltips"></a>CReBarCtrl::SetToolTips  
 Связывает управления всплывающей подсказки с элементом управления главной панели.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pToolTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта  
  
### <a name="remarks"></a>Примечания  
 Вы должны уничтожить `CToolTipCtrl` объекта, когда вы завершили работу с ним.  
  
##  <a name="a-namesetwindowthemea--crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme  
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
 Эта функция-член эмулирует работу [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowbanda--crebarctrlshowband"></a><a name="showband"></a>CReBarCtrl::ShowBand  
 Реализует поведение сообщение Win32 [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `uBand`  
 Отсчитываемый от нуля индекс диапазона в элементе управления главной панели.  
  
 *fShow*  
 Указывает, если диапазон должны быть отображены или скрыты. Если это значение равно **TRUE**, будут показаны полосе. В противном случае — диапазон будет скрыта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namesizetorecta--crebarctrlsizetorect"></a><a name="sizetorect"></a>CReBarCtrl::SizeToRect  
 Реализует поведение сообщение Win32 [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта, которая задает прямоугольник, иметь соответствующий размер элемента управления главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция-член использует `CRect` объект в качестве параметра, а не `RECT` структуры.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



