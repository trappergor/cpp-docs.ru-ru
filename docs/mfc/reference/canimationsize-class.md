---
title: "Класс CAnimationSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationSize"
  - "CAnimationSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationSize - класс"
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс CAnimationSize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функции объекта размера, размеры которого могут быть анимированы.  
  
## Синтаксис  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationSize::CAnimationSize](../Topic/CAnimationSize::CAnimationSize.md)|Перегружен.  Создает объект размера анимации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationSize::AddTransition](../Topic/CAnimationSize::AddTransition.md)|Добавляет переходы для ширины и высоты.|  
|[CAnimationSize::GetCX](../Topic/CAnimationSize::GetCX.md)|Предоставляет доступ к объекту CAnimationVariable, представляющему ширину.|  
|[CAnimationSize::GetCY](../Topic/CAnimationSize::GetCY.md)|Предоставляет доступ к объекту CAnimationVariable, представляющему высоту.|  
|[CAnimationSize::GetDefaultValue](../Topic/CAnimationSize::GetDefaultValue.md)|Возвращает значения по умолчанию для ширины и высоты.|  
|[CAnimationSize::GetValue](../Topic/CAnimationSize::GetValue.md)|Возвращает текущее значение.|  
|[CAnimationSize::SetDefaultValue](../Topic/CAnimationSize::SetDefaultValue.md)|Устанавливает значение по умолчанию.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationSize::GetAnimationVariableList](../Topic/CAnimationSize::GetAnimationVariableList.md)|Помещает инкапсулированные переменные анимации в список.  \(Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationSize::operator CSize](../Topic/CAnimationSize::operator%20CSize.md)|Преобразует объект CAnimationSize в объект CSize.|  
|[CAnimationSize::operator\=](../Topic/CAnimationSize::operator=.md)|Присваивает объекту CAnimationSize значение параметра szSrc.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationSize::m\_cxValue](../Topic/CAnimationSize::m_cxValue.md)|Инкапсулированная переменная анимации, представляющая ширину в размере анимации.|  
|[CAnimationSize::m\_cyValue](../Topic/CAnimationSize::m_cyValue.md)|Инкапсулированная переменная анимации, представляющая высоту в размере анимации.|  
  
## Заметки  
 Класс CAnimationSize инкапсулирует два объекта CAnimationVariable и может представлять размер в приложениях.  Например, этот класс можно использовать для анимации размера любого двумерного объекта на экране \(прямоугольника, элемента управления и т. д.\).  Чтобы использовать этот класс в приложении, просто создайте экземпляр объекта этого класса, добавьте его в контроллер анимации с помощью метода CAnimationController::AddAnimationObject и вызовите метод AddTransition для каждого перехода, применяемого к ширине и\/или высоте.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationSize](../../mfc/reference/canimationsize-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)