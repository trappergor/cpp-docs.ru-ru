---
title: "CRowset::MoveNext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.MoveNext"
  - "ATL.CRowset.MoveNext"
  - "ATL::CRowset<TAccessor>::MoveNext"
  - "CRowset<TAccessor>.MoveNext"
  - "CRowset.MoveNext"
  - "CRowset<TAccessor>::MoveNext"
  - "CRowset::MoveNext"
  - "ATL::CRowset::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext - метод"
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемещение курсора к следующей записи.  
  
## Синтаксис  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### Параметры  
 `lSkip`  
 \[in\] число строк, которые нужно пропустить до получения.  
  
 `bForward`  
 \[in\] передайте **true** для перемещения переднее к следующей записи, **false** для перехода обратно.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  Когда конец набора строк достигался, возвращается значение **DB\_S\_ENDOFROWSET**.  
  
## Заметки  
 Последовательная получить следующую строку из объекта `CRowset`, вспоминая предыдущую положение.  При необходимости можно выбрать пропустить поиск строки `lSkip` или переместить его.  
  
 Этот метод требуется установить следующие свойства до вызова метода **Открыть** на таблице или команда, содержащий набор строк:  
  
-   **DBPROP\_CANSCROLLBACKWARDS** должен быть `VARIANT_TRUE` при `lSkip` \< 0  
  
-   **DBPROP\_CANFETCHBACKWARDS** должен быть `VARIANT_TRUE` при `bForward` \= false  
  
 В противном случае \(если `lSkip` \>\= 0 и `bForward` \= true\), нет необходимости устанавливать все дополнительные свойства.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)