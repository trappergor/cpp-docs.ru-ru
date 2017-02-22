---
title: "CComObjectGlobal Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectGlobal"
  - "ATL::CComObjectGlobal<Base>"
  - "ATL::CComObjectGlobal"
  - "ATL.CComObjectGlobal"
  - "ATL.CComObjectGlobal<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectGlobal class"
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectGlobal Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс управляет счетчик ссылок на модуль, содержащий объект `Base`.  
  
## Синтаксис  
  
```  
  
      template<  
   class Base   
>  
class CComObjectGlobal :  
   public Base  
```  
  
#### Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любого другого интерфейса нужно поддерживать в объекте.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComObjectGlobal::CComObjectGlobal](../Topic/CComObjectGlobal::CComObjectGlobal.md)|Конструктор.|  
|[CComObjectGlobal::~CComObjectGlobal](../Topic/CComObjectGlobal::~CComObjectGlobal.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComObjectGlobal::AddRef](../Topic/CComObjectGlobal::AddRef.md)|Реализует глобальное `AddRef`.|  
|[CComObjectGlobal::QueryInterface](../Topic/CComObjectGlobal::QueryInterface.md)|Реализует глобальное `QueryInterface`.|  
|[CComObjectGlobal::Release](../Topic/CComObjectGlobal::Release.md)|Реализует глобальное **Выпуск**.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComObjectGlobal::m\_hResFinalConstruct](../Topic/CComObjectGlobal::m_hResFinalConstruct.md)|Содержит  **HRESULT**, возвращенным во время создания объекта `CComObjectGlobal`.|  
  
## Заметки  
 `CComObjectGlobal` управляет счетчик ссылок на модуль, содержащий объект `Base`.  `CComObjectGlobal` гарантирует, что объект не будет удален до тех пор, пока модуль не будет освобожден.  Объект будет удалить только когда счетчик ссылок на всем модуле будет отправлена нулю.  
  
 Например, с помощью `CComObjectGlobal`, фабрика класса может храниться общий глобальный объект, который совместно использоваться всеми его клиентами.  
  
## Иерархия наследования  
 `Base`  
  
 `CComObjectGlobal`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComObjectStack Class](../Topic/CComObjectStack%20Class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)