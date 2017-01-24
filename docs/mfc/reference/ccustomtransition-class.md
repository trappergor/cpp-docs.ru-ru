---
title: "Класс CCustomTransition | Microsoft Docs"
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
  - "afxanimationcontroller/CCustomTransition"
  - "CCustomTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomTransition - класс"
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CCustomTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует пользовательский переход.  
  
## Синтаксис  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCustomTransition::CCustomTransition](../Topic/CCustomTransition::CCustomTransition.md)|Создает пользовательский объект перехода.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCustomTransition::Create](../Topic/CCustomTransition::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
|[CCustomTransition::SetInitialValue](../Topic/CCustomTransition::SetInitialValue.md)|Устанавливает начальное значение, которое будет применено к переменной анимации, связанной с данным переходом.|  
|[CCustomTransition::SetInitialVelocity](../Topic/CCustomTransition::SetInitialVelocity.md)|Устанавливает начальную скорость, которая будет применена к переменной анимации, связанной с данным переходом.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CCustomTransition::m\_bInitialValueSpecified](../Topic/CCustomTransition::m_bInitialValueSpecified.md)|Указывает, было ли начальное значение задано с помощью метода SetInitialValue.|  
|[CCustomTransition::m\_bInitialVelocitySpecified](../Topic/CCustomTransition::m_bInitialVelocitySpecified.md)|Указывает, была ли начальная скорость задана с помощью метода SetInitialVelocity.|  
|[CCustomTransition::m\_initialValue](../Topic/CCustomTransition::m_initialValue.md)|Хранит начальное значение.|  
|[CCustomTransition::m\_initialVelocity](../Topic/CCustomTransition::m_initialVelocity.md)|Хранит начальную скорость.|  
|[CCustomTransition::m\_pInterpolator](../Topic/CCustomTransition::m_pInterpolator.md)|Хранит указатель на пользовательский интерполятор.|  
  
## Заметки  
 Класс CCustomTransitions позволяет разработчикам реализовывать пользовательские переходы.  Он создается и используется как стандартный переход, однако его конструктор принимает в качестве параметра указатель на пользовательский интерполятор.  Для использования пользовательских переходов выполните следующие действия. 1.  Наследуйте класс от CCustomInterpolator и реализуйте хотя бы метод InterpolateValue.  2.  Следите за тем, чтобы время существования объекта пользовательского интерполятора превышало длительность анимации там, где он используется.  3.  Создайте \(с помощью оператора new\) экземпляр объекта CCustomTransition и передайте в конструкторе указатель на пользовательский интерполятор.  4.  Вызовите методы CCustomTransition::SetInitialValue и CCustomTransition::SetInitialVelocity, если соответствующие параметры необходимы для пользовательской интерполяции.  5.  Передайте указатель на пользовательский переход методу AddTransition объекта анимации, значение которого должно анимироваться по пользовательскому алгоритму.  6.  Когда значение объекта анимации должно измениться, Windows Animation API вызывает метод InterpolateValue \(и другие необходимые методы\) в классе CCustomInterpolator.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCustomTransition](../../mfc/reference/ccustomtransition-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)