---
title: "Класс CAnimationVariableChangeHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationVariableChangeHandler"
  - "CAnimationVariableChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableChangeHandler - класс"
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс CAnimationVariableChangeHandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.  
  
## Синтаксис  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Создает объект `CAnimationVariableChangeHandler`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Создает экземпляр объекта `CAnimationVariableChangeHandler`.|  
|[CAnimationVariableChangeHandler::OnValueChanged](../Topic/CAnimationVariableChangeHandler::OnValueChanged.md)|Вызывается при изменении значения переменной анимации.  \(Переопределяет `CUIAnimationVariableChangeHandlerBase::OnValueChanged`\).|  
|[CAnimationVariableChangeHandler::SetAnimationController](../Topic/CAnimationVariableChangeHandler::SetAnimationController.md)|Хранит указатель на контроллер анимации для маршрутизации событий.|  
  
## Заметки  
 Этому обработчику событий создается и передается `IUIAnimationVariable::SetVariableChangeHandler` метода, при вызове `CAnimationVariable::EnableValueChangedEvent` или `CAnimationBaseObject::EnableValueChangedEvent` \(которые включают это событие для всех переменных анимации, инкапсулированных в объекте анимации\).  
  
## Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)