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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298718"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Почему может уменьшиться точность чисел с плавающей запятой

Десятичные значения с плавающей запятой обычно не имеют точного двоичного представления. Это побочный результат того, как ЦП представляет данные с плавающей запятой. По этой причине вы можете столкнуться с некоторой потерей точности, а некоторые операции с плавающей запятой могут привести к непредвиденным результатам.

Это поведение является результатом одного из следующих действий:

- Двоичное представление десятичного числа может быть неточным.

- Несоответствие типов используемых чисел (например, смешивание float и Double).

Для решения этой проблемы большинство программистов либо гарантируют, что значение больше или меньше необходимого, либо получают и используют двоично-закодированную библиотеку (BCD), которая будет поддерживать точность.

Двоичное представление значений с плавающей запятой влияет на точность и точность вычислений с плавающей запятой. В Microsoft C++ Visual используется [Формат с плавающей запятой IEEE](ieee-floating-point-representation.md).

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

## <a name="comments"></a>Comments

Для ЭПСИЛОН можно использовать константы FLT_EPSILON, определенные для float как 1.192092896 e-07F или DBL_EPSILON, которые определены для типа Double как 2.2204460492503131 e-016. Для этих констант необходимо включить float. h. Эти константы определяются как наименьшее положительное число x, что означает, что x + 1.0 не равно 1,0. Так как это очень небольшое число, следует применять определенное пользователем отклонение для вычислений, включающих очень большие числа.

## <a name="see-also"></a>См. также:

[Оптимизация кода](optimizing-your-code.md)
