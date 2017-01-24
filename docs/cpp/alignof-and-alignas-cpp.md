---
title: "alignof и alignas (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# alignof и alignas (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Спецификатор типа `alignas` — стандартный для C\+\+ переносимый способ задания настраиваемого выравнивания переменных и пользовательских типов.  Оператор `alignof` — аналогичен стандартному переносимому способу получения выравнивания указанного типа или переменной.  
  
## Пример  
 `alignas` можно использовать для класса, прохода или объединения, а также для отдельных членов.  При обнаружении нескольких спецификаторов `alignas` компилятор выберет самый строгий из них \(который имеет наибольшее значение\).  
  
```  
struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  
…  
cout << alignof(Bar) << endl; // output: 16  
  
```  
  
## См. также  
 [Выравнивание](../cpp/alignment-cpp-declarations.md)