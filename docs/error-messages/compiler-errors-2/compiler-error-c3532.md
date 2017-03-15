---
title: "Ошибка компилятора C3532 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3532"
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": неверное использование ключевого слова "auto"  
  
 Указанный тип нельзя объявлять с помощью ключевого слова `auto`.  Например, нельзя использовать ключевое слово `auto` для объявления массива или типа значения, возвращаемого методом.  
  
### Исправление этой ошибки  
  
1.  Убедитесь, что выражение инициализации возвращает допустимый тип.  
  
2.  Убедитесь, что не выполняется объявление массива или типа значения, возвращаемого методом.  
  
## Пример  
 Следующий пример вызывает ошибку C3532, поскольку ключевое слово `auto` нельзя использовать для объявления типа значения, возвращаемого методом.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## Пример  
 Следующий пример вызывает ошибку C3532, поскольку ключевое слово `auto` нельзя использовать для объявления массива.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)