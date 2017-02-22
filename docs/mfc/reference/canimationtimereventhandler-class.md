---
title: "Класс CAnimationTimerEventHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationTimerEventHandler"
  - "CAnimationTimerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationTimerEventHandler - класс"
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CAnimationTimerEventHandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует обратный вызов, используемый API анимации, когда происходит событие расчета времени.  
  
## Синтаксис  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationTimerEventHandler::CreateInstance](../Topic/CAnimationTimerEventHandler::CreateInstance.md)|Создает экземпляр обратного вызова `CAnimationTimerEventHandler`.|  
|[CAnimationTimerEventHandler::OnPostUpdate](../Topic/CAnimationTimerEventHandler::OnPostUpdate.md)|Обрабатывает события, происходящие по окончании обновления анимации.  \(Переопределяет `CUIAnimationTimerEventHandlerBase::OnPostUpdate`\).|  
|[CAnimationTimerEventHandler::OnPreUpdate](../Topic/CAnimationTimerEventHandler::OnPreUpdate.md)|Обрабатывает события, происходящие до начала обновления анимации.  \(Переопределяет `CUIAnimationTimerEventHandlerBase::OnPreUpdate`\).|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](../Topic/CAnimationTimerEventHandler::OnRenderingTooSlow.md)|Обрабатывает события, происходящие, когда частота кадров отрисовки для анимации падает ниже минимальной желаемой частоты кадров.  \(Переопределяет `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`\).|  
|[CAnimationTimerEventHandler::SetAnimationController](../Topic/CAnimationTimerEventHandler::SetAnimationController.md)|Хранит указатель на контроллер анимации для маршрутизации событий.|  
  
## Заметки  
 Этот обработчик событий создается и передается методу IUIAnimationTimer::SetTimerEventHandler при вызове CAnimationController::EnableAnimationTimerEventHandler.  
  
## Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)