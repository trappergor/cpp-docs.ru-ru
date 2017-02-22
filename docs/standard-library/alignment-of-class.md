---
title: "Класс alignment_of | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.alignment_of"
  - "std::tr1::alignment_of"
  - "alignment_of"
  - "std.alignment_of"
  - "std::alignment_of"
  - "type_traits/std::alignment_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "выравнивание класса [TR1]"
  - "alignment_of"
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс alignment_of
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает выравнивание указанного типа.  Эта структура реализована на основе [alignof](../cpp/alignof-and-alignas-cpp.md).  Используйте `alignof` напрямую, если нужно просто запросить значение выравнивания.  Используйте функцию alignment\_of, когда нужна целочисленная константа, например, при отправке тегов.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct alignment_of;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Запрос типа содержит значение выравнивания типа `Ty`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс aligned\_storage](../standard-library/aligned-storage-class.md)