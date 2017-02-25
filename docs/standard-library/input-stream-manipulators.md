---
title: "Манипуляторы входных потоков | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "объекты потока ввода"
  - "потоки ввода, манипуляторы"
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Манипуляторы входных потоков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Многие манипуляторов, например [setprecision](../Topic/setprecision.md), определенных для класса `ios` и таким образом применяются к входным потоки.  Несколько манипуляторов, фактически влияют на объекты входного потока.  Этих преобразует, наиболее важной манипуляторов, `dec`, `oct` и `hex` корневой, определяющие базу преобразования, используемую с номерами от входного потока.  
  
 При извлечении, манипулятор `hex` включает обработку различных форматов.  Например, C, C, 0xc, 0xC, 0Xc и 0XC все интерпретируются как десятичное целое число 12.  Любой символ, отличный от 0 до 9, F, a с a по f, x и x заканчивается числовое преобразование.  Таким образом последовательность `"124n5"` нужно преобразовать в число 124 с набором в [basic\_ios::fail](../Topic/basic_ios::fail.md).  
  
## См. также  
 [Потоки ввода](../standard-library/input-streams.md)