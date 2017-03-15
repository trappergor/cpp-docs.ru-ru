---
title: "BEGIN_ACCESSOR_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR_MAP - макрос"
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отмечает начало карты записей метода доступа.  
  
## Синтаксис  
  
```  
  
BEGIN_ACCESSOR_MAP(  
x  
,   
num  
 )  
  
```  
  
#### Параметры  
 *x*  
 \[входные данные\] Имя класса записей пользователя.  
  
 *num*  
 \[входные данные\] Число методов доступа в этой карте метода доступа.  
  
## Заметки  
 Если в наборе строк имеется несколько методов доступа, необходимо указать `BEGIN_ACCESSOR_MAP` в начале и использовать макрос `BEGIN_ACCESSOR` для каждого отдельного метода доступа. Макрос `BEGIN_ACCESSOR` выполняется с помощью макроса `END_ACCESSOR`. Карта метода доступа выполняется с помощью макроса `END_ACCESSOR_MAP`.  
  
 Если в записи пользователя имеется только один метод доступа, используйте макрос [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md).  
  
## Пример  
 [!CODE [NVC_OLEDB_Consumer#15](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#15)]  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)