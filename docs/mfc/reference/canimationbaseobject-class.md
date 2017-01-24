---
title: "Класс CAnimationBaseObject | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationBaseObject"
  - "CAnimationBaseObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationBaseObject - класс"
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CAnimationBaseObject
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для всех объектов анимации.  
  
## Синтаксис  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationBaseObject::CAnimationBaseObject](../Topic/CAnimationBaseObject::CAnimationBaseObject.md)|Перегружен.  Создает объект анимации.|  
|[CAnimationBaseObject::~CAnimationBaseObject](../Topic/CAnimationBaseObject::~CAnimationBaseObject.md)|Деструктор.  Вызывается при уничтожении объекта анимации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationBaseObject::ApplyTransitions](../Topic/CAnimationBaseObject::ApplyTransitions.md)|Добавляет переходы в раскадровку с инкапсулированной переменной анимации.|  
|[CAnimationBaseObject::ClearTransitions](../Topic/CAnimationBaseObject::ClearTransitions.md)|Удаляет все связанные переходы.|  
|[CAnimationBaseObject::ContainsVariable](../Topic/CAnimationBaseObject::ContainsVariable.md)|Определяет, содержит ли объект анимации определенную переменную анимации.|  
|[CAnimationBaseObject::CreateTransitions](../Topic/CAnimationBaseObject::CreateTransitions.md)|Создает переходы, связанные с объектом анимации.|  
|[CAnimationBaseObject::DetachFromController](../Topic/CAnimationBaseObject::DetachFromController.md)|Отсоединяет объект анимации от родительского контроллера анимации.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](../Topic/CAnimationBaseObject::EnableIntegerValueChangedEvent.md)|Настраивает обработчик событий IntegerValueChanged.|  
|[CAnimationBaseObject::EnableValueChangedEvent](../Topic/CAnimationBaseObject::EnableValueChangedEvent.md)|Настраивает обработчик событий ValueChanged.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](../Topic/CAnimationBaseObject::GetAutodestroyTransitions.md)|Сообщает, уничтожаются ли связанные переходы автоматически.|  
|[CAnimationBaseObject::GetGroupID](../Topic/CAnimationBaseObject::GetGroupID.md)|Возвращает ИД текущей группы.|  
|[CAnimationBaseObject::GetObjectID](../Topic/CAnimationBaseObject::GetObjectID.md)|Возвращает ИД текущего объекта.|  
|[CAnimationBaseObject::GetUserData](../Topic/CAnimationBaseObject::GetUserData.md)|Возвращает определенные пользователем данные.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](../Topic/CAnimationBaseObject::SetAutodestroyTransitions.md)|Устанавливает флаг, дающий указание автоматически уничтожать переходы.|  
|[CAnimationBaseObject::SetID](../Topic/CAnimationBaseObject::SetID.md)|Устанавливает новые идентификаторы.|  
|[CAnimationBaseObject::SetUserData](../Topic/CAnimationBaseObject::SetUserData.md)|Устанавливает определенные пользователем данные.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md)|Собирает указатели на содержащиеся в объекте переменные анимации.|  
|[CAnimationBaseObject::SetParentAnimationObjects](../Topic/CAnimationBaseObject::SetParentAnimationObjects.md)|Устанавливает отношение между переменными анимации, содержащимися в объекте анимации, и их контейнером.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationBaseObject::m\_bAutodestroyTransitions](../Topic/CAnimationBaseObject::m_bAutodestroyTransitions.md)|Указывает, следует ли автоматически уничтожать связанные переходы.|  
|[CAnimationBaseObject::m\_dwUserData](../Topic/CAnimationBaseObject::m_dwUserData.md)|Хранит определенные пользователем данные.|  
|[CAnimationBaseObject::m\_nGroupID](../Topic/CAnimationBaseObject::m_nGroupID.md)|Задает ИД группы объекта анимации.|  
|[CAnimationBaseObject::m\_nObjectID](../Topic/CAnimationBaseObject::m_nObjectID.md)|Задает ИД объекта объекта анимации.|  
|[CAnimationBaseObject::m\_pParentController](../Topic/CAnimationBaseObject::m_pParentController.md)|Указатель на родительский контроллер анимации.|  
  
## Заметки  
 Этот класс реализует базовые методы для всех объектов анимации.  Объект анимации может представлять значение, точку, размер, прямоугольник или цвет в приложении, а также любую пользовательскую сущность.  Объекты анимации хранятся в группах анимации \(см. CAnimationGroup\).  Каждая группа может анимироваться отдельно и рассматриваться как аналог раскадровки.  Объект анимации инкапсулирует одну или несколько переменных анимации \(см. CAnimationVariable\), в зависимости от его логического представления.  Например, CAnimationRect содержит четыре переменные анимации — по одной переменной для каждой стороны прямоугольника.  Каждый класс объекта анимации предоставляет перегруженный метод AddTransition, который следует использовать для применения переходов к инкапсулированным переменным анимации.  Объект анимации может идентифицироваться ИД объекта \(необязательно\) и ИД группы.  ИД группы необходим для помещения объекта анимации в правильную группу, однако, если ИД группы не задан, объект помещается в группу по умолчанию с ИД\=0.  При вызове метода SetID с другим ИД группы объект анимации будет перемещен в другую группу \(при необходимости создается новая группа\).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)