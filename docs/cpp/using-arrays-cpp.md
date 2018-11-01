---
title: Использование массивов (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
ms.openlocfilehash: 7f7a987a2b4c18e59dd058ccfc4375c304188398
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575517"
---
# <a name="using-arrays-c"></a>Использование массивов (C++)

К отдельным элементам массива можно обращаться при помощи оператора индекса массива (`[ ]`). Если в выражении используется одномерный массив, в котором нет индекса, то вычисление преобразует имя массива в указатель на первый элемент массива.

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

Если используются многомерные массивы, в выражениях можно использовать различные сочетания.

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

В приведенном выше коде `multi` является трехмерный массив типа **двойные**. `p2multi` Указатель указывает на массив объектов типа **двойные** размером 3. В этом примере массив используется с одним, двумя и тремя индексами. Хотя чаще всего определяют все индексы, в операторе `cout` иногда бывает удобнее выбирать определенное подмножество элементов массива, как показано в операторах, следующих за указанием объекта `cout`.

## <a name="see-also"></a>См. также

[Массивы](../cpp/arrays-cpp.md)