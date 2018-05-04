---
title: Почему может уменьшиться точность чисел с плавающей запятой | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb673f087d98f6c7acdd1e98b5649cc84a48d277
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Почему может уменьшиться точность чисел с плавающей запятой
Десятичные значения с плавающей запятой обычно не имеют точного двоичного представления. Это является побочным эффектом ЦП представление данных с плавающей запятой. По этой причине происходит потеря точности и некоторые операции с плавающей запятой может привести к непредвиденным результатам.  
  
 Такое поведение является результатом следующего вида:  
  
-   Двоичное представление десятичного числа может быть точно.  
  
-   Существует несоответствие типов между чисел (например, смешивая float и double).  
  
 Чтобы устранить проблему, большинство программистов убедитесь, что значение больше или меньше, чем то, что требуется, или же их получить и использовать библиотеку двоично-десятичный (BCD), которая будет поддерживать точность.  
  
 Двоичное представление значений с плавающей запятой влияет на точность и правильность вычислений с плавающей запятой. Microsoft Visual C++ использует [формате с плавающей запятой IEEE](../../build/reference/ieee-floating-point-representation.md).  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
They are not equal! The value of c is  2.4679999352 or 2.468000  
```  
  
## <a name="comments"></a>Комментарии  
 Для EPSILON, можно использовать константы FLT_EPSILON, который определен для типа float, как 1, 192092896e-07F, или DBL_EPSILON, который определен для двойного как 2, 2204460492503131e-016. Необходимо включить файл float.h для этих констант. Эти константы определены как наименьшее положительное число x, например, x + 1,0 не равно 1.0. Поскольку это очень небольшую величину, следует использовать заданное пользователем допустимое расчетов очень больших чисел.  
  
## <a name="see-also"></a>См. также  
 [Оптимизация кода](../../build/reference/optimizing-your-code.md)