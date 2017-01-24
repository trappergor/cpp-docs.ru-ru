---
title: "Класс CAnimationPoint | Microsoft Docs"
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
  - "CAnimationPoint"
  - "afxanimationcontroller/CAnimationPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationPoint - класс"
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CAnimationPoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функции точки, координаты которой могут быть анимированы.  
  
## Синтаксис  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationPoint::CAnimationPoint](../Topic/CAnimationPoint::CAnimationPoint.md)|Перегружен.  Создает объект CAnimationPoint.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationPoint::AddTransition](../Topic/CAnimationPoint::AddTransition.md)|Добавляет переходы для координат X и Y.|  
|[CAnimationPoint::GetDefaultValue](../Topic/CAnimationPoint::GetDefaultValue.md)|Возвращает значения по умолчанию для координат X и Y.|  
|[CAnimationPoint::GetValue](../Topic/CAnimationPoint::GetValue.md)|Возвращает текущее значение.|  
|[CAnimationPoint::GetX](../Topic/CAnimationPoint::GetX.md)|Предоставляет доступ к объекту CAnimationVariable для получения координаты X.|  
|[CAnimationPoint::GetY](../Topic/CAnimationPoint::GetY.md)|Предоставляет доступ к объекту CAnimationVariable для получения координаты Y.|  
|[CAnimationPoint::SetDefaultValue](../Topic/CAnimationPoint::SetDefaultValue.md)|Устанавливает значение по умолчанию.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationPoint::GetAnimationVariableList](../Topic/CAnimationPoint::GetAnimationVariableList.md)|Помещает инкапсулированные переменные анимации в список.  \(Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationPoint::operator CPoint](../Topic/CAnimationPoint::operator%20CPoint.md)|Преобразует объект CAnimationPoint в объект CPoint.|  
|[CAnimationPoint::operator\=](../Topic/CAnimationPoint::operator=.md)|Присваивает объекту CAnimationPoint значение параметра ptSrc.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationPoint::m\_xValue](../Topic/CAnimationPoint::m_xValue.md)|Инкапсулированная переменная анимации, представляющая координату X точки анимации.|  
|[CAnimationPoint::m\_yValue](../Topic/CAnimationPoint::m_yValue.md)|Инкапсулированная переменная анимации, представляющая координату Y точки анимации.|  
  
## Заметки  
 Класс CAnimationPoint инкапсулирует два объекта CAnimationVariable и может представлять точку в приложениях.  Например, этот класс можно использовать для анимации положения любого объекта на экране \(текстовой строки, окружности, точки и т. д.\).  Чтобы использовать этот класс в приложении, просто создайте экземпляр объекта этого класса, добавьте его в контроллер анимации с помощью метода CAnimationController::AddAnimationObject и вызовите метод AddTransition для каждого перехода, применяемого к координате X и\/или Y.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationPoint](../../mfc/reference/canimationpoint-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)