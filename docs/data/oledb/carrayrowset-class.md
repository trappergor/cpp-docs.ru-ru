---
title: "Класс CArrayRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CArrayRowset<TAccessor>"
  - "ATL.CArrayRowset"
  - "CArrayRowset"
  - "ATL::CArrayRowset"
  - "ATL::CArrayRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArrayRowset - класс"
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс CArrayRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Доступ к элементам набора строк с помощью синтаксиса массива.  
  
## Синтаксис  
  
```  
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### Параметры  
 `TAccessor`  
 Тип класса доступа, который требуется использовать набор строк.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|Конструктор.|  
|[Моментальный снимок](../../data/oledb/carrayrowset-snapshot.md)|Считывает весь набор строк в память.|  
  
### Операторы  
  
|||  
|-|-|  
|[Оператор &#91;&#93;](../Topic/CArrayRowset::operator.md)|Получает элемент набора строк.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[CArrayRowset::m\_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|Количество прочитанных строк уже.|  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CRowset](../Topic/CRowset%20Class.md)