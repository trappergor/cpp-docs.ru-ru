---
title: "Класс CAnimationVariableIntegerChangeHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationVariableIntegerChangeHandler"
  - "CAnimationVariableIntegerChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableIntegerChangeHandler - класс"
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CAnimationVariableIntegerChangeHandler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.  
  
## Синтаксис  
  
```  
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](../Topic/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler.md)|Создает объект `CAnimationVariableIntegerChangeHandler`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariableIntegerChangeHandler::CreateInstance](../Topic/CAnimationVariableIntegerChangeHandler::CreateInstance.md)|Создает экземпляр обратного вызова `CAnimationVariableIntegerChangeHandler`.|  
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](../Topic/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged.md)|Вызывается при изменении значения переменной анимации.  \(Переопределяет `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`\).|  
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](../Topic/CAnimationVariableIntegerChangeHandler::SetAnimationController.md)|Хранит указатель на контроллер анимации для маршрутизации событий.|  
  
## Заметки  
 Этот обработчик событий создается и передается методу IUIAnimationVariable::SetVariableIntegerChangeHandler при вызове метода CAnimationVariable::EnableIntegerValueChangedEvent или CAnimationBaseObject::EnableIntegerValueChangedEvent \(который включает это событие для всех переменных анимации, инкапсулированных в объекте анимации\).  
  
## Иерархия наследования  
 [Классы MFC](../Topic/MFC%20Classes.md)  
  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableIntegerChangeHandlerBase`  
  
 `CAnimationVariableIntegerChangeHandler`  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)