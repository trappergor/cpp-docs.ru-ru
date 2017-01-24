---
title: "Класс CParabolicTransitionFromAcceleration | Microsoft Docs"
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
  - "afxanimationcontroller/CParabolicTransitionFromAcceleration"
  - "CParabolicTransitionFromAcceleration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CParabolicTransitionFromAcceleration - класс"
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CParabolicTransitionFromAcceleration
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует переход с параболическим ускорением.  
  
## Синтаксис  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](../Topic/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration.md)|Создает переход с параболическим ускорением и инициализирует его заданными параметрами.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CParabolicTransitionFromAcceleration::Create](../Topic/CParabolicTransitionFromAcceleration::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CParabolicTransitionFromAcceleration::m\_dblAcceleration](../Topic/CParabolicTransitionFromAcceleration::m_dblAcceleration.md)|Ускорение переменной анимации во время перехода.|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalValue](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalValue.md)|Значение переменной анимации в конце перехода.|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalVelocity](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalVelocity.md)|Скорость переменной анимации в конце перехода.|  
  
## Заметки  
 Во время перехода с параболическим ускорением значение переменной анимации изменяется от начального значения до конечного значения так, что переход заканчивается на заданной скорости.  Управлять тем, как быстро переменная достигает конечного значения, можно путем задания ускорения.  Поскольку все переходы удаляются автоматически, рекомендуется размещать их в стеке с помощью оператора new.  Инкапсулированный COM\-объект IUIAnimationTransition создается методом CAnimationController::AnimateGrou; до этого он имеет значение NULL.  Изменение переменных\-членов после создания этого COM\-объекта ни на что не влияет.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)