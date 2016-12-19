---
title: "CDynamicAccessor::GetColumnInfo | Microsoft Docs"
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
  - "GetColumnInfo"
  - "ATL.CDynamicAccessor.GetColumnInfo"
  - "ATL::CDynamicAccessor::GetColumnInfo"
  - "CDynamicAccessor.GetColumnInfo"
  - "CDynamicAccessor::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo - метод"
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает метаданные столбца, требуемые большинством объектов\-получателей.  
  
## Синтаксис  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### Параметры  
 `pRowset`  
 \[in\] указатель на интерфейс [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx).  
  
 *pColumns*  
 \[out\] указатель на памяти, в которой для возврата числа столбцов в наборе строк; это число включает столбец закладки, если таковое имеется.  
  
 *ppColumnInfo*  
 \[out\] указатель на памяти, в которой для возвращения массива структур **DBCOLUMNINFO**.  В разделе «структуры DBCOLUMNINFO» в разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *справочнике программиста OLE DB*.  
  
 `ppStringsBuffer`  
 \[out\] указатель на в памяти, чтобы вернуть указатель на хранилище для всех строк \(имена или использовать в *columnid* или для *pwszName*\) в одном блоке выделения.  
  
## Возвращаемое значение  
 Один из стандартных значений `HRESULT`.  
  
## Заметки  
 В разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) справочника *программиста OLE DB* сведения о типах данных **DBORDINAL**, **DBCOLUMNINFO** и **OLECHAR**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)