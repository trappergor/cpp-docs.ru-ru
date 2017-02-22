---
title: "CDynamicAccessor::SetLength | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::SetLength"
  - "CDynamicAccessor.SetLength"
  - "CDynamicAccessor::SetLength"
  - "ATL.CDynamicAccessor.SetLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetLength - метод"
ms.assetid: 8109ae73-04ec-4a47-be97-ba1e60080384
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает длину выбранного столбца.  
  
## Синтаксис  
  
```  
  
      bool SetLength(   
   DBORDINAL nColumn,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const CHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
```  
  
#### Параметры  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Значение 0 указывает на столбец закладки, если таковые имеются.  
  
 `nLength`  
 \[in\] длина столбца в байтах.  
  
 `pColumnName`  
 \[in\] указатель на символьной строки, содержащей имя столбца.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если указанная длина столбца устанавливается успешно.  В противном случае эта функция возвращает **false**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetLength](../../data/oledb/cdynamicaccessor-getlength.md)