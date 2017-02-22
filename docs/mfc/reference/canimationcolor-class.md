---
title: "Класс CAnimationColor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationColor"
  - "afxanimationcontroller/CAnimationColor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationColor - класс"
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс CAnimationColor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функции цвета, красный, зеленый и синий компоненты которого могут быть анимированы.  
  
## Синтаксис  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationColor::CAnimationColor](../Topic/CAnimationColor::CAnimationColor.md)|Перегружен.  Создает объект цвета анимации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationColor::AddTransition](../Topic/CAnimationColor::AddTransition.md)|Добавляет переходы для красного, зеленого и синего компонентов.|  
|[CAnimationColor::GetB](../Topic/CAnimationColor::GetB.md)|Предоставляет доступ к объекту CAnimationVariable, представляющему синий компонент.|  
|[CAnimationColor::GetDefaultValue](../Topic/CAnimationColor::GetDefaultValue.md)|Возвращает значения по умолчанию для компонентов цвета.|  
|[CAnimationColor::GetG](../Topic/CAnimationColor::GetG.md)|Предоставляет доступ к объекту CAnimationVariable, представляющему зеленый компонент.|  
|[CAnimationColor::GetR](../Topic/CAnimationColor::GetR.md)|Предоставляет доступ к объекту CAnimationVariable, представляющему красный компонент.|  
|[CAnimationColor::GetValue](../Topic/CAnimationColor::GetValue.md)|Возвращает текущее значение.|  
|[CAnimationColor::SetDefaultValue](../Topic/CAnimationColor::SetDefaultValue.md)|Устанавливает значение по умолчанию.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationColor::GetAnimationVariableList](../Topic/CAnimationColor::GetAnimationVariableList.md)|Помещает инкапсулированные переменные анимации в список.  \(Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationColor::operator COLORREF](../Topic/CAnimationColor::operator%20COLORREF.md)||  
|[CAnimationColor::operator\=](../Topic/CAnimationColor::operator=.md)|Присваивает объекту CAnimationColor цвет.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationColor::m\_bValue](../Topic/CAnimationColor::m_bValue.md)|Инкапсулированная переменная анимации, представляющая синий компонент цвета анимации.|  
|[CAnimationColor::m\_gValue](../Topic/CAnimationColor::m_gValue.md)|Инкапсулированная переменная анимации, представляющая зеленый компонент цвета анимации.|  
|[CAnimationColor::m\_rValue](../Topic/CAnimationColor::m_rValue.md)|Инкапсулированная переменная анимации, представляющая красный компонент цвета анимации.|  
  
## Заметки  
 Класс CAnimationColor инкапсулирует три объекта CAnimationVariable и может представлять цвет в приложениях.  Например, этот класс можно использовать для анимации цветов любого объекта на экране \(цвета текста, цвета фона и т. д.\).  Чтобы использовать этот класс в приложении, просто создайте экземпляр объекта этого класса, добавьте его в контроллер анимации с помощью метода CAnimationController::AddAnimationObject и вызовите метод AddTransition для каждого перехода, применяемого к красному, зеленому и синему компонентам.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationColor](../../mfc/reference/canimationcolor-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)