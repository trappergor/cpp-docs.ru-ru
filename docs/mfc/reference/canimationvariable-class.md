---
title: "Класс CAnimationVariable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationVariable"
  - "afxanimationcontroller/CAnimationVariable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariable - класс"
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс CAnimationVariable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет переменную анимации.  
  
## Синтаксис  
  
```  
class CAnimationVariable;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariable::CAnimationVariable](../Topic/CAnimationVariable::CAnimationVariable.md)|Создает объект переменной анимации.|  
|[CAnimationVariable::~CAnimationVariable](../Topic/CAnimationVariable::~CAnimationVariable.md)|Деструктор.  Вызывается при уничтожении объекта CAnimationVariable.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariable::AddTransition](../Topic/CAnimationVariable::AddTransition.md)|Добавляет переход.|  
|[CAnimationVariable::ApplyTransitions](../Topic/CAnimationVariable::ApplyTransitions.md)|Добавляет переходы из внутреннего списка в раскадровку.|  
|[CAnimationVariable::ClearTransitions](../Topic/CAnimationVariable::ClearTransitions.md)|Удаляет переходы.|  
|[CAnimationVariable::Create](../Topic/CAnimationVariable::Create.md)|Создает базовый COM\-объект переменной анимации.|  
|[CAnimationVariable::CreateTransitions](../Topic/CAnimationVariable::CreateTransitions.md)|Создает все переходы для применения к данной переменной анимации.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](../Topic/CAnimationVariable::EnableIntegerValueChangedEvent.md)|Включает или отключает событие IntegerValueChanged.|  
|[CAnimationVariable::EnableValueChangedEvent](../Topic/CAnimationVariable::EnableValueChangedEvent.md)|Включает или отключает событие ValueChanged.|  
|[CAnimationVariable::GetDefaultValue](../Topic/CAnimationVariable::GetDefaultValue.md)|Возвращает значение по умолчанию.|  
|[CAnimationVariable::GetParentAnimationObject](../Topic/CAnimationVariable::GetParentAnimationObject.md)|Возвращает родительский объект анимации.|  
|[CAnimationVariable::GetValue](../Topic/CAnimationVariable::GetValue.md)|Перегружен.  Возвращает текущее значение переменной анимации.|  
|[CAnimationVariable::GetVariable](../Topic/CAnimationVariable::GetVariable.md)|Возвращает указатель на COM\-объект IUIAnimationVariable.|  
|[CAnimationVariable::SetDefaultValue](../Topic/CAnimationVariable::SetDefaultValue.md)|Устанавливает значение по умолчанию и освобождает COM\-объект IUIAnimationVariable.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariable::SetParentAnimationObject](../Topic/CAnimationVariable::SetParentAnimationObject.md)|Устанавливает отношение между переменной анимации и объектом анимации.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariable::m\_bAutodestroyTransitions](../Topic/CAnimationVariable::m_bAutodestroyTransitions.md)|Указывает, следует ли удалять связанные объекты переходов.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationVariable::m\_dblDefaultValue](../Topic/CAnimationVariable::m_dblDefaultValue.md)|Задает значение по умолчанию, которое распространяется на IUIAnimationVariable.|  
|[CAnimationVariable::m\_lstTransitions](../Topic/CAnimationVariable::m_lstTransitions.md)|Содержит список переходов, анимирующих данную переменную анимации.|  
|[CAnimationVariable::m\_pParentObject](../Topic/CAnimationVariable::m_pParentObject.md)|Указатель на объект анимации, инкапсулирующий данную переменную анимации.|  
|[CAnimationVariable::m\_variable](../Topic/CAnimationVariable::m_variable.md)|Хранит указатель на COM\-объект IUIAnimationVariable.  Значение NULL, если COM\-объект еще не создан или если создать его не удалось.|  
  
## Заметки  
 Класс CAnimationVariable инкапсулирует COM\-объект IUIAnimationVariable.  Также он содержит список переходов, применяемых к переменной анимации в раскадровке.  Объекты CAnimationVariable внедряются в объекты анимации, которые могут представлять в приложении анимируемое значение, точку, размер, цвет и прямоугольник.  
  
## Иерархия наследования  
 [CAnimationVariable](../../mfc/reference/canimationvariable-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)