---
title: Почему может уменьшиться точность чисел с плавающей запятой
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 373ce9fa2c2c96fac349940076873a4a637a9dbe
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298718"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Почему может уменьшиться точность чисел с плавающей запятой

Десятичные значения с плавающей запятой, как правило, не имеют точного двоичного представления. Это побочный эффект того, как данные с плавающей запятой представляются в ЦП. По этой причине может происходить некоторая потеря точности, а некоторые операции с плавающей запятой могут давать непредвиденный результат.

Причины такого поведения могут быть следующими.

- Двоичное представление десятичного числа может быть неточным.

- Несоответствие типов используемых чисел (например, float и double).

Для решения этой проблемы большинство программистов либо гарантируют, что значение больше или меньше необходимого, либо используют библиотеку двоично-десятичного кода (BCD), которая будет обеспечивать точность.

Двоичное представление значений с плавающей запятой влияет на точность и правильность вычислений с плавающей запятой. В Microsoft Visual C++ используется [формат IEEE с плавающей запятой](ieee-floating-point-representation.md).

## <a name="example"></a>Пример

```c
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

Для EPSILON можно использовать константу FLT_EPSILON, которая определена для float как 1,192092896e-07F, или DBL_EPSILON, которая определена для double как 2,2204460492503131e-016. Для этих констант необходимо включить файл float.h. Эти константы определены как наименьшее положительное число x, при котором x + 1,0 не равно 1,0. Так как это очень маленькое число, для вычислений с очень большими числами следует использовать пользовательскую погрешность.

## <a name="see-also"></a>См. также

[Оптимизация кода](optimizing-your-code.md)
