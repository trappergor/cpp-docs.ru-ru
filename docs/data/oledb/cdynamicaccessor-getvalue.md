---
title: "CDynamicAccessor::GetValue | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetValue"
  - "CDynamicAccessor::GetValue<ctype>"
  - "ATL.CDynamicAccessor.GetValue<ctype>"
  - "CDynamicAccessor.GetValue"
  - "CDynamicAccessor::GetValue"
  - "ATL.CDynamicAccessor.GetValue"
  - "ATL::CDynamicAccessor::GetValue"
  - "ATL::CDynamicAccessor::GetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetValue - метод"
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает данные для указанного столбца.  
  
## Синтаксис  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### Параметры  
 `ctype`  
 \[in\] a атрибутами параметр обработки любого типа данных, за исключением строковых типов \(**CHAR\***, **WCHAR\***\), которые требуют специальной обработки.  `GetValue` используется соответствующий тип данных, на основе которого указано ниже.  
  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Значение 0 указывает на столбец закладки, если таковые имеются.  
  
 `pColumnName`  
 \[in\] имя столбца.  
  
 `pData`  
 \[out\] указатель на содержимое указанного столбца.  
  
## Возвращаемое значение  
 Если необходимо передать строковые данные, используйте nontemplated версии `GetValue`.  Nontemplated версии этого метода, который возвращает значение **void\*** указывает на части буфера, который содержит указанные данные столбца.  Возвращает значение **NULL**, если столбец не найден.  
  
 Для всех других типов данных он проще использовать шаблонные версии `GetValue`.  Шаблонные версии возвращают **true** в успехе или **false** при сбое.  
  
## Заметки  
 Используйте nontemplated версии, чтобы возвращать столбцы, содержащие строки и шаблонная версии для столбцов, которые содержат другие типы данных.  
  
 В режиме отладки утверждение, возникает, если размер `pData` неравен до размера столбца, на который он указывает.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)