---
title: "CRectTracker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRectTracker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker class"
  - "displaying items"
  - "resizing items"
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRectTracker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет элементу, который необходимо отобразить, перемещенный и изменен размерный различными способами.  
  
## Синтаксис  
  
```  
  
class CRectTracker  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRectTracker::CRectTracker](../Topic/CRectTracker::CRectTracker.md)|Создает объект `CRectTracker`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRectTracker::AdjustRect](../Topic/CRectTracker::AdjustRect.md)|Если прямоугольник с именем размер.|  
|[CRectTracker::Draw](../Topic/CRectTracker::Draw.md)|Отрисовывает прямоугольник.|  
|[CRectTracker::DrawTrackerRect](../Topic/CRectTracker::DrawTrackerRect.md)|Вызываемый при рисовании граница объекта `CRectTracker`.|  
|[CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)|Вызываемый для получения маску маркеров изменения размера элемента `CRectTracker`.|  
|[CRectTracker::GetTrueRect](../Topic/CRectTracker::GetTrueRect.md)|Возвращает ширину и высоту прямоугольника, включая маркеры изменения размера.|  
|[CRectTracker::HitTest](../Topic/CRectTracker::HitTest.md)|Возвращает текущее положение курсора, связанного с объектом `CRectTracker`.|  
|[CRectTracker::NormalizeHit](../Topic/CRectTracker::NormalizeHit.md)|Нормализует код проверки нажатия.|  
|[CRectTracker::OnChangedRect](../Topic/CRectTracker::OnChangedRect.md)|Вызываемый, когда был размер или перемещение прямоугольника.|  
|[CRectTracker::SetCursor](../Topic/CRectTracker::SetCursor.md)|Устанавливает курсор, в зависимости от его позиции перед прямоугольником.|  
|[CRectTracker::Track](../Topic/CRectTracker::Track.md)|Позволяет пользователю управлять прямоугольник.|  
|[CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)|Позволяет пользователю "резин\- полосе" выделение.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CRectTracker::m\_nHandleSize](../Topic/CRectTracker::m_nHandleSize.md)|Определяет размер маркеров изменения размера.|  
|[CRectTracker::m\_nStyle](../Topic/CRectTracker::m_nStyle.md)|Текущие стили отслеживания.|  
|[CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)|Текущая позиция \(в точках\) прямоугольника.|  
|[CRectTracker::m\_sizeMin](../Topic/CRectTracker::m_sizeMin.md)|Указывает минимальную ширину и высоту прямоугольника.|  
  
## Заметки  
 `CRectTracker` не имеет базовый класс.  
  
 Хотя класс `CRectTracker` предназначен для разрешения пользователя для взаимодействия с элементами с помощью графического интерфейса OLE, его использование не ограничиватьа к OLE\- разрешить приложениям.  Ее можно использовать такое пользовательскому интерфейсу необходимости.  
  
 Границы `CRectTracker` могут быть тверды или пунктирная линия.  Элемент может быть присвоено насиженную границу или overlaid с насиженным шаблоном для отображения различных состояний элемента.  Можно задать 8 маркеров изменения размера либо на границе внешних или внутри элемента.  \(Описание маркеров изменения размера, см. в разделе [GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)\). Наконец, `CRectTracker` позволяет изменение ориентации элемента во время изменения размера.  
  
 Для использования `CRectTracker`, создайте объект `CRectTracker` и определите, какие состояния отображения инициализированы.  Затем можно использовать этот интерфейс для предоставления пользователю визуальную обратную связь о текущем состоянии OLE элемента, связанного с объектом `CRectTracker`.  
  
 Дополнительные сведения об использовании `CRectTracker` см. в статье [отслежыватели](../../mfc/trackers.md).  
  
## Иерархия наследования  
 `CRectTracker`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [MFC просматривает TRACKER](../../top/visual-cpp-samples.md)   
 [Образец DRAWCLI MFC](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleResizeBar Class](../../mfc/reference/coleresizebar-class.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)