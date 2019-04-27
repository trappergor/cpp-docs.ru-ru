---
title: Аргументы по умолчанию
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
ms.openlocfilehash: 5ffc0301e7a89a379a2ea1eda9a113276df7a88e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154520"
---
# <a name="default-arguments"></a>Аргументы по умолчанию

Во многих случаях функции имеют аргументы, которые используются настолько редко, что достаточно значения по умолчанию. В таких случаях возможность задания аргументов по умолчанию позволяет указывать только те аргументы функции, которые важны в конкретном вызове. Чтобы проиллюстрировать этот принцип, рассмотрим пример, представленный в [перегрузка функций](../cpp/function-overloading.md).

```cpp
// Prototype three print functions.
int print( char *s );                  // Print a string.
int print( double dvalue );            // Print a double.
int print( double dvalue, int prec );  // Print a double with a
//  given precision.
```

Во многих приложениях для аргумента `prec` можно задать разумное значение по умолчанию, что исключает необходимость наличия двух функций:

```cpp
// Prototype two print functions.
int print( char *s );                    // Print a string.
int print( double dvalue, int prec=2 );  // Print a double with a
//  given precision.
```

Реализация `print` функция слегка отличается чтобы отразить тот факт, что для типа существует только одна такая функция **double**:

```cpp
// default_arguments.cpp
// compile with: /EHsc /c

// Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.

#include <iostream>
#include <math.h>
using namespace std;

int print( double dvalue, int prec ) {
   // Use table-lookup for rounding/truncation.
   static const double rgPow10[] = {
      10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,
         10E1,  10E2,  10E3,  10E4, 10E5,  10E6
   };
   const int iPowZero = 6;
   // If precision out of range, just print the number.
   if( prec >= -6 && prec <= 7 )
      // Scale, truncate, then rescale.
      dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *
      rgPow10[iPowZero - prec];
   cout << dvalue << endl;
   return cout.good();
}
```

Чтобы вызвать новую функцию `print`, используйте следующий код:

```cpp
print( d );    // Precision of 2 supplied by default argument.
print( d, 0 ); // Override default argument to achieve other
//  results.
```

При использовании аргументов по умолчанию обратите внимание на следующие моменты:

- Аргументы по умолчанию используются только в вызовах функции, в которых опущены заключительные аргументы — они должны быть последними аргументами. Поэтому следующий код недопустим:

    ```cpp
    int print( double dvalue = 0.0, int prec );
    ```

- Переопределение аргумента по умолчанию в последующих объявлениях не допускается, даже если переопределение совпадает с оригиналом. Поэтому приведенный ниже код вызывает ошибку:

    ```cpp
    // Prototype for print function.
    int print( double dvalue, int prec = 2 );

    ...

    // Definition for print function.
    int print( double dvalue, int prec = 2 )
    {
    ...
    }
    ```

   Проблема с этим кодом заключается в том, что объявление функции в определении переопределяет аргумент по умолчанию для аргумента `prec`.

- В последующих определениях допускается добавлять дополнительные аргументы по умолчанию.

- Аргументы по умолчанию могут указываться для указателей на функции. Пример:

    ```cpp
    int (*pShowIntVal)( int i = 0 );
    ```