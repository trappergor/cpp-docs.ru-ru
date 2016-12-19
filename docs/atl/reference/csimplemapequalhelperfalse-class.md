---
title: "CSimpleMapEqualHelperFalse Class | Microsoft Docs"
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
  - "ATL::CSimpleMapEqualHelperFalse"
  - "CSimpleMapEqualHelperFalse"
  - "ATL.CSimpleMapEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelperFalse class"
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс вспомогательного метода для класса [CSimpleMap](../../atl/reference/csimplemap-class.md).  
  
## Синтаксис  
  
```  
  
template < class TKey, class TVal > class CSimpleMapEqualHelperFalse  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](../Topic/CSimpleMapEqualHelperFalse::IsEqualKey.md)|\(Статический\) Проверяет равенство 2 ключей.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](../Topic/CSimpleMapEqualHelperFalse::IsEqualValue.md)|\(Статический\) Возвращает значение false.|  
  
## Заметки  
 Этот класс признаков дополнение к классу `CSimpleMap`.  Она предоставляет метод для сравнения 2 элементов, содержащихся в объекте `CSimpleMap`, 2 или 2 значений ключа элемента позиции.  
  
 Сравнение значения всегда возвращает значение false, а кроме того, будут вызывать `ATLASSERT` с аргументом false, если он всегда производится ссылка.  В ситуациях, когда тест равенства не указан, этот класс обеспечивает сопоставление, содержащий пары " ключ\-значение ", чтобы правильно работать для большинства методов завершается ошибкой только в чётком образом, методов сравнения который зависит от того, как [CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md).  
  
## Требования  
 **Header:** atlsimpcoll.h  
  
## См. также  
 [CSimpleMapEqualHelper Class](../../atl/reference/csimplemapequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)