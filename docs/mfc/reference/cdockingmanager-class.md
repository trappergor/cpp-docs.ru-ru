---
title: "Класс CDockingManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockingManager
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager class
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
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
ms.openlocfilehash: 106046dc9dc671b5baea7c6df78b91ba37098978
ms.lasthandoff: 02/24/2017

---
# <a name="cdockingmanager-class"></a>Класс CDockingManager
Реализует базовую функциональность, которая контролирует макет закрепления в окне главного фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Создание области закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Добавление на панель дескриптор области в список скрытых MDI с вкладками областями строки.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Добавляет кадр в список мини-кадры.|  
|[CDockingManager::AddPane](#addpane)|Регистрирует область закрепления manager.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Повторно вычисляет и настраивает макета всех областей в окне фрейма.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Вызывает `WM_NCCALCSIZE` сообщения для всех областей и `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Выравнивает прямоугольника.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Изменяет размер закрепляемой области в режиме Автоскрытие таким образом, требуется полная ширина или Высота клиентской области фрейма, окруженный закрепление сайтов.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Создает автоматическое скрытие панели инструментов.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Переводит закрепленные столбцы, имеющие указанное выравнивание в начало.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Добавляет имена закрепляемых панелей и панели инструментов меню.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Рассчитывает ожидаемое прямоугольник закрепленное окно.|  
|[CDockingManager::Create](#create)|Создает диспетчер закрепления.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Определяет области, содержащий заданной точки и его состояние закрепления.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Включает или отключает загрузку макета закрепления из реестра.|  
|[CDockingManager::DockPane](#dockpane)|Закрепляет область в другую область или фрейме окна.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Закрепляет область слева от другой области.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Позволяет Закрепление панели в основном фрейме, создается область закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::EnableDocking](#enabledocking)|Создание области закрепления и позволяет Закрепление панели в основном фрейме.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Отображает дополнительные кнопки открывается всплывающее меню заголовков всех закрепляемых панелей.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Указывает библиотеку для вызова специальных контекстного меню со списком приложений панелей инструментов и закрепляемых областей, при щелчке правой кнопкой мыши и библиотеке обрабатывает сообщение WM_CONTEXTMENU и Показать сообщение.|  
|[CDockingManager::FindDockSite](#finddocksite)|Извлекает строке области в указанной позиции и имеющего указанное выравнивание.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Возвращает панель с идентификатором область панели целевой области.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Находит панели с помощью идентификатора указанного элемента управления.|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Фиксирует все текущее положение панелей инструментов в виртуальный прямоугольники.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Возвращает фрейма, содержащего заданной точки.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Возвращает прямоугольник, содержащий границы клиентской области.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Возвращает текущий режим закрепления.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Возвращает указатель на родительского окна.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Возвращает включено выравнивание областей.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Получает список miniframes.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Возвращает прямоугольник, содержащий внешние края рамки.|  
|[CDockingManager::GetPaneList](#getpanelist)|Возвращает список областей, относящиеся к диспетчеру закрепления. Сюда входят все плавающей панели.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Извлекает указатель на смарт-закрепления manager.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Извлекает указатель на смарт-закрепления manager.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Возвращает параметры смарт-закрепления для закрепления диспетчера.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Статический метод, возвращающий темы, используемый для отображения интеллектуальные маркеры стыковки.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Скрывает область, в которой находится в режиме Автоскрытие.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Создание области закрепления и вставляет его в списке панелей элементов управления.|  
|[CDockingManager::InsertPane](#insertpane)|Вставляет панели управления в списке панелей элементов управления.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Задает отображение всплывающего меню заголовков всех областей.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Определяет, если корректируются макеты всех областей.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Указывает, является ли закрепления manager в режиме контейнера OLE.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайта закрепления.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Определяет, если задан режим предварительного просмотра.|  
|[CDockingManager::LoadState](#loadstate)|Загружает состояние стыковки manager из реестра.|  
|[CDockingManager::LockUpdate](#lockupdate)|Блокирует данного окна.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Вызывается инфраструктурой при фрейме окна делается активным или отключена.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Вызывается платформой для перемещения окна области.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Вызывается инфраструктурой при построении меню, которое содержит список областей.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Возвращает область, содержащую заданной точки.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Вызывается платформой установите или снимите флажок для определенной команды и перерасчет макета отображаются области.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Повторно вычисляет внутренней структуры элементов управления, присутствует в списке элементов управления.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Освобождает контейнеры пустая область.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Удаляет указанный скрыты панели области.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Удаляет указанный промежуток в списке мини-кадры.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет регистрацию область и удаляет его из списка в диспетчере закрепления.|  
|[CDockingManager::ReplacePane](#replacepane)|Заменяет одну панель другой.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Использует кадров в списке мини-кадры.|  
|[CDockingManager::SaveState](#savestate)|Сохраняет состояние стыковки manager в реестре.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Отправляет указанное сообщение все мини-кадры.|  
|[CDockingManager::Serialize](#serialize)|Записывает закрепления manager в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Задает размер, ширина и высота панели элементов управления и в указанной области.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Задает режим закрепления.|  
|[CDockingManager::SetDockState](#setdockstate)|Задает состояние закрепления панели элементов управления, мини-кадры и автоматическое скрытие панелей.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Задает режим предварительного просмотра линий, которые отображаются в режиме предварительного просмотра.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Задает параметры, которые определяют поведение смарт-закрепления.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Отображение или скрытие окна мини-кадры.|  
|[CDockingManager::ShowPanes](#showpanes)|Отображение или скрытие панели управления и автоматическое скрытие панелей.|  
|[CDockingManager::StartSDocking](#startsdocking)|Запускает смарт-закрепления указанного окна в соответствии с выравниванием смарт-закрепления manager.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Останавливает смарт-закрепления.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Указывает, скрывается ли закрепления Диспетчер панелей в режиме контейнера OLE.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Указывает глобальный режим закрепления.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Чувствительность закрепления.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Указывает время, в миллисекундах перед закрепляемой области закреплен в режиме интерпретации закрепления.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.|  
  
## <a name="remarks"></a>Примечания  
 Фрейма главного окна, создает и инициализирует автоматически.  
  
 Объект диспетчера закрепления содержит список всех областей, которые находятся в макет закрепления, а также список всех [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) windows, которые принадлежат фрейма главного окна.  
  
 `CDockingManager` Класс реализует некоторые службы, которые можно использовать для поиска в области или `CPaneFrameWnd` окна. Обычно не вызывается эти службы напрямую, так как они помещаются в объект фрейма главного окна. Дополнительные сведения см. в разделе [CPaneFrameWnd класса](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Ниже приведены рекомендации применяются к `CDockingManager` объектов:  
  
- [Класс CDockingManager](../../mfc/reference/cdockingmanager-class.md) поддерживает следующие режимы закрепления:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Эти режимы закрепления определяются [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) и установить путем вызова [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Если вы хотите создать область не с плавающей запятой, неизменяемый, вызвать [CDockingManager::AddPane](#addpane) метод. Этот метод регистрирует области закрепления диспетчер, который отвечает за размещение области.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CDockingManager` класс для настройки `CDockingManager` объекта. В примере показано, как отобразить дополнительные кнопки открывается всплывающее меню заголовков всех закрепляемых панелей и как задать режим закрепления объекта. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#24;](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDockingManager.h  
  
##  <a name="a-nameadddocksitea--cdockingmanageradddocksite"></a><a name="adddocksite"></a>CDockingManager::AddDockSite  
 Создание области закрепления и добавляет его в список панелей элементов управления.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `info`  
 Ссылка на структуру, содержащий сведения о Закрепить панель выравнивания.  
  
 [выходной] `ppDockBar`  
 Указатель на указатель на новой области закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепить панель была создана успешно. `FALSE` в противном случае.  
  
##  <a name="a-nameaddhiddenmditabbedbara--cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 Добавление на панель дескриптор области в список скрытых MDI с вкладками областями строки.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панель области  
  
##  <a name="a-nameaddpanea--cdockingmanageraddpane"></a><a name="addpane"></a>CDockingManager::AddPane  
 Регистрирует область закрепления manager.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pWnd`  
 Указывает области, чтобы добавить в диспетчер закрепления.  
  
 [in] `bTail`  
 `TRUE`для добавления в конец списка областей области для закрепления manager; в противном случае — `FALSE`.  
  
 [in] `bAutoHide`  
 Только для внутреннего использования. Всегда использовать значение по умолчанию `FALSE`.  
  
 [in] `bInsertForOuterEdge`  
 Только для внутреннего использования. Всегда использовать значение по умолчанию `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области успешно зарегистрирован с диспетчером, закрепления; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для регистрации не с плавающей запятой, неизменяемый областей с диспетчером, закрепления. Если не следует регистрировать панелей, они не будут правильно отображаться при выстраивается закрепления manager.  
  
##  <a name="a-nameadjustdockinglayouta--cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 Повторно вычисляет и настраивает макета всех областей в окне фрейма.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hdwp`  
 Указывает положение структуру отложенное окна. Дополнительные сведения см. в разделе [типы данных Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameaddminiframea--cdockingmanageraddminiframe"></a><a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 Добавляет кадр в список мини-кадры.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель кадра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если рамка не находится в списке мини-кадры и был успешно добавлен; `FALSE` в противном случае.  
  
##  <a name="a-nameadjustpaneframesa--cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 Вызывает `WM_NCCALCSIZE` сообщения для всех областей и `CPaneFrameWnd` windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameadjustrecttoclientareaa--cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea  
 Выравнивает прямоугольника.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectResult`  
 Ссылку на `CRect` объект  
  
 [in] `dwAlignment`  
 Выравнивание `CRect` объекта  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если выравнивание `CRect` была скорректирована объекта; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment` Параметр может принимать одно из следующих значений:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="a-namealignautohidepanea--cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 Изменяет размер закрепляемой области в режиме Автоскрытие таким образом, требуется полная ширина или Высота клиентской области фрейма, окруженный закрепление сайтов.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDefaultSlider`  
 Области закрепления ползунка.  
  
 [in] `bIsVisible`  
 `TRUE`Закрепляемая область является видимым; `FALSE` в противном случае.  
  
##  <a name="a-nameautohidepanea--cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingManager::AutoHidePane  
 Создает автоматическое скрытие панели инструментов.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панель области.  
  
 [in] `pCurrAutoHideToolBar`  
 Указатель на автоматическое скрытие панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `NULL`Если автоматическое скрытие панели инструментов не был создан; в противном случае указатель на новую панель инструментов.  
  
##  <a name="a-namebringbarstotopa--cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 Переводит закрепленные столбцы, имеющие указанное выравнивание в начало.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Выравнивание закрепление панелей, которые попадают в верхней части окна.  
  
 [in] `bExcludeDockedBars`  
 `TRUE`Чтобы исключить из процесса сверху; закрепленной панели в противном случае `FALSE`.  
  
##  <a name="a-namebuildpanesmenua--cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 Добавляет имена закрепляемых панелей и панели инструментов меню.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menu`  
 Меню, чтобы добавить имена закрепляемых панелей и панели инструментов.  
  
 [in] `bToolbarsOnly`  
 `TRUE`Добавление только имена панелей инструментов и меню; `FALSE` в противном случае.  
  
##  <a name="a-namecalcexpecteddockedrecta--cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect  
 Рассчитывает ожидаемое прямоугольник закрепленное окно.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на окно, чтобы закрепить.  
  
 [in] `ptMouse`  
 Положение мыши.  
  
 [выходной] `rectResult`  
 Расчетный прямоугольник.  
  
 [in] `bDrawTab`  
 `TRUE`для рисования вкладки. в противном случае `FALSE`.  
  
 [выходной] `ppTargetBar`  
 Указатель на указатель на целевой области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет прямоугольник, должны занимать окна, если пользователь перетащил окна в точку, указанную `ptMouse` и закрепленные он существует.  
  
##  <a name="a-namecreatea--cdockingmanagercreate"></a><a name="create"></a>CDockingManager::Create  
 Создает диспетчер закрепления.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель родительского фрейма для закрепления диспетчера. Это значение не должно быть `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`всегда.  
  
##  <a name="a-namedeterminepaneandstatusa--cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 Определяет области, содержащий заданной точки и его состояние закрепления.  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Расположение панели для проверки.  
  
 [in] `nSensitivity`  
 Значение, чтобы увеличить прямоугольника каждого проверенного области окна. Область удовлетворяет условиям поиска, если заданная точка находится в области повышения.  
  
 [in] `dwEnabledAlignment`  
 Выравнивание закрепляемой области.  
  
 [выходной] `ppTargetBar`  
 Указатель на указатель на целевой области.  
  
 [in] `pBarToIgnore`  
 Области, в которой этот метод игнорирует.  
  
 [in] `pBarToDock`  
 Области, расположенной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние закрепления.  
  
### <a name="remarks"></a>Примечания  
 Состояние стыковки может принимать одно из следующих значений:  
  
|Значение AFX_CS_STATUS|Значение|  
|---------------------------|-------------|  
|CS_NOTHING|Указатель не наведен сайта закрепления. Таким образом, сохранить области с плавающей запятой.|  
|CS_DOCK_IMMEDIATELY|Указатель находится на сайте закрепления в режиме интерпретации (стиль DT_IMMEDIATE включен), поэтому области должен фиксироваться немедленно.|  
|CS_DELAY_DOCK|Указатель находится над другой закрепляемую область или край фрейма главного сайта закрепления.|  
|CS_DELAY_DOCK_TO_TAB|Указатель находится на сайте закрепления, вызывающая панели для закрепления в окно с вкладками. Это происходит, когда указатель мыши находится над заголовком другой закрепляемой области или область вкладки панели с вкладками.|  
  
##  <a name="a-namedisablerestoredockstatea--cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 Включает или отключает загрузку макета закрепления из реестра.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDisable`  
 `TRUE`Чтобы отключить загрузку макет закрепления в реестре; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается в том случае, если необходимо сохранить текущую структуру закрепляемых панелей и панели инструментов при загрузке состояния приложения.  
  
##  <a name="a-namedockpanea--cdockingmanagerdockpane"></a><a name="dockpane"></a>CDockingManager::DockPane  
 Закрепляет область в другую область или фрейме окна.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на строку панели, чтобы закрепить.  
  
 [in] `nDockBarID`  
 Идентификатор окна, чтобы закрепить.  
  
 [in] `lpRect`  
 Прямоугольник назначения.  
  
##  <a name="a-namedockpaneleftofa--cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf  
 Закрепляет область слева от другой области.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBarToDock`  
 Указатель на панели, чтобы закрепить слева от `pTargetBar`.  
  
 [in] `pTargetBar`  
 Указатель на целевой области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были закреплены успешно; в противном случае — `FALSE`.  
  
##  <a name="a-nameenableautohidepanesa--cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 Позволяет Закрепление панели в основном фрейме, создается область закрепления и добавляет его в список панелей элементов управления.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyle`  
 Выравнивание закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепить панель была создана успешно. `FALSE` в противном случае.  
  
##  <a name="a-nameenabledockinga--cdockingmanagerenabledocking"></a><a name="enabledocking"></a>CDockingManager::EnableDocking  
 Создание области закрепления и позволяет Закрепление панели в основном фрейме.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyle`  
 Выравнивание закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепить панель была создана успешно. `FALSE` в противном случае.  
  
##  <a name="a-nameenabledocksitemenua--cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 Отображает дополнительные кнопки открывается всплывающее меню заголовков всех закрепляемых панелей.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить всплывающего меню узла; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Сайт всплывающего меню отображаются следующие параметры для изменения состояния закрепления панели:  
  
- `Floating`-Перемещается в область  
  
- `Docking`-Закрепляет область при главного фрейма в месте, где последнего Закрепить области  
  
- `AutoHide`-Переключения панели в режим автоскрытия  
  
- `Hide`-Скрывает панель  
  
 По умолчанию это меню не отображается.  
  
##  <a name="a-nameenablepanecontextmenua--cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 Указывает библиотеку для вызова специальных контекстного меню со списком приложений панелей инструментов и закрепляемых областей, при щелчке правой кнопкой мыши и библиотеке обрабатывает сообщение WM_CONTEXTMENU и Показать сообщение.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Если `TRUE`, библиотеке включает поддержку автоматического контекстного меню; Если `FALSE` библиотеки отключает поддержку автоматического контекстного меню.  
  
 [in] `uiCustomizeCmd`  
 Идентификатор команды для **Настройка** в меню.  
  
 [in] `strCustomizeText`  
 Текст **Настройка** элемента.  
  
 [in] `bToolbarsOnly`  
 Если `TRUE`, меню отображаются только список панелей инструментов приложения; Если `FALSE`, библиотека закрепляемых областей приложения добавляет в этот список.  
  
##  <a name="a-namefinddocksitea--cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>CDockingManager::FindDockSite  
 Извлекает строке области в указанной позиции и имеющего указанное выравнивание.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Выравнивание панели области.  
  
 [in] `bOuter`  
 Если `TRUE`, получить панели в головном положение в списке панелей элементов управления. В противном случае — получить панели в заключительного положение в списке панелей элементов управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Закрепляемая область, с заданным видом выравнивания; `NULL` в противном случае.  
  
##  <a name="a-namefindpanebyida--cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 Находит панели с помощью идентификатора указанного элемента управления.  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uBarID`  
 Указывает идентификатор элемента управления панели для поиска.  
  
 [in] `bSearchMiniFrames`  
 `TRUE`Чтобы включить все плавающей панели поиска. `FALSE`Чтобы включить только закрепленной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [CBasePane](../../mfc/reference/cbasepane-class.md) объекта, имеющего идентификатор указанного элемента управления или `NULL` найденные указанной области.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefinddocksitebypanea--cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 Возвращает панель с идентификатором область панели целевой области.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTargetBar`  
 Указатель на область панели target.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панели область, которая имеет идентификатор целевой строке области; `NULL` Если данный строке области не существует.  
  
##  <a name="a-namefixupvirtualrectsa--cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 Фиксирует все текущее положение панелей инструментов в виртуальный прямоугольники.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь начинает перетаскивать панели инструментов, приложение запоминает исходное положение в *виртуального прямоугольник*. Когда пользователь перемещает панель инструментов по его сайта закрепления, панели инструментов могут быть смещены других панелей инструментов. Исходное положение других панелей инструментов, хранятся в соответствующих виртуальных прямоугольников.  
  
##  <a name="a-nameframefrompointa--cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>CDockingManager::FrameFromPoint  
 Возвращает фрейма, содержащего заданной точки.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Указывает точку в координатах экрана, для проверки.  
  
 [in] `pFrameToExclude`  
 Указатель кадра для исключения.  
  
 [in] `bFloatMultiOnly`  
 `TRUE`Чтобы исключить кадры, которые не являются экземплярами `CMultiPaneFrameWnd`; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фрейма, содержащего заданной точки; `NULL` в противном случае.  
  
##  <a name="a-namegetclientareaboundsa--cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds  
 Возвращает прямоугольник, содержащий границы клиентской области.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rcClient`  
 Ссылка на прямоугольник, содержащий границы клиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, содержащий границы клиентской области.  
  
##  <a name="a-namegetdockingmodea--cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>CDockingManager::GetDockingMode  
 Возвращает текущий режим закрепления.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечислителя, который представляет текущий режим закрепления. Он может принимать одно из следующих значений:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать режим закрепления, вызовите [CDockingManager::SetDockingMode](#setdockingmode).  
  
##  <a name="a-namegetdocksiteframewnda--cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd  
 Возвращает указатель на родительского окна.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель кадра родительского окна.  
  
##  <a name="a-namegetenabledautohidealignmenta--cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 Возвращает включено выравнивание областей.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание `CBRS_ALIGN_` флаги, или 0, если не включено автоматическое скрытие панелей. Дополнительные сведения см. в разделе [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Примечания  
 Метод возвращает выравнивания включено автоматическое скрытие панелей элементов управления. Чтобы включить автоматическое скрытие панелей, вызовите [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="a-namegetminiframesa--cdockingmanagergetminiframes"></a><a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 Получает список miniframes.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список miniframes, содержащие, принадлежащих к диспетчеру закрепляемых панелей элементов управления.  
  
##  <a name="a-namegetouteredgeboundsa--cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 Возвращает прямоугольник, содержащий внешние края рамки.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, содержащий внешние края рамки.  
  
##  <a name="a-namegetpanelista--cdockingmanagergetpanelist"></a><a name="getpanelist"></a>CDockingManager::GetPaneList  
 Возвращает список областей, относящиеся к диспетчеру закрепления. Сюда входят все плавающей панели.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `lstBars`  
 Содержит все области текущий диспетчер закрепления.  
  
 [in] `bIncludeAutohide`  
 `TRUE`Чтобы включить области, находящиеся в режиме Автоскрытие; в противном случае — `FALSE`.  
  
 [in] `pRTCFilter`  
 Если это не `NULL`, возвращаемый список содержит панели только из указанного класса среды выполнения.  
  
 [in] `bIncludeTabs`  
 `TRUE`Чтобы включить вкладок; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если в диспетчере закрепления все вкладки, метод возвращает указатели на [CBaseTabbedPane класса](../../mfc/reference/cbasetabbedpane-class.md) объекты и вам необходимо перечислить вкладки явным образом.  
  
 Используйте `pRTCFilter` для получения определенного класса областей. Например можно получить только панели инструментов, установка этого значения соответствующим образом.  
  
##  <a name="a-namegetsmartdockingmanagera--cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 Извлекает указатель на смарт-закрепления manager.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [смарт-закрепления manager](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="a-namegetsmartdockingmanagerpermanenta--cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 Извлекает указатель на смарт-закрепления manager.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на смарт-закрепления manager.  
  
##  <a name="a-namegetsmartdockingparamsa--cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 Возвращает параметры смарт-закрепления для закрепления диспетчера.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Класс, содержащий смарт-закрепления параметров для текущего диспетчера закрепления. Дополнительные сведения см. в разделе [CSmartDockingInfo класса](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehideautohidepanesa--cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 Скрывает область, в которой находится в режиме Автоскрытие.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBarToExclude`  
 Указатель на строку, чтобы исключить из скрытие.  
  
 [in] `bImmediately`  
 `TRUE`Чтобы скрыть область немедленно; `FALSE` для скрытия области с эффектом Автоскрытие.  
  
##  <a name="a-nameinsertdocksitea--cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 Создание области закрепления и вставляет его в списке панелей элементов управления.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `info`  
 Структура, содержащая сведения о выравнивании об области закрепления.  
  
 [in] `dwAlignToInsertAfter`  
 Выравнивание области закрепления.  
  
 [выходной] `ppDockBar`  
 Указатель на указатель на область закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепить панель была создана успешно. `FALSE` в противном случае.  
  
##  <a name="a-nameinsertpanea--cdockingmanagerinsertpane"></a><a name="insertpane"></a>CDockingManager::InsertPane  
 Вставляет панели управления в списке панелей элементов управления.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на панели управления.  
  
 [in] `pTarget`  
 Указатель на целевой области.  
  
 [in] `bAfter`  
 `TRUE`для вставки области после позиции целевой области; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если на панели управления успешно добавлен в список панели элементов управления; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение false, если на панели управления уже находится в списке панелей элементов управления или целевой области не существует в списке панелей элементов управления.  
  
##  <a name="a-nameisdocksitemenua--cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 Задает отображение всплывающего меню заголовков всех областей.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если сайт всплывающего меню отображается на заголовки все области закрепления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Сайт всплывающего меню можно включить путем вызова [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="a-nameisinadjustlayouta--cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 Определяет, если корректируются макеты всех областей.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если корректируются макеты всех областей; `FALSE` в противном случае.  
  
##  <a name="a-nameisolecontainermodea--cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 Указывает, является ли закрепления manager в режиме контейнера OLE.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепления manager находится в режиме контейнера OLE. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В режиме контейнера OLE скрыты все области закрепления и панелей инструментов приложения. Области также скрыты в этом режиме, если вы задали [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) в `TRUE`.  
  
##  <a name="a-nameispointneardocksitea--cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
 Определяет, является ли указанная точка рядом с сайта закрепления.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указанная точка.  
  
 [выходной] `dwBarAlignment`  
 Задает край приближается к точке. Допустимые значения: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` и `CBRS_ALIGN_BOTTOM`.  
  
 [выходной] `bOuterEdge`  
 `TRUE`Если точка находится рядом с внешней границы сайта закрепления; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если точка находится рядом с сайта закрепления; в противном случае `FALSE`.  
  
##  <a name="a-nameisprintpreviewvalida--cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 Определяет, если задан режим предварительного просмотра.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если установлен режим предварительного просмотра; `FALSE` в противном случае.  
  
##  <a name="a-nameloadstatea--cdockingmanagerloadstate"></a><a name="loadstate"></a>CDockingManager::LoadState  
 Загружает состояние стыковки manager из реестра.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `uiID`  
 Идентификатор диспетчера закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если состояние стыковки manager был загружен успешно. в противном случае `FALSE`.  
  
##  <a name="a-namelockupdatea--cdockingmanagerlockupdate"></a><a name="lockupdate"></a>CDockingManager::LockUpdate  
 Блокирует данного окна.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bLock`  
 `TRUE`Если окно заблокирован; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Заблокированное окно нельзя переместить и не может быть перерисованы.  
  
##  <a name="a-namembhidedockingbarsincontainermodea--cdockingmanagermbhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode  
 Указывает, скрывается ли закрепления Диспетчер панелей в режиме контейнера OLE.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение равно `FALSE` Если вы хотите сохранить все области, которые прикрепляются к видимым фрейма главного когда приложение находится в режиме контейнера OLE. По умолчанию это значение равно `TRUE`.  
  
##  <a name="a-namemdockmodeglobala--cdockingmanagermdockmodeglobal"></a><a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 Указывает глобальный режим закрепления.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию каждой закрепляемой области использует этот режим закрепления. Дополнительные сведения о значениях, которые в этом поле можно задать в разделе [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="a-namemndocksensitivitya--cdockingmanagermndocksensitivity"></a><a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 Чувствительность закрепления.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Примечания  
 Закрепления чувствительности определяет как закрыть плавающей панели можно будет перейти закрепляемой области, стыковочного узла или другой области перед платформа изменяет свое состояние, чтобы закрепить.  
  
##  <a name="a-namemntimeoutbeforedockingbardocka--cdockingmanagermntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Указывает время, в миллисекундах перед закрепляемой области закреплен в режиме интерпретации закрепления.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Примечания  
 Перед закрепленной панели платформа ожидает в течение указанного периода времени. Это предотвращает случайное закрепление в место пока пользователь по-прежнему перетащив его области.  
  
##  <a name="a-namemntimeoutbeforetoolbardocka--cdockingmanagermntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Примечания  
 Перед закрепленной панели инструментов, платформа ожидает в течение указанного периода времени. Это предотвращает случайное закрепление в место пока пользователь по-прежнему перетащив его панели инструментов.  
  
##  <a name="a-nameonactivateframea--cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 Вызывается инфраструктурой при фрейме окна делается активным или отключена.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActivate`  
 Если `TRUE`, окно делается активным; Если `FALSE`, деактивации окна фрейма.  
  
##  <a name="a-nameonclosepopupmenua--cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu  
 Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа отправляет сообщение WM_DESTROY при намерении закрытия текущего главного окна. Переопределите этот метод для обработки уведомлений из `CMFCPopupMenu` объектов, принадлежащих фрейме окна при `CMFCPopupMenu` объекта процессов `WM_DESTROY` сообщение.  
  
##  <a name="a-nameonmoveminiframea--cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 Вызывается платформой для перемещения окна области.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrame`  
 Указатель окна области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="a-nameonpanecontextmenua--cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 Вызывается инфраструктурой при построении меню, которое содержит список областей.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает расположение меню.  
  
##  <a name="a-namepanefrompointa--cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>CDockingManager::PaneFromPoint  
 Возвращает область, содержащую заданной точки.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает точку в координатах экрана, для проверки.  
  
 [in] `nSensitivity`  
 Значение, которое увеличению прямоугольника каждого проверенного области окна. Область удовлетворяет условиям поиска, если заданная точка находится в этой области завышенной.  
  
 [in] `bExactBar`  
 `TRUE`Чтобы игнорировать `nSensitivity` параметр; в противном случае — `FALSE`.  
  
 [in] `pRTCBarType`  
 Если это не `NULL`, метод выполняет поиск только области указанного типа.  
  
 [in] `bCheckVisibility`  
 `TRUE`Чтобы проверить видимой области; в противном случае — `FALSE`.  
  
 [выходной] `dwAlignment`  
 Если область находится в указанном месте, этот параметр содержит боковой панели, ближайшей к заданной точке. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] `pBarToIgnore`  
 Если это не `NULL`, этот метод игнорирует панелей, заданного этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-производный объект, содержащий определенный момент или `NULL` Если области не был найден.  
  
### <a name="remarks"></a>Примечания  
 Если функция возвращает и область найден, `dwAlignment` содержит выравнивание заданной точке. Например, если точка находится ближайший к верхней части области `dwAlignment` равен `CBRS_ALIGN_TOP`.  
  
##  <a name="a-nameprocesspanecontextmenucommanda--cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 Вызывается платформой установите или снимите флажок для определенной команды и перерасчет макета отображаются области.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор панели элементов управления в меню.  
  
 [in] `nCode`  
 Код команды уведомления.  
  
 [in] `pExtra`  
 Указатель void, привести к указателю на `CCmdUI` Если `nCode` является CN_UPDATE_COMMAND_UI.  
  
 [in] `pHandlerInfo`  
 Указатель на структуру сведений. Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pEXtra` не равно NULL и `nCode` равняется CN_UPDATE_COMMAND_UI, или если панель элементов управления с указанным `nID`.  
  
##  <a name="a-namerecalclayouta--cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>CDockingManager::RecalcLayout  
 Повторно вычисляет внутренней структуры элементов управления, присутствует в списке элементов управления.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNotify`  
 Этот параметр не используется.  
  
##  <a name="a-namereleaseemptypanecontainersa--cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers  
 Освобождает контейнеры пустая область.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="a-nameremovehiddenmditabbedbara--cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar  
 Удаляет указанный скрыты панели области.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на строку области для удаления.  
  
##  <a name="a-nameremoveminiframea--cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame  
 Удаляет указанный промежуток в списке мини-кадры.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель кадра для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанный кадр удален. `FALSE` в противном случае.  
  
##  <a name="a-nameremovepanefromdockmanagera--cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager  
 Отменяет регистрацию область и удаляет его из списка в диспетчере закрепления.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на область удаляется.  
  
 [in] `bDestroy`  
 Если `TRUE`, уничтожается области удален.  
  
 [in] `bAdjustLayout`  
 Если `TRUE`, настроить макет закрепления немедленно.  
  
 [in] `bAutoHide`  
 Если `TRUE`, область удаляется из списка, автоматическое скрытие панелей. Если `FALSE`, область удаляется из списка регулярных областей.  
  
 [in] `pBarReplacement`  
 Указатель на область, которая заменит область удален.  
  
##  <a name="a-namereplacepanea--cdockingmanagerreplacepane"></a><a name="replacepane"></a>CDockingManager::ReplacePane  
 Заменяет одну панель другой.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOriginalBar`  
 Указатель на исходной области.  
  
 [in] `pNewBar`  
 Указатель для области, которая заменяет исходной области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области успешно заменен; `FALSE` в противном случае.  
  
##  <a name="a-nameresortminiframesforzordera--cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder  
 Использует кадров в списке мини-кадры.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="a-namesavestatea--cdockingmanagersavestate"></a><a name="savestate"></a>CDockingManager::SaveState  
 Сохраняет состояние стыковки manager в реестре.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь к разделу реестра.  
  
 [in] `uiID`  
 Закрепления идентификатора диспетчера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если состояние была сохранена успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Сохранение состояния закрепления manager в реестр включает сохранение состояния панели элементов управления, автоматическое скрытие панелей и состояниях мини-кадров, присутствует в диспетчере закрепления.  
  
##  <a name="a-namesendmessagetominiframesa--cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames  
 Отправляет указанное сообщение все мини-кадры.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uMessage`  
 Отправляемое сообщение.  
  
 [in] `wParam`  
 Сведения, зависящие от дополнительных сообщений.  
  
 [in] `lParam`  
 Сведения, зависящие от дополнительных сообщений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`всегда.  
  
##  <a name="a-nameserializea--cdockingmanagerserialize"></a><a name="serialize"></a>CDockingManager::Serialize  
 Записывает закрепления manager в архив.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
 Ссылка на объект архива.  
  
### <a name="remarks"></a>Примечания  
 Записи в архив закрепления manager подразумевает определение номер закрепление панелей элементов управления и ползунков и написания панелей элементов управления, мини-кадры, автоматическое скрытие панелей и полосы с вкладками MDI в архив.  
  
##  <a name="a-namesetautohidezordera--cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder  
 Задает размер, ширина и высота панели элементов управления и в указанной области.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pAHDockingBar`  
 Указатель закрепляемой области.  
  
##  <a name="a-namesetdockingmodea--cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>CDockingManager::SetDockingMode  
 Задает режим закрепления.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Параметры  
 `dockMode`  
 Задает новый режим закрепления. Дополнительные сведения см. в разделе "Примечания".  
  
 `theme`  
 Определяет тему для интеллектуальных маркеров закрепления. Он может принимать одно из следующих значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Примечания  
 Вызовите статический метод для задания режима закрепления.  
  
 `dockMode`может принимать одно из следующих значений:  
  
- `DT_STANDARD`-Режим закрепления, реализованное в Visual Studio .NET 2003 standard. Области при перетаскивании без перетаскивания контекста.  
  
- `DT_IMMEDIATE`-Режим интерпретации закрепления, как реализовано в Microsoft Visio. При перетаскивании областей с помощью перетаскивания контекста, но маркеры не отображаются.  
  
- `DT_SMART`-Смарт-закрепления режим, реализованное в Visual Studio 2005. При перетаскивании областей с помощью перетаскивания контекста и интеллектуальные маркеры отображаются, показывающие, где можно закрепить области.  
  
##  <a name="a-namesetdockstatea--cdockingmanagersetdockstate"></a><a name="setdockstate"></a>CDockingManager::SetDockState  
 Задает состояние закрепления панели элементов управления, мини-кадры и автоматическое скрытие панелей.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="a-namesetprintpreviewmodea--cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode  
 Задает режим предварительного просмотра линий, которые отображаются в режиме предварительного просмотра.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPreview`  
 `TRUE`Если задан режим предварительного просмотра; `FALSE` в противном случае.  
  
 [in] `pState`  
 Указатель на состоянии предварительной версии. Этот параметр не используется.  
  
##  <a name="a-namesetsmartdockingparamsa--cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 Задает параметры, которые определяют поведение смарт-закрепления.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `params`  
 Определяет параметры для смарт-закрепления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается в том случае, если требуется настроить внешний вид, цвет и форма интеллектуальные маркеры стыковки.  
  
 Чтобы использовать заданные по умолчанию вид интеллектуальные маркеры стыковки, передать неинициализированный экземпляр [класса CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) в `params`.  
  
##  <a name="a-nameshowdelayshowminiframesa--cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 Отображение или скрытие окна мини-кадры.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 `TRUE`Чтобы активировать окно показано фрейма; `FALSE to` скрыть окно фрейма.  
  
##  <a name="a-nameshowpanesa--cdockingmanagershowpanes"></a><a name="showpanes"></a>CDockingManager::ShowPanes  
 Отображение или скрытие панели управления и автоматическое скрытие панелей.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 `TRUE`для отображения области; `FALSE to` скрыть области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
##  <a name="a-namestartsdockinga--cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>CDockingManager::StartSDocking  
 Запускает смарт-закрепления указанного окна в соответствии с выравниванием смарт-закрепления manager.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockingWnd`  
 Указатель на окно будет закреплено.  
  
##  <a name="a-namestopsdockinga--cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>CDockingManager::StopSDocking  
 Останавливает смарт-закрепления.  
  
```  
void StopSDocking();
```  
  
##  <a name="a-namegetsmartdockingthemea--cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 Статический метод, возвращающий темы, используемый для отображения интеллектуальные маркеры стыковки.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает одно из следующих значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)

