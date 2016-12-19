---
title: "IConvertTypeImpl::CanConvert | Microsoft Docs"
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
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert - метод"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConvertTypeImpl::CanConvert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет сведения о доступности преобразований типов в команде или в наборе строк.  
  
## Синтаксис  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### Параметры  
 В разделе [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Использует преобразование данных OLE DB в `MSADC.DLL`.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)