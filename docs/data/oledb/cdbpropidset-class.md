---
title: "Класс CDBPropIDSet | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropIDSet"
  - "ATL.CDBPropIDSet"
  - "ATL::CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet - класс"
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс CDBPropIDSet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Наследуется от структуры **DBPROPIDSET** и добавляет конструктор, который инициализирует ключевые поля, а также метод доступа [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md).  
  
## Синтаксис  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Добавляет свойство в набор идентификатор свойства.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Конструктор.|  
|[SetGUID](../Topic/CDBPropIDSet::SetGUID.md)|Задает GUID набора идентификатор свойства.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cdbpropidset-operator-equal.md)|Присвоить содержимое одного заданного идентификатора свойства в другой.|  
  
## Заметки  
 Объект\-получатели OLE DB используют структуры **DBPROPIDSET**, чтобы передать массив идентификаторов свойства, для которых объект\-получатель может принимать данные свойства.  Свойства, определенные в одной структуре [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) принадлежат одному набор свойств.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)