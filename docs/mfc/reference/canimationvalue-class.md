---
title: "Класс CAnimationValue | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationValue"
  - "CAnimationValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationValue - класс"
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CAnimationValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функции объекта анимации, имеющего одно значение.  
  
## Синтаксис  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationValue::CAnimationValue](../Topic/CAnimationValue::CAnimationValue.md)|Перегружен.  Создает объект CAnimationValue.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationValue::AddTransition](../Topic/CAnimationValue::AddTransition.md)|Добавляет переход, применяемый к значению.|  
|[CAnimationValue::GetValue](../Topic/CAnimationValue::GetValue.md)|Перегружен.  Извлекает текущее значение.|  
|[CAnimationValue::GetVariable](../Topic/CAnimationValue::GetVariable.md)|Предоставляет доступ к инкапсулированной переменной анимации.|  
|[CAnimationValue::SetDefaultValue](../Topic/CAnimationValue::SetDefaultValue.md)|Устанавливает значение по умолчанию.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationValue::GetAnimationVariableList](../Topic/CAnimationValue::GetAnimationVariableList.md)|Помещает инкапсулированную переменную анимации в список.  \(Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationValue::operator DOUBLE](../Topic/CAnimationValue::operator%20DOUBLE.md)|Обеспечивает преобразование между объектом CAnimationValue и значением типа DOUBLE.|  
|[CAnimationValue::operator INT32](../Topic/CAnimationValue::operator%20INT32.md)|Обеспечивает преобразование между объектом CAnimationValue и значением типа INT32.|  
|[CAnimationValue::operator\=](../Topic/CAnimationValue::operator=.md)|Перегружен.  Присваивает объекту CAnimationValue значение типа INT32.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationValue::m\_value](../Topic/CAnimationValue::m_value.md)|Инкапсулированная переменная анимации, представляющая значение анимации.|  
  
## Заметки  
 Класс CAnimationValue инкапсулирует один объект CAnimationVariable и может представлять отдельное анимируемое значение в приложениях.  Например, этот класс можно использовать для анимации прозрачности \(угасание\/затемнение\), угла \(для поворота объектов\) или в любых других случаях, когда требуется создать анимацию, основанную на одной анимируемой переменной.  Чтобы использовать этот класс в приложении, просто создайте экземпляр объекта этого класса, добавьте его в контроллер анимации с помощью метода CAnimationController::AddAnimationObject и вызовите метод AddTransition для каждого перехода, применяемого к значению.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationValue](../../mfc/reference/canimationvalue-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)