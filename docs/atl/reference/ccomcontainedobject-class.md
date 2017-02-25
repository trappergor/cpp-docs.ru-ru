---
title: "CComContainedObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], в ATL"
  - "aggregation [C++], ATL-объекты"
  - "CComContainedObject class"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComContainedObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), делегировать к **IUnknown** объекта владельцем.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
class Base   
>  
class CComContainedObject :  
public Base  
```  
  
#### Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|Конструктор.  Инициализирует указатель члена к `IUnknown` объекта владельцем.|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|Увеличивает счетчик ссылок в объекте владельца.|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|Извлекает `IUnknown` объекта владельцем.|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|Извлекает указатель на интерфейс, запрошенный в объекте владельца.|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|Уменьшает счетчик ссылок в объекте владельца.|  
  
## Заметки  
 Библиотеки ATL используется `CComContainedObject` в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md) и [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md).  `CComContainedObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), делегировать к **IUnknown** объекта владельцем.  Внешний объект \(владелец или агрегата или создать объект, для которого перемещаемый интерфейс.\) `CComContainedObject` вызывает `OuterQueryInterface`, `OuterAddRef` и `OuterRelease` объекта `CComObjectRootEx`, все унаследованные через `Base`.  
  
## Иерархия наследования  
 `Base`  
  
 `CComContainedObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)