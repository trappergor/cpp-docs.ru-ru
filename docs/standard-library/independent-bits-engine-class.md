---
title: "Класс independent_bits_engine | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.independent_bits_engine"
  - "std::tr1::independent_bits_engine"
  - "tr1::independent_bits_engine"
  - "tr1.independent_bits_engine"
  - "independent_bits_engine"
  - "random/std::tr1::independent_bits_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "independent_bits_engine - класс"
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс independent_bits_engine
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает случайную последовательность чисел с указанным числом разрядов, перемешивая разряды из значений, возвращенных базовым механизмом.  
  
## Синтаксис  
  
```  
template<class Engine, size_t W, class UIntType> class independent_bits_engine;  
```  
  
#### Параметры  
 `Engine`  
 Тип базового механизма.  
  
 `W`  
 **Размер слова**.  Размер каждого полученного числа в битах.  **Предусловие**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 Беззнаковый целочисленный тип результата.  Возможные типы см. в разделе [\<random\>](../standard-library/random.md).  
  
## Члены  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Дополнительные сведения о членах механизма см. в разделе [\<random\>](../standard-library/random.md).  
  
## Заметки  
 Этот класс шаблона описывает *адаптер механизма*, формирующий значения за счет упаковки разрядов из значений, возвращаемых базовым механизмом, что приводит к получению `W`\-разрядных значений.  
  
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)