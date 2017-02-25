---
title: "CSimpleArrayEqualHelper Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleArrayEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelper class"
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleArrayEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс вспомогательного метода для класса [CSimpleArray](../../atl/reference/csimplearray-class.md).  
  
## Синтаксис  
  
```  
  
      template <  
   class T   
>  
class CSimpleArrayEqualHelper  
```  
  
#### Параметры  
 `T`  
 Производный класс.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleArrayEqualHelper::IsEqual](../Topic/CSimpleArrayEqualHelper::IsEqual.md)|\(Статический\) Проверяет 2 элемента объекта `CSimpleArray` на равенство.|  
  
## Заметки  
 Этот класс признаков дополнение к классу `CSimpleArray`.  Он предоставляет метод для сравнения 2 элемента, хранящегося в объекте `CSimpleArray`.  По умолчанию элементы сравнитьо с помощью **operator\=\(\)**, но если массив содержит сложные типы данных, которые нуждаются их собственном оператора равенства, необходимо переопределить этот класс.  
  
## Требования  
 **Header:** atlsimpcoll.h  
  
## См. также  
 [CSimpleArray Class](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse Class](../Topic/CSimpleArrayEqualHelperFalse%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)