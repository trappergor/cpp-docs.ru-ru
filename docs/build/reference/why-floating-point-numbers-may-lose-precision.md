---
title: Почему может уменьшиться точность чисел с плавающей запятой
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 4b001bff2f5327599fc5ad2ecae141976403ec58
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424071"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Почему может уменьшиться точность чисел с плавающей запятой

Десятичного значения с плавающей запятой, как правило, не имеют точного двоичного представления. Это является побочным эффектом представление данных с плавающей запятой в ЦП. По этой причине, может появиться к некоторой потере точности и некоторые операции с плавающей запятой может привести к непредвиденным результатам.

Такое поведение является результатом следующего вида:

- Двоичное представление десятичного числа не может быть точным.

- Существует несоответствие типов между чисел (например, совместное использование float и double).

Для решения проблемы, убедитесь, что значение больше или меньше, чем то, что требуется большинство программистов, или они получить и использовать библиотеку двоично-десятичный (BCD), которая будет поддерживать точность.

Двоичное представление значения с плавающей запятой влияет на точность и точность вычислений с плавающей запятой. Microsoft Visual C++ использует [формате с плавающей запятой IEEE](../../build/reference/ieee-floating-point-representation.md).

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

Для ЭПСИЛОН, можно использовать константы FLT_EPSILON, который определен для типа float как 1.192092896e-07F, или DBL_EPSILON, который определен для двойной как 2.2204460492503131e-016. Вам потребуется включить float.h для этих констант. Эти константы определены как наименьшее положительное число x, например, x + 1,0 не равно 1,0. Так как это очень небольшую величину, следует использовать заданное пользователем допустимое число для вычисления с очень больших чисел.

## <a name="see-also"></a>См. также

[Оптимизация кода](../../build/reference/optimizing-your-code.md)
