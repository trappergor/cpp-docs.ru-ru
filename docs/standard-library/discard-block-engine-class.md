---
title: "Класс discard_block_engine | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.discard_block_engine"
  - "std.tr1.discard_block_engine"
  - "std::tr1::discard_block_engine"
  - "random/std::tr1::discard_block_engine"
  - "discard_block_engine"
  - "tr1::discard_block_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discard_block_engine - класс"
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс discard_block_engine
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает случайную последовательность, удаляя значения, возвращенные базовым механизмом.  
  
## Синтаксис  
  
```  
template<class Engine, size_t P, size_t R> class discard_block_engine;  
```  
  
#### Параметры  
 `Engine`  
 Тип базового механизма.  
  
 `P`  
 **Размер блока**.  Количество значений в каждом блоке.  
  
 `R`  
 **Используемый блок**.  Количество используемых значений в каждом блоке.  Остальные значения удаляются \(`P` \- `R`\).  **Предусловие**: `0 < R ≤ P`  
  
## Члены  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 Дополнительные сведения о членах механизма см. в разделе [\<random\>](../standard-library/random.md).  
  
## Заметки  
 Этот класс шаблона описывает адаптер механизма, формирующий значения за счет удаления некоторых значений, возвращаемых базовым механизмом.  
  
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)