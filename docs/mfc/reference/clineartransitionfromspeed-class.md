---
title: "Класс CLinearTransitionFromSpeed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CLinearTransitionFromSpeed"
  - "CLinearTransitionFromSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransitionFromSpeed - класс"
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс CLinearTransitionFromSpeed
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует переход с линейной скоростью.  
  
## Синтаксис  
  
```  
class CLinearTransitionFromSpeed : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](../Topic/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed.md)|Создает объект перехода с линейной скоростью и инициализирует его скоростью и конечным значением.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransitionFromSpeed::Create](../Topic/CLinearTransitionFromSpeed::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransitionFromSpeed::m\_dblFinalValue](../Topic/CLinearTransitionFromSpeed::m_dblFinalValue.md)|Значение переменной анимации в конце перехода.|  
|[CLinearTransitionFromSpeed::m\_dblSpeed](../Topic/CLinearTransitionFromSpeed::m_dblSpeed.md)|Абсолютное значение скорости переменной.|  
  
## Заметки  
 Во время перехода с линейной скоростью значение переменной анимации изменяется с заданной скоростью.  Длительность перехода определяется разностью между начальным значением и заданным конечным значением.  Поскольку все переходы удаляются автоматически, рекомендуется размещать их в стеке с помощью оператора new.  Инкапсулированный COM\-объект IUIAnimationTransition создается методом CAnimationController::AnimateGrou; до этого он имеет значение NULL.  Изменение переменных\-членов после создания этого COM\-объекта ни на что не влияет.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)