---
title: "CSimpleMapEqualHelper Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleMapEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelper class"
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс вспомогательного метода для класса [CSimpleMap](../../atl/reference/csimplemap-class.md).  
  
## Синтаксис  
  
```  
  
      template <  
   class TKey,  
   class TVal   
>  
class CSimpleMapEqualHelper  
```  
  
#### Параметры  
 `TKey`  
 Является ключевым элементом.  
  
 `TVal`  
 Элемент value.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleMapEqualHelper::IsEqualKey](../Topic/CSimpleMapEqualHelper::IsEqualKey.md)|\(Статический\) Проверяет равенство 2 ключей.|  
|[CSimpleMapEqualHelper::IsEqualValue](../Topic/CSimpleMapEqualHelper::IsEqualValue.md)|\(Статический\) Проверяет значения на равенство 2.|  
  
## Заметки  
 Этот класс признаков дополнение к классу `CSimpleMap`.  Он предоставляет методы для сравнения 2 элемента объекта `CSimpleMap` \(в частности, ключ и значение\), чтобы определить, равны ли они.  По умолчанию ключи и значения сравнитьы с помощью `operator==()`, но если сопоставление содержит сложные типы данных, которые нуждаются их собственном оператора равенства этот класс может переопределить, чтобы обеспечить дополнительные функциональные необходимые функциональные возможности.  
  
## Требования  
 **заголовок:** atlsimpcoll.h  
  
## См. также  
 [CSimpleMapEqualHelperFalse Class](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)