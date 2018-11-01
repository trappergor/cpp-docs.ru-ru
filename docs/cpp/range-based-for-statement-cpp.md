---
title: Основанное на диапазоне выражение for (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: 965159a3bd4f92bbb1bd044882451a2b98daf6aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469996"
---
# <a name="range-based-for-statement-c"></a>Основанное на диапазоне выражение for (C++)

Циклически и последовательно выполняет оператор (`statement`) каждого элемента в выражении (`expression`).

## <a name="syntax"></a>Синтаксис

```
for ( for-range-declaration : expression )
   statement
```

## <a name="remarks"></a>Примечания

Используйте по диапазону **для** инструкции для создания циклов, которые должны выполняться по «диапазон», которая определяется как все, что можно выполнить итерацию — например, `std::vector`, или любые другие стандартной библиотеки C++ последовательности, диапазон которого определяется `begin()` и `end()`. Имя, которое объявляется в `for-range-declaration` часть является локальным для **для** инструкции и не может быть повторно объявлена в `expression` или `statement`. Обратите внимание, что [автоматически](../cpp/auto-cpp.md) ключевое слово является предпочтительным в `for-range-declaration` часть инструкции.

**Возможности Visual Studio 2017:** основанных на диапазоне циклы больше не требуется, чтобы begin() и end() возвращали объекты одного типа. Это позволяет функции end() возвращать объект sentinel, используемый, например, диапазонами, как определено в предложении Ranges-V3. Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) и в документе о [библиотеке range-v3 на сайте GitHub](https://github.com/ericniebler/range-v3).

Этот код показан способ использования по диапазону **для** циклы для перебора массива и вектора:

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

Выходные данные этого кода:

```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
end of integer array test

0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159
end of vector test
```

По диапазону **для** цикл завершается, когда один из них в `statement` выполняется: [break](../cpp/break-statement-cpp.md), [возвращают](../cpp/return-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md) для с метками оператор вне по диапазону **для** цикла. Объект [по-прежнему](../cpp/continue-statement-cpp.md) инструкции в основанном на диапазоне **для** цикла завершает только текущую итерацию.

Имейте в виду следующие факты о по диапазону **для**:

- Такие циклы автоматически распознают массивы.

- Такие циклы автоматически распознают контейнеры с методами `.begin()` и `.end()`.

- Для всех остальных итераторов в них используются поиск, зависящий от аргументов (`begin()` и `end()`).

## <a name="see-also"></a>См. также

[auto](../cpp/auto-cpp.md)<br/>
[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Оператор for (C++)](../cpp/for-statement-cpp.md)