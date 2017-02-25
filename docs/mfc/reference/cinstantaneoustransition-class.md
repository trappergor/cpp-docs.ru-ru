---
title: "Класс CInstantaneousTransition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CInstantaneousTransition"
  - "CInstantaneousTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInstantaneousTransition - класс"
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CInstantaneousTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует мгновенный переход.  
  
## Синтаксис  
  
```  
class CInstantaneousTransition : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInstantaneousTransition::CInstantaneousTransition](../Topic/CInstantaneousTransition::CInstantaneousTransition.md)|Создает объект перехода и инициализирует его конечное значение.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInstantaneousTransition::Create](../Topic/CInstantaneousTransition::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CInstantaneousTransition::m\_dblFinalValue](../Topic/CInstantaneousTransition::m_dblFinalValue.md)|Значение переменной анимации в конце перехода.|  
  
## Заметки  
 Во время мгновенного перехода значение переменной анимации изменяется мгновенно от текущего значения до заданного конечного значения.  Длительность этого перехода всегда равна нулю.  Поскольку все переходы удаляются автоматически, рекомендуется размещать их в стеке с помощью оператора new.  Инкапсулированный COM\-объект IUIAnimationTransition создается методом CAnimationController::AnimateGrou; до этого он имеет значение NULL.  Изменение переменных\-членов после создания этого COM\-объекта ни на что не влияет.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)