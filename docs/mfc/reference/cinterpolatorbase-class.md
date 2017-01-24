---
title: "Класс CInterpolatorBase | Microsoft Docs"
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
  - "afxanimationcontroller/CInterpolatorBase"
  - "CInterpolatorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterpolatorBase - класс"
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CInterpolatorBase
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует обратный вызов, используемый API анимации, когда требуется рассчитать новое значение переменной анимации.  
  
## Синтаксис  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInterpolatorBase::CInterpolatorBase](../Topic/CInterpolatorBase::CInterpolatorBase.md)|Создает объект `CInterpolatorBase`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInterpolatorBase::CreateInstance](../Topic/CInterpolatorBase::CreateInstance.md)|Создает экземпляр `CInterpolatorBase` и сохраняет указатель на пользовательский интерполятору, который будет обрабатывать события.|  
|[CInterpolatorBase::GetDependencies](../Topic/CInterpolatorBase::GetDependencies.md)|Получает зависимости интерполятора.  \(Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`\).|  
|[CInterpolatorBase::GetDuration](../Topic/CInterpolatorBase::GetDuration.md)|Получает длительность интерполятора.  \(Переопределяет `CUIAnimationInterpolatorBase::GetDuration`\).|  
|[CInterpolatorBase::GetFinalValue](../Topic/CInterpolatorBase::GetFinalValue.md)|Получает конечное значение, к которому ведет интерполятор.  \(Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`\).|  
|[CInterpolatorBase::InterpolateValue](../Topic/CInterpolatorBase::InterpolateValue.md)|Осуществляет интерполяцию значение с указанным смещением \(переопределяет `CUIAnimationInterpolatorBase::InterpolateValue`\).|  
|[CInterpolatorBase::InterpolateVelocity](../Topic/CInterpolatorBase::InterpolateVelocity.md)|Осуществляет интерполяцию скорость с указанным смещением \(переопределяет `CUIAnimationInterpolatorBase::InterpolateVelocity`\).|  
|[CInterpolatorBase::SetCustomInterpolator](../Topic/CInterpolatorBase::SetCustomInterpolator.md)|Хранит указатель на пользовательский интерполятор, который будет обрабатывать события.|  
|[CInterpolatorBase::SetDuration](../Topic/CInterpolatorBase::SetDuration.md)|Задает длительность интерполятора \(переопределяет `CUIAnimationInterpolatorBase::SetDuration`\).|  
|[CInterpolatorBase::SetInitialValueAndVelocity](../Topic/CInterpolatorBase::SetInitialValueAndVelocity.md)|Устанавливает начальные значение и скорость интерполятора.  \(Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`\).|  
  
## Заметки  
 Этот механизм создания и передается `IUIAnimationTransitionFactory::CreateTransition` после создания объекта `CCustomTransition` как часть процесса инициализации анимации \(запущенного `CAnimationController::AnimateGroup`\).  Обычно нет необходимости использовать этот класс, он просто направляете все события в `CCustomInterpolator`\- производный класс, указатель которого передается в конструктор `CCustomTransition`.  
  
## Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)