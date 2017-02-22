---
title: "CComObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObject<Base>"
  - "ATL::CComObject"
  - "ATL::CComObject<Base>"
  - "ATL.CComObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObject class"
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** для nonaggregated объекта.  
  
## Синтаксис  
  
```  
  
      template<  
   class Base   
>  
class CComObject :  
   public Base  
```  
  
#### Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от других интерфейсов нужно поддерживать в объекте.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComObject::CComObject](../Topic/CComObject::CComObject.md)|Конструктор.|  
|[CComObject::~CComObject](../Topic/CComObject::~CComObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComObject::AddRef](../Topic/CComObject::AddRef.md)|Увеличивает счетчик ссылок на объект.|  
|[CComObject::CreateInstance](../Topic/CComObject::CreateInstance.md)|\(Статический\) Создает новый объект `CComObject`.|  
|[CComObject::QueryInterface](../Topic/CComObject::QueryInterface.md)|Извлекает указатель на запрашиваемый интерфейс.|  
|[CComObject::Release](../Topic/CComObject::Release.md)|Уменьшает счетчик ссылок на объект.|  
  
## Заметки  
 Средства [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)`CComObject` для nonaggregated объекта.  Однако вызовы `QueryInterface`, `AddRef` и **Выпуск** делегированы к `CComObjectRootEx`.  
  
 Дополнительные сведения об использовании `CComObject` см. в статье [Принципы COM\-объект библиотеки ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Иерархия наследования  
 `Base`  
  
 `CComObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)