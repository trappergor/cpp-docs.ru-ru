---
title: "CDynamicAccessor::SetValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicAccessor.SetValue"
  - "ATL::CDynamicAccessor::SetValue"
  - "ATL::CDynamicAccessor::SetValue<ctype>"
  - "CDynamicAccessor.SetValue"
  - "ATL.CDynamicAccessor.SetValue<ctype>"
  - "CDynamicAccessor::SetValue"
  - "CDynamicAccessor::SetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetValue - метод"
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Хранение данных определенным столбцом.  
  
## Синтаксис  
  
```  
  
      template < class ctype >    
bool SetValue(   
   DBORDINAL nColumn,   
   const ctype& data    
) throw( );  
template < class ctype >    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data    
) throw( );  
template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data   
) throw( );  
```  
  
#### Параметры  
 `ctype`  
 \[in\] a атрибутами параметр обработки любого типа данных, за исключением строковых типов \(**CHAR\***, **WCHAR\***\), которые требуют специальной обработки.  `GetValue` используется соответствующий тип данных, на основе которого указано ниже.  
  
 `pColumnName`  
 \[in\] указатель на символьной строки, содержащей имя столбца.  
  
 `data`  
 \[in\] указатель на адрес памяти, содержащие данные.  
  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Значение 0 указывает на столбец закладки, если таковые имеются.  
  
## Возвращаемое значение  
 Если следует разместить строковые данные, используйте nontemplated версии `GetValue`.  Nontemplated версии этого метода, который возвращает значение **void\*** указывает на части буфера, который содержит указанные данные столбца.  Возвращает значение **NULL**, если столбец не найден.  
  
 Для всех других типов данных он проще использовать шаблонные версии `GetValue`.  Шаблонные версии возвращают **true** в успехе или **false** при сбое.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)