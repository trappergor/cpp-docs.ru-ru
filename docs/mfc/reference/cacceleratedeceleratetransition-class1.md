---
title: "CAccelerateDecelerateTransition Class1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAccelerateDecelerateTransition"
  - "afxanimationcontroller/CAccelerateDecelerateTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CAccelerateDecelerateTransition"
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс CAccelerateDecelerateTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует переход между ускорением и замедлением.  
  
## Синтаксис  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](../Topic/CAccelerateDecelerateTransition::CAccelerateDecelerateTransition.md)|Создает объект перехода.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAccelerateDecelerateTransition::Create](../Topic/CAccelerateDecelerateTransition::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAccelerateDecelerateTransition::m\_accelerationRatio](../Topic/CAccelerateDecelerateTransition::m_accelerationRatio.md)|Отношение времени, затраченного на ускорение, к длительности.|  
|[CAccelerateDecelerateTransition::m\_decelerationRatio](../Topic/CAccelerateDecelerateTransition::m_decelerationRatio.md)|Отношение времени, затраченного на замедление, к длительности.|  
|[CAccelerateDecelerateTransition::m\_duration](../Topic/CAccelerateDecelerateTransition::m_duration.md)|Длительность перехода.|  
|[CAccelerateDecelerateTransition::m\_finalValue](../Topic/CAccelerateDecelerateTransition::m_finalValue.md)|Значение переменной анимации в конце перехода.|  
  
## Заметки  
 Во время перехода с ускорением и замедлением переменная анимации ускоряется и затем замедляется в течение длительности перехода так, что переход заканчивается при заданном значении.  Управлять быстротой ускорения и замедления переменной можно независимо путем задания разных коэффициентов ускорения и замедления.  Когда начальная скорость равна нулю, коэффициент ускорения представляет собой долю длительности, в течение которой переменная будет ускоряться; аналогично с коэффициентом замедления.  Если начальная скорость отлична от нуля, он представляет собой долю времени между достижением скоростью нуля и концом перехода.  Сумма коэффициента ускорения и коэффициента замедления не должна превышать 1,0.  Поскольку все переходы удаляются автоматически, рекомендуется размещать их в стеке с помощью оператора new.  Инкапсулированный COM\-объект IUIAnimationTransition создается методом CAnimationController::AnimateGrou; до этого он имеет значение NULL.  Изменение переменных\-членов после создания этого COM\-объекта ни на что не влияет.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CAccelerateDecelerateTransition](../../mfc/reference/cacceleratedeceleratetransition-class1.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)