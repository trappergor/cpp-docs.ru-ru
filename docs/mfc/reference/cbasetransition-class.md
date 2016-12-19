---
title: "Класс CBaseTransition | Microsoft Docs"
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
  - "CBaseTransition"
  - "afxanimationcontroller/CBaseTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTransition - класс"
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CBaseTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет базовый переход.  
  
## Синтаксис  
  
```  
class CBaseTransition : public CObject;  
```  
  
## Члены  
  
### Открытые перечисления  
  
|Имя|Описание|  
|---------|--------------|  
|[Перечисление CBaseTransition::TRANSITION\_TYPE](../Topic/CBaseTransition::TRANSITION_TYPE%20Enumeration.md)|Определяет тип перехода, в настоящее время поддерживаемый MFC\-реализацией Windows Animation API.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBaseTransition::CBaseTransition](../Topic/CBaseTransition::CBaseTransition.md)|Создает базовый объект перехода.|  
|[CBaseTransition::~CBaseTransition](../Topic/CBaseTransition::~CBaseTransition.md)|Деструктор.  Вызывается при уничтожении объекта перехода.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBaseTransition::AddToStoryboard](../Topic/CBaseTransition::AddToStoryboard.md)|Добавляет переход в раскадровку.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](../Topic/CBaseTransition::AddToStoryboardAtKeyframes.md)|Добавляет переход в раскадровку.|  
|[CBaseTransition::Clear](../Topic/CBaseTransition::Clear.md)|Освобождает инкапсулированный COM\-объект IUIAnimationTransition.|  
|[CBaseTransition::Create](../Topic/CBaseTransition::Create.md)|Создает COM\-переход.|  
|[CBaseTransition::GetEndKeyframe](../Topic/CBaseTransition::GetEndKeyframe.md)|Возвращает начальный опорный кадр.|  
|[CBaseTransition::GetRelatedVariable](../Topic/CBaseTransition::GetRelatedVariable.md)|Возвращает указатель на связанную переменную.|  
|[CBaseTransition::GetStartKeyframe](../Topic/CBaseTransition::GetStartKeyframe.md)|Возвращает начальный опорный кадр.|  
|[CBaseTransition::GetTransition](../Topic/CBaseTransition::GetTransition.md)|Перегружен.  Возвращает указатель на базовый COM\-объект перехода.|  
|[CBaseTransition::GetType](../Topic/CBaseTransition::GetType.md)|Возвращает тип перехода.|  
|[CBaseTransition::IsAdded](../Topic/CBaseTransition::IsAdded.md)|Сообщает, добавлен ли переход в раскадровку.|  
|[CBaseTransition::SetKeyframes](../Topic/CBaseTransition::SetKeyframes.md)|Устанавливает опорные кадры для перехода.|  
|[CBaseTransition::SetRelatedVariable](../Topic/CBaseTransition::SetRelatedVariable.md)|Устанавливает отношение между переменной анимации и переходом.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CBaseTransition::m\_bAdded](../Topic/CBaseTransition::m_bAdded.md)|Указывает, добавлен ли переход в раскадровку.|  
|[CBaseTransition::m\_pEndKeyframe](../Topic/CBaseTransition::m_pEndKeyframe.md)|Хранит указатель на опорный кадр, задающий конец перехода.|  
|[CBaseTransition::m\_pRelatedVariable](../Topic/CBaseTransition::m_pRelatedVariable.md)|Указатель на переменную анимации, анимируемую переходом, хранящимся в m\_transition.|  
|[CBaseTransition::m\_pStartKeyframe](../Topic/CBaseTransition::m_pStartKeyframe.md)|Хранит указатель на опорный кадр, задающий начало перехода.|  
|[CBaseTransition::m\_transition](../Topic/CBaseTransition::m_transition.md)|Хранит указатель на IUIAnimationTransition.  Значение NULL, если COM\-объект перехода не создан.|  
|[CBaseTransition::m\_type](../Topic/CBaseTransition::m_type.md)|Хранит тип перехода.|  
  
## Заметки  
 Этот класс инкапсулирует интерфейс IUIAnimationTransition и служит базовым классом для всех переходов.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)