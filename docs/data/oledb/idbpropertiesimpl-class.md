---
title: "Класс IDBPropertiesImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBPropertiesImpl - класс"
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс IDBPropertiesImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает реализацию интерфейса `IDBProperties`.  
  
## Синтаксис  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IDBPropertiesImpl`.  
  
## Члены  
  
### Методы Interface  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Возвращает значения свойств групп свойств источника данных, данные источника данных и инициализации, которые в данный момент установлены на объект источника данных или значений свойств в группе свойств инициализации, которые в данный момент установлены на перечислитель.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Возвращает сведения обо всех свойствах, поддерживаемых поставщиком.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Задает свойства групп свойств источника данных и инициализации, для объектов источника данных или группу свойств инициализации, для перечислителей.|  
  
## Заметки  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) обязательный интерфейс для объектов источника данных и необязательного интерфейса для перечислителей.  Однако если перечислитель предоставляет [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), он должен предоставлять `IDBProperties`.  `IDBPropertiesImpl` реализует `IDBProperties` с помощью статической определенной функции [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md).  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)