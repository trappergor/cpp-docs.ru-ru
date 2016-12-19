---
title: "CPane Class | Microsoft Docs"
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
  - "CPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPane class"
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CPane` улучшение [CControlBar Class](../../mfc/reference/ccontrolbar-class.md).  При обновлении существующего проекта MFC, замените все вхождения `CControlBar` с `CPane`.  
  
## Синтаксис  
  
```  
class CPane : public CBasePane  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CPane::~CPane`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)|Немедленно повторно вычисляет макет панели.|  
|[CPane::AllocElements](../Topic/CPane::AllocElements.md)|Выбирает хранилище для внутреннего использования.|  
|[CPane::AllowShowOnPaneMenu](../Topic/CPane::AllowShowOnPaneMenu.md)|Определяет, является ли панель перечислитьа в списке создаваемые средой выполнения\- панелей для приложения.|  
|[CPane::CalcAvailableSize](../Topic/CPane::CalcAvailableSize.md)|Вычисляет различия в размерах между указанным прямоугольником и текущим прямоугольником окна.|  
|[CPane::CalcInsideRect](../Topic/CPane::CalcInsideRect.md)|Вычисляет внутренний прямоугольника области учитывающ границы и захваты.|  
|[CPane::CalcRecentDockedRect](../Topic/CPane::CalcRecentDockedRect.md)|Вычисляет недавно закрепленного прямоугольник.|  
|[CPane::CalcSize](../Topic/CPane::CalcSize.md)|Вычисляет размер панели.|  
|[CPane::CanBeDocked](../Topic/CPane::CanBeDocked.md)|Определяет, является ли панель можно закрепить в заданной базовой области.|  
|[CPane::CanBeTabbedDocument](../Topic/CPane::CanBeTabbedDocument.md)|Определяет, является ли панель можно преобразовать в нашитому документ.|  
|[CPane::ConvertToTabbedDocument](../Topic/CPane::ConvertToTabbedDocument.md)|Преобразование закрепляемая область в нашитому документ.|  
|[CPane::CopyState](../Topic/CPane::CopyState.md)|Копирует состояние области.  \(Переопределяет [CBasePane::CopyState](../Topic/CBasePane::CopyState.md)\).|  
|[CPane::Create](../Topic/CPane::Create.md)|Создает вложение панель элементов управления и его к объекту `CPane`.|  
|[CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)|Создает плавающее окно область для области.|  
|[CPane::CreateEx](../Topic/CPane::CreateEx.md)|Создает вложение панель элементов управления и его к объекту `CPane`.|  
|`CPane::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CPane::DockByMouse](../Topic/CPane::DockByMouse.md)|Закрепит панель с помощью метода закрепления мыши.|  
|[CPane::DockPane](../Topic/CPane::DockPane.md)|Закрепит панель запрещены для базовой области.|  
|[CPane::DockPaneStandard](../Topic/CPane::DockPaneStandard.md)|Закрепит панель с помощью закрепления структуры \(стандартной\).|  
|[CPane::DockToFrameWindow](../Topic/CPane::DockToFrameWindow.md)|Закрепит закрепляемая панель к кадру.  \(Переопределяет `CBasePane::DockToFrameWindow`\).|  
|[CPane::DoesAllowSiblingBars](../Topic/CPane::DoesAllowSiblingBars.md)|Указывает, можно ли закрепление другую панель, на одной и той же строке, в котором текущая область закреплена.|  
|[CPane::FloatPane](../Topic/CPane::FloatPane.md)|Область располагается.|  
|[CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)|Возвращает размер в пикселях, панель может развернуть.|  
|[CPane::GetAvailableStretchSize](../Topic/CPane::GetAvailableStretchSize.md)|Возвращает размер в пикселях, панель может сжать.|  
|[CPane::GetBorders](../Topic/CPane::GetBorders.md)|Возвращает ширину границ панели.|  
|[CPane::GetClientHotSpot](../Topic/CPane::GetClientHotSpot.md)|Возвращает *гиперзону* для панели.|  
|[CPane::GetDockSiteRow](../Topic/CPane::GetDockSiteRow.md)|Возвращает строку, в которой панели закрепления закреплена.|  
|[CPane::GetExclusiveRowMode](../Topic/CPane::GetExclusiveRowMode.md)|Определяет, является ли область в монопольном режиме строки.|  
|[CPane::GetHotSpot](../Topic/CPane::GetHotSpot.md)|Возвращает гиперзону, которое хранится в базовом объекте `CMFCDragFrameImpl`.|  
|[CPane::GetMinSize](../Topic/CPane::GetMinSize.md)|Получает минимально допустимый размер для области.|  
|[CPane::GetPaneName](../Topic/CPane::GetPaneName.md)|Получает название для панели.|  
|`CPane::GetResizeStep`|Для внутреннего использования.|  
|`CPane::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CPane::GetVirtualRect](../Topic/CPane::GetVirtualRect.md)|Получает *виртуальный прямоугольник* панели.|  
|[CPane::IsChangeState](../Topic/CPane::IsChangeState.md)|По мере того, как панель переместить, этот метод выполняет синтаксический анализ положение панели задается относительно другую панель, закрепит строки и окна области и передачи соответствующего значения `AFX_CS_STATUS`.|  
|[CPane::IsDragMode](../Topic/CPane::IsDragMode.md)|Определяет, является ли область перетаскивание.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](../Topic/CPane::IsInFloatingMultiPaneFrameWnd.md)|Определяет, является ли область фреймовом окне multi\- панели.  \(Переопределяет `CBasePane::IsInFloatingMultiPaneFrameWnd`\).|  
|[CPane::IsLeftOf](../Topic/CPane::IsLeftOf.md)|Определяет, является ли панель оставлена \(или выше\) заданного прямоугольника.|  
|[CPane::IsResizable](../Topic/CPane::IsResizable.md)|Определяет, является ли панель можно изменить размер.  \(Переопределяет [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)\).|  
|[CPane::IsTabbed](../Topic/CPane::IsTabbed.md)|Определяет, была ли вставлена в набор нашитого панель вкладок окна.  \(Переопределяет [CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)\).|  
|[CPane::LoadState](../Topic/CPane::LoadState.md)|Загружает состояние области из реестра.  \(Переопределяет [CBasePane::LoadState](../Topic/CBasePane::LoadState.md)\).|  
|[CPane::MoveByAlignment](../Topic/CPane::MoveByAlignment.md)|Перемещает панель и виртуальный прямоугольник на указанную величину.|  
|[CPane::MovePane](../Topic/CPane::MovePane.md)|Перемещает панель к заданному прямоугольнику.|  
|[CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md)|Вызываемый платформой, если родительский панели изменяется.|  
|[CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md)|Вызываемый платформой, если родительский панели изменением.|  
|[CPane::OnPressCloseButton](../Topic/CPane::OnPressCloseButton.md)|Вызываемый платформой, когда пользователь выбирает кнопку Закрыть на панели заголовка.|  
|`CPane::OnProcessDblClk`|Для внутреннего использования.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Вызываемый платформой, когда специальные меню панели будет отображаться.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|Вызываемый платформой, когда специальные меню панели будет отображаться.|  
|`CPane::PrepareToDock`|Для внутреннего использования.|  
|[CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)|Повторно вычисляет сведения о макете для панели.  \(Переопределяет [CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)\).|  
|[CPane::SaveState](../Topic/CPane::SaveState.md)|Сохраняет состояние области в реестр.  \(Переопределяет [CBasePane::SaveState](../Topic/CBasePane::SaveState.md)\).|  
|[CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md)|Пометит панель как активные.|  
|[CPane::SetBorders](../Topic/CPane::SetBorders.md)|Задает значения границ панели.|  
|[CPane::SetClientHotSpot](../Topic/CPane::SetClientHotSpot.md)|Устанавливает гиперзону для панели.|  
|[CPane::SetDockState](../Topic/CPane::SetDockState.md)|Закрепляющий сведения о состоянии восстановления для панели.|  
|[CPane::SetExclusiveRowMode](../Topic/CPane::SetExclusiveRowMode.md)|Включение или отключение монопольный режим строки.|  
|[CPane::SetMiniFrameRTC](../Topic/CPane::SetMiniFrameRTC.md)|Устанавливает данные времени выполнения класса по умолчанию для окна области.|  
|[CPane::SetMinSize](../Topic/CPane::SetMinSize.md)|Задает минимально допустимый размер для области.|  
|[CPane::SetVirtualRect](../Topic/CPane::SetVirtualRect.md)|Задает *виртуальный прямоугольник* панели.|  
|[CPane::StretchPaneDeferWndPos](../Topic/CPane::StretchPaneDeferWndPos.md)|Панель растянет вертикально или горизонтально на основе стиль закрепления.|  
|[CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md)|Переключает режим автоматического скрытия.|  
|[CPane::UndockPane](../Topic/CPane::UndockPane.md)|Удаляет панели закрепления из сайта по умолчанию ползунка или окна области, где его в настоящий момент закрепить.  \(Переопределяет [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)\).|  
|[CPane::UpdateVirtualRect](../Topic/CPane::UpdateVirtualRect.md)|Обновляет виртуальный прямоугольник.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPane::OnAfterDock](../Topic/CPane::OnAfterDock.md)|Если панель с границами будет закреплена.|  
|[CPane::OnAfterFloat](../Topic/CPane::OnAfterFloat.md)|Если панель с границами будет плавающая.|  
|[CPane::OnBeforeDock](../Topic/CPane::OnBeforeDock.md)|Если панель с границами намерении закрепленным.|  
|[CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)|Если панель с границами должен быть плытым.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPane::m\_bHandleMinSize](../Topic/CPane::m_bHandleMinSize.md)|Включает последовательное обработка минимального размера панелей.|  
|[CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)|Содержит последние данные закрепления.|  
  
## Заметки  
 Как правило, объекты `CPane` создается непосредственно.  Если требуется области, которая содержит функции закрепления, создайте объект из [CDockablePane](../Topic/CDockablePane%20Class.md).  Если требуется функциональность панели инструментов, он должен быть производным от объекта [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 При наследовании от класса `CPane`, его можно закрепить в [CDockSite](../../mfc/reference/cdocksite-class.md) и его можно плыть в [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## Требования  
 **заголовок:** afxPane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)