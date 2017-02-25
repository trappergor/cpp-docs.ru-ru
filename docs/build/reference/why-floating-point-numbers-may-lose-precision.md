---
title: "Почему может уменьшиться точность чисел с плавающей запятой | Microsoft Docs"
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
  - "DBL_EPSILON - константа"
  - "числа с плавающей запятой, точность"
  - "FLT_EPSILON - константа"
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Почему может уменьшиться точность чисел с плавающей запятой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Десятичные значения с плавающей запятой обычно не имеют точного двоичного представления.  Это побочный эффект представления центральным процессором данных с плавающей запятой.  Поэтому можно получить небольшую потерю точности и некоторые операции с плавающей запятой могут привести к неожиданным результатам.  
  
 Данное поведение возникает в результате выполнения одного из перечисленных ниже действий:  
  
-   Двоичное представление десятичных чисел может быть не точным.  
  
-   Существует тип несовпадения используемых чисел \(например, смешивание плавающей запятой и удвоение\).  
  
 Для разрешения поведения большинство программистов проверяют наличие значения, большего или меньшего, чем необходимое или возвращают и используют библиотеку десятичных чисел в двоичной кодировке \(BCD\), которая позволит поддерживать точность значений.  
  
 Двоичное представление значений с плавающей запятой влияет на точность и правильность расчета плавающей запятой.  Microsoft Visual C\+\+ использует [формат плавающей запятой IEEE](../../build/reference/ieee-floating-point-representation.md).  
  
## Пример  
  
```  
// Floating-point_number_precision.c  
// Compile options needed: none. Value of c is printed with a decimal   
// point precision of 10 and 6 (printf rounded value by default) to   
// show the difference  
#include <stdio.h>  
  
#define EPSILON 0.0001   // Define your own tolerance  
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))  
  
int main() {  
   float a, b, c;  
  
   a = 1.345f;  
   b = 1.123f;  
   c = a + b;  
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result  
   if (c == 2.468)            // Comment this line for correct result  
      printf_s("They are equal.\n");  
   else  
      printf_s("They are not equal! The value of c is %13.10f "  
                "or %f",c,c);  
}  
```  
  
  **Они не являются одинаковыми\!  Значение параметра c равно 2,4679999352 или 2,468000**    
## Комментарии  
 Для EPSILON можно использовать константу FLT\_EPSILON, которая определена для типа float как 1.192092896e\-07F или DBL\_EPSILON, которая определена для типа double как 2.2204460492503131e\-016.  Для этих констант необходимо включить файл float.h.  Эти константы определены как самые маленькие положительные числа x, например, x\+1.0 не равно 1.0.  Поскольку это очень маленькое число, следует задействовать определенный пользователем допуск для расчетов с использованием очень больших чисел.  
  
## См. также  
 [Оптимизация кода](../../build/reference/optimizing-your-code.md)