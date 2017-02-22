---
title: "CPaneFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneFrameWnd.Serialize"
  - "CPaneFrameWnd.PreTranslateMessage"
  - "CPaneFrameWnd"
  - "CPaneFrameWnd::Serialize"
  - "PreTranslateMessage"
  - "CPaneFrameWnd::PreTranslateMessage"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneFrameWnd class"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Реализует окно минифрейма, которое содержит одну область.  Область заполняет собой клиентскую область окна.  
  
## Синтаксис  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## Участники  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)|Добавляет панель.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](../Topic/CPaneFrameWnd::AddRemovePaneFromGlobalList.md)|Добавляет панель в глобальный список или удаляет из него.|  
|[CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)|Настраивает макет окна области.|  
|[CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)||  
|[CPaneFrameWnd::CalcBorderSize](../Topic/CPaneFrameWnd::CalcBorderSize.md)|Вычисляет размер границ окна области.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)|Вычисляет ожидаемый прямоугольник закрепленного окна.|  
|[CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)|Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.|  
|[CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)|Определяет, может ли окно области быть закреплено на панели.|  
|[CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)|Преобразует панель в документ с вкладками.|  
|[CPaneFrameWnd::Create](../Topic/CPaneFrameWnd::Create.md)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|  
|[CPaneFrameWnd::CreateEx](../Topic/CPaneFrameWnd::CreateEx.md)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|  
|[CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)|Закрепляет область.|  
|[CPaneFrameWnd::FindFloatingPaneByID](../Topic/CPaneFrameWnd::FindFloatingPaneByID.md)|Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.|  
|[CPaneFrameWnd::FrameFromPoint](../Topic/CPaneFrameWnd::FrameFromPoint.md)|Находит окно области, содержащее предоставленную пользователем точку.|  
|[CPaneFrameWnd::GetCaptionHeight](../Topic/CPaneFrameWnd::GetCaptionHeight.md)|Возвращает высоту заголовка окна области.|  
|[CPaneFrameWnd::GetCaptionRect](../Topic/CPaneFrameWnd::GetCaptionRect.md)|Вычисляет ограничивающий прямоугольник заголовка окна области.|  
|[CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)|Возвращает текст заголовка.|  
|[CPaneFrameWnd::GetDockingManager](../Topic/CPaneFrameWnd::GetDockingManager.md)||  
|[CPaneFrameWnd::GetDockingMode](../Topic/CPaneFrameWnd::GetDockingMode.md)|Возвращает режим закрепления.|  
|[CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)|Возвращает первую видимую панель, содержащуюся в окне области.|  
|[CPaneFrameWnd::GetHotPoint](../Topic/CPaneFrameWnd::GetHotPoint.md)||  
|[CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)|Возвращает панель, содержащуюся в окне области.|  
|[CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)|Возвращает число панелей, содержащихся в окне области.|  
|[CPaneFrameWnd::GetParent](../Topic/CPaneFrameWnd::GetParent.md)||  
|[CPaneFrameWnd::GetPinState](../Topic/CPaneFrameWnd::GetPinState.md)||  
|[CPaneFrameWnd::GetRecentFloatingRect](../Topic/CPaneFrameWnd::GetRecentFloatingRect.md)||  
|[CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)|Возвращает число видимых панелей, содержащихся в окне области.|  
|[CPaneFrameWnd::HitTest](../Topic/CPaneFrameWnd::HitTest.md)|Определяет, какая часть окна области находится в заданной точке.|  
|[CPaneFrameWnd::IsCaptured](../Topic/CPaneFrameWnd::IsCaptured.md)||  
|[CPaneFrameWnd::IsDelayShow](../Topic/CPaneFrameWnd::IsDelayShow.md)||  
|[CPaneFrameWnd::IsRollDown](../Topic/CPaneFrameWnd::IsRollDown.md)|Определяет, требуется ли развертывание окна области.|  
|[CPaneFrameWnd::IsRollUp](../Topic/CPaneFrameWnd::IsRollUp.md)|Определяет, требуется ли свертывание окна области.|  
|[CPaneFrameWnd::KillDockingTimer](../Topic/CPaneFrameWnd::KillDockingTimer.md)|Останавливает таймер закрепления.|  
|[CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)|Загружает состояние панели из реестра.|  
|[CPaneFrameWnd::OnBeforeDock](../Topic/CPaneFrameWnd::OnBeforeDock.md)|Определяет возможность закрепления.|  
|[CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)|Закрепляет окно области в его последней позиции.|  
|[CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)|Останавливает таймер свертки.|  
|[CPaneFrameWnd::OnMovePane](../Topic/CPaneFrameWnd::OnMovePane.md)|Смещает окно области на указанное расстояние.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)|Настраивает макет содержащейся панели.|  
|[CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)|Устанавливает таймер свертки.|  
|[CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)|Вызывается платформой при скрытии или отображении панели в окне области.|  
|[CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)|Возвращает панель, если она содержит предоставленную пользователем точку в пределах окна области.|  
|[CPaneFrameWnd::Pin](../Topic/CPaneFrameWnd::Pin.md)||  
|`CPaneFrameWnd::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CPaneFrameWnd::RedrawAll](../Topic/CPaneFrameWnd::RedrawAll.md)|Перерисовывает все окна областей.|  
|[CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)|Вызывается платформой для удаления недопустимых панелей.|  
|[CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)|Удаляет панель из окна области.|  
|[CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)|Заменяет одну панель другой.|  
|[CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)|Сохраняет состояние панели в реестр.|  
|`CPaneFrameWnd::Serialize`|Считывает этот объект из архива или записывает в него.|  
|[CPaneFrameWnd::SetCaptionButtons](../Topic/CPaneFrameWnd::SetCaptionButtons.md)|Задает кнопки заголовка.|  
|[CPaneFrameWnd::SetDelayShow](../Topic/CPaneFrameWnd::SetDelayShow.md)||  
|[CPaneFrameWnd::SetDockingManager](../Topic/CPaneFrameWnd::SetDockingManager.md)||  
|[CPaneFrameWnd::SetDockingTimer](../Topic/CPaneFrameWnd::SetDockingTimer.md)|Устанавливает таймер закрепления.|  
|[CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)|Задает состояние закрепления.|  
|[CPaneFrameWnd::SetHotPoint](../Topic/CPaneFrameWnd::SetHotPoint.md)||  
|[CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)|Вызывается платформой для задания предварительного состояния закрепления.|  
|[CPaneFrameWnd::SizeToContent](../Topic/CPaneFrameWnd::SizeToContent.md)|Делает размер окна области равным размеру содержащейся в нем панели.|  
|[CPaneFrameWnd::StartTearOff](../Topic/CPaneFrameWnd::StartTearOff.md)|Делает меню перемещаемым.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)||  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaneFrameWnd::OnCheckRollState](../Topic/CPaneFrameWnd::OnCheckRollState.md)|Определяет, требуется ли свертывание или развертывание окна области.|  
|[CPaneFrameWnd::OnDrawBorder](../Topic/CPaneFrameWnd::OnDrawBorder.md)|Рисует границы окна области.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaneFrameWnd::m\_bUseSaveBits](../Topic/CPaneFrameWnd::m_bUseSaveBits.md)|Указывает, требуется ли регистрация класса окна со стилем класса `CS_SAVEBITS`.|  
  
## Заметки  
 Когда панель переходит из закрепленного состояния в плавающее, платформа автоматически создает объект `CPaneFrameWnd`.  
  
 Окно области можно перетащить вместе с его видимым содержимым \(немедленное закрепление\) или с помощью прямоугольника перетаскивания \(стандартное закрепление\).  Режим закрепления панели контейнера окна области определяет поведение окна области при перетаскивании.  Дополнительные сведения см. в разделе [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md).  
  
 В заголовке окна области отображаются кнопки, зависящие от стиля включенной панели.  Если панель можно закрыть \([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\), на ней отображается кнопка закрытия.  Если для панели используется стиль `AFX_CBRS_AUTO_ROLLUP`, отображается кнопка закрепления.  
  
 Если вы получаете производный класс из класса `CPaneFrameWnd`, необходимо сообщить платформе способ его создания.  Вы можете создать класс, переопределив метод [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md), или настроив член `CPane::m_pMiniFrameRTC` так, чтобы он указывал на сведения о классе среды выполнения для вашего класса.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
## Требования  
 **Заголовок:** afxPaneFrameWnd.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)