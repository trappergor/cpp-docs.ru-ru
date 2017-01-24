---
title: "Класс CBaseTabbedPane | Microsoft Docs"
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
  - "CBaseTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CBaseTabbedPane"
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CBaseTabbedPane
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Расширяет функцию [CDockablePane Class](../Topic/CDockablePane%20Class.md) для создания предварительного окон.  
  
## Синтаксис  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)|Добавляет новую вкладку на нашитой области.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)|Определяет, является ли нашитую пустую область можно удалить.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](../Topic/CBaseTabbedPane::ApplyRestoredTabInfo.md)|Применяет параметры табуляции, загруженные из реестра, в нашитой области.|  
|[CBaseTabbedPane::CanFloat](../Topic/CBaseTabbedPane::CanFloat.md)|Определяет, является ли область может плыть.  Переопределения \( [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)\).|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)|Указывает, должен ли заголовок для нашитой области отображать один и тот же текст, как активная вкладку.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](../Topic/CBaseTabbedPane::ConvertToTabbedDocument.md)|Переопределения \( [CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md)\).|  
|[CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)|Преобразует один или несколько закрепляемых области к MDI нашил документы.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](../Topic/CBaseTabbedPane::EnableSetCaptionTextToTabName.md)|Включает или нашитой области отключит возможность синхронизировать подписи с текстом меток на активной вкладке.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](../Topic/CBaseTabbedPane::FillDefaultTabsOrderArray.md)|Восстановление внутренняя последовательность табуляции в состояние по умолчанию.|  
|[CBaseTabbedPane::FindBarByTabNumber](../Topic/CBaseTabbedPane::FindBarByTabNumber.md)|Возвращает область, которая хранится на вкладке, если вкладка определяется отсчитываемый от нуля индекс вкладки.|  
|||  
|[CBaseTabbedPane::FindPaneByID](../Topic/CBaseTabbedPane::FindPaneByID.md)|Возвращает область, определенная идентификатором области|  
|[CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)|Будет плавающим область, но только если область в данный момент находится в отделяемой вкладке.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](../Topic/CBaseTabbedPane::GetDefaultTabsOrder.md)|Возвращает порядок по умолчанию вкладок в области.|  
|[CBaseTabbedPane::GetFirstVisibleTab](../Topic/CBaseTabbedPane::GetFirstVisibleTab.md)|Извлекает указатель на первом, отображаемого на вкладке.|  
|[CBaseTabbedPane::GetMinSize](../Topic/CBaseTabbedPane::GetMinSize.md)|Возвращает минимальный допустимый размер рабочей области.  Переопределения \( [CPane::GetMinSize](../Topic/CPane::GetMinSize.md)\).|  
|[CBaseTabbedPane::GetPaneIcon](../Topic/CBaseTabbedPane::GetPaneIcon.md)|Возвращает дескриптор значок области.  Переопределения \( [CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)\).|  
|[CBaseTabbedPane::GetPaneList](../Topic/CBaseTabbedPane::GetPaneList.md)|Возвращает список областей, в которых содержатся будут отображены в области с вкладками.|  
|[CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)|Возвращает ограничивающие прямоугольники для верхних и нижних областей вкладки.|  
|[CBaseTabbedPane::GetTabsNum](../Topic/CBaseTabbedPane::GetTabsNum.md)|Возвращает количество вкладок в окне вкладки.|  
|[CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md)|Получает основному \(создается программу\-оболочку\) окно вкладки.|  
|[CBaseTabbedPane::GetVisibleTabsNum](../Topic/CBaseTabbedPane::GetVisibleTabsNum.md)|Возвращает количество отображаемых вкладок.|  
|[CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)|Определяет, является ли нашитую область можно переключиться в режим автоматического скрытия.|  
|[CBaseTabbedPane::IsHideSingleTab](../Topic/CBaseTabbedPane::IsHideSingleTab.md)|Определяет область нашитая скрыта, если только одна вкладка.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется внутренне во время сериализации.|  
|[CBaseTabbedPane::RecalcLayout](../Topic/CBaseTabbedPane::RecalcLayout.md)|Выполняет перерасчет данные макета для области.  Переопределения \( [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)\).|  
|[CBaseTabbedPane::RemovePane](../Topic/CBaseTabbedPane::RemovePane.md)|Удаляет область из нашитой области.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется внутренне во время сериализации.|  
|`CBaseTabbedPane::Serialize`|Переопределения \( [CDockablePane::Serialize](http://msdn.microsoft.com/ru-ru/09787e59-e446-4e76-894b-206d303dcfd6)\).|  
|`CBaseTabbedPane::SerializeTabWindow`|Используется внутренне во время сериализации.|  
|[CBaseTabbedPane::SetAutoDestroy](../Topic/CBaseTabbedPane::SetAutoDestroy.md)|Указывает, будет ли разрушена нашитая панель элементов управления автоматически.|  
|[CBaseTabbedPane::SetAutoHideMode](../Topic/CBaseTabbedPane::SetAutoHideMode.md)|Переключение между режимами отображения области закрепления и скрытием автоматически.  Переопределения \( [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)\).|  
|[CBaseTabbedPane::ShowTab](../Topic/CBaseTabbedPane::ShowTab.md)|Показывает или скрывает вкладки.|  
  
## Заметки  
 Этот класс является абстрактным классом и не может быть создан экземпляр.  Реализует службы, общие для всех типов предварительного областей.  
  
 В настоящее время, библиотека содержит 2 предварительного производных класса области: [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) и [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Объект `CBaseTabbedPane` создается указатель на объект [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md).  [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) будет дочерним окном нашитой области.  
  
 Дополнительные сведения о создании нашитые области см. в разделах [CDockablePane Class](../Topic/CDockablePane%20Class.md), [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) и [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
## Требования  
 **Заголовок:** afxBaseTabbedPane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)