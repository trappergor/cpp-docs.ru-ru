---
title: "CUtlProps::IsValidValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps::IsValidValue"
  - "CUtlProps.IsValidValue"
  - "IsValidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsValidValue - метод"
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::IsValidValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется для проверки, прежде чем устанавливать свойство.  
  
## Синтаксис  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### Параметры  
 `iCurSet`  
 Индекс массива набора свойств; ноль, если только один набор свойств.  
  
 `pDBProp`  
 Идентификатор свойства и новое значение в структуре [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx).  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  Возвращаемое значение по умолчанию `S_OK`.  
  
## Заметки  
 Если существуют какие\-либо процедуры проверки, следует выполнить над значением, которое планируется использовать для задания свойства, необходимо переопределить этой функции.  Например, можно проверить **DBPROP\_AUTH\_PASSWORD** для таблицы пароля, чтобы указать допустимое значение.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)