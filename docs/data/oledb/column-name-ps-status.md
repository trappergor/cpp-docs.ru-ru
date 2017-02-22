---
title: "COLUMN_NAME_PS_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_NAME_PS_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_PS_STATUS - макрос"
ms.assetid: 134e1bfe-abfa-4b64-9159-e492f31de44b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_NAME_PS_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет привязку в наборе строк к конкретному столбцу в наборе строк.  Аналогично [COLUMN\_NAME](../Topic/COLUMN_NAME.md), за исключением того, что этот макрос также имеет точность, масштаб и состояния столбца.  
  
## Синтаксис  
  
```  
  
COLUMN_NAME_PS_STATUS(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
status )  
```  
  
#### Параметры  
 `pszName`  
 \[in\] указатель на имени столбца.  Имя должно быть строкой юникод.  Можно выполнить путем установки «L» перед именем, например: `L"MyColumn"`.  
  
 `nPrecision`  
 \[in\] максимальная точность столбца требуется выполнить привязку.  
  
 `nScale`  
 \[in\] масштаба столбца требуется выполнить привязку.  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
 *status*  
 \[in\] переменная, привязываемая к состояние столбца.  
  
## Заметки  
 В разделе [COLUMN\_NAME](../Topic/COLUMN_NAME.md) сведения о, макрос **COLUMN\_NAME\_\*** используются.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_NAME](../Topic/COLUMN_NAME.md)   
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../Topic/COLUMN_NAME_LENGTH.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../Topic/COLUMN_NAME_LENGTH_STATUS.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../Topic/COLUMN_NAME_PS_LENGTH.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../Topic/COLUMN_NAME_TYPE_STATUS.md)