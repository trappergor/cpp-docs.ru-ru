---
title: "CDynamicAccessor::GetColumnFlags | Microsoft Docs"
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
  - "CDynamicAccessor.GetColumnFlags"
  - "ATL::CDynamicAccessor::GetColumnFlags"
  - "ATL.CDynamicAccessor.GetColumnFlags"
  - "CDynamicAccessor::GetColumnFlags"
  - "GetColumnFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnFlags - метод"
ms.assetid: b2ba2f3a-2c61-4a49-abfb-75823908ccf4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetColumnFlags
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает характеристики столбца.  
  
## Синтаксис  
  
```  
  
      bool GetColumnFlags(   
   DBORDINAL nColumn,   
   DBCOLUMNFLAGS* pFlags    
) const throw( );  
```  
  
#### Параметры  
 `nColumn`  
 \[in\] число столбцов.  Начало номера столбца с 1.  Значение 0 указывает на столбец закладки, если таковые имеются.  
  
 `pFlags`  
 \[out\] указатель на битовой маске, которая описывает характеристики столбца.  В разделе «перечисляемый тип DBCOLUMNFLAGS» в разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *справочнике программиста OLE DB*.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если характеристики столбца успешно извлечены.  В противном случае возвращается значение **false**.  
  
## Заметки  
 Число отрицательное значение смещения из одного столбца.  Столбец не является особым случаем; это закладки, если таковые имеются.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)