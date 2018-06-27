---
title: Класс CDockingManager | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e2fe05ba1bde0fc3d0de22d58a29f49f2130fc
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954082"
---
# <a name="cdockingmanager-class"></a>Класс CDockingManager
Реализует базовую функциональность, которая контролирует макет закрепления в окне главного фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Создает область закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Добавляет в гистограмму дескриптор области в список скрытых MDI с вкладками областями строки.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Добавляет кадр в список мини-кадры.|  
|[CDockingManager::AddPane](#addpane)|Регистрирует область в диспетчере закрепления.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Повторно вычисляет и настраивает макет все области в окне фрейма.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|В результате WM_NCCALCSIZE сообщение должно отправляться все области и `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Выравнивает прямоугольник.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Изменяет размер закрепляемую область в режим автоматического скрытия требуется полная ширина или Высота клиентской области рамки, заключенных в прикрепить сайтов.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Создает автоматическое скрытие панели инструментов.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Переводит закрепленной панели, имеющие указанное выравнивание в начало.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Добавляет имена закрепляемых панелей и панели инструментов меню.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Вычисляет ожидаемый прямоугольник закрепленного окна.|  
|[CDockingManager::Create](#create)|Создает диспетчере закрепления.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Определяет области, в которой содержится заданная точка и состояние его закрепления.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Включает или отключает загрузку макет закрепления из реестра.|  
|[CDockingManager::DockPane](#dockpane)|Закрепляет область в другую область или область окна.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Закрепляет область слева от другой области.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Включает закрепления панели для главного фрейма, создает область закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::EnableDocking](#enabledocking)|Создает область закрепления и включает закрепления панели для главного фрейма.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Отображает дополнительные кнопки открывается всплывающее меню заголовков всех области закрепления.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Указывает библиотеку для вызова специальных контекстного меню, имеющий список панелей инструментов приложения и области закрепления при щелчке правой кнопкой мыши и обрабатывает сообщение WM_CONTEXTMENU библиотеки.|  
|[CDockingManager::FindDockSite](#finddocksite)|Извлекает строке области в указанной позиции и имеющего указанное выравнивание.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Возвращает полосу с идентификатором область панели целевой области.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Находит области с помощью идентификатора указанного элемента управления.|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Фиксирует все текущее положение панелей инструментов для виртуального прямоугольники.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Возвращает кадр, содержащее заданную точку.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Возвращает прямоугольник, содержащий границы клиентской области.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Возвращает текущий режим закрепления.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Возвращает указатель на фрейм родительского окна.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Возвращает включено выравнивание областей.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Получает список miniframes.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Возвращает прямоугольник, содержащий внешние края рамки.|  
|[CDockingManager::GetPaneList](#getpanelist)|Возвращает список областей, которые принадлежат диспетчере закрепления. Сюда входят все плавающих панелей.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Извлекает указатель на смарт-закрепления диспетчера.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Извлекает указатель на смарт-закрепления диспетчера.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Возвращает параметры смарт-закрепления для диспетчера закрепления.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Статический метод, возвращающий темы, используемый для отображения интеллектуальных маркеров закрепления.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Скрывает область, в которой находится в режим автоматического скрытия.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Создает область закрепления и вставляет его в список панелей элементов управления.|  
|[CDockingManager::InsertPane](#insertpane)|Вставляет панель управления в список панелей элементов управления.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Задает отображение всплывающего меню заголовков всех областей.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Определяет, если корректируются макеты всех областей.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Указывает, является ли в диспетчере закрепления в режиме контейнера OLE.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайта закрепления.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Определяет, если устанавливается режим предварительного просмотра.|  
|[CDockingManager::LoadState](#loadstate)|Загружает состояние закрепления manager из реестра.|  
|[CDockingManager::LockUpdate](#lockupdate)|Блокирует заданное окно.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Вызывается платформой, когда фрейм окна делается активным или отключена.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Вызывается платформой для перемещения окна области.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Вызывается платформой при построении меню, которое содержит список областей.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Возвращает область, содержащее заданную точку.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Вызывается платформой для выберите снимите флажок для определенной команды и повторно рассчитать компоновку показано области.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Повторно вычисляет внутренний макет элементов управления присутствует в списке элементов управления.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Освобождает контейнеры пустая область.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Удаляет указанный скрыты панели области.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Удаляет заданный промежуток в списке мини-кадры.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет регистрацию областью и удаляет его из списка в диспетчере закрепления.|  
|[CDockingManager::ReplacePane](#replacepane)|Заменяет одну панель другой.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Использует кадров в списке мини-кадры.|  
|[CDockingManager::SaveState](#savestate)|Сохраняет состояние в диспетчере закрепления в реестре.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Отправляет указанное сообщение все мини-кадры.|  
|[CDockingManager::Serialize](#serialize)|Записывает в диспетчере закрепления в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Задает размер, ширину и высоту панели элементов управления и в указанной области.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Задает режим закрепления.|  
|[CDockingManager::SetDockState](#setdockstate)|Задает состояние закрепления панели элементов управления, мини-кадры и автоматическое скрытие панелей.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Задает режим предварительного просмотра панелей, которые отображаются в режиме предварительного просмотра.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Задает параметры, определяющие поведение смарт-закрепления.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Отображение или скрытие окна мини-кадры.|  
|[CDockingManager::ShowPanes](#showpanes)|Отображение или скрытие панели управления и автоматическое скрытие панелей.|  
|[CDockingManager::StartSDocking](#startsdocking)|Запускает смарт-закрепления указанного окна в соответствии с выравнивание смарт-закрепления диспетчера.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Останавливает смарт-закрепления.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Указывает, скрывается ли в диспетчере закрепления панелей в режиме контейнера OLE.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Указывает глобальный режим закрепления.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Чувствительность закрепления.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Указывает время в миллисекундах перед закрепляемой области подключено в режиме интерпретации закрепления.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.|  
  
## <a name="remarks"></a>Примечания  
 Фрейм главного окна, создает и инициализирует автоматически.  
  
 Объект диспетчера закрепления содержит список всех областей, которые находятся в макете закрепления, а также список всех [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) окна, принадлежащие фрейма главного окна.  
  
 `CDockingManager` Класс реализует несколько служб, которые можно использовать для поиска в области или `CPaneFrameWnd` окна. Обычно не вызывается эти службы непосредственно, так как они помещаются в объект фрейма главного окна. Дополнительные сведения см. в разделе [CPaneFrameWnd класса](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Ниже приведены рекомендации применяются к `CDockingManager` объектов:  
  
- [Класс CDockingManager](../../mfc/reference/cdockingmanager-class.md) поддерживает следующие режимы закрепления:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Эти режимы закрепления определяются [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) и задать вызвав [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Если вы хотите создать область не с плавающей запятой, неизменяемый, вызовите [CDockingManager::AddPane](#addpane) метод. Этот метод регистрирует область в диспетчере закрепления, отвечающий за макета панели.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CDockingManager` класса, чтобы настроить `CDockingManager` объекта. В примере показано, как отображать дополнительные кнопки открывается всплывающее меню заголовков всех области закрепления и как задать режим закрепления объекта. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>  CDockingManager::AddDockSite  
 Создает область закрепления и добавляет его в список панелей элементов управления.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *сведения*  
 Ссылка на структуру сведений, содержащий закрепить выравнивание панели.  
  
 [out] *ppDockBar*  
 Указатель на указатель на новой области закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область закрепления был создан успешно. `FALSE` в противном случае.  
  
##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar  
 Добавляет в гистограмму дескриптор области в список скрытых MDI с вкладками областями строки.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на панель области  
  
##  <a name="addpane"></a>  CDockingManager::AddPane  
 Регистрирует область в диспетчере закрепления.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] *pWnd*  
 Указывает на панели, чтобы добавить в диспетчере закрепления.  
  
 [in] *bTail*  
 `TRUE` для добавления в конец списка областей области для диспетчера закрепления; в противном случае `FALSE`.  
  
 [in] *bAutoHide*  
 Только для внутреннего использования. Всегда использовать значение по умолчанию `FALSE`.  
  
 [in] *bInsertForOuterEdge*  
 Только для внутреннего использования. Всегда использовать значение по умолчанию `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если области успешно зарегистрирован в диспетчере закрепления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для регистрации не с плавающей запятой, неизменяемый панелей в диспетчере закрепления. Если не следует регистрировать областей, они не будут правильно отображаться при располагаются в диспетчере закрепления.  
  
##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout  
 Повторно вычисляет и настраивает макет все области в окне фрейма.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hdwp*  
 Указывает положение структуру отложенное окна. Дополнительные сведения см. в разделе [Типы данных Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame  
 Добавляет кадр в список мини-кадры.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWnd*  
 Указатель кадра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если кадр не находится в списке мини-кадры и был успешно добавлен; `FALSE` в противном случае.  
  
##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames  
 Вызывает `WM_NCCALCSIZE` сообщение должно отправляться все области и `CPaneFrameWnd` windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="adjustrecttoclientarea"></a>  CDockingManager::AdjustRectToClientArea  
 Выравнивает прямоугольник.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rectResult*  
 Ссылку на `CRect` объекта  
  
 [in] *dwAlignment*  
 Выравнивание `CRect` объекта  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если выравнивание `CRect` объекта была скорректирована; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 *DwAlignment* параметр может принимать одно из следующих значений:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane  
 Изменяет размер закрепляемую область в режим автоматического скрытия требуется полная ширина или Высота клиентской области рамки, заключенных в прикрепить сайтов.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDefaultSlider*  
 Область закрепления ползунка.  
  
 [in] *bIsVisible*  
 `TRUE` Если области закрепления видима. `FALSE` в противном случае.  
  
##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane  
 Создает автоматическое скрытие панели инструментов.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на панель области.  
  
 [in] *pCurrAutoHideToolBar*  
 Указатель на автоматическое скрытие панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `NULL` Если параметр автоматического скрытия панели инструментов не был создан; в противном случае указатель на новую панель инструментов.  
  
##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop  
 Переводит закрепленной панели, имеющие указанное выравнивание в начало.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *dwAlignment*  
 Выравнивание закрепления панелей, которые попадают в начало других окон.  
  
 [in] *bExcludeDockedBars*  
 `TRUE` Чтобы исключить закрепленной панели из процесса в верхней части; в противном случае `FALSE`.  
  
##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu  
 Добавляет имена закрепляемых панелей и панели инструментов меню.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *меню*  
 Меню, чтобы добавить имена закрепляемых панелей и инструментов.  
  
 [in] *bToolbarsOnly*  
 `TRUE` Чтобы добавить только имена панелей инструментов в меню; `FALSE` в противном случае.  
  
##  <a name="calcexpecteddockedrect"></a>  CDockingManager::CalcExpectedDockedRect  
 Вычисляет ожидаемый прямоугольник закрепленного окна.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWnd*  
 Указатель на окно будет закреплено.  
  
 [in] *ptMouse*  
 Положение мыши.  
  
 [out] *rectResult*  
 Расчетный прямоугольник.  
  
 [in] *bDrawTab*  
 `TRUE` Чтобы нарисовать вкладки. в противном случае `FALSE`.  
  
 [out] *ppTargetBar*  
 Указатель на указатель на целевой области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет прямоугольник, должны занимать окна, если пользователь перетащить окна в точке, заданной *ptMouse* и закрепленные он существует.  
  
##  <a name="create"></a>  CDockingManager::Create  
 Создает диспетчере закрепления.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pParentWnd*  
 Указатель родительского фрейма для диспетчера закрепления. Это значение не должно быть `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` всегда.  
  
##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus  
 Определяет области, в которой содержится заданная точка и состояние его закрепления.  
  
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
 [in] *pt*  
 Расположение панели для проверки.  
  
 [in] *nSensitivity*  
 Значение, чтобы увеличить прямоугольника каждого проверенного области окна. Область удовлетворяет условиям поиска, если заданная точка находится в этой области увеличения.  
  
 [in] *dwEnabledAlignment*  
 Выравнивание по области закрепления.  
  
 [out] *ppTargetBar*  
 Указатель на указатель на целевой области.  
  
 [in] *pBarToIgnore*  
 Области, в которой этот метод игнорирует.  
  
 [in] *pBarToDock*  
 Область, закрепленную.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние закрепления.  
  
### <a name="remarks"></a>Примечания  
 Состояние закрепления может принимать одно из следующих значений:  
  
|Значение AFX_CS_STATUS|Значение|  
|---------------------------|-------------|  
|CS_NOTHING|Указатель находится не на сайте закрепления. Таким образом, оставьте области с плавающей запятой.|  
|CS_DOCK_IMMEDIATELY|Указатель находится на сайте закрепления в режиме интерпретации (стиль DT_IMMEDIATE включен), поэтому области должно быть закреплено немедленно.|  
|CS_DELAY_DOCK|Указатель находится на сайте закрепления другой области закрепления или края главного фрейма.|  
|CS_DELAY_DOCK_TO_TAB|Указатель находится на сайте закрепления, вызывающее области быть закреплено в окно с вкладками. Это происходит, когда указатель мыши находится над заголовок от другой области закрепления или область вкладки области с вкладками.|  
  
##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState  
 Включает или отключает загрузку макет закрепления из реестра.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bDisable*  
 `TRUE` Чтобы отключить загрузку макет закрепления в реестре; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда необходимо сохранить текущий макет закрепления панели и панелей инструментов при загрузке состояния приложения.  
  
##  <a name="dockpane"></a>  CDockingManager::DockPane  
 Закрепляет область в другую область или область окна.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на строку панели, чтобы закрепить.  
  
 [in] *nDockBarID*  
 Идентификатор окна, чтобы закрепить.  
  
 [in] *lpRect*  
 Прямоугольника назначения.  
  
##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf  
 Закрепляет область слева от другой области.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBarToDock*  
 Указатель на панели можно закреплять слева от *pTargetBar*.  
  
 [in] *pTargetBar*  
 Указатель на нужной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область была закреплена успешно. в противном случае `FALSE`.  
  
##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes  
 Включает закрепления панели для главного фрейма, создает область закрепления и добавляет его в список панелей элементов управления.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *dwStyle*  
 Выравнивание закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область закрепления был создан успешно. `FALSE` в противном случае.  
  
##  <a name="enabledocking"></a>  CDockingManager::EnableDocking  
 Создает область закрепления и включает закрепления панели для главного фрейма.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *dwStyle*  
 Выравнивание закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область закрепления был создан успешно. `FALSE` в противном случае.  
  
##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu  
 Отображает дополнительные кнопки открывается всплывающее меню заголовков всех области закрепления.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 `TRUE` Чтобы включить всплывающего меню сайта; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Меню сайта закрепления имеются следующие параметры для изменения состояния закрепления панели:  
  
- `Floating` — Преобразует панель в  
  
- `Docking` -Закрепляет область в главного фрейма в расположении, где последнего закрепления панели  
  
- `AutoHide` -Переключается области в режим автоматического скрытия  
  
- `Hide` -Скрывает панель  
  
 По умолчанию это меню не отображается.  
  
##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu  
 Указывает библиотеку для вызова специальных контекстного меню, имеющий список панелей инструментов приложения и области закрепления при щелчке правой кнопкой мыши и обрабатывает сообщение WM_CONTEXTMENU библиотеки.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Если `TRUE`, библиотеке включает поддержку автоматического контекстного меню; Если `FALSE` библиотеке отключает поддержку автоматического контекстного меню.  
  
 [in] *uiCustomizeCmd*  
 Идентификатор команды для **Настройка** элемента меню.  
  
 [in] *strCustomizeText*  
 Текст **Настройка** элемента.  
  
 [in] *bToolbarsOnly*  
 Если `TRUE`, в меню отображаются только список панелей инструментов приложения; Если `FALSE`, библиотеки области закрепления приложение добавляет в этот список.  
  
##  <a name="finddocksite"></a>  CDockingManager::FindDockSite  
 Извлекает строке области в указанной позиции и имеющего указанное выравнивание.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *dwAlignment*  
 Выравнивание панели области.  
  
 [in] *bOuter*  
 Если `TRUE`, получить панели в головном позицию в списке панелей элементов управления. В противном случае получить строке заключительного позиции в списке панелей элементов управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Закрепляемой области, который имеет указанное выравнивание; `NULL` в противном случае.  
  
##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID  
 Находит области с помощью идентификатора указанного элемента управления.  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uBarID*  
 Указывает идентификатор элемента панели управления для поиска.  
  
 [in] *bSearchMiniFrames*  
 `TRUE` Чтобы включить все плавающих панелей в поиск. `FALSE` Чтобы включить только закрепленных панелей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [CBasePane](../../mfc/reference/cbasepane-class.md) объект с указанным Идентификатором элемента управления, или `NULL` найденные указанной области.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane  
 Возвращает полосу с идентификатором область панели целевой области.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pTargetBar*  
 Указатель на область панели целевой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строке панели с идентификатором область панели цели; `NULL` Если такой строке области существует.  
  
##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects  
 Фиксирует все текущее положение панелей инструментов для виртуального прямоугольники.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь начинает перетаскивать панели инструментов, приложение запоминает исходную позицию в *виртуального прямоугольник*. Когда пользователь перемещает панель инструментов по его сайта закрепления, панели инструментов могут быть смещены других панелей инструментов. Исходное положение других панелей инструментов, хранятся в соответствующих виртуальных прямоугольники.  
  
##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint  
 Возвращает кадр, содержащее заданную точку.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pt*  
 Указывает точку, в экранных координатах, для проверки.  
  
 [in] *pFrameToExclude*  
 Указатель кадра для исключения.  
  
 [in] *bFloatMultiOnly*  
 `TRUE` Чтобы исключить кадры, которые не являются экземплярами `CMultiPaneFrameWnd`; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Кадр, содержащее заданную точку; `NULL` в противном случае.  
  
##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds  
 Возвращает прямоугольник, содержащий границы клиентской области.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Параметры  
 [out] *rcClient*  
 Ссылка на прямоугольник, содержащий границы клиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, содержащий границы клиентской области.  
  
##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode  
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
  
##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd  
 Возвращает указатель на фрейм родительского окна.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель кадра родительского окна.  
  
##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment  
 Возвращает включено выравнивание областей.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание `CBRS_ALIGN_` флаги, или 0, если автоматическое скрытие панелей не включены. Дополнительные сведения см. в разделе [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Примечания  
 Метод возвращает выравнивание включено автоматическое скрытие панелей элементов управления. Чтобы включить автоматическое скрытие панелей, вызовите [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames  
 Получает список miniframes.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список miniframes, содержащих панелей элементов управления, относящиеся к диспетчеру закрепления.  
  
##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds  
 Возвращает прямоугольник, содержащий внешние края рамки.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, содержащий внешние края рамки.  
  
##  <a name="getpanelist"></a>  CDockingManager::GetPaneList  
 Возвращает список областей, которые принадлежат диспетчере закрепления. Сюда входят все плавающих панелей.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] *lstBars*  
 Содержит все области текущего диспетчера закрепления.  
  
 [in] *bIncludeAutohide*  
 `TRUE` для включения областей, которые находятся в режим автоматического скрытия; в противном случае `FALSE`.  
  
 [in] *pRTCFilter*  
 В противном случае `NULL`, возвращаемый список содержит панели только из указанного класса среды выполнения.  
  
 [in] *bIncludeTabs*  
 `TRUE` Чтобы включить вкладок; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если в диспетчере закрепления все панели с вкладками, метод возвращает указатели на [класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md) объектах и должен создаваться список вкладок явным образом.  
  
 Используйте *pRTCFilter* для получения определенного класса панелей. Например можно получить только панели инструментов соответствующим образом увеличить это значение.  
  
##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager  
 Извлекает указатель на смарт-закрепления диспетчера.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [смарт-закрепления диспетчер](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent  
 Извлекает указатель на смарт-закрепления диспетчера.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на смарт-закрепления диспетчера.  
  
##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams  
 Возвращает параметры смарт-закрепления для диспетчера закрепления.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Класс, содержащий параметры смарт-закрепления для текущего диспетчера закрепления. Дополнительные сведения см. в разделе [CSmartDockingInfo класса](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes  
 Скрывает область, в которой находится в режим автоматического скрытия.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBarToExclude*  
 Указатель на строку, чтобы исключить из скрытие.  
  
 [in] *bImmediately*  
 `TRUE` Чтобы скрыть область немедленно; `FALSE` скрыть область с эффектом автоматическое скрытие.  
  
##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite  
 Создает область закрепления и вставляет его в список панелей элементов управления.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *сведения*  
 Структура, содержащая сведения о выравнивании об области закрепления.  
  
 [in] *dwAlignToInsertAfter*  
 Выравнивание область закрепления.  
  
 [out] *ppDockBar*  
 Указатель на указатель на область закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область закрепления был создан успешно. `FALSE` в противном случае.  
  
##  <a name="insertpane"></a>  CDockingManager::InsertPane  
 Вставляет панель управления в список панелей элементов управления.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pControlBar*  
 Указатель на панели управления.  
  
 [in] *pTarget*  
 Указатель в целевой области.  
  
 [in] *bAfter*  
 `TRUE` для вставки области после позиции в целевой области; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если на панели управления успешно добавлен в список панелей элементов управления; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение false, если на панели управления уже находится в списке панелей элементов управления или целевой области не существует в списке панелей элементов управления.  
  
##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu  
 Задает отображение всплывающего меню заголовков всех областей.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если сайт всплывающего меню отображается на заголовков всех закрепления областей; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Можно включить всплывающего меню узла, вызвав [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout  
 Определяет, если корректируются макеты всех областей.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если корректируются макеты всех областей; `FALSE` в противном случае.  
  
##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode  
 Указывает, является ли в диспетчере закрепления в режиме контейнера OLE.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если в диспетчере закрепления находится в режиме контейнера OLE. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В режиме контейнера OLE будут скрыты все области закрепления и панелей инструментов приложения. Области также скрыты в этом режиме, если вы задали [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) для `TRUE`.  
  
##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite  
 Определяет, является ли указанная точка рядом с сайта закрепления.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *точки*  
 Указанная точка.  
  
 [out] *dwBarAlignment*  
 Задает край приближается к точке. Допустимые значения: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` и `CBRS_ALIGN_BOTTOM`.  
  
 [out] *bOuterEdge*  
 `TRUE` Если точка находится рядом с внешней границы сайта закрепления; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если точка находится рядом с сайта закрепления; в противном случае `FALSE`.  
  
##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid  
 Определяет, если устанавливается режим предварительного просмотра.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если установлен режим предварительного просмотра; `FALSE` в противном случае.  
  
##  <a name="loadstate"></a>  CDockingManager::LoadState  
 Загружает состояние закрепления manager из реестра.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszProfileName*  
 Имя профиля.  
  
 [in] *uiID*  
 Идентификатор диспетчера закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если состояние стыковки manager был загружен успешно. в противном случае `FALSE`.  
  
##  <a name="lockupdate"></a>  CDockingManager::LockUpdate  
 Блокирует заданное окно.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *блок*  
 `TRUE` Если окно заблокирован; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 При блокировке окна, ее нельзя переместить, и не может быть перерисованы.  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode  
 Указывает, скрывается ли в диспетчере закрепления панелей в режиме контейнера OLE.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение равно `FALSE` Если вы хотите сохранить все области, которые прикрепляются к видимым главного фрейма не приложение в режиме контейнера OLE. По умолчанию это значение равно `TRUE`.  
  
##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal  
 Указывает глобальный режим закрепления.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию каждая закрепляемую панель использует этот режим закрепления. Дополнительные сведения о значениях, которые можно присвоить это поле в разделе [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity  
 Чувствительность закрепления.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Примечания  
 Закрепления чувствительности определяет как закрыть плавающей области может приближаться к отметке закрепляемой области, закрепления узла или другой области перед платформа изменяет свое состояние, закреплено.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Указывает время в миллисекундах перед закрепляемой области подключено в режиме интерпретации закрепления.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Примечания  
 Прежде, чем панель закреплена, платформа ожидает в течение указанного периода времени. Это предотвращает случайно, закрепленный в расположение, пока пользователь по-прежнему перетащив его области.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock  
 Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Примечания  
 Прежде чем Закрепить панель инструментов, платформа ожидает в течение указанного периода времени. Это предотвращает случайно, закрепленный в расположение, пока пользователь по-прежнему перетащив его панели инструментов.  
  
##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame  
 Вызывается платформой, когда фрейм окна делается активным или отключена.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bActivate*  
 Если `TRUE`, окно фрейма делается активным; Если `FALSE`, деактивации фрейм окна.  
  
##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu  
 Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа отправляет сообщение WM_DESTROY при намерении закрытия текущего главного окна. Переопределите этот метод для обработки уведомлений из `CMFCPopupMenu` объектов, которые принадлежат к фрейму окна при `CMFCPopupMenu` объекта процессов `WM_DESTROY` сообщения.  
  
##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame  
 Вызывается платформой для перемещения окна области.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pFrame*  
 Указатель окна области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu  
 Вызывается платформой при построении меню, которое содержит список областей.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *точки*  
 Указывает расположение меню.  
  
##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint  
 Возвращает область, содержащее заданную точку.  
  
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
 [in] *точки*  
 Указывает точку, в экранных координатах, для проверки.  
  
 [in] *nSensitivity*  
 Значение, которое увеличению прямоугольника каждого проверенного области окна. Область удовлетворяет условиям поиска, если заданная точка находится в этом увеличенную регионе.  
  
 [in] *bExactBar*  
 `TRUE` Чтобы игнорировать *nSensitivity* параметр; в противном случае `FALSE`.  
  
 [in] *pRTCBarType*  
 В противном случае `NULL`, метод выполняет поиск только области заданного типа.  
  
 [in] *bCheckVisibility*  
 `TRUE` Чтобы проверить только видимых панелей; в противном случае `FALSE`.  
  
 [out] *dwAlignment*  
 Если панель находится в заданной точке, этот параметр содержит части панели, ближайшей к заданной точке. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] *pBarToIgnore*  
 В противном случае `NULL`, этот метод игнорирует панелей, заданного этим параметром.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-производного объекта, содержащее заданную точку или `NULL` Если области не был найден.  
  
### <a name="remarks"></a>Примечания  
 Если область не найдена, функция возвращает *dwAlignment* содержит выравнивание по заданной точке. Например, если точка находится ближайший к верхней части области *dwAlignment* равно `CBRS_ALIGN_TOP`.  
  
##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand  
 Вызывается платформой для выберите снимите флажок для определенной команды и повторно рассчитать компоновку показано области.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 Идентификатор элемента панели элементов управления в меню.  
  
 [in] *nCode*  
 Код уведомления команды.  
  
 [in] *pExtra*  
 Указатель на void, приведено в указатель на `CCmdUI` Если *nCode* — CN_UPDATE_COMMAND_UI.  
  
 [in] *pHandlerInfo*  
 Указатель на структуру сведений. Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если *pEXtra* не равно NULL и *nCode* равняется CN_UPDATE_COMMAND_UI, или если панель элементов управления с указанным *nID*.  
  
##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout  
 Повторно вычисляет внутренний макет элементов управления присутствует в списке элементов управления.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bNotify*  
 Этот параметр не используется.  
  
##  <a name="releaseemptypanecontainers"></a>  CDockingManager::ReleaseEmptyPaneContainers  
 Освобождает контейнеры пустая область.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>  CDockingManager::RemoveHiddenMDITabbedBar  
 Удаляет указанный скрыты панели области.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pBar*  
 Указатель на строку области для удаления.  
  
##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame  
 Удаляет заданный промежуток в списке мини-кадры.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWnd*  
 Указатель кадра для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если указанный кадр был удален. `FALSE` в противном случае.  
  
##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager  
 Отменяет регистрацию областью и удаляет его из списка в диспетчере закрепления.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWnd*  
 Указатель на область для удаления.  
  
 [in] *bDestroy*  
 Если `TRUE`, уничтожается области удален.  
  
 [in] *bAdjustLayout*  
 Если `TRUE`, настроить макет закрепления немедленно.  
  
 [in] *bAutoHide*  
 Если `TRUE`, области удаляется из списка, автоматическое скрытие панелей. Если `FALSE`, области удаляется из списка регулярных панелей.  
  
 [in] *pBarReplacement*  
 Указатель на область, которая заменяет области удален.  
  
##  <a name="replacepane"></a>  CDockingManager::ReplacePane  
 Заменяет одну панель другой.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pOriginalBar*  
 Указатель на исходной области.  
  
 [in] *pNewBar*  
 Указатель на область, которую заменяет исходной области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если области успешно заменен; `FALSE` в противном случае.  
  
##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder  
 Использует кадров в списке мини-кадры.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>  CDockingManager::SaveState  
 Сохраняет состояние в диспетчере закрепления в реестре.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszProfileName*  
 Путь к разделу реестра.  
  
 [in] *uiID*  
 Закрепления идентификатор руководителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если состояние была сохранена успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Сохранение состояния диспетчере закрепления в реестр связано с сохранением состояния панелей элементов управления, автоматическое скрытие панелей состояния и состояния мини-кадры, которые присутствуют в диспетчере закрепления.  
  
##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames  
 Отправляет указанное сообщение все мини-кадры.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uMessage*  
 Отправляемое сообщение.  
  
 [in] *wParam*  
 Сведения, зависящие от дополнительное сообщение.  
  
 [in] *lParam*  
 Сведения, зависящие от дополнительное сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` всегда.  
  
##  <a name="serialize"></a>  CDockingManager::Serialize  
 Записывает в диспетчере закрепления в архив.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *ar*  
 Ссылка на объект архива.  
  
### <a name="remarks"></a>Примечания  
 Записи в диспетчере закрепления в архив подразумевает определение того, количество закрепляемых панелей элементов управления и ползунков и записи в архиве панелей элементов управления, мини-кадры, автоматическое скрытие панелей и полосы с вкладками MDI.  
  
##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder  
 Задает размер, ширину и высоту панели элементов управления и в указанной области.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pAHDockingBar*  
 Указатель на закрепляемую панель.  
  
##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode  
 Задает режим закрепления.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Параметры  
 *dockMode*  
 Задает новый режим закрепления. Дополнительные сведения см. в разделе "Примечания".  
  
 *Темы*  
 Определяет тему для интеллектуальных маркеров закрепления. Он может принимать одно из следующих значений: AFX_SDT_DEFAULT AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот статический метод, чтобы задать режим закрепления.  
  
 *dockMode* может принимать одно из следующих значений:  
  
- `DT_STANDARD` -Стандарт закрепление режим реализованное в Visual Studio .NET 2003. Области при перетаскивании без перетаскивания контекста.  
  
- `DT_IMMEDIATE` -Режим интерпретации закрепления как реализован в Microsoft Visio. При перетаскивании области перетаскивания контекстом, но отображаются без маркеров.  
  
- `DT_SMART` -Смарт-закрепления режим реализованное в Visual Studio 2005. При перетаскивании области перетаскивания контекстом и будут отображаться маркеры смарт-, показывающие, где можно закрепить области.  
  
##  <a name="setdockstate"></a>  CDockingManager::SetDockState  
 Задает состояние закрепления панели элементов управления, мини-кадры и автоматическое скрытие панелей.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>  CDockingManager::SetPrintPreviewMode  
 Задает режим предварительного просмотра панелей, которые отображаются в режиме предварительного просмотра.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bPreview*  
 `TRUE` Если включен режим предварительного просмотра печати; `FALSE` в противном случае.  
  
 [in] *состояния производительности*  
 Указатель на состоянии предварительной версии. Этот параметр не используется.  
  
##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams  
 Задает параметры, определяющие поведение смарт-закрепления.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] *params*  
 Определяет параметры для смарт-закрепления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается в том случае, если вы хотите настроить внешний вид, цвет и форма интеллектуальных маркеров закрепления.  
  
 Чтобы использовать заданные по умолчанию вид интеллектуальных маркеров закрепления, передать неинициализированный экземпляр [класса CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) для *params*.  
  
##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames  
 Отображение или скрытие окна мини-кадры.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bShow*  
 `TRUE` Чтобы активировать окно показано фрейма; `FALSE` скрыть окно фрейма.  
  
##  <a name="showpanes"></a>  CDockingManager::ShowPanes  
 Отображение или скрытие панели управления и автоматическое скрытие панелей.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bShow*  
 `TRUE` для отображения панели; `FALSE` скрытие панелей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
##  <a name="startsdocking"></a>  CDockingManager::StartSDocking  
 Запускает смарт-закрепления указанного окна в соответствии с выравнивание смарт-закрепления диспетчера.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDockingWnd*  
 Указатель на окно будет закреплено.  
  
##  <a name="stopsdocking"></a>  CDockingManager::StopSDocking  
 Останавливает смарт-закрепления.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>  CDockingManager::GetSmartDockingTheme  
 Статический метод, возвращающий темы, используемый для отображения интеллектуальных маркеров закрепления.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает одно из следующих значений: AFX_SDT_DEFAULT AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)
