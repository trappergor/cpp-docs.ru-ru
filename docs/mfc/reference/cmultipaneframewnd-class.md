---
title: "CMultiPaneFrameWnd Class | Microsoft Docs"
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
  - "CMultiPaneFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPaneFrameWnd class"
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMultiPaneFrameWnd` расширяет [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  Он может поддерживать несколько панелей.  Вместо отдельного внедренного маркера на панель элементов управления, `CMultiPaneFrameWnd` содержит объект, который позволяет пользователю закрепление одно `CMultiPaneFrameWnd` в другую и динамически создать несколько перемещаемый окна со вкладками, [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md).  
  
## Синтаксис  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMultiPaneFrameWnd::AddPane](../Topic/CMultiPaneFrameWnd::AddPane.md)|Добавляет панель.  \(Переопределяет [CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)\).|  
|[CMultiPaneFrameWnd::AddRecentPane](../Topic/CMultiPaneFrameWnd::AddRecentPane.md)||  
|[CMultiPaneFrameWnd::AdjustLayout](../Topic/CMultiPaneFrameWnd::AdjustLayout.md)|Обрабатывает макет окна области.  \(Переопределяет [CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)\).|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](../Topic/CMultiPaneFrameWnd::AdjustPaneFrames.md)|\(Переопределяет [CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)\).|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](../Topic/CMultiPaneFrameWnd::CalcExpectedDockedRect.md)|Вычисляет ожидаемый прямоугольник состыкованного окна.  \(Переопределяет [CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)\).|  
|[CMultiPaneFrameWnd::CanBeAttached](../Topic/CMultiPaneFrameWnd::CanBeAttached.md)|Определяет, является ли текущая область может закрепляться в другой области или фреймовому окно.  \(Переопределяет [CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)\).|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](../Topic/CMultiPaneFrameWnd::CanBeDockedToPane.md)|Определяет, является ли окно области может закрепляться в области.  \(Переопределяет [CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)\).|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](../Topic/CMultiPaneFrameWnd::CheckGripperVisibility.md)|\(Переопределяет [CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)\).|  
|[CMultiPaneFrameWnd::CloseMiniFrame](../Topic/CMultiPaneFrameWnd::CloseMiniFrame.md)|\(Переопределяет `CPaneFrameWnd::CloseMiniFrame`\).|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](../Topic/CMultiPaneFrameWnd::ConvertToTabbedDocument.md)|Преобразование панели в нашитому документ.  \(Переопределяет [CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)\).|  
|[CMultiPaneFrameWnd::DockFrame](../Topic/CMultiPaneFrameWnd::DockFrame.md)||  
|[CMultiPaneFrameWnd::DockPane](../Topic/CMultiPaneFrameWnd::DockPane.md)|Закрепит панель.  \(Переопределяет [CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)\).|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](../Topic/CMultiPaneFrameWnd::DockRecentPaneToMainFrame.md)||  
|[CMultiPaneFrameWnd::GetCaptionText](../Topic/CMultiPaneFrameWnd::GetCaptionText.md)|Возвращает текст заголовка.  \(Переопределяет [CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)\).|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](../Topic/CMultiPaneFrameWnd::GetPaneContainerManager.md)|Возвращает ссылку на внутренний объект диспетчера контейнера.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](../Topic/CMultiPaneFrameWnd::GetFirstVisiblePane.md)|Возвращает первую видимую область, которая содержится в окне области.  \(Переопределяет [CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)\).|  
|[CMultiPaneFrameWnd::GetPane](../Topic/CMultiPaneFrameWnd::GetPane.md)|Возвращает панель, которая содержится в окне области.  \(Переопределяет [CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)\).|  
|[CMultiPaneFrameWnd::GetPaneCount](../Topic/CMultiPaneFrameWnd::GetPaneCount.md)|Возвращает количество областей, содержащихся в окне области.  \(Переопределяет [CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)\).|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](../Topic/CMultiPaneFrameWnd::GetVisiblePaneCount.md)|Возвращает количество видимых панелей, содержащиеся в окне области.  \(Переопределяет [CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)\).|  
|[CMultiPaneFrameWnd::InsertPane](../Topic/CMultiPaneFrameWnd::InsertPane.md)||  
|[CMultiPaneFrameWnd::LoadState](../Topic/CMultiPaneFrameWnd::LoadState.md)|Загружает состояние области из реестра.  \(Переопределяет [CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)\).|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](../Topic/CMultiPaneFrameWnd::OnDockToRecentPos.md)|Закрепит окно области в своей самой последней позиции.  \(Переопределяет [CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)\).|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](../Topic/CMultiPaneFrameWnd::OnKillRollUpTimer.md)|Останавливает таймер свертки.  \(Переопределяет [CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)\).|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](../Topic/CMultiPaneFrameWnd::OnPaneRecalcLayout.md)|Обрабатывает структуру области внутри окна области.  \(Переопределяет [CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)\).|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](../Topic/CMultiPaneFrameWnd::OnSetRollUpTimer.md)|Устанавливает таймер свертки.  \(Переопределяет [CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)\).|  
|[CMultiPaneFrameWnd::OnShowPane](../Topic/CMultiPaneFrameWnd::OnShowPane.md)|Вызываемый платформой, когда будет скрыта или будет отображаться область в окне области.  \(Переопределяет [CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)\).|  
|[CMultiPaneFrameWnd::PaneFromPoint](../Topic/CMultiPaneFrameWnd::PaneFromPoint.md)|Возвращает панель, если она содержит пользователь\- предоставленный точка внутри окна области.  \(Переопределяет [CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)\).|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](../Topic/CMultiPaneFrameWnd::RemoveNonValidPanes.md)|Вызываемый платформой для удаления области не является допустимым.  \(Переопределяет [CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)\).|  
|[CMultiPaneFrameWnd::RemovePane](../Topic/CMultiPaneFrameWnd::RemovePane.md)|Удаляет из области панель окна.  \(Переопределяет [CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)\).|  
|[CMultiPaneFrameWnd::ReplacePane](../Topic/CMultiPaneFrameWnd::ReplacePane.md)|Заменяет одну панель с другими.  \(Переопределяет [CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)\).|  
|[CMultiPaneFrameWnd::SaveState](../Topic/CMultiPaneFrameWnd::SaveState.md)|Сохраняет состояние области в реестр.  \(Переопределяет [CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)\).|  
|[CMultiPaneFrameWnd::Serialize](../Topic/CMultiPaneFrameWnd::Serialize.md)|\(Переопределяет `CPaneFrameWnd::Serialize`\).|  
|[CMultiPaneFrameWnd::SetDockState](../Topic/CMultiPaneFrameWnd::SetDockState.md)|Устанавливает для состояния закрепления.  \(Переопределяет [CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)\).|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](../Topic/CMultiPaneFrameWnd::SetLastFocusedPane.md)||  
|[CMultiPaneFrameWnd::SetPreDockState](../Topic/CMultiPaneFrameWnd::SetPreDockState.md)|Задает predocking состояние.  \(Переопределяет [CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)\).|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CMultiPaneFrameWnd::StoreRecentDockSiteInfo.md)|\(Переопределяет [CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)\).|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo.md)|\(Переопределяет [CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)\).|  
  
## Заметки  
 Большинство методов в методах этого переопределения класса в классе [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  
  
 Если панель `AFX_CBRS_AUTO_ROLLUP` и используется стиль закрепления, то пользователя, к фреймовому окно панель multi\- панели, пользователь может сведения окно независимо от параметров стиля других состыкованных панелей.  
  
 Платформа автоматически создают объект `CMultiPaneFrameWnd`, когда пользователь располагается панель, которая используется стиль `CBRS_FLOAT_MULTI`.  
  
 Дополнительные сведения о `CPaneFrameWnd` создания производного класса от класса и создание его динамически см. в разделе [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## Пример  
 В следующем примере показано, как получить указатель на объект `CMultiPaneFrameWnd`.  Этот фрагмент кода является частью [Задайте размер панели образца](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/CPP/cmultipaneframewnd-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## Требования  
 **заголовок:** afxMultiPaneFrameWnd.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)