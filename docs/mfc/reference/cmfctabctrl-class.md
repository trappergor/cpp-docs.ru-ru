---
title: "Класс CMFCTabCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs: C++
helpviewer_keywords:
- CMFCTabCtrl [MFC], ActivateMDITab
- CMFCTabCtrl [MFC], AllowDestroyEmptyTabbedPane
- CMFCTabCtrl [MFC], AutoSizeWindow
- CMFCTabCtrl [MFC], CalcRectEdit
- CMFCTabCtrl [MFC], Create
- CMFCTabCtrl [MFC], EnableActiveTabCloseButton
- CMFCTabCtrl [MFC], EnableInPlaceEdit
- CMFCTabCtrl [MFC], EnableTabDocumentsMenu
- CMFCTabCtrl [MFC], EnsureVisible
- CMFCTabCtrl [MFC], GetDocumentIcon
- CMFCTabCtrl [MFC], GetFirstVisibleTabNum
- CMFCTabCtrl [MFC], GetResizeMode
- CMFCTabCtrl [MFC], GetScrollBar
- CMFCTabCtrl [MFC], GetTabArea
- CMFCTabCtrl [MFC], GetTabMaxWidth
- CMFCTabCtrl [MFC], GetTabsHeight
- CMFCTabCtrl [MFC], GetTabsRect
- CMFCTabCtrl [MFC], GetWndArea
- CMFCTabCtrl [MFC], HideActiveWindowHorzScrollBar
- CMFCTabCtrl [MFC], HideInactiveWindow
- CMFCTabCtrl [MFC], HideNoTabs
- CMFCTabCtrl [MFC], HideSingleTab
- CMFCTabCtrl [MFC], IsActiveInMDITabGroup
- CMFCTabCtrl [MFC], IsActiveTabBoldFont
- CMFCTabCtrl [MFC], IsActiveTabCloseButton
- CMFCTabCtrl [MFC], IsDrawFrame
- CMFCTabCtrl [MFC], IsFlatFrame
- CMFCTabCtrl [MFC], IsFlatTab
- CMFCTabCtrl [MFC], IsLeftRightRounded
- CMFCTabCtrl [MFC], IsMDITabGroup
- CMFCTabCtrl [MFC], IsOneNoteStyle
- CMFCTabCtrl [MFC], IsSharedScroll
- CMFCTabCtrl [MFC], IsTabDocumentsMenu
- CMFCTabCtrl [MFC], IsVS2005Style
- CMFCTabCtrl [MFC], ModifyTabStyle
- CMFCTabCtrl [MFC], OnDragEnter
- CMFCTabCtrl [MFC], OnDragOver
- CMFCTabCtrl [MFC], OnShowTabDocumentsMenu
- CMFCTabCtrl [MFC], SetActiveInMDITabGroup
- CMFCTabCtrl [MFC], SetActiveTab
- CMFCTabCtrl [MFC], SetActiveTabBoldFont
- CMFCTabCtrl [MFC], SetDrawFrame
- CMFCTabCtrl [MFC], SetFlatFrame
- CMFCTabCtrl [MFC], SetImageList
- CMFCTabCtrl [MFC], SetResizeMode
- CMFCTabCtrl [MFC], SetTabMaxWidth
- CMFCTabCtrl [MFC], StopResize
- CMFCTabCtrl [MFC], SynchronizeScrollBar
- CMFCTabCtrl [MFC], m_bEnableActivate
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1aa415846d8f504ef907bf4e9a041b86062853cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
`CMFCTabCtrl` Класс предоставляет функциональные возможности для элемента управления tab. Элемент управления "вкладка" отображает закрепляемое окно с плоскими или трехмерными вкладками в верхней или нижней части. Вкладки могут отображать текст и изображение и могут изменять цвет, когда активны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Конструктор по умолчанию.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|Отображает указанную вкладку текущей вкладок и устанавливает фокус ввода на этой вкладке.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Указывает, является ли платформа для изменения размера клиентской области окна всех вкладку элемента управления при элемент пользовательского интерфейса элемента управления tab.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Уменьшение объема размер области указанной вкладки. (Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Создает набор вкладок и прикрепляет его к `CMFCTabCtrl` объекта.|  
|`CMFCTabCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Показывает или скрывает кнопку Закрыть ( **X**) на активной вкладке.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Включает или отключает меток вкладок для редактирования. (Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Заменяет две кнопки, прокрутите окно вкладки с кнопкой, которая открывает меню окон с вкладками.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Обеспечивает видимость вкладки.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Возвращает символ, который связан с вкладки в всплывающего меню окон с вкладками.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Возвращает индекс первой вкладки, который является видимым в текущий набор вкладок.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Получает значение, указывающее способ изменения размеров текущего элемента управления tab.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Извлекает указатель на объект строки прокрутки, связанный с элементом управления tab.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Возвращает прямоугольник, ограничивающий область метку вкладки в верхней или нижней части вкладок элемента управления. (Переопределяет [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Возвращает вкладку, содержащую указанную точку. (Переопределяет [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Возвращает максимальную ширину вкладки.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Получает высоту области вкладок текущего элемента управления tab.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Возвращает прямоугольник, ограничивающий область вкладки текущего элемента управления tab. (Переопределяет [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Возвращает границы клиентской области текущего элемента управления tab.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Скрывает горизонтальную полосу прокрутки, если таковая имеется, активного окна.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Указывает, является ли платформа для отображения неактивных вкладку элемента управления windows.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Включает или отключает Рисование области вкладки, если нет видимых вкладок.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Включает или отключает Рисование вкладки, при наличии одного окна с вкладками. (Переопределяет [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Указывает, является ли текущей вкладки элемента управления вкладками активной вкладки в нескольких группу вкладок документов интерфейса.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Указывает, отображается ли для полужирный шрифт текста активной вкладки.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Указывает, является ли кнопка «Закрыть» ( **X**) отображается на активной вкладке или в правом верхнем углу области вкладок.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Указывает ли окна с вкладками Рисование прямоугольника рамки вокруг внедренные панелей.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Указывает, является ли рамку вокруг области вкладок плоским или трехмерным.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Указывает, является ли вид вкладок в текущем элементе управления вкладками плоских или нет.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Указывает, округляются ли внешний вид левой и правой части вкладки в текущем элементе управления вкладками.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Указывает, содержится ли текущий набор вкладок в клиентской области окна многодокументного интерфейса.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Указывает, отображается ли текущий набор вкладок в стиле Microsoft OneNote.|  
|`CMFCTabCtrl::IsPtInTabArea`|Определяет, является ли точка в области вкладок. (Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Указывает, имеет ли текущий набор вкладок полосы прокрутки прокрутки вкладками в группу.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Указывает, отображаются ли вкладок элемента управления кнопки прокрутки или кнопку, которая отображает меню окон с вкладками.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Указывает, отображаются ли вкладки в стиле Visual Studio .NET 2005.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Определяет внешний вид вкладок в текущем элементе управления вкладками.|  
|`CMFCTabCtrl::MoveTab`|Перемещение вкладки в другое положение вкладки. (Переопределяет [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|Вызывается платформой, когда курсор сначала перетаскивается в окне элемента управления tab.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Вызывается платформой при выполнении операции перетаскивания при перемещении указателя мыши по окна цели перетаскивания. (Переопределяет [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Отображает всплывающее меню окон с вкладками, ожидает, когда пользователь выбирает вкладку и делает выбранная вкладка активной вкладки.|  
|`CMFCTabCtrl::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Повторно вычисляет внутренний макет элемента управления tab. (Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Задает в качестве активной вкладки в нескольких группу вкладок документов интерфейса текущей вкладки элемента управления вкладками.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Активирует вкладку. (Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Включает или отключает использование полужирного шрифта для активных вкладок.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Включает или отключает drawinga кадра прямоугольник вокруг внедренные строки.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Указывает, следует ли Рисование плоской или объемной рамки вокруг области вкладок.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Задает список изображений. (Переопределяет [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Задает способ изменения размеров текущего управления "Вкладка" и затем повторно отображает элемент управления.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|Указывает ширину максимальное вкладку в окно с вкладками.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Завершает текущую операцию изменения размера для элемента управления tab.|  
|`CMFCTabCtrl::SwapTabs`|Меняет местами пару вкладок. (Переопределяет [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Рисует горизонтальную полосу прокрутки для элемента управления tab, отображает плоский вкладки.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Запрещает активное представление теряет фокусировку включением и вставить новую вкладку.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCTabCtrl` Поддерживает класс:  
  
-   На вкладке Стили элемента управления, включая 3D, плоские и плоский с общей горизонтальной полосы прокрутки.  
  
-   Вкладки, расположенные в верхней или нижней части окна.  
  
-   Вкладки, отображающие текст, изображения, или текст и изображения.  
  
-   Вкладки, на которых изменение цвета при активной вкладке.  
  
-   Границы изменения размера для регулируемой вкладок.  
  
-   Отделяемые окон с вкладками.  
  
 `CMFCTabCtrl` Класс может использоваться с диалоговым окном, но он предназначен для приложений, использующих закрепления элемента управления полосы как [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] и [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Дополнительные сведения см. в разделе [класс CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
 Выполните следующие шаги для добавления изменяемого размера, закрепление элемента управления tab в приложении.  
  
1.  Создайте экземпляр класса [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Вызовите [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Используйте [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) или [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) Добавление новых вкладок.  
  
4.  Вызовите [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) , чтобы текущего закрепления элемента управления tab можно закрепить окно главного фрейма.  
  
5.  Вызовите [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) для закрепления окна с вкладками в главного фрейма.  
  
 Пример того, как создать окно с вкладками в закрепляемую панель элементов управления см. в разделе [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md). Для использования `CMFCTabCtrl` -закрепления элемента управления, создавать `CMFCTabCtrl` объекта, а затем вызвать [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCTabCtrl` класса, чтобы настроить `CMFCTabCtrl` объекта. Примере объясняется, как добавить вкладку, Показать Кнопка «Закрыть» на активной вкладке, включите меток вкладок для редактирования и отображения всплывающего меню окна с вкладками меток. Данный пример является частью [образец сбор данных о состоянии](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 Отображает указанную вкладку текущей вкладок и устанавливает фокус ввода на этой вкладке.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTab`  
 Отсчитываемый от нуля индекс вкладки для отображения или -1, чтобы указать активной вкладки.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 Указывает, является ли платформа для изменения размера клиентской области окна всех вкладку элемента управления при элемент пользовательского интерфейса элемента управления tab.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoSize`  
 `TRUE`для автоматического изменения размера вкладки элемента управления windows; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
 Создает набор вкладок и прикрепляет его к `CMFCTabCtrl` объекта.  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `style`  
 Стиль элемента управления tab. Дополнительные сведения см. в разделе "Замечания".  
  
 [in] `rect`  
 Прямоугольник, ограничивающий набор вкладок.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно. Значение не должно быть равно `NULL`.  
  
 [in] `nID`  
 Идентификатор набора вкладок.  
  
 [in] `location`  
 Расположение вкладок. Значение по умолчанию — `LOCATION_BOTTOM`. Дополнительные сведения см. в разделе "Замечания".  
  
 [in] `bCloseBtn`  
 `TRUE`для отображения кнопки Закрыть на вкладке. в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице описаны значения, можно указать для `style` параметра.  
  
|Стиль|Описание:|  
|-----------|-----------------|  
|STYLE_3D|Создает набор вкладок с объемный вид.|  
|STYLE_FLAT|Создает набор вкладок с плоскими вкладок.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Создает набор вкладок с плоскими вкладки и полосы прокрутки, можно прокрутить вкладки, если они будут обрезаны родительское окно.|  
|STYLE_3D_ONENOTE|Создает элемент управления вкладки в стиле Microsoft OneNote.|  
|STYLE_3D_VS2005|Создает элемент управления вкладки в стиле Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED|Создает набор вкладок с закругленными вкладки в стиле Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED_SCROLL|Создает набор вкладок с закругленными вкладки и кнопки прокрутки в стиле Microsoft Visual Studio 2005.|  
  
 В следующей таблице перечислены значения, можно указать для `location` параметра.  
  
|Расположение|Описание:|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Вкладки расположены в нижней части вкладок элемента управления.|  
|LOCATION_TOP|Вкладки расположены в верхней части вкладок элемента управления.|  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CMFCTabCtrl` класса. Данный пример является частью [образец сбор данных о состоянии](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#2](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 Уменьшение объема размер области указанной вкладки.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectEdit`  
 Прямоугольник, определяющий область вкладки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при изменении метку вкладки. Этот метод сжимает левую и правую части, в заданном прямоугольнике половина вкладку высота и уменьшение объема вверх и вниз на одну единицу.  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 Показывает или скрывает кнопку Закрыть ( **X**) на активной вкладке.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы отобразить Кнопка «Закрыть» на вкладке «активный»; `FALSE` для отображения Кнопка «Закрыть» в правом верхнем углу области вкладок. Значение по умолчанию — `TRUE`.  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 Включает или отключает меток вкладок для редактирования.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для включения вкладки для редактирования меток; `FALSE` отключение меток вкладок для редактирования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 Переключение между пользовательский интерфейс, который использует две кнопки для перехода между вкладками окна и интерфейс, который отображает контекстное меню окна с вкладками.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы открыть контекстное меню окна с вкладками меток; `FALSE` для отображения кнопки прокрутки вперед и назад. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает метку вкладки, платформа отображает соответствующее окно с вкладками. Если отображается метку вкладки, окна с вкладками открывается без изменения его позиции. Если пользователь выбирает документа из всплывающего меню и соответствующее окно с вкладками находится вне экрана, окна с вкладками становится первой позицией табуляции.  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 Обеспечивает видимость вкладки.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` Если `iTab` используется недопустимый индекс параметра.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы гарантировать, что указанная вкладка видимой. При необходимости прокручивает вкладок элемента управления.  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 Возвращает изображение, связанный с вкладкой во всплывающем меню окон с вкладками.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCmdID`  
 Идентификатор команды вкладки во всплывающем меню окон с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор растрового изображения.  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 Возвращает индекс первой вкладки, который является видимым в текущий набор вкладок.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс вкладки в элементе управления вкладками.  
  
### <a name="remarks"></a>Примечания  
 Этот метод следует используйте только в том случае, когда появится набор вкладок в стиле Microsoft OneNote. Используйте [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) метод для определения стиля.  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 Получает значение, указывающее способ изменения размеров текущего элемента управления tab.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из `CMFCTabCtrl::ResizeMode` значений перечисления, определяющее способ изменения размеров вкладок элемента управления. Список возможных значений см. в разделе «Примечания» [CMFCTabCtrl::SetResizeMode](#setresizemode) метод.  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 Извлекает указатель на объект строки прокрутки, связанный с элементом управления tab.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект полосы прокрутки, а также в `NULL` Если управления "Вкладка" не был создан с помощью `STYLE_FLAT_SHARED_HORZ_SCROLL` стиля.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для доступа к панели управления "Вкладка" embedded прокрутки. Объект панели прокрутки создается только в том случае, если вкладка содержит `STYLE_FLAT_SHARED_HORZ_SCROLL` стиля.  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 Возвращает прямоугольник, ограничивающий область метку вкладки в верхней или нижней части вкладок элемента управления.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectTabAreaTop`  
 При возвращении данного метода этот справочник содержит прямоугольник, ограничивающий область метки верхней вкладки. Прямоугольник представлены в клиентских координатах. Данная ссылка является пустым, если существует область метки не вкладки в верхней части вкладок элемента управления.  
  
 [выходной] `rectTabAreaBottom`  
 При возвращении данного метода этот справочник содержит прямоугольник, ограничивающий область метки нижней вкладки. Прямоугольник представлены в клиентских координатах. Данная ссылка является пустым, если существует область метки не вкладки в нижней части вкладок элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить размер и положение области вкладок в окне с вкладками.  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 Возвращает максимальную ширину вкладки.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная ширина знаку табуляции, в пикселях. Если возвращаемое значение равно 0, интервал табуляции не ограничено.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) метод, чтобы задать интервал максимальное табуляции.  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 Получает высоту области вкладок текущего элемента управления tab.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота области вкладки, если любой вкладка отображается, или нуль, если вкладка не отображается.  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 Возвращает прямоугольник, ограничивающий область вкладки текущего элемента управления tab.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rect`  
 По возвращении из этого метода `rect` параметр содержит прямоугольник, ограничивающий область вкладки.  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 Возвращает границы клиентской области текущего элемента управления tab.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `rect`  
 При возвращении данного метода этот параметр содержит прямоугольник, ограничивающий текущего элемента управления tab.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Скрывает горизонтальную полосу прокрутки, если таковая имеется, в активном окне.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы предотвратить мерцание при переключении между страниц вкладок элемента управления вкладок элемента управления.  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 Указывает, отображаются ли платформа неактивные вкладку элемента управления windows.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHide`  
 `TRUE`Чтобы не отображать неактивного окна; `FALSE` для отображения неактивного окна. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 Включает или отключает Рисование области вкладок, если нет видимых вкладок.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHide`  
 `TRUE`Чтобы включить рисование области вкладок; `FALSE` отключение рисования. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 Включает или отключает вкладку документа при наличии одного окна с вкладками.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHide`  
 `TRUE`Чтобы не отображаются на вкладке для одного окна с вкладками; `FALSE` для отрисовки на одной вкладке. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 Указывает, является ли текущей вкладки элемента управления вкладками активной вкладки в группе вкладок интерфейса нескольких документов.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текущей вкладки элемента управления вкладками активной вкладки в группе вкладок MDI; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Можно организовать несколько окон документов в любой группы вертикальных и горизонтальных вкладок и легко переносить документы из одной группы в другую.  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 Указывает, отображается ли для полужирный шрифт текста активной вкладки.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если выбрана вкладка отображается полужирным шрифтом; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) метод, чтобы изменить шрифт активной вкладки.  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 Указывает, является ли кнопка «Закрыть» ( **X**) отображается на активной вкладке или в правом верхнем углу области вкладок.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка «Закрыть» отображается на вкладке «активный»; `FALSE` Если кнопка «Закрыть» отображается в правом верхнем углу области вкладок.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 Указывает ли окна с вкладками Рисование прямоугольника рамки вокруг внедренные панелей.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если отображается прямоугольник фрейма; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::SetDrawFrame](#setdrawframe) метод, чтобы включить или отключить Рисование прямоугольника кадра.  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 Указывает, является ли рамку вокруг области вкладок плоским или трехмерным.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если рамку вокруг области вкладок плоской. `FALSE` Если трехмерного рамки.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::SetFlatFrame](#setflatframe) метод, чтобы изменить способ рисования рамки.  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 Указывает, является ли вид вкладок в текущем элементе управления вкладками плоских или нет.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если внешний вид вкладок в текущем элементе управления вкладками плоской. в противном случае `FALSE`.  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 Указывает, округляются ли внешний вид левой и правой части вкладки в текущем элементе управления вкладками.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если округляется стороны каждой из вкладок; в противном случае `FALSE`.  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 Указывает, содержится ли текущий набор вкладок в клиентской области окна многодокументного интерфейса.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текущий набор вкладок в окне области клиента MDI. в противном случае `FALSE`.  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Указывает, отображается ли текущий набор вкладок в стиле Microsoft OneNote.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если отображается элемент управления вкладки в стиле Microsoft OneNote; в противном случае `FALSE`.  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 Указывает, имеет ли текущий набор вкладок полосы прокрутки прокрутки вкладками в группу.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладка содержит полосу прокрутки общей; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `TRUE` Если `style` параметр [CMFCTabCtrl::Create](#create) метод является STYLE_FLAT_SHARED_HORZ_SCROLL.  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 Указывает, отображаются ли вкладок элемента управления кнопки прокрутки или кнопку, которая отображает меню окон с вкладками.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если оказались окон с вкладками, с помощью всплывающего меню окна с вкладками меток; `FALSE` Если оказались окон с вкладками, с помощью кнопок прокрутки вперед и назад.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) метод, чтобы указать метод прокрутки с вкладками windows.  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Указывает, отображаются ли вкладки с использованием стиля, Visual Studio 2005.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладки с использованием стиля, Visual Studio 2005; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте `style` параметр [CMFCTabCtrl::Create](#create) метод, чтобы задать способ рисования вкладок.  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 Запрещает активное представление теряет фокусировку включением и вставить новую вкладку.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Примечания  
 Фокус обычно выполняемое нового окна с вкладками, когда вставляется и сделана активной вкладке. Задать `CMFCTabCtrl::m_bEnableActivate` переменной-члена для `FALSE` сохранить исходный фокус. Значение по умолчанию — `TRUE`.  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 Определяет внешний вид вкладок в текущем элементе управления вкладками.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `style`  
 Одно из значений перечисления, которое определяет внешний вид вкладок элемента управления. Дополнительные сведения см. в таблице в примечаниях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Значение `style` параметр может иметь одно из следующих `CMFCTabCtrl::Style` перечисления.  
  
|name|Описание:|  
|----------|-----------------|  
|STYLE_3D|Отображает трехмерного, прямоугольная вкладок, имеющих скругленные углы.|  
|STYLE_3D_ONENOTE|Отображает трехмерного вкладок, имеющих одного вертикальной один Наклонные стороне и и которые имеют закругленные углы.|  
|STYLE_3D_ROUNDED|Отображает трехмерного вкладки, которые наклон сторон и скругленные углы.|  
|STYLE_3D_ROUNDED_SCROLL|Отображает трехмерного вкладки, которые наклон сторон и скругленные углы. Если есть несколько вкладок, чем может быть отображено в то же время, платформа отображает стрелку раскрывающегося списка и меню, вкладок, чтобы сделать активной.|  
|STYLE_3D_SCROLLED|Отображает вкладки трехмерного, прямоугольной. Если есть несколько вкладок, чем может быть отображено в то же время, платформа отображает стрелку раскрывающегося списка и меню, вкладок, чтобы сделать активной.|  
|STYLE_3D_VS2005|Отображает трехмерного, округленное вкладок, имеющих один Наклонные одного вертикальной стороне и.|  
|STYLE_FLAT|Отображает двухмерный вкладки, которые наклонными левую и правую части.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Отображает двухмерный вкладок. Если есть несколько вкладок, чем может быть отображено в то же время, платформа отображает стрелками на концах области вкладок.|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 Вызывается средой во время операции перетаскивания и вставки при курсор в первый раз входит окна текущего элемента управления tab.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDataObject`  
 Указывает объект, который содержит данные, которые пользователь перетаскивает.  
  
 [in] `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Этот параметр представляет собой битовую комбинацию (OR) из следующих значений: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`. Дополнительные сведения см. в разделе **параметры сообщений** раздел [о ввода мыши](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Содержит текущее положение курсора в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `DROPEFFECT_NONE`, что означает, что объект-приемник не может принимать данные.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для поддержки операции перетаскивания и вставки. Переопределите этот метод для реализации собственного пользовательского поведения.  
  
 По умолчанию этот метод вызывает только `CMFCTabCtrl::OnDragOver`, который всегда возвращает `DROPEFFECT_NONE`.  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 Вызывается платформой при выполнении операции перетаскивания при перемещении указателя мыши по окна цели перетаскивания.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объект, перетаскиваемый над конечным расположением сброса.  
  
 [in] `dwKeyState`  
 Состояние клавиши-модификаторы, которые представляет собой битовую комбинацию (или) `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`. Дополнительные сведения см. в разделе «Параметры сообщения» в [о ввода мыши](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Текущая позиция мыши.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `DROPEFFECT_NONE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, с помощью пользовательской реализации. Дополнительные сведения см. в разделе [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) метод.  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 Отображает контекстное меню окна с вкладками, ожидает, когда пользователь выбирает вкладку и делает выбранная вкладка активной вкладки.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты место отображения контекстного меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 Задает текущей вкладки управления "Вкладка" в качестве активной вкладки в группе вкладок интерфейса нескольких документов.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActive`  
 `TRUE`Чтобы сделать текущей активной вкладкой; `FALSE` чтобы сделать неактивными текущей вкладки.  
  
### <a name="remarks"></a>Примечания  
 Можно организовать несколько окон документов в любой группы вертикальных и горизонтальных вкладок и легко переносить документы из одной группы в другую.  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 Активирует вкладку.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Задает отсчитываемый от нуля индекс вкладки для активации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанная вкладка был активирован; `FALSE` Если указанный `iTab` недопустимое значение параметра.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не отправляет `AFX_WM_CHANGE_ACTIVE_TAB` уведомления в родительское окно элемента управления tab.  
  
 `SetActiveTab` Автоматически вызывает метод [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) метод, чтобы предотвратить мерцание экрана.  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 Включает или отключает использование полужирного шрифта для активных вкладок.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsBold`  
 `TRUE`использовать полужирный шрифт для отображения метки активной вкладки; `FALSE` следует использовать стандартный шрифт для отображения метки. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 Указывает, отображается ли прямоугольник рамки вокруг внедренные строки.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDraw`  
 `TRUE`для отображения рамки прямоугольник вокруг внедренные строки. в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 Указывает, следует ли Рисование плоской или объемной рамки вокруг области вкладок.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 `TRUE`Чтобы нарисовать фрейм плоский (2D) вокруг области вкладок; `FALSE` для отрисовки трехмерного кадра (3D). Значение по умолчанию — `TRUE`.  
  
 [in] `bRepaint`  
 `TRUE`Чтобы обновить окно немедленно; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 Задает список изображений.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор ресурса точечного рисунка, который содержит список изображений.  
  
 [in] `cx`  
 Ширина каждого изображения в пикселях. Значение по умолчанию — 15.  
  
 [in] `clrTransp`  
 Цвет прозрачное изображение. Части изображения, которые имеют этот цвет будет прозрачной. Значение по умолчанию — пурпурный цвет RGB(255,0,255).  
  
 [in] `hImageList`  
 Дескриптор в список предварительно загруженный образ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполняется успешно. `FALSE`Если вкладок элемента управления создается с помощью плоский стиль или первой перегрузки метода, не удается загрузить точечный рисунок, который задается параметром `uiID` параметр.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для задания списка изображений для элемента управления tab. Рядом с меткой вкладки отображаются изображений из списка изображений. Этот метод пересчитывает высоту вкладку, чтобы вкладке подбирается содержать изображения и текст.  
  
 Используйте [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) метод, от которого наследует набор вкладок, чтобы задать индекс изображения для отображения.  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 Задает способ изменения размеров текущего управления "Вкладка" и затем повторно отображает элемент управления.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `resizeMode`  
 Один из `CMFCTabCtrl::ResizeMode` значений перечисления, определяющее способ изменения размеров вкладок элемента управления. Список возможных значений см. в таблице в примечаниях.  
  
### <a name="remarks"></a>Примечания  
 `resizeMode` Параметр может иметь одно из следующих `ResizeMode` значений перечисления.  
  
|name|Описание:|  
|----------|-----------------|  
|RESIZE_NO|Невозможно изменить размер вкладок элемента управления.|  
|RESIZE_VERT|Можно изменять вкладок элемента управления по вертикали, но не по горизонтали.|  
|RESIZE_HORIZ|Можно изменять вкладок элемента управления по горизонтали, но не по вертикали.|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 Указывает ширину максимальное вкладку в окно с вкладками.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTabMaxWidth`  
 Максимальное вкладку ширина в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы ограничить ширину вкладок окна с вкладками. Этот метод полезен, если вкладки имеют очень длинные подписи. [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) класса конструктор инициализирует ширину вкладку максимальное значение 0, что фактически означает, что ширина не ограничено.  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 Завершает текущую операцию изменения размера для элемента управления tab.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCancel`  
 `TRUE`Чтобы прервать текущую операцию изменения размера; `FALSE` для завершения текущего операцию изменения размера. В любом случае платформа останавливает Рисование прямоугольника изменения размера.  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 Рисует горизонтальную полосу прокрутки для элемента управления tab, отображает плоский вкладки.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `pScrollInfo`  
 Указатель на [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структуры или `NULL`. При возвращении этим методом, и если этот параметр не является `NULL`, структура содержит все параметры полосы прокрутки. Значение по умолчанию — `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод затрагивает только управления "Вкладка", отображающий плоский вкладок. Полоса прокрутки повлияет на все вкладки в то же время.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)
