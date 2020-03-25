---
title: Основанное на диапазоне выражение for (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: 504f177cf68b978642f15ba4799cab8cb517f447
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188354"
---
# <a name="range-based-for-statement-c"></a>Основанное на диапазоне выражение for (C++)

Циклически и последовательно выполняет оператор (`statement`) каждого элемента в выражении (`expression`).

## <a name="syntax"></a>Синтаксис

```
for ( for-range-declaration : expression )
   statement
```

## <a name="remarks"></a>Remarks

Используйте оператор на основе диапазона **for** для создания циклов, которые должны выполняться с помощью диапазона, который определен как любой объект, по которому можно выполнить итерацию, например `std::vector`или любую другую C++ последовательность стандартной библиотеки, диапазон которой определяется `begin()` и `end()`. Имя, объявленное в `for-range-declaration` части, является локальным для оператора **for** и не может быть повторно объявлено в `expression` или `statement`. Обратите внимание, что ключевое слово [Auto](../cpp/auto-cpp.md) является предпочтительным в `for-range-declaration` части инструкции.

**Новые в Visual Studio 2017:**  Для циклов for на основе диапазонов больше не требуется, чтобы операторы Begin () и End () возвращали объекты одного и того же типа. Это позволяет функции end() возвращать объект sentinel, используемый, например, диапазонами, как определено в предложении Ranges-V3. Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](https://wg21.link/p0184r0) и в документе о [библиотеке range-v3 на сайте GitHub](https://github.com/ericniebler/range-v3).

В этом коде показано, как использовать циклы **for** на основе диапазона для итерации по массиву и вектору.

```cpp
// range-based-for.cpp
// compile by using: cl /EHsc /nologo /W4
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // Basic 10-element integer array.
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    // Range-based for loop to iterate through the array.
    for( int y : x ) { // Access by value using a copy declared as a specific type.
                       // Not preferred.
        cout << y << " ";
    }
    cout << endl;

    // The auto keyword causes type inference to be used. Preferred.

    for( auto y : x ) { // Copy of 'x', almost always undesirable
        cout << y << " ";
    }
    cout << endl;

    for( auto &y : x ) { // Type inference by reference.
        // Observes and/or modifies in-place. Preferred when modify is needed.
        cout << y << " ";
    }
    cout << endl;

    for( const auto &y : x ) { // Type inference by const reference.
        // Observes in-place. Preferred when no modify is needed.
        cout << y << " ";
    }
    cout << endl;
    cout << "end of integer array test" << endl;
    cout << endl;

    // Create a vector object that contains 10 elements.
    vector<double> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back(i + 0.14159);
    }

    // Range-based for loop to iterate through the vector, observing in-place.
    for( const auto &j : v ) {
        cout << j << " ";
    }
    cout << endl;
    cout << "end of vector test" << endl;
}
```

Результат выглядит так:

```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
end of integer array test

0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159
end of vector test
```

Цикл **for** , основанный на диапазоне, завершается, когда выполняется одно из следующих действий в `statement`: [разрыв](../cpp/break-statement-cpp.md), [Возврат](../cpp/return-statement-cpp.md)или [Переход](../cpp/goto-statement-cpp.md) к оператору с меткой за пределами цикла **for** , основанного на диапазоне. Оператор [Continue](../cpp/continue-statement-cpp.md) в цикле **for** на основе диапазона завершает только текущую итерацию.

Помните о таких фактах, **как на основе диапазона:**

- Такие циклы автоматически распознают массивы.

- Такие циклы автоматически распознают контейнеры с методами `.begin()` и `.end()`.

- Для всех остальных итераторов в них используются поиск, зависящий от аргументов (`begin()` и `end()`).

## <a name="see-also"></a>См. также раздел

[auto](../cpp/auto-cpp.md)<br/>
[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Оператор for (C++)](../cpp/for-statement-cpp.md)
