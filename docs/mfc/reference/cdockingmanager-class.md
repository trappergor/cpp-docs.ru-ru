---
title: "CDockingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingManager class"
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CDockingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует основные функциональные возможности, элементы управления фреймовом закрепляющий структура в главном окне.  
  
## Синтаксис  
  
```  
class CDockingManager : public CObject  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDockingManager::AddDockSite](../Topic/CDockingManager::AddDockSite.md)|Создает панели закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::AddHiddenMDITabbedBar](../Topic/CDockingManager::AddHiddenMDITabbedBar.md)|Добавляет маркер на панели список скрытый нашитых MDI панелей панели.|  
|[CDockingManager::AddMiniFrame](../Topic/CDockingManager::AddMiniFrame.md)|Добавить фрейм в список миникадров.|  
|[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)|Регистрирует область с диспетчером закрепления.|  
|[CDockingManager::AdjustDockingLayout](../Topic/CDockingManager::AdjustDockingLayout.md)|Повторно вычисляет макет и обрабатывает всех панелей в фреймовом окне.|  
|[CDockingManager::AdjustPaneFrames](../Topic/CDockingManager::AdjustPaneFrames.md)|Приводит к тому, что сообщение `WM_NCCALCSIZE` отправку на все окна и панели `CPaneFrameWnd`.|  
|[CDockingManager::AdjustRectToClientArea](../Topic/CDockingManager::AdjustRectToClientArea.md)|Обрабатывает выравнивание прямоугольника.|  
|[CDockingManager::AlignAutoHidePane](../Topic/CDockingManager::AlignAutoHidePane.md)|Изменяет размер панели закрепления в режиме автоматического скрытия таким образом, чтобы он принимает полные ширина или высота клиентской области фреймов окруженной сайтами закрепления.|  
|[CDockingManager::AutoHidePane](../Topic/CDockingManager::AutoHidePane.md)|Создает панель инструментов autohide.|  
|[CDockingManager::BringBarsToTop](../Topic/CDockingManager::BringBarsToTop.md)|Перемещение закрепленных области, которые содержат указанное выравнивание к верхнему краю.|  
|[CDockingManager::BuildPanesMenu](../Topic/CDockingManager::BuildPanesMenu.md)|Добавляет имена панели закрепления в меню и панелей инструментов.|  
|[CDockingManager::CalcExpectedDockedRect](../Topic/CDockingManager::CalcExpectedDockedRect.md)|Вычисляет ожидаемый прямоугольник состыкованного окна.|  
|[CDockingManager::Create](../Topic/CDockingManager::Create.md)|Создает диспетчер закрепления.|  
|[CDockingManager::DeterminePaneAndStatus](../Topic/CDockingManager::DeterminePaneAndStatus.md)|Определяет область, которая содержит заданную точку и состояния закрепления.|  
|[CDockingManager::DisableRestoreDockState](../Topic/CDockingManager::DisableRestoreDockState.md)|Позволяет включить или отключить загрузку структуры закрепления из реестра.|  
|[CDockingManager::DockPane](../Topic/CDockingManager::DockPane.md)|Закрепит панель к другой области или фреймовому окно.|  
|[CDockingManager::DockPaneLeftOf](../Topic/CDockingManager::DockPaneLeftOf.md)|Закрепит область слева от другой области.|  
|[CDockingManager::EnableAutoHidePanes](../Topic/CDockingManager::EnableAutoHidePanes.md)|Включает закрепления панелей в главного фрейма, создает панели закрепления и добавляет его в список панелей элементов управления.|  
|[CDockingManager::EnableDocking](../Topic/CDockingManager::EnableDocking.md)|Создает панели закрепления и включает закрепления панелей в главного фрейма.|  
|[CDockingManager::EnableDockSiteMenu](../Topic/CDockingManager::EnableDockSiteMenu.md)|Отображает дополнительные кнопку, которая открывает всплывающее меню в заголовках всех панелей закрепления.|  
|[CDockingManager::EnablePaneContextMenu](../Topic/CDockingManager::EnablePaneContextMenu.md)|Указывает, что библиотека указывающее специальные контекстное меню, которое содержит список панелей инструментов приложения и закрепления панелей, когда пользователь щелкает правой кнопкой мыши и библиотека обрабатывающей сообщение WM\_CONTEXTMENU.|  
|[CDockingManager::FindDockSite](../Topic/CDockingManager::FindDockSite.md)|Возвращает панель, которая в указанной позиции и имеющего указанный тип выравнивания.|  
|[CDockingManager::FindDockSiteByPane](../Topic/CDockingManager::FindDockSiteByPane.md)|Возвращает панель, которая имеет идентификатор панели целевого объекта.|  
|[CDockingManager::FindPaneByID](../Topic/CDockingManager::FindPaneByID.md)|Находит панель управления идентификатором.|  
|[CDockingManager::FixupVirtualRects](../Topic/CDockingManager::FixupVirtualRects.md)|Фиксирует все текущие части панели инструментов в виртуальный прямоугольникам.|  
|[CDockingManager::FrameFromPoint](../Topic/CDockingManager::FrameFromPoint.md)|Возвращает кадр, который содержит заданную точку.|  
|[CDockingManager::GetClientAreaBounds](../Topic/CDockingManager::GetClientAreaBounds.md)|Возвращает прямоугольник, содержащий границы клиентской области.|  
|[CDockingManager::GetDockingMode](../Topic/CDockingManager::GetDockingMode.md)|Возвращает текущий режим закрепления.|  
|[CDockingManager::GetDockSiteFrameWnd](../Topic/CDockingManager::GetDockSiteFrameWnd.md)|Получает указатель к кадру родительского окна.|  
|[CDockingManager::GetEnabledAutoHideAlignment](../Topic/CDockingManager::GetEnabledAutoHideAlignment.md)|Возвращает включена выравнивание областей.|  
|[CDockingManager::GetMiniFrames](../Topic/CDockingManager::GetMiniFrames.md)|Получает список miniframes.|  
|[CDockingManager::GetOuterEdgeBounds](../Topic/CDockingManager::GetOuterEdgeBounds.md)|Возвращает прямоугольник, который содержит внешний края кадра.|  
|[CDockingManager::GetPaneList](../Topic/CDockingManager::GetPaneList.md)|Возвращает список панелей, относящихся к диспетчеру закрепления.  Это включает все области плавающей запятой.|  
|[CDockingManager::GetSmartDockingManager](../Topic/CDockingManager::GetSmartDockingManager.md)|Извлекает указатель на умному диспетчер закрепления.|  
|[CDockingManager::GetSmartDockingManagerPermanent](../Topic/CDockingManager::GetSmartDockingManagerPermanent.md)|Извлекает указатель на умному диспетчер закрепления.|  
|[CDockingManager::GetSmartDockingParams](../Topic/CDockingManager::GetSmartDockingParams.md)|Возвращает интеллектуальные параметры закрепления для диспетчера закрепления.|  
|[CDockingManager::GetSmartDockingTheme](../Topic/CDockingManager::GetSmartDockingTheme.md)|Статический метод, который возвращает тему, используемую для отображения меток умных закрепления.|  
|[CDockingManager::HideAutoHidePanes](../Topic/CDockingManager::HideAutoHidePanes.md)|Скрывает панель, которая находится в режиме автоматического скрытия.|  
|[CDockingManager::InsertDockSite](../Topic/CDockingManager::InsertDockSite.md)|Создает панели закрепления и вставки их в список панелей элементов управления.|  
|[CDockingManager::InsertPane](../Topic/CDockingManager::InsertPane.md)|Вставляет панель элементов управления в список панелей элементов управления.|  
|[CDockingManager::IsDockSiteMenu](../Topic/CDockingManager::IsDockSiteMenu.md)|Указывает, отображается ли контекстное меню меню в заголовках всех панелей.|  
|[CDockingManager::IsInAdjustLayout](../Topic/CDockingManager::IsInAdjustLayout.md)|Определяет, структуры всех панелей корректируются.|  
|[CDockingManager::IsOLEContainerMode](../Topic/CDockingManager::IsOLEContainerMode.md)|Определяет, является ли диспетчер закрепления в режиме OLE\-контейнер.|  
|[CDockingManager::IsPointNearDockSite](../Topic/CDockingManager::IsPointNearDockSite.md)|Определяет, является ли указанная точка находится рядом с сайта закрепления.|  
|[CDockingManager::IsPrintPreviewValid](../Topic/CDockingManager::IsPrintPreviewValid.md)|Указывает, установлен режим предварительного просмотра.|  
|[CDockingManager::LoadState](../Topic/CDockingManager::LoadState.md)|Загружает состояние диспетчера закрепления из реестра.|  
|[CDockingManager::LockUpdate](../Topic/CDockingManager::LockUpdate.md)|Блокирует данного окна.|  
|[CDockingManager::OnActivateFrame](../Topic/CDockingManager::OnActivateFrame.md)|Вызываемый платформой, когда фреймовое окно будет сделать активным или деактивации.|  
|[CDockingManager::OnClosePopupMenu](../Topic/CDockingManager::OnClosePopupMenu.md)|Вызываемый платформой, когда контекстное меню меню активного отображает сообщение WM\_DESTROY.|  
|[CDockingManager::OnMoveMiniFrame](../Topic/CDockingManager::OnMoveMiniFrame.md)|Вызываемый платформой для перемещения окна области.|  
|[CDockingManager::OnPaneContextMenu](../Topic/CDockingManager::OnPaneContextMenu.md)|Вызываемый платформой, когда он создает меню, содержащее список панелей.|  
|[CDockingManager::PaneFromPoint](../Topic/CDockingManager::PaneFromPoint.md)|Возвращает панель, которая содержит заданную точку.|  
|[CDockingManager::ProcessPaneContextMenuCommand](../Topic/CDockingManager::ProcessPaneContextMenuCommand.md)|Вызываемый платформой, чтобы установить или снять флажок для указанной команды и повторно вычислять макет, отображаемой панели.|  
|[CDockingManager::RecalcLayout](../Topic/CDockingManager::RecalcLayout.md)|Повторно вычисляет внутреннюю структуру элементов управления, представленных в списке элементов управления.|  
|[CDockingManager::ReleaseEmptyPaneContainers](../Topic/CDockingManager::ReleaseEmptyPaneContainers.md)|Освобождает пустых контейнеров панели.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](../Topic/CDockingManager::RemoveHiddenMDITabbedBar.md)|Удаляет указанную панель слой.|  
|[CDockingManager::RemoveMiniFrame](../Topic/CDockingManager::RemoveMiniFrame.md)|Удаляет указанный кадр из списка миникадров.|  
|[CDockingManager::RemovePaneFromDockManager](../Topic/CDockingManager::RemovePaneFromDockManager.md)|Отменяет регистрацию панель и удаляет его из списка в диспетчере закрепления.|  
|[CDockingManager::ReplacePane](../Topic/CDockingManager::ReplacePane.md)|Заменяет одну панель с другими.|  
|[CDockingManager::ResortMiniFramesForZOrder](../Topic/CDockingManager::ResortMiniFramesForZOrder.md)|Прибегают кадров в списке миникадров.|  
|[CDockingManager::SaveState](../Topic/CDockingManager::SaveState.md)|Сохраняет состояние диспетчера закрепления в реестр.|  
|[CDockingManager::SendMessageToMiniFrames](../Topic/CDockingManager::SendMessageToMiniFrames.md)|Отправляет указанное сообщение для всех миниым фреймам.|  
|[CDockingManager::Serialize](../Topic/CDockingManager::Serialize.md)|Записывает диспетчер закрепления архивирование.  \(Переопределяет [CObject::Serialize](../Topic/CObject::Serialize.md)\).|  
|[CDockingManager::SetAutohideZOrder](../Topic/CDockingManager::SetAutohideZOrder.md)|Устанавливает размер, ширину и высоту панелей элементов управления и заданной области.|  
|[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md)|Устанавливает режим закрепления.|  
|[CDockingManager::SetDockState](../Topic/CDockingManager::SetDockState.md)|Устанавливает для состояния закрепления панелей элементов управления, миникадров и панелей автоматического скрытия.|  
|[CDockingManager::SetPrintPreviewMode](../Topic/CDockingManager::SetPrintPreviewMode.md)|Устанавливает режим предварительного просмотра панелей, которые отображаются в средстве предварительного просмотра.|  
|[CDockingManager::SetSmartDockingParams](../Topic/CDockingManager::SetSmartDockingParams.md)|Задает параметры, которые определяют расширения функциональности умной закрепления.|  
|[CDockingManager::ShowDelayShowMiniFrames](../Topic/CDockingManager::ShowDelayShowMiniFrames.md)|Миниых показывать или скрывать окна кадров.|  
|[CDockingManager::ShowPanes](../Topic/CDockingManager::ShowPanes.md)|Показать или скрывает панель панелей элементов управления и autohide.|  
|[CDockingManager::StartSDocking](../Topic/CDockingManager::StartSDocking.md)|Запускает интеллектуального элемент закрепление заданного окна в соответствии с выравнивание умного диспетчера закрепления.|  
|[CDockingManager::StopSDocking](../Topic/CDockingManager::StopSDocking.md)|Останавливает интеллектуального элемент закрепление.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDockingManager::m\_bHideDockingBarsInContainerMode](../Topic/CDockingManager::m_bHideDockingBarsInContainerMode.md)|Определяет, следует ли скрывать диспетчер закрепления панели в режиме OLE\-контейнер.|  
|[CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md)|Определяет глобальный режим закрепления.|  
|[CDockingManager::m\_nDockSensitivity](../Topic/CDockingManager::m_nDockSensitivity.md)|Определяет учет закрепления.|  
|[CDockingManager::m\_nTimeOutBeforeDockingBarDock](../Topic/CDockingManager::m_nTimeOutBeforeDockingBarDock.md)|Указывает время в миллисекундах, прежде чем панели закрепления закреплена при немедленном режиме закрепления.|  
|[CDockingManager::m\_nTimeOutBeforeToolBarDock](../Topic/CDockingManager::m_nTimeOutBeforeToolBarDock.md)|Определяет время \(в миллисекундах\) до того, как панель инструментов закреплена к главному фреймовому окно.|  
  
## Заметки  
 Главное фреймовое окно создает и инициализирует этот класс автоматически.  
  
 Объект диспетчера закрепления содержит список всех панелей, в структуре закрепления, а также список всех окон [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md), относящихся к главному фреймовому окно.  
  
 Класс `CDockingManager` реализует ряд служб, которые можно использовать для поиска области или окна `CPaneFrameWnd`.  Обычно не нужно вызывать эти службы напрямую, поскольку они создает программу\-оболочку в основном объекте фреймового окна.  Дополнительные сведения см. в разделе [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  
  
## Советы по настройке  
 Следующие советы, применяются к `CDockingManager` объекты:  
  
-   [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) поддерживает эти режимы закрепления.  
  
    -   `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    -   `AFX_DOCK_TYPE::DT_STANDARD`  
  
    -   `AFX_DOCK_TYPE::DT_SMART`  
  
     Эти режимы закрепления определены [CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md) и устанавливаются путем вызова [CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md).  
  
-   Если требуется создать, не являющихся перемещаемый, то можно изменять, не являющихся панели вызывает метод [CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md).  Этот метод регистрирует область с диспетчером закрепления, который отвечает за структуры области.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CDockingManager` для настройки объект `CDockingManager`.  Примере показано, как отобразить дополнительные кнопку, которая открывает всплывающее меню в заголовках всех панели закрепления и как задать режим закрепления объекта.  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/reference/codesnippet/CPP/cdockingmanager-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## Требования  
 **заголовок:** afxDockingManager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)