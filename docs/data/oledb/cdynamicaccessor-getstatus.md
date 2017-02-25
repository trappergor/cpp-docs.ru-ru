---
title: "CDynamicAccessor::GetStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::GetStatus"
  - "CDynamicAccessor.GetStatus"
  - "ATL.CDynamicAccessor.GetStatus"
  - "CDynamicAccessor::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus - метод"
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает состояние выбранного столбца.  
  
## Синтаксис  
  
```  
  
      bool GetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS* pStatus    
) const throw( );  
bool GetStatus(  
   const CHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
bool GetStatus(  
   const WCHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
```  
  
#### Параметры  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Значение 0 указывает на столбец закладки, если таковые имеются.  
  
 `pColumnName`  
 \[in\] указатель на символьной строки, содержащей имя столбца.  
  
 `pStatus`  
 \[out\] указатель на переменную, содержащую состояния столбца.  В разделе [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) справочника *программиста OLE DB* дополнительные сведения.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если указанный столбец найден.  В противном случае эта функция возвращает **false**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../Topic/CDynamicAccessor::SetStatus.md)