---
title: Класс CDockingManager | Документация Майкрософт
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
ms.openlocfilehash: 24b663e1b07d1012c1611714390340df3ce3867f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448509"
---
# <a name="cdockingmanager-class"></a>Класс CDockingManager

Реализует базовую функциональность, которая контролирует макет закрепления в окне главного фрейма.

## <a name="syntax"></a>Синтаксис

```
class CDockingManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDockingManager::AddDockSite](#adddocksite)|Создает область закрепления и добавляет его в список панелей элементов управления.|
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Добавляет маркер в панель области в список скрытых MDI с вкладками областями строки.|
|[CDockingManager::AddMiniFrame](#addminiframe)|Добавляет кадр в список мини-кадры.|
|[CDockingManager::AddPane](#addpane)|Регистрирует область в диспетчере закрепления.|
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Повторно вычисляет и настраивает макет все области в окне фрейма.|
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Приводит к отправляться на всех панелях сообщения WM_NCCALCSIZE и `CPaneFrameWnd` windows.|
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Выравнивает прямоугольник.|
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Изменяет размер закрепляемой области в режим автоматического скрытия, таким образом, требуется полная ширина или Высота клиентской области рамки, заключив его закрепление сайтов.|
|[CDockingManager::AutoHidePane](#autohidepane)|Создает автоматически скрываемой панели инструментов.|
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Переводит закрепленной столбцы, которые имеют указанное выравнивание в начало.|
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Добавляет имена закрепления панели и панелей инструментов в меню.|
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Вычисляет ожидаемый прямоугольник закрепленного окна.|
|[CDockingManager::Create](#create)|Создает диспетчере закрепления.|
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Определяет область, которая содержит заданной точки и его состояние закрепления.|
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Включает или отключает загрузку макет закрепления из реестра.|
|[CDockingManager::DockPane](#dockpane)|Закрепляет область на другую панель, или в окне фрейма.|
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Закрепляет область слева от другой области.|
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Позволяет закрепление области в главном фрейме, создает область закрепления и добавляет его в список панелей элементов управления.|
|[CDockingManager::EnableDocking](#enabledocking)|Создает область закрепления и включает закрепление области в главном фрейме.|
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Отображает дополнительную кнопку, открывается всплывающее меню заголовков всех закрепляемых панелей.|
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Указывает библиотеке для отображения специальных контекстное меню со списком приложений панелей инструментов и закрепляемых панелей, когда пользователь щелкает правой кнопкой мыши и обрабатывает сообщение WM_CONTEXTMENU библиотеки.|
|[CDockingManager::FindDockSite](#finddocksite)|Извлекает строке области, расположенной в указанной позиции и имеет указанное выравнивание.|
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Возвращает панель области с идентификатором панели целевой строки.|
|[CDockingManager::FindPaneByID](#findpanebyid)|Находит области с помощью идентификатора указанного элемента управления.|
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Фиксирует все текущее положение панелей инструментов в виртуальный прямоугольники.|
|[CDockingManager::FrameFromPoint](#framefrompoint)|Возвращает границу, содержащее заданную точку.|
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Возвращает прямоугольник, содержащий границы клиентской области.|
|[CDockingManager::GetDockingMode](#getdockingmode)|Возвращает текущий режим закрепления.|
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Получает указатель на рамку окна родительского.|
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Возвращает включено выравнивание областей.|
|[CDockingManager::GetMiniFrames](#getminiframes)|Получает список miniframes.|
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Возвращает прямоугольник, содержащий внешние края рамки.|
|[CDockingManager::GetPaneList](#getpanelist)|Возвращает список областей, которые принадлежат диспетчере закрепления. Сюда входят все плавающих панелей.|
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Извлекает указатель на диспетчер смарт-закрепления.|
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Извлекает указатель на диспетчер смарт-закрепления.|
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Возвращает параметры смарт-закрепления для диспетчера закрепления.|
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Статический метод, возвращающий темы, используемый для отображения интеллектуальных маркеров закрепления.|
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Скрывает область, в которой находится в режиме автоматического скрытия.|
|[CDockingManager::InsertDockSite](#insertdocksite)|Создает область закрепления и вставляет его в список панелей элементов управления.|
|[CDockingManager::InsertPane](#insertpane)|Вставляет панель элемента управления в список панелей элементов управления.|
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Указывает, отображение всплывающего меню заголовков всех областей.|
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Определяет, если корректируются макеты всех областей.|
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Указывает, находится ли в диспетчере закрепления в режиме контейнера OLE.|
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайтом закрепления.|
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Определяет, если устанавливается режим предварительного просмотра.|
|[CDockingManager::LoadState](#loadstate)|Загружает состояние закрепления manager из реестра.|
|[CDockingManager::LockUpdate](#lockupdate)|Блокирует заданного окна.|
|[CDockingManager::OnActivateFrame](#onactivateframe)|Вызывается платформой, когда он становится активным или отключении окна фрейма.|
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.|
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Вызывается платформой для перемещения окна области.|
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Вызывается платформой при построении меню, которое содержит список областей.|
|[CDockingManager::PaneFromPoint](#panefrompoint)|Возвращает область, содержащее заданную точку.|
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Вызывается платформой для выберите снимите флажок для указанной команды и повторно рассчитать макет показано области.|
|[CDockingManager::RecalcLayout](#recalclayout)|Повторно вычисляет внутренний макет элементов управления присутствует в списке элементов управления.|
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Освобождает контейнеры пустая область.|
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Удаляет указанный скрыты панели области.|
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Удаляет заданный промежуток в списке мини-кадры.|
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет регистрацию область и удаляет его из списка в диспетчере закрепления.|
|[CDockingManager::ReplacePane](#replacepane)|Заменяет одну панель другой.|
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Использует фреймы в списке мини-кадры.|
|[CDockingManager::SaveState](#savestate)|Сохраняет состояние в диспетчере закрепления в реестре.|
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Отправляет указанное сообщение все мини-кадры.|
|[CDockingManager::Serialize](#serialize)|Записывает в диспетчере закрепления в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Задает размер, ширину и высоту панелей элементов управления и в указанной области.|
|[CDockingManager::SetDockingMode](#setdockingmode)|Задает режим закрепления.|
|[CDockingManager::SetDockState](#setdockstate)|Задает состояние стыковки панелей элементов управления, мини-кадры и автоматическое скрытие панелей.|
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Задает режим предварительного просмотра панелей, которые отображаются в режиме предварительного просмотра.|
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Задает параметры, определяющие поведение смарт-закрепления.|
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Отображение или скрытие окна мини-кадры.|
|[CDockingManager::ShowPanes](#showpanes)|Отображение или скрытие панели управления и автоматическое скрытие панелей.|
|[CDockingManager::StartSDocking](#startsdocking)|Запускает смарт-закрепления указанного окна в соответствии с выравнивание смарт-закрепления диспетчера.|
|[CDockingManager::StopSDocking](#stopsdocking)|Останавливает смарт-закрепления.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Указывает, скрываются ли диспетчере закрепления панелей в режиме контейнера OLE.|
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Указывает глобальный режим закрепления.|
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Чувствительность закрепления.|
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Указывает время, в миллисекундах, прежде чем закрепляемой области, расположенной в режиме интерпретации закрепления.|
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.|

## <a name="remarks"></a>Примечания

Фрейма главного окна, создает и инициализирует автоматически.

Объект диспетчера закрепления содержит список всех областей, которые находятся в макете закрепления, а также список всех [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) окна, принадлежащие к фрейма главного окна.

`CDockingManager` Класс реализует некоторые службы, которые можно использовать для поиска в области или `CPaneFrameWnd` окна. Вы обычно не вызывают эти службы напрямую, так как они упаковываются в объект фрейма главного окна. Дополнительные сведения см. в разделе [класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).

## <a name="customization-tips"></a>Советы по настройке

Ниже приведены рекомендации применяются к `CDockingManager` объектов:

- [Класс CDockingManager](../../mfc/reference/cdockingmanager-class.md) поддерживает эти закрепления режима:

    - `AFX_DOCK_TYPE::DT_IMMEDIATE`

    - `AFX_DOCK_TYPE::DT_STANDARD`

    - `AFX_DOCK_TYPE::DT_SMART`

     Эти режимы закрепления определяются [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) и устанавливаются с помощью вызова [CDockingManager::SetDockingMode](#setdockingmode).

- Если вы хотите создать область неплавающего, неизменяемый, вызвать [CDockingManager::AddPane](#addpane) метод. Этот метод регистрирует области в диспетчере закрепления, который отвечает за размещение области.

## <a name="example"></a>Пример

Следующий пример демонстрирует использование различных методов `CDockingManager` класс для настройки `CDockingManager` объекта. В примере показано, как отображать дополнительную кнопку, открывается всплывающее меню заголовков всех закрепляемых панелей и как задать режим закрепления объекта. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).

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

*Сведения о*<br/>
[in] Ссылка на структуру сведений, содержащий закрепления панели выравнивания.

*ppDockBar*<br/>
[out] Указатель на указатель на новую область закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если на панели dock был создан успешно; Значение FALSE в противном случае.

##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar

Добавляет маркер в панель области в список скрытых MDI с вкладками областями строки.

```
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Указатель на строку области

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

*pWnd*<br/>
[in, out] Указывает панель, чтобы добавить в диспетчере закрепления.

*bTail*<br/>
[in] Значение TRUE, добавляемый в конец списка областей на панели для закрепления manager; в противном случае — значение FALSE.

*bAutoHide*<br/>
[in] Только для внутреннего использования. Всегда используйте значение по умолчанию FALSE.

*bInsertForOuterEdge*<br/>
[in] Только для внутреннего использования. Всегда используйте значение по умолчанию FALSE.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области успешно зарегистрирован в диспетчере закрепления; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для регистрации области неплавающего, неизменяемый в диспетчере закрепления. Если вы не зарегистрируете области, они не будут отображаться правильно при располагаются в диспетчере закрепления.

##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout

Повторно вычисляет и настраивает макет все области в окне фрейма.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>Параметры

*hdwp*<br/>
[in] Задает структуру позиции отложенного окна. Дополнительные сведения см. в разделе [типы данных Windows](/windows/desktop/WinProg/windows-data-types).

### <a name="remarks"></a>Примечания

##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame

Добавляет кадр в список мини-кадры.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Указатель на кадр.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр не находится в списке мини-кадры и был успешно добавлен; Значение FALSE в противном случае.

##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames

Приводит к отправляться на всех панелях сообщения WM_NCCALCSIZE и `CPaneFrameWnd` windows.

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

*rectResult*<br/>
[in] Ссылку на `CRect` объекта

*dwAlignment*<br/>
[in] Выравнивание `CRect` объекта

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выравнивание `CRect` отразил объекта; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

*DwAlignment* параметр может принимать одно из следующих значений:

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane

Изменяет размер закрепляемой области в режим автоматического скрытия, таким образом, требуется полная ширина или Высота клиентской области рамки, заключив его закрепление сайтов.

```
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>Параметры

*pDefaultSlider*<br/>
[in] На панели закрепления ползунка.

*bIsVisible*<br/>
[in] Значение TRUE, если закрепляемой области является видимым. Значение FALSE в противном случае.

##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane

Создает автоматически скрываемой панели инструментов.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Указатель на панель области.

*pCurrAutoHideToolBar*<br/>
[in] Указатель на автоматически скрывать панель инструментов.

### <a name="return-value"></a>Возвращаемое значение

Значение NULL, если автоматическое скрытие панели инструментов не был создан; в противном случае указатель на новой панели инструментов.

##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop

Переводит закрепленной столбцы, которые имеют указанное выравнивание в начало.

```
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>Параметры

*dwAlignment*<br/>
[in] Выравнивание панели закрепления, которые вводятся в верхнюю часть других окон.

*bExcludeDockedBars*<br/>
[in] Значение TRUE, чтобы исключить закрепленной панели из процесса в верхней части; в противном случае — значение FALSE.

##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu

Добавляет имена закрепления панели и панелей инструментов в меню.

```
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
[in] Меню, чтобы добавить имена закрепления панели и панелей инструментов.

*bToolbarsOnly*<br/>
[in] Значение TRUE, чтобы добавить имена только панелей инструментов в меню; Значение FALSE в противном случае.

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

*pWnd*<br/>
[in] Указатель на окно будет закреплено.

*ptMouse*<br/>
[in] Положение мыши.

*rectResult*<br/>
[out] Расчетный прямоугольник.

*bDrawTab*<br/>
[in] Значение true, чтобы нарисовать вкладку; в противном случае — значение FALSE.

*ppTargetBar*<br/>
[out] Указатель на указатель на целевой области.

### <a name="remarks"></a>Примечания

Этот метод вычисляет прямоугольник, который должны занимать окна, если пользователь перетащил окна точку, указанную *ptMouse* и закрепленные он существует.

##  <a name="create"></a>  CDockingManager::Create

Создает диспетчере закрепления.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in] Указатель на родительского фрейма диспетчера закрепления. Это значение не должно быть значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, всегда.

##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus

Определяет область, которая содержит заданной точки и его состояние закрепления.

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

*pt*<br/>
[in] Расположение панели для проверки.

*nSensitivity*<br/>
[in] Значение, чтобы увеличить прямоугольной области окна каждой из них установлен. Область удовлетворяет условиям поиска, если заданная точка находится в этот Повышенная регионе.

*dwEnabledAlignment*<br/>
[in] Выравнивание панели закрепления.

*ppTargetBar*<br/>
[out] Указатель на указатель на целевой области.

*pBarToIgnore*<br/>
[in] Области, в которой игнорируется.

*pBarToDock*<br/>
[in] Области, расположенной.

### <a name="return-value"></a>Возвращаемое значение

Состояние закрепления.

### <a name="remarks"></a>Примечания

Состояние закрепления может принимать одно из следующих значений:

|Значение AFX_CS_STATUS|Значение|
|---------------------------|-------------|
|CS_NOTHING|Указатель не наведен на сайте закрепления. Таким образом, поддерживать области с плавающей запятой.|
|CS_DOCK_IMMEDIATELY|Указатель находится на сайте закрепления в режим интерпретации (стиль DT_IMMEDIATE включен), поэтому области должен фиксироваться немедленно.|
|CS_DELAY_DOCK|Указатель находится на сайте закрепления, в другой области закрепления или края главного фрейма.|
|CS_DELAY_DOCK_TO_TAB|Указатель находится на сайте закрепления, в которой эта панель быть закреплено в окно с вкладками. Это происходит, когда указатель мыши находится заголовок другого закрепляемой области или области вкладок области с вкладками.|

##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState

Включает или отключает загрузку макет закрепления из реестра.

```
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>Параметры

*bDisable*<br/>
[in] Значение true, чтобы отключить загрузку макет закрепления из реестра; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается в том случае, если необходимо сохранить текущий макет закрепления панели и панелей инструментов, при загрузке состояния приложения.

##  <a name="dockpane"></a>  CDockingManager::DockPane

Закрепляет область на другую панель, или в окне фрейма.

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Указатель на строку области, чтобы закрепить.

*nDockBarID*<br/>
[in] Идентификатор окна, чтобы закрепить.

*lpRect*<br/>
[in] Прямоугольник назначения.

##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf

Закрепляет область слева от другой области.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*pBarToDock*<br/>
[in] Указатель на панели, чтобы закрепить слева от *pTargetBar*.

*pTargetBar*<br/>
[in] Указатель на целевой области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области была закреплена успешно; в противном случае — значение FALSE.

##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes

Позволяет закрепление области в главном фрейме, создает область закрепления и добавляет его в список панелей элементов управления.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
[in] Выравнивание закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если на панели dock был создан успешно; Значение FALSE в противном случае.

##  <a name="enabledocking"></a>  CDockingManager::EnableDocking

Создает область закрепления и включает закрепление области в главном фрейме.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
[in] Выравнивание закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если на панели dock был создан успешно; Значение FALSE в противном случае.

##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu

Отображает дополнительную кнопку, открывается всплывающее меню заголовков всех закрепляемых панелей.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, чтобы включить всплывающего меню сайта; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В меню сайта закрепления отображаются следующие параметры для изменения состояния закрепления панели:

- `Floating` — Преобразует панель

- `Docking` -Закрепляет область в главного фрейма в расположении, где последнего закрепленной панели

- `AutoHide` -Переключается панели в режим автоматического скрытия

- `Hide` -Скрывает область

По умолчанию это меню не отображается.

##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu

Указывает библиотеке для отображения специальных контекстное меню со списком приложений панелей инструментов и закрепляемых панелей, когда пользователь щелкает правой кнопкой мыши и обрабатывает сообщение WM_CONTEXTMENU библиотеки.

```
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, если библиотека включает поддержку автоматического контекстное меню; Если значение равно FALSE библиотеке отключает поддержку автоматического контекстного меню.

*uiCustomizeCmd*<br/>
[in] Идентификатор команды для **Настройка** элемента меню.

*strCustomizeText*<br/>
[in] Текст **Настройка** элемента.

*bToolbarsOnly*<br/>
[in] Если значение равно TRUE, в меню отображаются только список панелей инструментов приложения; Если значение равно FALSE, библиотеке в этот список добавляются закрепляемых областей приложения.

##  <a name="finddocksite"></a>  CDockingManager::FindDockSite

Извлекает строке области, расположенной в указанной позиции и имеет указанное выравнивание.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>Параметры

*dwAlignment*<br/>
[in] Выравнивание панели области.

*bOuter*<br/>
[in] Значение TRUE, если получить панели в головном положение панелей элементов управления в списке. В противном случае получите панели в заключительного положение в списке панелей элементов управления.

### <a name="return-value"></a>Возвращаемое значение

Закрепляемой области, который имеет указанное выравнивание; В противном случае — значение NULL.

##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID

Находит области с помощью идентификатора указанного элемента управления.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>Параметры

*uBarID*<br/>
[in] Указывает идентификатор элемента панели управления для поиска.

*bSearchMiniFrames*<br/>
[in] Значение TRUE, чтобы включить в поиск всех плавающих панелей. Значение FALSE, чтобы включать только закрепленных панелей.

### <a name="return-value"></a>Возвращаемое значение

[CBasePane](../../mfc/reference/cbasepane-class.md) объект, содержащий указанный элемент управления или значение NULL, если не удается найти указанную область.

### <a name="remarks"></a>Примечания

##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane

Возвращает панель области с идентификатором панели целевой строки.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*pTargetBar*<br/>
[in] Указатель на область панели target.

### <a name="return-value"></a>Возвращаемое значение

Панели панели, содержащую идентификатор области целевой строке. Значение NULL, если существует такой панели области.

##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects

Фиксирует все текущее положение панелей инструментов в виртуальный прямоугольники.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Примечания

Когда пользователь начинает перетаскивание панели инструментов, приложение запоминает исходное положение в *виртуального прямоугольник*. Когда пользователь перемещает панель инструментов между его сайтом закрепления, панели инструментов может привести к небольшому других панелей инструментов. Исходное положение других панелей инструментов, хранятся в соответствующей виртуальной прямоугольников.

##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint

Возвращает границу, содержащее заданную точку.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>Параметры

*pt*<br/>
[in] Указывает точку, в экранных координатах, для проверки.

*pFrameToExclude*<br/>
[in] Указатель на кадр для исключения.

*bFloatMultiOnly*<br/>
[in] Значение true, чтобы исключить кадры, которые не являются экземплярами `CMultiPaneFrameWnd`; Значение FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Кадр, содержащее заданную точку; В противном случае — значение NULL.

##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds

Возвращает прямоугольник, содержащий границы клиентской области.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>Параметры

*rcClient*<br/>
[out] Ссылка на прямоугольник, содержащий границы клиентской области.

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, содержащий границы клиентской области.

##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode

Возвращает текущий режим закрепления.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>Возвращаемое значение

Значение перечислителя, который представляет текущий режим закрепления. Он может принимать одно из следующих значений:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>Примечания

Чтобы задать режим закрепления, вызовите [CDockingManager::SetDockingMode](#setdockingmode).

##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd

Получает указатель на рамку окна родительского.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на рамку окна родительского.

##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment

Возвращает включено выравнивание областей.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>Возвращаемое значение

Побитовое сочетание флагов CBRS_ALIGN_, или 0, если автоматическое скрытие панелей не включены. Дополнительные сведения см. в разделе [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).

### <a name="remarks"></a>Примечания

Метод возвращает выравнивание по поддержкой для автоматического скрытия панели элементов управления. Чтобы включить автоматическое скрытие панелей, вызовите [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).

##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames

Получает список miniframes.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>Возвращаемое значение

Список miniframes, содержащие панелей элементов управления, которые принадлежат диспетчере закрепления.

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

*lstBars*<br/>
[in, out] Содержит все области текущего диспетчера закрепления.

*bIncludeAutohide*<br/>
[in] Значение TRUE для включения областей, которые находятся в режиме автоматического скрытия. в противном случае — значение FALSE.

*pRTCFilter*<br/>
[in] Если значение не NULL, этот список содержит панели только из указанного класса среды выполнения.

*bIncludeTabs*<br/>
[in] Значение TRUE, чтобы включить табуляции; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При возникновении любой вкладки в диспетчере закрепления, метод возвращает указатели на [класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md) объектах и ее необходимо перечислить вкладки явным образом.

Используйте *pRTCFilter* для получения определенного класса из панелей. Например можно получить только панелей инструментов, задав это значение соответствующим образом.

##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager

Извлекает указатель на диспетчер смарт-закрепления.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на диспетчер смарт-закрепления.

##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent

Извлекает указатель на диспетчер смарт-закрепления.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на диспетчер смарт-закрепления.

##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams

Возвращает параметры смарт-закрепления для диспетчера закрепления.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>Возвращаемое значение

Класс, содержащий параметры смарт-закрепления для текущего диспетчера закрепления. Дополнительные сведения см. в разделе [класс CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md).

### <a name="remarks"></a>Примечания

##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes

Скрывает область, в которой находится в режиме автоматического скрытия.

```
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>Параметры

*pBarToExclude*<br/>
[in] Указатель на строку, чтобы исключить из скрытие.

*bImmediately*<br/>
[in] Значение TRUE, чтобы скрыть область немедленно; Значение FALSE, чтобы скрыть область с эффектом автоматического скрытия.

##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite

Создает область закрепления и вставляет его в список панелей элементов управления.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Параметры

*Сведения о*<br/>
[in] Структура, которая содержит сведения о выравнивании Общие сведения о панели закрепления.

*dwAlignToInsertAfter*<br/>
[in] Выравнивание панели закрепления.

*ppDockBar*<br/>
[out] Указатель на указатель на область закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если на панели dock был создан успешно; Значение FALSE в противном случае.

##  <a name="insertpane"></a>  CDockingManager::InsertPane

Вставляет панель элемента управления в список панелей элементов управления.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Параметры

*pControlBar*<br/>
[in] Указатель на панели управления.

*pTarget*<br/>
[in] Указатель на целевой области.

*bAfter*<br/>
[in] Значение TRUE, если нужно вставить панель после позиции на нужной панели; Значение FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если на панели управления успешно добавлен в список панелей элементов управления; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение false, если на панели управления уже находится в списке панелей элементов управления или области целевой объект не существует в списке панелей элементов управления.

##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu

Указывает, отображение всплывающего меню заголовков всех областей.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если меню сайта закрепления отображается на заголовков всех закрепляемых областей; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вы можете включить всплывающего меню сайта путем вызова [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).

##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout

Определяет, если корректируются макеты всех областей.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если корректируются макеты всех областей; Значение FALSE в противном случае.

##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode

Указывает, находится ли в диспетчере закрепления в режиме контейнера OLE.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в диспетчере закрепления находится в режиме контейнера OLE; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В режиме контейнера OLE скрыты все области закрепления и панелей инструментов приложения. Области также скрыты в этом режиме, если вы задали [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) значение true.

##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite

Определяет, является ли указанная точка рядом с сайтом закрепления.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>Параметры

*точка*<br/>
[in] Указанная точка.

*dwBarAlignment*<br/>
[out] Задает край приближается к точке. Возможные значения: CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP и CBRS_ALIGN_BOTTOM.

*bOuterEdge*<br/>
[out] Значение TRUE, если точка находится рядом с внешней границы элемента на сайте закрепления; Значение FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если точка находится рядом с сайтом закрепления; в противном случае — значение FALSE.

##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid

Определяет, если устанавливается режим предварительного просмотра.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если задан режим предварительного просмотра печати; Значение FALSE в противном случае.

##  <a name="loadstate"></a>  CDockingManager::LoadState

Загружает состояние закрепления manager из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Имя профиля.

*uiID*<br/>
[in] Идентификатор диспетчера закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если состояние закрепления manager был загружен успешно; в противном случае — значение FALSE.

##  <a name="lockupdate"></a>  CDockingManager::LockUpdate

Блокирует заданного окна.

```
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>Параметры

*Блок*<br/>
[in] Значение TRUE, если окно заблокирован; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

При блокировке окна, ее нельзя переместить, и не может быть перерисованы.

##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode

Указывает, скрываются ли диспетчере закрепления панелей в режиме контейнера OLE.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>Примечания

Это значение равно FALSE, если вы хотите сохранить все области, прикрепленные к главного фрейма видимым, когда приложение находится в режиме контейнера OLE. По умолчанию это значение равно TRUE.

##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal

Указывает глобальный режим закрепления.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>Примечания

По умолчанию каждый закрепляемой области использует этот режим закрепления. Дополнительные сведения о значениях, это поле может быть присвоено см. в разделе [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity

Чувствительность закрепления.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>Примечания

Закрепления чувствительности определяет насколько плавающей панели можно будет перейти закрепляемой области, закрепления узла или другую панель прежде, чем платформа изменяет свое состояние закреплено.

##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock

Указывает время, в миллисекундах, прежде чем закрепляемой области, расположенной в режиме интерпретации закрепления.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>Примечания

Прежде, чем панель закреплена, платформа ожидает в течение указанного периода времени. Это предотвращает случайно, закрепленный в расположение, пока пользователь по-прежнему перетаскивает его области.

##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock

Указывает время, в миллисекундах, прежде чем панель инструментов закреплены фрейма главного окна.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>Примечания

Прежде чем закрепленной панели инструментов, платформы ожидает в течение указанного периода времени. Это предотвращает случайно, закрепленный в расположение, пока пользователь по-прежнему перетаскивает его панели инструментов.

##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame

Вызывается платформой, когда он становится активным или отключении окна фрейма.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
[in] Значение TRUE, если фрейм окна делается активным; Если значение равно FALSE, деактивируется фрейма окна.

##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu

Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.

```
void OnClosePopupMenu();
```

### <a name="remarks"></a>Примечания

Платформа отправляет сообщение WM_DESTROY, когда он собирается закрыть текущее основное окно. Переопределите этот метод для обработки уведомлений от `CMFCPopupMenu` объектов, принадлежащих к окну фрейма при `CMFCPopupMenu` объект обрабатывает сообщение WM_DESTROY.

##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame

Вызывается платформой для перемещения окна области.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
[in] Указатель на окна области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu

Вызывается платформой при построении меню, которое содержит список областей.

```
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>Параметры

*точка*<br/>
[in] Указывает расположение меню.

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

*точка*<br/>
[in] Указывает точку, в экранных координатах, для проверки.

*nSensitivity*<br/>
[in] Значение, на которую увеличится прямоугольной области окна каждой из них установлен. Область удовлетворяет условиям поиска, если заданная точка находится в этом увеличенную регионе.

*bExactBar*<br/>
[in] Значение TRUE, чтобы игнорировать *nSensitivity* параметра; в противном случае — значение FALSE.

*pRTCBarType*<br/>
[in] Если значение не NULL, метод выполняет поиск только областей указанного типа.

*bCheckVisibility*<br/>
[in] Значение TRUE, чтобы проверить только видимых панелей; в противном случае — значение FALSE.

*dwAlignment*<br/>
[out] Если область находится в заданной точке, данный параметр содержит части панели, который был ближайший к заданной точке. Дополнительные сведения см. в разделе "Примечания".

*pBarToIgnore*<br/>
[in] Если значение не NULL, метод не обрабатывает панелей, заданный этим параметром.

### <a name="return-value"></a>Возвращаемое значение

[CBasePane](../../mfc/reference/cbasepane-class.md)-производный объект, содержащий в момент, или значение NULL, если области не был найден.

### <a name="remarks"></a>Примечания

Если функция возвращает и область была найдена, *dwAlignment* содержит выравнивание указанную точку. Например, если точка находилась ближе всего к верхней части области *dwAlignment* присваивается CBRS_ALIGN_TOP.

##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand

Вызывается платформой для выберите снимите флажок для указанной команды и повторно рассчитать макет показано области.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Идентификатор панели элементов управления в меню.

*nCode*<br/>
[in] Код уведомления команды.

*pExtra*<br/>
[in] Указатель на void, привести к указателю на `CCmdUI` Если *nCode* является CN_UPDATE_COMMAND_UI.

*pHandlerInfo*<br/>
[in] Указатель на структуру сведений. Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *pEXtra* не равно NULL и *nCode* равно CN_UPDATE_COMMAND_UI, или если имеется панель элементов управления с указанным *nID*.

##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout

Повторно вычисляет внутренний макет элементов управления присутствует в списке элементов управления.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*bNotify*<br/>
[in] Этот параметр не используется.

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

*pBar*<br/>
[in] Указатель на строку области для удаления.

##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame

Удаляет заданный промежуток в списке мини-кадры.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Указатель на кадр для удаления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если удаляется заданного фрейма; Значение FALSE в противном случае.

##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager

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

*pWnd*<br/>
[in] Указатель на область для удаления.

*bDestroy*<br/>
[in] Значение TRUE, если уничтожается области удален.

*bAdjustLayout*<br/>
[in] Значение TRUE, если настройте макет закрепления немедленно.

*bAutoHide*<br/>
[in] Значение TRUE, если области удаляется из списка автоматического скрытия панели. Если значение равно FALSE, области удаляется из списка регулярных панелей.

*pBarReplacement*<br/>
[in] Указатель на область, которая заменяет области удален.

##  <a name="replacepane"></a>  CDockingManager::ReplacePane

Заменяет одну панель другой.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>Параметры

*pOriginalBar*<br/>
[in] Указатель на исходной области.

*pNewBar*<br/>
[in] Указатель на область, которая заменяет исходной области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области успешно заменен; Значение FALSE в противном случае.

##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder

Использует фреймы в списке мини-кадры.

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

*lpszProfileName*<br/>
[in] Путь к разделу реестра.

*uiID*<br/>
[in] Закрепления идентификатор руководителя.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если состояние было сохранено успешно. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Сохранение состояния диспетчере закрепления в реестр связано с сохранением состояния панели элементов управления, состояния панели Автоскрытие и состояния мини-кадры, в диспетчере закрепления.

##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames

Отправляет указанное сообщение все мини-кадры.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>Параметры

*uMessage*<br/>
[in] Отправляемое сообщение.

*wParam*<br/>
[in] Сведения, зависящие от дополнительное сообщение.

*lParam*<br/>
[in] Сведения, зависящие от дополнительное сообщение.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, всегда.

##  <a name="serialize"></a>  CDockingManager::Serialize

Записывает в диспетчере закрепления в архив.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
[in] Ссылка на объект архива.

### <a name="remarks"></a>Примечания

Записи в диспетчере закрепления в архив подразумевает определение номер закрепляемых панелей элементов управления, а также ползунков и написания панелей элементов управления, мини-кадры, автоматического скрытия и с вкладками MDI полосы в архив.

##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder

Задает размер, ширину и высоту панелей элементов управления и в указанной области.

```
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>Параметры

*pAHDockingBar*<br/>
[in] Указатель на закрепляемую панель.

##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode

Задает режим закрепления.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>Параметры

*dockMode*<br/>
Задает новый режим закрепления. Дополнительные сведения см. в разделе "Примечания".

*Темы*<br/>
Определяет тему для интеллектуальных маркеров закрепления. Он может принимать одно из следующих значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Примечания

Вызовите этот статический метод, чтобы задать режим закрепления.

*dockMode* может принимать одно из следующих значений:

- DT_STANDARD - стандартный режим закрепления, как они реализованы в Visual Studio .NET 2003. Области при перетаскивании без перетаскивания контекста.

- DT_IMMEDIATE - режим интерпретации закрепления, как они реализованы в Microsoft Visio. Области при перетаскивании с контекстом перетаскивания, но маркеры не отображаются.

- DT_SMART - режим смарт-закрепления, как они реализованы в Visual Studio 2005. Области при перетаскивании с контекстом перетаскивания и будут отображаться смарт-маркеры, показывающие, где можно закрепить области.

##  <a name="setdockstate"></a>  CDockingManager::SetDockState

Задает состояние стыковки панелей элементов управления, мини-кадры и автоматическое скрытие панелей.

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

*bPreview*<br/>
[in] Значение TRUE, если задан режим предварительного просмотра печати; Значение FALSE в противном случае.

*состояния производительности*<br/>
[in] Указатель на предварительной версии. Этот параметр не используется.

##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams

Задает параметры, определяющие поведение смарт-закрепления.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Параметры

*params*<br/>
[in, out] Определяет параметры для смарт-закрепления.

### <a name="remarks"></a>Примечания

Этот метод вызывается в том случае, если вы хотите настроить внешний вид, цвет и форму интеллектуальных маркеров закрепления.

Для использования по умолчанию внешний вид интеллектуальных маркеров закрепления, передать экземпляр неинициализированный [класс CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) для *params*.

##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames

Отображение или скрытие окна мини-кадры.

```
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
[in] Значение TRUE, чтобы активировать окно показано фрейма; Значение FALSE, чтобы скрыть окно фрейма.

##  <a name="showpanes"></a>  CDockingManager::ShowPanes

Отображение или скрытие панели управления и автоматическое скрытие панелей.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
[in] Значение TRUE для отображения области; Значение FALSE, чтобы скрыть области.

### <a name="return-value"></a>Возвращаемое значение

Всегда имеет значение FALSE.

##  <a name="startsdocking"></a>  CDockingManager::StartSDocking

Запускает смарт-закрепления указанного окна в соответствии с выравнивание смарт-закрепления диспетчера.

```
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>Параметры

*pDockingWnd*<br/>
[in] Указатель на окно будет закреплено.

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

Возвращает одно из следующих значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)<br/>
[Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)
