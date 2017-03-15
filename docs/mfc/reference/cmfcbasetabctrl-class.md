---
title: "Класс CMFCBaseTabCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseTabCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseTabCtrl class
ms.assetid: 7270c55f-6f6e-4dd2-b0d2-291afeac3882
caps.latest.revision: 41
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d82cde70595bf6d7a4629f54cc48e2b422cd5e8c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasetabctrl-class"></a>Класс CMFCBaseTabCtrl
Реализует базовую функциональность для окон с вкладками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCBaseTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCBaseTabCtrl::AddIcon](#addicon)||  
|[CMFCBaseTabCtrl::AddTab](#addtab)|Добавляет новую вкладку в окно с вкладками.|  
|[CMFCBaseTabCtrl::ApplyRestoredTabInfo](#applyrestoredtabinfo)||  
|[CMFCBaseTabCtrl::AutoDestroyWindow](#autodestroywindow)||  
|[CMFCBaseTabCtrl::CalcRectEdit](#calcrectedit)||  
|[CMFCBaseTabCtrl::CleanUp](#cleanup)||  
|[CMFCBaseTabCtrl::ClearImageList](#clearimagelist)||  
|[CMFCBaseTabCtrl::DetachTab](#detachtab)|Отделяет вкладку от окна с вкладками.|  
|[CMFCBaseTabCtrl::EnableActivateLastActive](#enableactivatelastactive)||  
|[CMFCBaseTabCtrl::EnableAutoColor](#enableautocolor)|Включает или выключает автоматическую цветовую маркировку вкладок.|  
|[CMFCBaseTabCtrl::EnableCustomToolTips](#enablecustomtooltips)|Включает или отключает настраиваемые подсказки для вкладок.|  
|[CMFCBaseTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Включает или отключает прямое редактирование меток вкладок.|  
|[CMFCBaseTabCtrl::EnableTabDetach](#enabletabdetach)|Включает отделяемые вкладки.|  
|[CMFCBaseTabCtrl::EnableTabSwap](#enabletabswap)|Включает или отключает возможность изменения порядка вкладок с помощью мыши.|  
|[CMFCBaseTabCtrl::EnsureVisible](#ensurevisible)|Прокручивает вкладки, пока не станет видна указанная вкладка. Не действует, если указанная вкладка уже видна.|  
|[CMFCBaseTabCtrl::EnterDragMode](#enterdragmode)||  
|[CMFCBaseTabCtrl::FindTargetWnd](#findtargetwnd)|Возвращает область, содержащую указанную точку.|  
|[CMFCBaseTabCtrl::FireChangeActiveTab](#firechangeactivetab)||  
|[CMFCBaseTabCtrl::FireChangingActiveTab](#firechangingactivetab)||  
|[CMFCBaseTabCtrl::GetActiveTab](#getactivetab)|Возвращает индекс активной вкладки.|  
|[CMFCBaseTabCtrl::GetActiveTabColor](#getactivetabcolor)|Возвращает цвет фона активной вкладки.|  
|[CMFCBaseTabCtrl::GetActiveTabTextColor](#getactivetabtextcolor)|Возвращает цвет текста активной вкладки.|  
|[CMFCBaseTabCtrl::GetActiveWnd](#getactivewnd)|Возвращает указатель на активную страницу набора вкладок.|  
|[CMFCBaseTabCtrl::GetAutoColors](#getautocolors)|Возвращает ссылку на массив цветов, используемых для автоматической цветовой маркировки.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTab](#getfirstvisibletab)|Возвращает указатель на первую видимую вкладку.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)||  
|[CMFCBaseTabCtrl::GetHighlightedTab](#gethighlightedtab)|Возвращает индекс выделенной вкладки.|  
|[CMFCBaseTabCtrl::GetImageList](#getimagelist)||  
|[CMFCBaseTabCtrl::GetImageSize](#getimagesize)||  
|[CMFCBaseTabCtrl::GetLastVisibleTab](#getlastvisibletab)||  
|[CMFCBaseTabCtrl::GetLocation](#getlocation)|Возвращает переменную типа LOCATION, указывающую положение области вкладок по отношению к элементу управления вкладки (например, сверху или снизу).|  
|[CMFCBaseTabCtrl::GetMaxWindowSize](#getmaxwindowsize)||  
|[CMFCBaseTabCtrl::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладок в окне с вкладками. Положение области вкладок определяется по координатам.|  
|[CMFCBaseTabCtrl::GetTabBkColor](#gettabbkcolor)|Возвращает цвет фона указанной вкладки.|  
|[CMFCBaseTabCtrl::GetTabBorderSize](#gettabbordersize)|Возвращает размер границ вкладки в наборе вкладок.|  
|[CMFCBaseTabCtrl::GetTabByID](#gettabbyid)|Возвращает индекс вкладки, определяемой по указанному идентификатору.|  
|[CMFCBaseTabCtrl::GetTabCloseButton](#gettabclosebutton)||  
|[CMFCBaseTabCtrl::GetTabFromHwnd](#gettabfromhwnd)|Возвращает индекс вкладки, содержащей указанный объект HWND.|  
|[CMFCBaseTabCtrl::GetTabFromPoint](#gettabfrompoint)|Возвращает вкладку, содержащую указанную точку.|  
|[CMFCBaseTabCtrl::GetTabFullWidth](#gettabfullwidth)||  
|[CMFCBaseTabCtrl::GetTabHicon](#gettabhicon)|Возвращает значок, связанный с указанной вкладкой.|  
|[CMFCBaseTabCtrl::GetTabID](#gettabid)|Возвращает идентификатор вкладки по ее индексу.|  
|[CMFCBaseTabCtrl::GetTabIcon](#gettabicon)|Возвращает идентификатор значка указанной вкладки.|  
|[CMFCBaseTabCtrl::GetTabLabel](#gettablabel)|Возвращает текст указанной вкладки.|  
|[CMFCBaseTabCtrl::GetTabRect](#gettabrect)|Извлекает размер и положение указанной вкладки.|  
|[CMFCBaseTabCtrl::GetTabsHeight](#gettabsheight)||  
|[CMFCBaseTabCtrl::GetTabsRect](#gettabsrect)||  
|[CMFCBaseTabCtrl::GetTabTextColor](#gettabtextcolor)|Возвращает цвет текста указанной вкладки.|  
|[CMFCBaseTabCtrl::GetTabWnd](#gettabwnd)|Возвращает указатель в область, расположенную на указанной странице вкладки.|  
|[CMFCBaseTabCtrl::GetTabWndNoWrapper](#gettabwndnowrapper)|Возвращает прямой указатель на элемент управления, находящийся на указанной странице вкладки, даже если у этого элемента управления имеется оболочка.|  
|[CMFCBaseTabCtrl::GetTabsNum](#gettabsnum)|Возвращает количество вкладок, входящих в набор вкладок.|  
|[CMFCBaseTabCtrl::GetToolTipCtrl](#gettooltipctrl)|Возвращает ссылку на элемент управления ToolTip, связанный с объектом `CMFCBaseTabCtrl` .|  
|[CMFCBaseTabCtrl::GetVisibleTabsNum](#getvisibletabsnum)|Возвращает количество видимых вкладок.|  
|[CMFCBaseTabCtrl::HasImage](#hasimage)||  
|[CMFCBaseTabCtrl::HideSingleTab](#hidesingletab)|Задает параметр, скрывающий вкладку окна, но только в случае, если в окне с вкладками отображается лишь одна видимая вкладка.|  
|[CMFCBaseTabCtrl::InsertTab](#inserttab)|Вставляет новую вкладку.|  
|[CMFCBaseTabCtrl::InvalidateTab](#invalidatetab)||  
|[CMFCBaseTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)||  
|[CMFCBaseTabCtrl::IsAutoColor](#isautocolor)|Возвращает значение, указывающее, включена ли для окна с вкладками автоматическая цветовая маркировка.|  
|[CMFCBaseTabCtrl::IsAutoDestroyWindow](#isautodestroywindow)||  
|[CMFCBaseTabCtrl::IsColored](#iscolored)||  
|[CMFCBaseTabCtrl::IsDialogControl](#isdialogcontrol)||  
|[CMFCBaseTabCtrl::IsDrawNoPrefix](#isdrawnoprefix)||  
|[CMFCBaseTabCtrl::IsFlatFrame](#isflatframe)|Возвращает значение, указывающее, является фрейм области вкладок плоским или трехмерным.|  
|[CMFCBaseTabCtrl::IsFlatTab](#isflattab)||  
|[CMFCBaseTabCtrl::IsHideSingleTab](#ishidesingletab)|Возвращает значение, указывающее, будет ли скрыта метка вкладки, если в окне с вкладками отображается лишь одна вкладка.|  
|[CMFCBaseTabCtrl::IsIconAdded](#isiconadded)||  
|[CMFCBaseTabCtrl::IsInPlaceEdit](#isinplaceedit)|Указывает, могут ли пользователи изменять метку вкладки.|  
|[CMFCBaseTabCtrl::IsLeftRightRounded](#isleftrightrounded)||  
|[CMFCBaseTabCtrl::IsMDITab](#ismditab)||  
|[CMFCBaseTabCtrl::IsOneNoteStyle](#isonenotestyle)|Указывает, отображаются ли вкладки в окне в стиле Microsoft OneNote.|  
|[CMFCBaseTabCtrl::IsPtInTabArea](#isptintabarea)|Проверяет, существует ли в области вкладок указанная точка.|  
|[CMFCBaseTabCtrl::IsTabCloseButtonHighlighted](#istabclosebuttonhighlighted)||  
|[CMFCBaseTabCtrl::IsTabCloseButtonPressed](#istabclosebuttonpressed)||  
|[CMFCBaseTabCtrl::IsTabDetachable](#istabdetachable)|Указывает, является ли вкладка отделяемой.|  
|[CMFCBaseTabCtrl::IsTabIconOnly](#istabicononly)|Указывает, отображаются ли для вкладок значки, а не метки.|  
|[CMFCBaseTabCtrl::IsTabSwapEnabled](#istabswapenabled)|Указывает, может ли пользователь менять положение вкладок путем их перетаскивания.|  
|[CMFCBaseTabCtrl::IsTabVisible](#istabvisible)|Указывает, является ли указанная вкладка видимой.|  
|[CMFCBaseTabCtrl::IsVS2005Style](#isvs2005style)||  
|[CMFCBaseTabCtrl::MoveTab](#movetab)||  
|[CMFCBaseTabCtrl::OnChangeTabs](#onchangetabs)|Вызывается платформой при изменении количества вкладок.|  
|[CMFCBaseTabCtrl::OnDragEnter](#ondragenter)||  
|[CMFCBaseTabCtrl::OnDragLeave](#ondragleave)||  
|[CMFCBaseTabCtrl::OnDragOver](#ondragover)||  
|[CMFCBaseTabCtrl::OnDrop](#ondrop)||  
|[CMFCBaseTabCtrl::OnRenameTab](#onrenametab)||  
|[CMFCBaseTabCtrl::PreTranslateMessage](#pretranslatemessage)|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для перевода оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCBaseTabCtrl::RecalcLayout](#recalclayout)|Повторно вычисляет внутренний макет окна с вкладками.|  
|[CMFCBaseTabCtrl::RemoveAllTabs](#removealltabs)|Удаляет все вкладки из окна.|  
|[CMFCBaseTabCtrl::RemoveTab](#removetab)|Удаляет вкладку из окна.|  
|[CMFCBaseTabCtrl::RenameTab](#renametab)||  
|[CMFCBaseTabCtrl::ResetImageList](#resetimagelist)|Сбрасывает список изображений, прикрепленный к окну с вкладками.|  
|[CMFCBaseTabCtrl::Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCBaseTabCtrl::SetActiveTab](#setactivetab)|Активирует вкладку.|  
|[CMFCBaseTabCtrl::SetActiveTabColor](#setactivetabcolor)|Задает цвет фона для активной вкладки.|  
|[CMFCBaseTabCtrl::SetActiveTabTextColor](#setactivetabtextcolor)|Задает цвет текста для активных вкладок.|  
|[CMFCBaseTabCtrl::SetAutoColors](#setautocolors)|Задает для набора вкладок цвета, используемые в режиме автоматической цветовой маркировки.|  
|[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](#setdockingbarwrapperrtc)|Задает класс-оболочку, который используется для всех объектов, которые не являются производными от [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).|  
|[CMFCBaseTabCtrl::SetDrawNoPrefix](#setdrawnoprefix)|Включает и отключает обработку символов префикса при отрисовке подписей вкладок.|  
|[CMFCBaseTabCtrl::SetImageList](#setimagelist)|Задает список изображений значка.|  
|[CMFCBaseTabCtrl::SetLocation](#setlocation)||  
|[CMFCBaseTabCtrl::SetTabBkColor](#settabbkcolor)|Задает цвет фона для указанной вкладки.|  
|[CMFCBaseTabCtrl::SetTabBorderSize](#settabbordersize)|Задает размер границ новой вкладки.|  
|[CMFCBaseTabCtrl::SetTabHicon](#settabhicon)|Задает значок вкладки.|  
|[CMFCBaseTabCtrl::SetTabIcon](#settabicon)|Задает идентификатор значка вкладки.|  
|[CMFCBaseTabCtrl::SetTabIconOnly](#settabicononly)|Включает и отключает режим "только значок" для указанной вкладки.|  
|[CMFCBaseTabCtrl::SetTabLabel](#settablabel)|Задает метку вкладки, аналогичную значению указанной строки.|  
|[CMFCBaseTabCtrl::SetTabsHeight](#settabsheight)||  
|[CMFCBaseTabCtrl::SetTabTextColor](#settabtextcolor)|Задает цвет текста для указанной вкладки.|  
|[CMFCBaseTabCtrl::SetTabsOrder](#settabsorder)|Располагает вкладки в указанном порядке.|  
|[CMFCBaseTabCtrl::ShowTab](#showtab)|Отображает или скрывает указанную вкладку.|  
|[CMFCBaseTabCtrl::StartRenameTab](#startrenametab)||  
|[CMFCBaseTabCtrl::SwapTabs](#swaptabs)||  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCBaseTabCtrl::CreateWrapper](#createwrapper)|Создает оболочку для объекта, производного от [CWnd](../../mfc/reference/cwnd-class.md) не является производным от `CDockablePane`. Чтобы закрепить объект `CMFCBaseTabCtrl` , каждый внедренный элемент управления должен иметь закрепляющую оболочку или быть производным от `CDockablePane`.<br /><br /> Класс оболочки задается с помощью `SetDockingBayWrapperRTC`.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCBaseTabCtrl::m_bActivateTabOnRightClick](#m_bactivatetabonrightclick)|Указывает, выбираются вкладки щелчком левой или правой кнопкой мыши.|  
|[CMFCBaseTabCtrl::m_bAutoDestroyWindow](#m_bautodestroywindow)|Указывает, будут ли автоматически уничтожаться области, входящие во вкладки.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CMFCBaseTabCtrl` является абстрактным. Это означает, что нельзя создать его экземпляр. Чтобы создать окно с вкладками, необходимо создать класс, производный от класса `CMFCBaseTabCtrl`. Библиотека MFC содержит примеры производного класса, два из которых являются [класса CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) и [CMFCOutlookBarTabCtrl класса](../../mfc/reference/cmfcoutlookbartabctrl-class.md).  
  
 Начиная с [!INCLUDE[vs_dev14](../../ide/includes/vs_dev14_md.md)], этот класс поддерживает Microsoft Active Accessibility.  
  
## <a name="customization-tips"></a>Советы по настройке  
 Следующие советы относятся к `CMFCBaseTabCtrl Class` и любые классы, производные от него:  
  
-   При включении отделяемых вкладок не следует оставлять указатели на окна с вкладками. Эти отделяемые вкладки могут динамически создаваться и уничтожаться, поэтому указатели могут стать недействительными.  
  
-   Вы можете настроить набор вкладок, чтобы пользователи получили возможность динамического перемещения входящих в него вкладок с помощью мыши. Эта функция входит в класс `CMFCBaseTabCtrl` . Чтобы включить его, вызовите [CMFCBaseTabCtrl::EnableTabSwap](#enabletabswap).  
  
-   По умолчанию в набор вкладок добавляются отделяемые вкладки. Можно также добавить-отключаемых вкладок с помощью [CMFCBaseTabCtrl::AddTab](#addtab). Если в качестве значения параметра `bDetachable` выбрать `FALSE`, соответствующая вкладка будет неотделяемой. Можно также изменить ли отключаемых вкладок, вызвав метод [CMFCBaseTabCtrl::EnableTabDetach](#enabletabdetach).  
  
-   Объекты, которые являются производными от [класс CWnd](../../mfc/reference/cwnd-class.md) можно поместить на Закрепляемая панель или Закрепляемое вкладки. Чтобы весь элемент управления стал закрепляемым, необходимо сделать закрепляемым объект `CWnd` . Для этого MFC использует класс-оболочку. Данный класс-оболочка — [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md). Любые объекты `CWnd` , добавляемые на закрепляемую панель управления или закрепляемую вкладку, будут помещены в оболочку в объекте `CDockablePaneAdapter` . Автоматическое помещение в оболочку можно отключить, установив для параметра `m_bEnableWrapping` объекта `CMFCBaseTablCtrl` значение `FALSE`. Можно также изменить класс, приложение будет использовать в качестве оболочки с помощью метода [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetabctrl.h  
  
##  <a name="a-nameaddicona--cmfcbasetabctrladdicon"></a><a name="addicon"></a>CMFCBaseTabCtrl::AddIcon  
 Добавляет в список значков в защищенном значок `CMap``m_mapAddedIcons` член.  
  
```  
void AddIcon(
    HICON hIcon,  
    int iIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 Дескриптор значка для добавления.  
  
 [in] `iIcon`  
 Отсчитываемый от нуля индекс значка в защищенный `CImageList``m_Images` член.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameaddtaba--cmfcbasetabctrladdtab"></a><a name="addtab"></a>CMFCBaseTabCtrl::AddTab  
 Добавляет новую вкладку вкладок элемента управления.  
  
```  
virtual void AddTab(
    CWnd* pTabWnd,  
    LPCTSTR lpszTabLabel,  
    UINT uiImageId = (UINT)-1,,  
    BOOL bDetachable = TRUE);

 
virtual void AddTab(
    CWnd* pTabWnd,  
    UINT uiResTabLabel,  
    UINT uiImageId = (UINT)-1,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTabWnd`  
 Указатель на окно, которое представляет этот метод в виде новой вкладки.  
  
 [in] `lpszTabLabel`  
 Строка, содержащая метки новой вкладки.  
  
 [in] `uiImageId`  
 Идентификатор изображения из списка изображений. Элемент управления вкладки использует этот образ как значок новой вкладки.  
  
 [in] `uiResTabLabel`  
 Идентификатор ресурса для метки.  
  
 [in] `bDetachable`  
 Логический параметр, который определяет, является ли новая вкладка отключаемых.  
  
### <a name="remarks"></a>Примечания  
 Если `pTabWnd` указывает на объект, который не является производным от [класса CDockablePane](../../mfc/reference/cdockablepane-class.md) и, если `bDetachable` — `TRUE`, платформа автоматически создает оболочку для `pTabWnd` объекта. Оболочка делает `pTabWnd` отключаемых объекта. По умолчанию оболочка представляет собой экземпляр [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md). Если функциональность, предлагаемая оболочки по умолчанию является недопустимым, используйте [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](#setdockingbarwrapperrtc) метод, чтобы задать другой оболочку.  
  
##  <a name="a-nameapplyrestoredtabinfoa--cmfcbasetabctrlapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CMFCBaseTabCtrl::ApplyRestoredTabInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bUseTabIndexes`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameautodestroywindowa--cmfcbasetabctrlautodestroywindow"></a><a name="autodestroywindow"></a>CMFCBaseTabCtrl::AutoDestroyWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AutoDestroyWindow(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoDestroy`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecalcrectedita--cmfcbasetabctrlcalcrectedit"></a><a name="calcrectedit"></a>CMFCBaseTabCtrl::CalcRectEdit  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectEdit`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecleanupa--cmfcbasetabctrlcleanup"></a><a name="cleanup"></a>CMFCBaseTabCtrl::CleanUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CleanUp();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameclearimagelista--cmfcbasetabctrlclearimagelist"></a><a name="clearimagelist"></a>CMFCBaseTabCtrl::ClearImageList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ClearImageList();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatewrappera--cmfcbasetabctrlcreatewrapper"></a><a name="createwrapper"></a>CMFCBaseTabCtrl::CreateWrapper  
 Создает оболочку для рамки окна, которое является производным от [класс CWnd](../../mfc/reference/cwnd-class.md) , но не является производным от [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).  
  
```  
virtual CWnd* CreateWrapper(
    CWnd* pWndToWrap,  
    LPCTSTR lpszTabLabel,  
    BOOL bDetachable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndToWrap`  
 Указатель кадра окна, которое заключается в оболочку.  
  
 [in] `lpszTabLabel`  
 Строка, содержащая метки для окна.  
  
 [in] `bDetachable`  
 Логический параметр, указывающий, является ли окно отключаемых.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Программу-оболочку производным от `CDockablePane` Если `CreateWrapper` успешно создает класс-оболочку для `pWndToWrap`. Если произойдет ошибка, она возвращает `pWndToWrap`.  
  
### <a name="remarks"></a>Примечания  
 Окна с вкладками можно закрепить объект, производный от `CWnd`. Тем не менее, в порядке для `CMFCBaseTabCtrl Class` объекта фиксируемыми, каждый объект `CMFCBaseTabCtrl` должен быть отключаемых. Таким образом `CMFCBaseTabCtrl` автоматически переносит все объекты, которые не являются производными от `CDockablePane`.  
  
 По умолчанию `CMFCBaseTabCtrl` создает экземпляры [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md). Чтобы изменить класс оболочки по умолчанию, вызовите [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](#setdockingbarwrapperrtc).  
  
 Если `pWndToWrap` является производным от `CDockablePane`, этот метод не создаст оболочку. Вместо этого будет давать сбой и возвращать `pWndToWrap`.  
  
##  <a name="a-namedetachtaba--cmfcbasetabctrldetachtab"></a><a name="detachtab"></a>CMFCBaseTabCtrl::DetachTab  
 Платформа вызывает этот метод, чтобы отсоединить вкладку из вкладок элемента управления.  
  
```  
virtual BOOL DetachTab(
    AFX_DOCK_METHOD dockMethod,  
    int nTabNum = -1,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dockMethod`  
 Тип перечислимых данных, предоставляемых [CBasePane класса](../../mfc/reference/cbasepane-class.md). Этот тип данных определяет метод, который использовался для отсоединения на вкладке.  
  
 [in] `nTabNum`  
 Отсчитываемый от нуля индекс вкладки для отсоединения.  
  
 [in] `bHide`  
 Логический параметр, указывает ли платформа следует скрыть вкладку отсоединения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если заданные вкладке `nTabNum` — не отключаемых, эта функция завершается неудачей и возвращает `FALSE`.  
  
##  <a name="a-nameenableactivatelastactivea--cmfcbasetabctrlenableactivatelastactive"></a><a name="enableactivatelastactive"></a>CMFCBaseTabCtrl::EnableActivateLastActive  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableActivateLastActive(BOOL bLastActive = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bLastActive`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenableautocolora--cmfcbasetabctrlenableautocolor"></a><a name="enableautocolor"></a>CMFCBaseTabCtrl::EnableAutoColor  
 Определяет, использует ли платформа автоматического фоновые цвета, при рисовании на вкладке.  
  
```  
void EnableAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логический параметр, который определяет, использует ли платформа автоматического цветов.  
  
### <a name="remarks"></a>Примечания  
 Вкладка содержит массив несколько стандартных цветов. Когда платформа использует автоматическое цветов, вкладок ряд вкладок назначается следующий цвет из этого массива.  
  
 По умолчанию автоматическое цвета определяются цвета определенные библиотеки. Массив пользовательских цветов можно предоставить, вызвав [CMFCBaseTabCtrl::SetAutoColors](#setautocolors).  
  
##  <a name="a-nameenablecustomtooltipsa--cmfcbasetabctrlenablecustomtooltips"></a><a name="enablecustomtooltips"></a>CMFCBaseTabCtrl::EnableCustomToolTips  
 Включает настраиваемые всплывающие подсказки для вкладок элемента управления.  
  
```  
BOOL EnableCustomToolTips(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логическое значение, определяющее, следует ли использовать настраиваемые всплывающие подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если включены настраиваемые всплывающие подсказки, отправляет вкладок `AFX_WM_ON_GET_TAB_TOOLTIP` сообщение главного фрейма. Если требуется поддерживать настраиваемые всплывающие подсказки в приложении, фрейма главного окна необходимо обрабатывать этот метод и предоставить пользовательский текст всплывающей подсказки. Дополнительные сведения о предоставлении пользовательский текст всплывающей подсказки в разделе [CMFCTabToolTipInfo структуры](../../mfc/reference/cmfctabtooltipinfo-structure.md).  
  
##  <a name="a-nameenableinplaceedita--cmfcbasetabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a>CMFCBaseTabCtrl::EnableInPlaceEdit  
 Позволяет осуществлять прямое редактирование корешков пользователем.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логический параметр, который указывает, следует ли включить прямое редактирование метки вкладок.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию прямое редактирование метки вкладок отключен для вкладок.  
  
 Можно включить прямого редактирования для подмножества вкладок для управления tab. Чтобы сделать это, переопределите метод `CMFCBaseTabCtrl::StartRenameTab`. `StartRenameTab`должна возвращать ненулевое значение для всех вкладок, которые поддерживают прямую правку корешков.  
  
 В `CMFCBaseTabCtrl Class`, этот метод является чисто виртуальную функцию и не имеет реализации. При наследовании от класса `CMFCBaseTabCtrl`, необходимо реализовать эту функцию.  
  
##  <a name="a-nameenabletabdetacha--cmfcbasetabctrlenabletabdetach"></a><a name="enabletabdetach"></a>CMFCBaseTabCtrl::EnableTabDetach  
 Включает отделяемые вкладки.  
  
```  
virtual BOOL EnableTabDetach(
    int iTab,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [in] `bEnable`  
 Логическое значение, определяющее необходимость отобразить вкладку отключаемых.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
##  <a name="a-nameenabletabswapa--cmfcbasetabctrlenabletabswap"></a><a name="enabletabswap"></a>CMFCBaseTabCtrl::EnableTabSwap  
 Позволяет пользователю изменить последовательность перехода с помощью мыши.  
  
```  
void EnableTabSwap(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логическое значение, указывающее, следует ли включить замену вкладку.  
  
### <a name="remarks"></a>Примечания  
 При включении вкладку Смена пользователя можно перетаскивать вкладки и изменить его относительное положение в элементе управления вкладками.  
  
##  <a name="a-nameensurevisiblea--cmfcbasetabctrlensurevisible"></a><a name="ensurevisible"></a>CMFCBaseTabCtrl::EnsureVisible  
 Прокручивает вкладки, пока не станет видна указанная вкладка.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не оказывает влияния обозначается вкладке `iTab` уже является видимым.  
  
 По умолчанию этот метод не поддерживается `CMFCBaseTabCtrl Class`. Эту функцию следует реализовать в пользовательский класс, производный от `CMFCBaseTabCtrl` Если пользовательская вкладка элемента управления поддерживает прокрутку вкладки. Этот метод поддерживается [CMFCTabCtrl класса](../../mfc/reference/cmfctabctrl-class.md).  
  
##  <a name="a-nameenterdragmodea--cmfcbasetabctrlenterdragmode"></a><a name="enterdragmode"></a>CMFCBaseTabCtrl::EnterDragMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnterDragMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindtargetwnda--cmfcbasetabctrlfindtargetwnd"></a><a name="findtargetwnd"></a>CMFCBaseTabCtrl::FindTargetWnd  
 Определяет области, содержащий заданной точке.  
  
```  
virtual CWnd* FindTargetWnd(const CPoint& pt) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Координаты точки, которая определяется с помощью клиентской области [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, если успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 В `CMFCBaseTabCtrl` класса, этот метод является чисто виртуальную функцию: это необходимо реализовать при наследовании от класса `CMFCBaseTabCtrl`.  
  
##  <a name="a-namefirechangeactivetaba--cmfcbasetabctrlfirechangeactivetab"></a><a name="firechangeactivetab"></a>CMFCBaseTabCtrl::FireChangeActiveTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void FireChangeActiveTab(int nNewTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nNewTab`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefirechangingactivetaba--cmfcbasetabctrlfirechangingactivetab"></a><a name="firechangingactivetab"></a>CMFCBaseTabCtrl::FireChangingActiveTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL FireChangingActiveTab(int nNewTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nNewTab`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetactivetaba--cmfcbasetabctrlgetactivetab"></a><a name="getactivetab"></a>CMFCBaseTabCtrl::GetActiveTab  
 Возвращает индекс текущей активной вкладки.  
  
```  
virtual int GetActiveTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс активной вкладке; -1, если нет активной вкладки.  
  
##  <a name="a-namegetactivetabcolora--cmfcbasetabctrlgetactivetabcolor"></a><a name="getactivetabcolor"></a>CMFCBaseTabCtrl::GetActiveTabColor  
 Получает цвет фона текущей активной вкладки.  
  
```  
virtual COLORREF GetActiveTabColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, задающее фоновый цвет активной вкладки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию — цвет фона активной вкладке `COLOR_WINDOW`. Можно изменить цвет фона для активной вкладки с помощью метода [CMFCBaseTabCtrl::SetActiveTabColor](#setactivetabcolor).  
  
##  <a name="a-namegetactivetabtextcolora--cmfcbasetabctrlgetactivetabtextcolor"></a><a name="getactivetabtextcolor"></a>CMFCBaseTabCtrl::GetActiveTabTextColor  
 Возвращает цвет текста для активной вкладки.  
  
```  
virtual COLORREF GetActiveTabTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, указывающее цвет активной вкладки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию — цвет текста для активной вкладки `COLOR_WINDOWTEXT`. Можно изменить цвет текста с помощью метода [CMFCBaseTabCtrl::SetActiveTabTextColor](#setactivetabtextcolor).  
  
##  <a name="a-namegetactivewnda--cmfcbasetabctrlgetactivewnd"></a><a name="getactivewnd"></a>CMFCBaseTabCtrl::GetActiveWnd  
 Извлекает указатель на активной вкладке окна.  
  
```  
virtual CWnd* GetActiveWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно.  
  
##  <a name="a-namegetautocolorsa--cmfcbasetabctrlgetautocolors"></a><a name="getautocolors"></a>CMFCBaseTabCtrl::GetAutoColors  
 Извлекает массив цветов, используемых для автоматического выделения цветом.  
  
```  
const CArray<COLORREF,COLORREF>& GetAutoColors() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на массив [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения, которые [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объект использует для автоматического перехода на следующий цвет.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа инициализирует массив цветов, цвета, определенные в библиотеке. Массив пользовательских цветов можно предоставить, вызвав метод [CMFCBaseTabCtrl::SetAutoColors](#setautocolors).  
  
##  <a name="a-namegetfirstvisibletaba--cmfcbasetabctrlgetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CMFCBaseTabCtrl::GetFirstVisibleTab  
 Извлекает указатель на первой вкладке видимым.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);

 
virtual CWnd* GetFirstVisibleTab(
    int iStartFrom,  
    int& iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `iTabNum`  
 Ссылка на целое число. Этот метод записывает отсчитываемый от нуля индекс первой видимой вкладки для этого параметра.  
  
 [in] `iStartFrom`  
 Отсчитываемый от нуля индекс первой вкладки для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первой вкладке отображается в случае успешного выполнения; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод не удается, он записывает значение -1 для `iStartFrom`.  
  
 Если `iStartFrom` больше или равно числу вкладок в элементе управления tab `GetFirstVisibleTab` автоматически переключается на другой.  
  
##  <a name="a-namegetfirstvisibletabnuma--cmfcbasetabctrlgetfirstvisibletabnum"></a><a name="getfirstvisibletabnum"></a>CMFCBaseTabCtrl::GetFirstVisibleTabNum  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegethighlightedtaba--cmfcbasetabctrlgethighlightedtab"></a><a name="gethighlightedtab"></a>CMFCBaseTabCtrl::GetHighlightedTab  
 Возвращает индекс текущей выделенной вкладки.  
  
```  
int GetHighlightedTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс выделенной вкладки.  
  
##  <a name="a-namegetimagelista--cmfcbasetabctrlgetimagelist"></a><a name="getimagelist"></a>CMFCBaseTabCtrl::GetImageList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual const CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetimagesizea--cmfcbasetabctrlgetimagesize"></a><a name="getimagesize"></a>CMFCBaseTabCtrl::GetImageSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlastvisibletaba--cmfcbasetabctrlgetlastvisibletab"></a><a name="getlastvisibletab"></a>CMFCBaseTabCtrl::GetLastVisibleTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetLastVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlocationa--cmfcbasetabctrlgetlocation"></a><a name="getlocation"></a>CMFCBaseTabCtrl::GetLocation  
 Получает расположение части вкладки области вкладок элемента управления.  
  
```  
Location GetLocation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение области вкладки.  
  
### <a name="remarks"></a>Примечания  
 Расположение значения возможных вкладку области `LOCATION_BOTTOM` и `LOCATION_TOP`.  
  
##  <a name="a-namegetmaxwindowsizea--cmfcbasetabctrlgetmaxwindowsize"></a><a name="getmaxwindowsize"></a>CMFCBaseTabCtrl::GetMaxWindowSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetMaxWindowSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabareaa--cmfcbasetabctrlgettabarea"></a><a name="gettabarea"></a>CMFCBaseTabCtrl::GetTabArea  
 Получает размер и положение вкладки области вкладок элемента управления.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectTabAreaTop`  
 Ссылка на объект `CRect`. `GetTabArea`Этот объект используется для хранения размер и положение вкладки в верхней области.  
  
 [in] `rectTabAreaBottom`  
 Ссылка на объект `CRect`. `GetTabArea`использует этот объект для хранения, размер и положение нижней области вкладки.  
  
### <a name="remarks"></a>Примечания  
 После `GetTabArea` возвращает, `CRect` параметры содержат размер и положение область вкладки в клиентских координат элемента управления "Вкладка". Если отсутствует область вкладки в верхней или нижней части вкладок, `rectTabAreaTop` или `rectTabAreaBottom` пусты.  
  
 В `CMFCBaseTabCtrl Class`, этот метод является чисто виртуальную функцию и не имеет реализации. При наследовании от класса `CMFCBaseTabCtrl`, необходимо реализовать эту функцию.  
  
##  <a name="a-namegettabbkcolora--cmfcbasetabctrlgettabbkcolor"></a><a name="gettabbkcolor"></a>CMFCBaseTabCtrl::GetTabBkColor  
 Получает цвет фона для указанной вкладки.  
  
```  
virtual COLORREF GetTabBkColor(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, указывающее цвет фона для указанной вкладки; -1, если `iTab` выходит за пределы диапазона.  
  
##  <a name="a-namegettabbordersizea--cmfcbasetabctrlgettabbordersize"></a><a name="gettabbordersize"></a>CMFCBaseTabCtrl::GetTabBorderSize  
 Получает размер границы вкладок в элементе управления вкладками.  
  
```  
virtual int GetTabBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер границы вкладки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Размер по умолчанию для границы вкладка — трем точкам. Этот размер границы можно изменить с помощью метода [CMFCBaseTabCtrl::SetTabBorderSize](#settabbordersize).  
  
##  <a name="a-namegettabbyida--cmfcbasetabctrlgettabbyid"></a><a name="gettabbyid"></a>CMFCBaseTabCtrl::GetTabByID  
 Извлекает индекс вкладки, на основе идентификатора вкладки.  
  
```  
virtual int GetTabByID(int id) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `id`  
 Идентификатор вкладки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс вкладки, если он найден; значение -1, если вкладка идентификатор не найден.  
  
### <a name="remarks"></a>Примечания  
 Вкладке идентификаторы назначаются автоматически при добавлении вкладок в наборе вкладок.  
  
##  <a name="a-namegettabclosebuttona--cmfcbasetabctrlgettabclosebutton"></a><a name="gettabclosebutton"></a>CMFCBaseTabCtrl::GetTabCloseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabfromhwnda--cmfcbasetabctrlgettabfromhwnd"></a><a name="gettabfromhwnd"></a>CMFCBaseTabCtrl::GetTabFromHwnd  
 Извлекает индекс вкладку, которая содержит указанный объект HWND.  
  
```  
virtual int GetTabFromHwnd(HWND hwnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hwnd`  
 Дескриптор окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс вкладки в случае успешного выполнения; -1, если отсутствует вкладка содержит `hwnd`.  
  
##  <a name="a-namegettabfrompointa--cmfcbasetabctrlgettabfrompoint"></a><a name="gettabfrompoint"></a>CMFCBaseTabCtrl::GetTabFromPoint  
 Получает вкладку, содержащую заданной точке.  
  
```  
virtual int GetTabFromPoint(CPoint& pt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Точка управления "Вкладка" в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс вкладки, который содержит `pt`; -1, если отсутствует вкладка содержит `pt`.  
  
##  <a name="a-namegettabfullwidtha--cmfcbasetabctrlgettabfullwidth"></a><a name="gettabfullwidth"></a>CMFCBaseTabCtrl::GetTabFullWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetTabFullWidth(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabhicona--cmfcbasetabctrlgettabhicon"></a><a name="gettabhicon"></a>CMFCBaseTabCtrl::GetTabHicon  
 Возвращает HICON, связанные с указанной вкладки.  
  
```  
virtual HICON GetTabHicon(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс для вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 HICON, связанный с меткой вкладку в случае успешного выполнения; `NULL` при не HICON или если происходит сбой метода.  
  
##  <a name="a-namegettabicona--cmfcbasetabctrlgettabicon"></a><a name="gettabicon"></a>CMFCBaseTabCtrl::GetTabIcon  
 Получает значок, связанный с указанной вкладки.  
  
```  
virtual UINT GetTabIcon(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значок идентификатор для указанной вкладки в случае успешного выполнения; значение -1, если индекс является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объект сохраняет значки во внутренней [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
##  <a name="a-namegettabida--cmfcbasetabctrlgettabid"></a><a name="gettabid"></a>CMFCBaseTabCtrl::GetTabID  
 Извлекает идентификатор для вкладки, заданного посредством индекса вкладки.  
  
```  
int GetTabID(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор вкладки или -1, если `iTab` выходит за пределы диапазона.  
  
##  <a name="a-namegettablabela--cmfcbasetabctrlgettablabel"></a><a name="gettablabel"></a>CMFCBaseTabCtrl::GetTabLabel  
 Извлекает текст подписи вкладки.  
  
```  
virtual BOOL GetTabLabel(
    int iTab,  
    CString& strLabel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [выходной] `strLabel`  
 Ссылка на объект `CString`. Этот метод сохраняет подпись вкладки в этом параметре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если индекс `iTab` является недопустимым.  
  
 Установите метку для вкладки, при создании вкладки с помощью [CMFCBaseTabCtrl::AddTab](#addtab). Можно также изменить метку, после создания с помощью метода [CMFCBaseTabCtrl::SetTabLabel](#settablabel).  
  
##  <a name="a-namegettabrecta--cmfcbasetabctrlgettabrect"></a><a name="gettabrect"></a>CMFCBaseTabCtrl::GetTabRect  
 Получает размер и положение заданной вкладки.  
  
```  
virtual BOOL GetTabRect(
    int iTab,  
    CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [выходной] `rect`  
 Ссылка на объект `CRect`. Этот метод сохраняет размер и положение вкладки в этом параметре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` Если индекс вкладки недействителен.  
  
##  <a name="a-namegettabsheighta--cmfcbasetabctrlgettabsheight"></a><a name="gettabsheight"></a>CMFCBaseTabCtrl::GetTabsHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabsnuma--cmfcbasetabctrlgettabsnum"></a><a name="gettabsnum"></a>CMFCBaseTabCtrl::GetTabsNum  
 Получает число вкладок в элементе управления вкладками.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество вкладок в элементе управления вкладками.  
  
##  <a name="a-namegettabsrecta--cmfcbasetabctrlgettabsrect"></a><a name="gettabsrect"></a>CMFCBaseTabCtrl::GetTabsRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabtextcolora--cmfcbasetabctrlgettabtextcolor"></a><a name="gettabtextcolor"></a>CMFCBaseTabCtrl::GetTabTextColor  
 Возвращает цвет текста для указанной вкладки.  
  
```  
virtual COLORREF GetTabTextColor(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет текста заданной вкладки; -1, если `iTab` выходит за пределы диапазона.  
  
##  <a name="a-namegettabwnda--cmfcbasetabctrlgettabwnd"></a><a name="gettabwnd"></a>CMFCBaseTabCtrl::GetTabWnd  
 Возвращает указатель на области, в которой находится на указанной вкладки.  
  
```  
virtual CWnd* GetTabWnd(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, который находится на вкладке, `iTab` указывает. `NULL`Если `iTab` является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект является тот, который при его вызове, либо добавить приложение [CMFCBaseTabCtrl::AddTab](#addtab) или [CMFCBaseTabCtrl::InsertTab](#inserttab).  
  
 Если у объекта на вкладке программа-оболочка, этот метод вернет оболочку для объекта. Дополнительные сведения о оболочек см [CMFCBaseTabCtrl::CreateWrapper](#createwrapper). Если требуется доступ к указателю на объект непосредственно, без оболочки, используйте метод [CMFCBaseTabCtrl::GetTabWndNoWrapper](#gettabwndnowrapper).  
  
##  <a name="a-namegettabwndnowrappera--cmfcbasetabctrlgettabwndnowrapper"></a><a name="gettabwndnowrapper"></a>CMFCBaseTabCtrl::GetTabWndNoWrapper  
 Возвращает указатель к элементу управления, который находится на вкладке, даже если элемент управления имеет оболочки.  
  
```  
virtual CWnd* GetTabWndNoWrapper(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, находящийся в указанной вкладки; `NULL` Если `iTab` является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 Этот метод получает прямой указатель `CWnd` объект, добавленный с помощью любого метода [CMFCBaseTabCtrl::AddTab](#addtab) или [CMFCBaseTabCtrl::InsertTab](#inserttab). `GetTabWndNoWrapper`Извлекает указатель на добавленный `CWnd`, даже если платформа оболочку для объекта. Дополнительные сведения о оболочки и [класса CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md), в разделе [CMFCBaseTabCtrl::CreateWrapper](#createwrapper).  
  
 Используйте метод [CMFCBaseTabCtrl::GetTabWnd](#gettabwnd) Если вы не хотите игнорировать класс-оболочку.  
  
##  <a name="a-namegettooltipctrla--cmfcbasetabctrlgettooltipctrl"></a><a name="gettooltipctrl"></a>CMFCBaseTabCtrl::GetToolTipCtrl  
 Извлекает ссылку производится всплывающей подсказки.  
  
```  
CToolTipCtrl& GetToolTipCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент управления всплывающей подсказки.  
  
##  <a name="a-namegetvisibletabsnuma--cmfcbasetabctrlgetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CMFCBaseTabCtrl::GetVisibleTabsNum  
 Получает количество видимых вкладок.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число вкладок видимым.  
  
##  <a name="a-namehasimagea--cmfcbasetabctrlhasimage"></a><a name="hasimage"></a>CMFCBaseTabCtrl::HasImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasImage(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehidesingletaba--cmfcbasetabctrlhidesingletab"></a><a name="hidesingletab"></a>CMFCBaseTabCtrl::HideSingleTab  
 Задает параметр для скрытия областей для вкладок элемента управления при одной вкладки видимыми.  
  
```  
virtual void HideSingleTab(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHide`  
 Логическое значение, указывающее, следует ли включить скрытие одной вкладки.  
  
### <a name="remarks"></a>Примечания  
 Если приложение настроено для скрытия одной вкладки, платформа автоматически отображает вкладки при добавлении второй вкладке вкладок элемента управления.  
  
##  <a name="a-nameinserttaba--cmfcbasetabctrlinserttab"></a><a name="inserttab"></a>CMFCBaseTabCtrl::InsertTab  
 Вставляет знак табуляции в вкладок элемента управления.  
  
```  
Virtual void InsertTab(
    CWnd* pNewWnd,  
    LPCTSTR lpszTabLabel,  
    int nInsertAt,  
    UINT uiImageId = (UINT)-1,  
    BOOL bDetachable = TRUE);

 
virtual void InsertTab(
    CWnd* pNewWnd,  
    UINT uiResTabLabel,  
    int nInsertAt,  
    UINT uiImageId = (UINT)-1,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pNewWnd`  
 Указатель на окно, этот метод добавляет в виде новой вкладки.  
  
 [in] `lpszTabLabel`  
 Строка, содержащая метки новой вкладки.  
  
 [in] `nInsertAt`  
 Отсчитываемый от нуля индекс новой вкладки.  
  
 [in] `uiImageId`  
 Идентификатор изображения из списка изображений. Элемент управления вкладки использует этот образ как значок новой вкладки.  
  
 [in] `bDetachable`  
 Логический параметр, который определяет, является ли новая вкладка отключаемых.  
  
 [in] `uiResTabLabel`  
 Идентификатор ресурса для метки.  
  
### <a name="remarks"></a>Примечания  
 Если объект обозначается `pNewWnd` не является производным от [класса CDockablePane](../../mfc/reference/cdockablepane-class.md) и, если `bDetachable` параметр `TRUE`, платформа создает специальные программы-оболочки для новой вкладки. По умолчанию оболочка представляет собой экземпляр [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md). Используйте [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](#setdockingbarwrapperrtc) метод для создания различных обертку. Любой пользовательский класс-оболочку должен быть производным от `CDockablePaneAdapter`.  
  
##  <a name="a-nameinvalidatetaba--cmfcbasetabctrlinvalidatetab"></a><a name="invalidatetab"></a>CMFCBaseTabCtrl::InvalidateTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void InvalidateTab(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisactivetabclosebuttona--cmfcbasetabctrlisactivetabclosebutton"></a><a name="isactivetabclosebutton"></a>CMFCBaseTabCtrl::IsActiveTabCloseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisautocolora--cmfcbasetabctrlisautocolor"></a><a name="isautocolor"></a>CMFCBaseTabCtrl::IsAutoColor  
 Определяет, является ли элемент управления вкладки в режиме autocolor.  
  
```  
BOOL IsAutoColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент управления вкладки находится в режиме autocolor; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить режим autocolor с помощью [CMFCBaseTabCtrl::EnableAutoColor](#enableautocolor) метод.  
  
##  <a name="a-nameisautodestroywindowa--cmfcbasetabctrlisautodestroywindow"></a><a name="isautodestroywindow"></a>CMFCBaseTabCtrl::IsAutoDestroyWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAutoDestroyWindow() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiscoloreda--cmfcbasetabctrliscolored"></a><a name="iscolored"></a>CMFCBaseTabCtrl::IsColored  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsColored() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdialogcontrola--cmfcbasetabctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>CMFCBaseTabCtrl::IsDialogControl  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdrawnoprefixa--cmfcbasetabctrlisdrawnoprefix"></a><a name="isdrawnoprefix"></a>CMFCBaseTabCtrl::IsDrawNoPrefix  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDrawNoPrefix() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisflatframea--cmfcbasetabctrlisflatframe"></a><a name="isflatframe"></a>CMFCBaseTabCtrl::IsFlatFrame  
 Указывает, отображается ли в плоский или трехмерный стиль рамки вкладок элемента управления.  
  
```  
virtual BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если рамки вкладок элемента управления отображается в плоский; `FALSE` при отрисовке фрейма в трехмерный стиль.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCTabCtrl::SetFlatFrame](../../mfc/reference/cmfctabctrl-class.md#setflatframe) изменить стиль рамки вкладок элемента управления.  
  
 Элементы управления вкладка, использующие Outlook невозможно с плоскими кадров. Сюда входят [CMFCOutlookBarTabCtrl класса](../../mfc/reference/cmfcoutlookbartabctrl-class.md) и любые классы, производные от этого класса.  
  
##  <a name="a-nameisflattaba--cmfcbasetabctrlisflattab"></a><a name="isflattab"></a>CMFCBaseTabCtrl::IsFlatTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameishidesingletaba--cmfcbasetabctrlishidesingletab"></a><a name="ishidesingletab"></a>CMFCBaseTabCtrl::IsHideSingleTab  
 Определяет ли вкладок скрывает метку вкладки, если имеется только одна вкладка.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладок скрывает всплывающие при наличии одной вкладки; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте метод [CMFCBaseTabCtrl::HideSingleTab](#hidesingletab) Чтобы скрыть метку вкладки при наличии только одной вкладки.  
  
##  <a name="a-nameisiconaddeda--cmfcbasetabctrlisiconadded"></a><a name="isiconadded"></a>CMFCBaseTabCtrl::IsIconAdded  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsIconAdded(
    HICON hIcon,  
    int& iIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 [in] `iIcon`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisinplaceedita--cmfcbasetabctrlisinplaceedit"></a><a name="isinplaceedit"></a>CMFCBaseTabCtrl::IsInPlaceEdit  
 Указывает, настроен ли вкладок элемента управления, чтобы дать пользователю возможность динамически изменять метки вкладок.  
  
```  
virtual BOOL IsInPlaceEdit() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в месте редактирование разрешено; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить, вызвав метод редактирования на месте [CMFCBaseTabCtrl::EnableInPlaceEdit](#enableinplaceedit).  
  
##  <a name="a-nameisleftrightroundeda--cmfcbasetabctrlisleftrightrounded"></a><a name="isleftrightrounded"></a>CMFCBaseTabCtrl::IsLeftRightRounded  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameismditaba--cmfcbasetabctrlismditab"></a><a name="ismditab"></a>CMFCBaseTabCtrl::IsMDITab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMDITab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisonenotestylea--cmfcbasetabctrlisonenotestyle"></a><a name="isonenotestyle"></a>CMFCBaseTabCtrl::IsOneNoteStyle  
 Определяет отображение вкладок в стиле Microsoft OneNote.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладки в стиле Microsoft OneNote; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите метод [CMDIFrameWndEx::EnableMDITabs](../../mfc/reference/cmdiframewndex-class.md#enablemditabs) Включение стиля Microsoft OneNote. Можно также включить этот стиль, при создании экземпляра [класса CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md): просто передается методу стиль STYLE_3D_ONENOTE [CMFCTabCtrl::Create](../../mfc/reference/cmfctabctrl-class.md#create).  
  
 По умолчанию стиль Microsoft OneNote не поддерживается в пользовательский класс, производный от `CMFCBaseTabCtrl Class`. Тем не менее, поддерживается в `CMFCTabCtrl` класса.  
  
##  <a name="a-nameisptintabareaa--cmfcbasetabctrlisptintabarea"></a><a name="isptintabarea"></a>CMFCBaseTabCtrl::IsPtInTabArea  
 Определяет, является ли точка внутри области вкладки.  
  
```  
virtual BOOL IsPtInTabArea(CPoint point) const = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точка для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если точка находится в области вкладки. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 В `CMFCBaseTabCtrl Class`, этот метод является чисто виртуальную функцию и не имеет реализации. При наследовании от класса `CMFCBaseTabCtrl`, необходимо реализовать эту функцию.  
  
##  <a name="a-nameistabclosebuttonhighlighteda--cmfcbasetabctrlistabclosebuttonhighlighted"></a><a name="istabclosebuttonhighlighted"></a>CMFCBaseTabCtrl::IsTabCloseButtonHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsTabCloseButtonHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameistabclosebuttonpresseda--cmfcbasetabctrlistabclosebuttonpressed"></a><a name="istabclosebuttonpressed"></a>CMFCBaseTabCtrl::IsTabCloseButtonPressed  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsTabCloseButtonPressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameistabdetachablea--cmfcbasetabctrlistabdetachable"></a><a name="istabdetachable"></a>CMFCBaseTabCtrl::IsTabDetachable  
 Определяет, является ли отключаемых вкладки.  
  
```  
virtual BOOL IsTabDetachable(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладка отключаемых; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сделать на вкладке отключаемых, используйте метод [CMFCBaseTabCtrl::EnableTabDetach](#enabletabdetach).  
  
##  <a name="a-nameistabicononlya--cmfcbasetabctrlistabicononly"></a><a name="istabicononly"></a>CMFCBaseTabCtrl::IsTabIconOnly  
 Определяет, содержит ли подпись вкладки только значки и текст.  
  
```  
virtual BOOL IsTabIconOnly(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладка метка имеет только значки. `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Установка позиций табуляции в приложении для отображения только значков, вызовите метод [CMFCBaseTabCtrl::SetTabIconOnly](#settabicononly).  
  
##  <a name="a-nameistabswapenableda--cmfcbasetabctrlistabswapenabled"></a><a name="istabswapenabled"></a>CMFCBaseTabCtrl::IsTabSwapEnabled  
 Определяет, позволяет ли вкладок пользователю изменять позиций табуляции с помощью мыши.  
  
```  
BOOL IsTabSwapEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если позиций табуляции может изменяться пользователем; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию пользователи не могут изменять порядок вкладок в наборе вкладок. Используйте [CMFCBaseTabCtrl::EnableTabSwap](#enabletabswap) метод, чтобы включить эту функцию.  
  
##  <a name="a-nameistabvisiblea--cmfcbasetabctrlistabvisible"></a><a name="istabvisible"></a>CMFCBaseTabCtrl::IsTabVisible  
 Указывает, видима ли указанной вкладки.  
  
```  
virtual BOOL IsTabVisible(int iTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанная вкладка является видимым. в противном случае — 0.  
  
##  <a name="a-nameisvs2005stylea--cmfcbasetabctrlisvs2005style"></a><a name="isvs2005style"></a>CMFCBaseTabCtrl::IsVS2005Style  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namembactivatetabonrightclicka--cmfcbasetabctrlmbactivatetabonrightclick"></a><a name="m_bactivatetabonrightclick"></a>CMFCBaseTabCtrl::m_bActivateTabOnRightClick  
 `m_bActivateTabOnRightClick`Определяет вкладки в фокус, когда пользователь щелкает ярлычок с помощью правой кнопки мыши.  
  
```  
BOOL m_bActivateTabOnRightClick;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для этого элемента данных — `FALSE`.  
  
##  <a name="a-namembautodestroywindowa--cmfcbasetabctrlmbautodestroywindow"></a><a name="m_bautodestroywindow"></a>CMFCBaseTabCtrl::m_bAutoDestroyWindow  
 `m_bAutoDestroyWindow`Определяет ли платформа автоматически удаляет объекты на вкладках при удалении вкладки.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию, этот член является `FALSE`.  
  
##  <a name="a-namemovetaba--cmfcbasetabctrlmovetab"></a><a name="movetab"></a>CMFCBaseTabCtrl::MoveTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void MoveTab(
    int nSource,  
    int nDest);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSource`  
 [in] `nDest`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonchangetabsa--cmfcbasetabctrlonchangetabs"></a><a name="onchangetabs"></a>CMFCBaseTabCtrl::OnChangeTabs  
 Платформа вызывает этот метод, когда число вкладок на вкладке управления изменениями.  
  
```  
virtual void OnChangeTabs();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод для выполнения пользовательского кода, когда число вкладок на вкладке управления изменениями.  
  
##  <a name="a-nameondropa--cmfcbasetabctrlondrop"></a><a name="ondrop"></a>CMFCBaseTabCtrl::OnDrop  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnDrop(
    COleDataObject*,
    DROPEFFECT,
    CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `COleDataObject*`  
 [in] `DROPEFFECT`  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondragovera--cmfcbasetabctrlondragover"></a><a name="ondragover"></a>CMFCBaseTabCtrl::OnDragOver  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject*,
    DWORD,
    CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `COleDataObject*`  
 [in] `DWORD`  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondragleavea--cmfcbasetabctrlondragleave"></a><a name="ondragleave"></a>CMFCBaseTabCtrl::OnDragLeave  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondragentera--cmfcbasetabctrlondragenter"></a><a name="ondragenter"></a>CMFCBaseTabCtrl::OnDragEnter  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject*,
    DWORD,
    CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `COleDataObject*`  
 [in] `DWORD`  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrenametaba--cmfcbasetabctrlonrenametab"></a><a name="onrenametab"></a>CMFCBaseTabCtrl::OnRenameTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnRenameTab(int, CString&);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `int`  
 [in] `CString&`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namepretranslatemessagea--cmfcbasetabctrlpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCBaseTabCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namerecalclayouta--cmfcbasetabctrlrecalclayout"></a><a name="recalclayout"></a>CMFCBaseTabCtrl::RecalcLayout  
 Повторно вычисляет макет внутреннего набора вкладок.  
  
```  
virtual void RecalcLayout() = 0;  
```  
  
### <a name="remarks"></a>Примечания  
 В `CMFCBaseTabCtrl Class`, этот метод является чисто виртуальную функцию. При наследовании от класса `CMFCBaseTabCtrl`, необходимо реализовать эту функцию.  
  
##  <a name="a-nameremovealltabsa--cmfcbasetabctrlremovealltabs"></a><a name="removealltabs"></a>CMFCBaseTabCtrl::RemoveAllTabs  
 Удаляет все вкладки из вкладок элемента управления.  
  
```  
virtual void RemoveAllTabs();
```  
  
### <a name="remarks"></a>Примечания  
 Если [CMFCBaseTabCtrl::m_bAutoDestroyWindow](#m_bautodestroywindow) — `TRUE`, платформа удаляет все [CWnd](../../mfc/reference/cwnd-class.md) объекты присоединяются на удаленные таблицы.  
  
##  <a name="a-nameremovetaba--cmfcbasetabctrlremovetab"></a><a name="removetab"></a>CMFCBaseTabCtrl::RemoveTab  
 Удаление вкладки из вкладок элемента управления.  
  
```  
virtual BOOL RemoveTab(
    int iTab,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [in] `bRecalcLayout`  
 Логический параметр, который указывает, следует ли повторно рассчитать компоновку вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод удаляет вкладку успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если [CMFCBaseTabCtrl::m_bAutoDestroyWindow](#m_bautodestroywindow) — `TRUE`, `RemoveTab` уничтожает [CWnd](../../mfc/reference/cwnd-class.md) объект, связанный с указанной вкладки.  
  
##  <a name="a-namerenametaba--cmfcbasetabctrlrenametab"></a><a name="renametab"></a>CMFCBaseTabCtrl::RenameTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL RenameTab();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameresetimagelista--cmfcbasetabctrlresetimagelist"></a><a name="resetimagelist"></a>CMFCBaseTabCtrl::ResetImageList  
 Сбрасывает список изображений для экземпляра [CMFCBaseTabCtrl класса](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
```  
void ResetImageList();
```  
  
##  <a name="a-nameserializea--cmfcbasetabctrlserialize"></a><a name="serialize"></a>CMFCBaseTabCtrl::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetactivetaba--cmfcbasetabctrlsetactivetab"></a><a name="setactivetab"></a>CMFCBaseTabCtrl::SetActiveTab  
 Активирует указанной вкладки.  
  
```  
virtual BOOL SetActiveTab(int iTab) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки. `SetActiveTab`делает вкладку с таким индексом active.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В `CMFCBaseTabCtrl Class`, этот метод является чисто виртуальную функцию. При наследовании от класса `CMFCBaseTabCtrl`, необходимо реализовать эту функцию.  
  
##  <a name="a-namesetactivetabcolora--cmfcbasetabctrlsetactivetabcolor"></a><a name="setactivetabcolor"></a>CMFCBaseTabCtrl::SetActiveTabColor  
 Задает цвет фона для активной вкладки.  
  
```  
virtual void SetActiveTabColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clr`  
 Указывает новый цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Платформа получает цвет фона по умолчанию для активной вкладки из [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)метод.  
  
##  <a name="a-namesetactivetabtextcolora--cmfcbasetabctrlsetactivetabtextcolor"></a><a name="setactivetabtextcolor"></a>CMFCBaseTabCtrl::SetActiveTabTextColor  
 Задает цвет текста для активных вкладок.  
  
```  
virtual void SetActiveTabTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clr`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, который указывает новый цвет текста.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа получает цвет текста из [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371). Переопределить этот цвет по умолчанию с помощью `SetActiveTabTextColor` метод.  
  
##  <a name="a-namesetautocolorsa--cmfcbasetabctrlsetautocolors"></a><a name="setautocolors"></a>CMFCBaseTabCtrl::SetAutoColors  
 Задает цвета элемента управления вкладками, инфраструктура использует в режиме автоматического цветов.  
  
```  
void SetAutoColors(const CArray<COLORREF,COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `arColors`  
 Массив цветов RGB.  
  
### <a name="remarks"></a>Примечания  
 Если предоставляется пользовательский массив цветов, массив цветов по умолчанию игнорируется. Если параметр `arColors` является пустым, платформа возвращается массив цветов по умолчанию.  
  
 Чтобы включить режим autocolor, используйте [CMFCBaseTabCtrl::EnableAutoColor](#enableautocolor) метод.  
  
##  <a name="a-namesetdockingbarwrapperrtca--cmfcbasetabctrlsetdockingbarwrapperrtc"></a><a name="setdockingbarwrapperrtc"></a>CMFCBaseTabCtrl::SetDockingBarWrapperRTC  
 Задает класс-оболочку, который используется для всех объектов, которые не являются производными от [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).  
  
```  
void SetDockingBarWrapperRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTC`  
 Информация о классе среды выполнения для нового класса-оболочки.  
  
### <a name="remarks"></a>Примечания  
 Можно добавить вкладки в набор вкладок с помощью методов [CMFCBaseTabCtrl::AddTab](#addtab) и [CMFCBaseTabCtrl::InsertTab](#inserttab). При добавлении вкладки, должен быть фиксируемого каждого элемента управления на этой вкладке. Все объекты, которые не являются производными от `CDockablePane` , должны быть упакованы. `AddTab`и `InsertTab` создание оболочки для этих объектов. По умолчанию используется класс обертки [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md). Метод `SetDockingBarWrapperRTC` позволяет изменить класс, который используется как класс-оболочку. Класс-оболочка, указываемое должен быть производным от `CDockablePaneAdapter`.  
  
##  <a name="a-namesetdrawnoprefixa--cmfcbasetabctrlsetdrawnoprefix"></a><a name="setdrawnoprefix"></a>CMFCBaseTabCtrl::SetDrawNoPrefix  
 Включает и выключает обработку символов префикса метки вкладок.  
  
```  
void SetDrawNoPrefix(
    BOOL bNoPrefix,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNoPrefix`  
 `TRUE`Если вы хотите обрабатывать символы префикса; в противном случае `FALSE`.  
  
 [in] `bRedraw`  
 `TRUE`Если требуется перерисовать окна с вкладками. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Назначенный символ, следующий за знаком амперсанда (&) является символ префикса.  
  
##  <a name="a-namesetimagelista--cmfcbasetabctrlsetimagelist"></a><a name="setimagelist"></a>CMFCBaseTabCtrl::SetImageList  
 Задает список изображений значков для вкладок элемента управления.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx = 15,  
    COLORREF clrTransp = RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор ресурса растрового изображения. `SetImageList`загружает список изображений из данного ресурса.  
  
 [in] `cx`  
 Ширина каждого изображения в пикселях.  
  
 [in] `clrTransp`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, который указывает прозрачный цвет изображения.  
  
 [in] `hImageList`  
 Дескриптор список предварительно загруженные изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Изображения из списка значок изображения отображаются наряду с метки для вкладки. Чтобы отобразить значок, необходимо указать его индекс, при вызове [CMFCBaseTabCtrl::AddTab](#addtab).  
  
 `SetImageList`Если вкладок элемента управления был создан с плоский завершится ошибкой. Она также завершится неудачно, если платформа не удается загрузить изображение согласно `uiID`.  
  
 Этот метод пересчитывает высоту вкладки по размерам текста и изображений.  
  
##  <a name="a-namesetlocationa--cmfcbasetabctrlsetlocation"></a><a name="setlocation"></a>CMFCBaseTabCtrl::SetLocation  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetLocation(Location location);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `location`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettabbkcolora--cmfcbasetabctrlsettabbkcolor"></a><a name="settabbkcolor"></a>CMFCBaseTabCtrl::SetTabBkColor  
 Задает цвет фона для указанной вкладки.  
  
```  
virtual BOOL SetTabBkColor(
    int iTab,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [in] `color`  
 Чтобы задать цвет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` в противном случае.  
  
##  <a name="a-namesettabbordersizea--cmfcbasetabctrlsettabbordersize"></a><a name="settabbordersize"></a>CMFCBaseTabCtrl::SetTabBorderSize  
 Задает новый размер границы вкладок элемента управления.  
  
```  
virtual void SetTabBorderSize(
    int nTabBorderSize,  
    BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTabBorderSize`  
 Новый размер границы в пикселях.  
  
 [in] `bRepaint`  
 Логический параметр, указывает ли платформа обновит элемент управления.  
  
##  <a name="a-namesettabhicona--cmfcbasetabctrlsettabhicon"></a><a name="settabhicon"></a>CMFCBaseTabCtrl::SetTabHicon  
 Задает значок для название вкладки.  
  
```  
virtual BOOL SetTabHicon(
    int iTab,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки. Этот метод изменяет значок для этой вкладки.  
  
 [in] `hIcon`  
 Дескриптор для значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
##  <a name="a-namesettabicona--cmfcbasetabctrlsettabicon"></a><a name="settabicon"></a>CMFCBaseTabCtrl::SetTabIcon  
 Задает значок для вкладки.  
  
```  
virtual BOOL SetTabIcon(
    int iTab,  
    UINT uiIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для обновления.  
  
 [in] `uiIcon`  
 Значок идентификатор нового значка. Этот идентификатор ссылается на внутренний [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
##  <a name="a-namesettabicononlya--cmfcbasetabctrlsettabicononly"></a><a name="settabicononly"></a>CMFCBaseTabCtrl::SetTabIconOnly  
 Включает отображение только значок (и текстовая метка не) на определенной вкладке.  
  
```  
virtual BOOL SetTabIconOnly(
    int iTab,  
    BOOL bIconOnly = TRUE,  
    BOOL bShowTooltipAlways = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс tab для изменения.  
  
 [in] `bIconOnly`  
 Логический параметр, который определяет, следует ли отображать только значки.  
  
 [in] `bShowTooltipAlways`  
 Логический параметр, который определяет, отображаются ли платформа всплывающие подсказки для метка вкладка, отображающая только значки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию элемент управления вкладками отображает значок и текст метки для каждой вкладки.  
  
##  <a name="a-namesettablabela--cmfcbasetabctrlsettablabel"></a><a name="settablabel"></a>CMFCBaseTabCtrl::SetTabLabel  
 Задает текст метки вкладки.  
  
```  
virtual BOOL SetTabLabel(
    int iTab,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для обновления.  
  
 [in] `strLabel`  
 Ссылка на строку, содержащую новый текст метки вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
##  <a name="a-namesettabsheighta--cmfcbasetabctrlsettabsheight"></a><a name="settabsheight"></a>CMFCBaseTabCtrl::SetTabsHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetTabsHeight();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettabsordera--cmfcbasetabctrlsettabsorder"></a><a name="settabsorder"></a>CMFCBaseTabCtrl::SetTabsOrder  
 Упорядочивает вкладки в указанном порядке.  
  
```  
BOOL SetTabsOrder(const CArray<int,int>& arOrder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `arOrder`  
 Массив индексов (с нуля), определяющий новый порядок табуляции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FAIL` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Размер `arOrder` массива должен быть равен число вкладок в элементе управления вкладками.  
  
##  <a name="a-namesettabtextcolora--cmfcbasetabctrlsettabtextcolor"></a><a name="settabtextcolor"></a>CMFCBaseTabCtrl::SetTabTextColor  
 Задает цвет текста для определенной вкладке.  
  
```  
virtual BOOL SetTabTextColor(
    int iTab,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки.  
  
 [in] `color`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, который указывает новый цвет текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
##  <a name="a-nameshowtaba--cmfcbasetabctrlshowtab"></a><a name="showtab"></a>CMFCBaseTabCtrl::ShowTab  
 Отображает или скрывает указанную вкладку.  
  
```  
virtual BOOL ShowTab(
    int iTab,  
    BOOL bShow = TRUE,  
    BOOL bRecalcLayout = TRUE,  
    BOOL bActivate = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Индекс вкладки, `ShowTab` будет отображать или скрывать.  
  
 [in] `bShow`  
 Логический параметр, который указывает, следует ли отображать вкладку.  
  
 [in] `bRecalcLayout`  
 Логический параметр, который указывает, следует ли немедленно повторно вычислить макет окна.  
  
 [in] `bActivate`  
 Логический параметр, который указывает на необходимость выбрать вкладку, указанную в `iTab`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Параметр `bActivate` применяется, только если `bShow` — `TRUE`. Если `bActivate` — `TRUE` и, если `ShowTab` прошла успешно, `ShowTab` отправит сообщение AFX_WM_CHANGE_ACTIVE_TAB родительского окна вкладки.  
  
##  <a name="a-namestartrenametaba--cmfcbasetabctrlstartrenametab"></a><a name="startrenametab"></a>CMFCBaseTabCtrl::StartRenameTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL StartRenameTab(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameswaptabsa--cmfcbasetabctrlswaptabs"></a><a name="swaptabs"></a>CMFCBaseTabCtrl::SwapTabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SwapTabs(
    int nFisrtTabID,  
    int nSecondTabID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFisrtTabID`  
 [in] `nSecondTabID`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)   
 [Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

