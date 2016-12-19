---
title: "CPaneContainerManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneContainerManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneContainerManager class"
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneContainerManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CPaneContainerManager` управляет хранением и отображение текущей структуры закрепления.  
  
## Синтаксис  
  
```  
class CPaneContainerManager : public CObject  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaneContainerManager::AddPane](../Topic/CPaneContainerManager::AddPane.md)||  
|[CPaneContainerManager::AddPaneContainerManager](../Topic/CPaneContainerManager::AddPaneContainerManager.md)||  
|[CPaneContainerManager::AddPaneContainerManagerToDockablePane](../Topic/CPaneContainerManager::AddPaneContainerManagerToDockablePane.md)||  
|[CPaneContainerManager::AddPanesToList](../Topic/CPaneContainerManager::AddPanesToList.md)||  
|[CPaneContainerManager::AddPaneToList](../Topic/CPaneContainerManager::AddPaneToList.md)||  
|[CPaneContainerManager::AddPaneToRecentPaneContainer](../Topic/CPaneContainerManager::AddPaneToRecentPaneContainer.md)||  
|[CPaneContainerManager::CalcRects](../Topic/CPaneContainerManager::CalcRects.md)||  
|[CPaneContainerManager::CanBeAttached](../Topic/CPaneContainerManager::CanBeAttached.md)||  
|[CPaneContainerManager::CheckAndRemoveNonValidPane](../Topic/CPaneContainerManager::CheckAndRemoveNonValidPane.md)||  
|[CPaneContainerManager::CheckForMiniFrameAndCaption](../Topic/CPaneContainerManager::CheckForMiniFrameAndCaption.md)||  
|[CPaneContainerManager::Create](../Topic/CPaneContainerManager::Create.md)||  
|[CPaneContainerManager::DoesAllowDynInsertBefore](../Topic/CPaneContainerManager::DoesAllowDynInsertBefore.md)||  
|[CPaneContainerManager::DoesContainFloatingPane](../Topic/CPaneContainerManager::DoesContainFloatingPane.md)||  
|[CPaneContainerManager::EnableGrippers](../Topic/CPaneContainerManager::EnableGrippers.md)||  
|[CPaneContainerManager::FindPaneContainer](../Topic/CPaneContainerManager::FindPaneContainer.md)||  
|[CPaneContainerManager::FindTabbedPane](../Topic/CPaneContainerManager::FindTabbedPane.md)||  
|[CPaneContainerManager::GetAvailableSpace](../Topic/CPaneContainerManager::GetAvailableSpace.md)||  
|[CPaneContainerManager::GetDefaultPaneDivider](../Topic/CPaneContainerManager::GetDefaultPaneDivider.md)||  
|[CPaneContainerManager::GetDockSiteFrameWnd](../Topic/CPaneContainerManager::GetDockSiteFrameWnd.md)||  
|[CPaneContainerManager::GetFirstPane](../Topic/CPaneContainerManager::GetFirstPane.md)||  
|[CPaneContainerManager::GetFirstVisiblePane](../Topic/CPaneContainerManager::GetFirstVisiblePane.md)||  
|[CPaneContainerManager::GetMinMaxOffset](../Topic/CPaneContainerManager::GetMinMaxOffset.md)||  
|[CPaneContainerManager::GetMinSize](../Topic/CPaneContainerManager::GetMinSize.md)||  
|[CPaneContainerManager::GetNodeCount](../Topic/CPaneContainerManager::GetNodeCount.md)||  
|[CPaneContainerManager::GetPaneContainerRTC](../Topic/CPaneContainerManager::GetPaneContainerRTC.md)||  
|[CPaneContainerManager::GetPaneCount](../Topic/CPaneContainerManager::GetPaneCount.md)||  
|[CPaneContainerManager::GetTotalRefCount](../Topic/CPaneContainerManager::GetTotalRefCount.md)||  
|[CPaneContainerManager::GetVisiblePaneCount](../Topic/CPaneContainerManager::GetVisiblePaneCount.md)||  
|[CPaneContainerManager::GetWindowRect](../Topic/CPaneContainerManager::GetWindowRect.md)||  
|[CPaneContainerManager::HideAll](../Topic/CPaneContainerManager::HideAll.md)||  
|[CPaneContainerManager::InsertPane](../Topic/CPaneContainerManager::InsertPane.md)||  
|[CPaneContainerManager::IsAutoHideMode](../Topic/CPaneContainerManager::IsAutoHideMode.md)||  
|[CPaneContainerManager::IsEmpty](../Topic/CPaneContainerManager::IsEmpty.md)||  
|[CPaneContainerManager::IsRootPaneContainerVisible](../Topic/CPaneContainerManager::IsRootPaneContainerVisible.md)||  
|[CPaneContainerManager::NotifyPaneDivider](../Topic/CPaneContainerManager::NotifyPaneDivider.md)||  
|[CPaneContainerManager::OnPaneDividerMove](../Topic/CPaneContainerManager::OnPaneDividerMove.md)||  
|[CPaneContainerManager::OnShowPane](../Topic/CPaneContainerManager::OnShowPane.md)||  
|[CPaneContainerManager::PaneFromPoint](../Topic/CPaneContainerManager::PaneFromPoint.md)||  
|[CPaneContainerManager::ReleaseEmptyPaneContainers](../Topic/CPaneContainerManager::ReleaseEmptyPaneContainers.md)||  
|[CPaneContainerManager::RemoveAllPanesAndPaneDividers](../Topic/CPaneContainerManager::RemoveAllPanesAndPaneDividers.md)||  
|[CPaneContainerManager::RemoveNonValidPanes](../Topic/CPaneContainerManager::RemoveNonValidPanes.md)||  
|[CPaneContainerManager::RemovePaneDivider](../Topic/CPaneContainerManager::RemovePaneDivider.md)||  
|[CPaneContainerManager::RemovePaneFromPaneContainer](../Topic/CPaneContainerManager::RemovePaneFromPaneContainer.md)||  
|[CPaneContainerManager::ReplacePane](../Topic/CPaneContainerManager::ReplacePane.md)||  
|[CPaneContainerManager::ResizePaneContainers](../Topic/CPaneContainerManager::ResizePaneContainers.md)||  
|[CPaneContainerManager::Serialize](../Topic/CPaneContainerManager::Serialize.md)|Считывает или записывает данный объект или архива.  \(Переопределяет [CObject::Serialize](../Topic/CObject::Serialize.md)\).|  
|[CPaneContainerManager::SetDefaultPaneDividerForPanes](../Topic/CPaneContainerManager::SetDefaultPaneDividerForPanes.md)||  
|[CPaneContainerManager::SetPaneContainerRTC](../Topic/CPaneContainerManager::SetPaneContainerRTC.md)||  
|[CPaneContainerManager::SetResizeMode](../Topic/CPaneContainerManager::SetResizeMode.md)||  
|[CPaneContainerManager::StoreRecentDockSiteInfo](../Topic/CPaneContainerManager::StoreRecentDockSiteInfo.md)||  
  
### Заметки  
 Платформа автоматически создают экземпляры объектов и их `CPaneContainerManager` внедряют или в объекты [CPaneDivider Class](../../mfc/reference/cpanedivider-class.md) или в объекты [CMultiPaneFrameWnd Class](../../mfc/reference/cmultipaneframewnd-class.md).  
  
 Класс `CPaneContainerManager` сохраняет указатель к корневому каталогу бинарный дерева, строится из объектов [CPaneContainer](../../mfc/reference/cpanecontainer-class.md).  
  
## Пример  
 В следующем примере показано, как получить ссылку на объект `CPaneContainerManager`.  Этот фрагмент кода является частью [Задайте размер панели образца](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#5](../../mfc/reference/codesnippet/CPP/cpanecontainermanager-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)  
  
## Требования  
 **заголовок:** afxpanecontainermanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)   
 [CPaneDivider Class](../../mfc/reference/cpanedivider-class.md)