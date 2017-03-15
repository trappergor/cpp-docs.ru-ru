---
title: "CDynamicParameterAccessor::CDynamicParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::CDynamicParameterAccessor"
  - "CDynamicParameterAccessor.CDynamicParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicParameterAccessor - класс, конструктор"
  - "CDynamicParameterAccessor - метод"
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::CDynamicParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Конструктор.  
  
## Синтаксис  
  
```  
  
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor( eBlobHandling, nBlobSize )  
```  
  
#### Параметры  
 `eBlobHandling`  
 Определяет, как данные больших двоичных объектов обрабатываться.  Значение по умолчанию **DBBLOBHANDLING\_DEFAULT**.  В разделе [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) для описания значений **DBBLOBHANDLINGENUM**.  
  
 `nBlobSize`  
 Максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА в байтах. данные столбца с этим значением обрабатывается как БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ.  Значение по умолчанию — 8,000.  Дополнительные сведения см. в разделе [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  
  
## Заметки  
 Конструктор [CDynamicAccessor::CDynamicAccessor](../Topic/CDynamicAccessor::CDynamicAccessor.md) см. дополнительные сведения об обработке БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)