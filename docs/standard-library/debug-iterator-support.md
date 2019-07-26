---
title: Debug Iterator Support
ms.date: 09/13/2018
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
- C++ Standard Library, debug iterator support
- iterators, debug iterator support
- iterators, incompatible
- incompatible iterators
- debug iterator support
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
ms.openlocfilehash: 3ccb618c9a3c6b21d6ffe3fbbce7b6c1140e0564
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450592"
---
# <a name="debug-iterator-support"></a>Debug Iterator Support

Библиотека времени выполнения Visual C++ обнаруживает некорректное использование итераторов, выполняет проверочное утверждение и отображает диалоговое окно во время выполнения. Чтобы включить поддержку отладочных итераторов, необходимо использовать отладочные версии стандартной библиотеки C++ и библиотеки времени выполнения C для компиляции программы. Дополнительные сведения см. в разделе [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md). Сведения об использовании проверяемых итераторов см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

В стандарте языка C++ описано, как функции-члены могут сделать недействительными итераторы в контейнер. Ниже приведены два примера:

- В случае удаления элемента из контейнера итераторы в этот элемент становятся недействительными.

- Увеличение размера [вектора](../standard-library/vector.md) с помощью операции выталкивания или вставки делает недействительными итераторы в `vector`.

## <a name="invalid-iterators"></a>Недопустимые итераторы

При компиляции данного примера программы в режиме отладки во время выполнения она выполняет подтверждение и прекращает выполнение.

```cpp
// iterator_debugging_0.cpp
// compile by using /EHsc /MDd
#include <vector>
#include <iostream>

int main() {
   std::vector<int> v {10, 15, 20};
   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

## <a name="using-iteratordebuglevel"></a>Использование _ITERATOR_DEBUG_LEVEL

Для выключения функции отладки итераторов в отладочной сборке можно использовать макрос препроцессора [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md). Эта программа не утверждает, но по-прежнему вызывает неопределенное поведение.

```cpp
// iterator_debugging_1.cpp
// compile by using: /EHsc /MDd
#define _ITERATOR_DEBUG_LEVEL 0
#include <vector>
#include <iostream>

int main() {
    std::vector<int> v {10, 15, 20};

   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

```Output
20
-572662307
```

## <a name="unitialized-iterators"></a>Итераторы неинициализированные

Утверждение также возникает при попытке использования итератора до его инициализации, как показано ниже:

```cpp
// iterator_debugging_2.cpp
// compile by using: /EHsc /MDd
#include <string>
using namespace std;

int main() {
   string::iterator i1, i2;
   if (i1 == i2)
      ;
}
```

## <a name="incompatible-iterators"></a>Несовместимые итераторы

Следующий пример кода вызывает проверочное утверждение, так как два итератора для алгоритма [for_each](../standard-library/algorithm-functions.md#for_each) несовместимы. Алгоритмы пытаются проверить, ссылаются ли предоставляемые в них итераторы на один и тот же контейнер.

```cpp
// iterator_debugging_3.cpp
// compile by using /EHsc /MDd
#include <algorithm>
#include <vector>
using namespace std;

int main()
{
    vector<int> v1 {10, 20};
    vector<int> v2 {10, 20};

    // The next line asserts because v1 and v2 are
    // incompatible.
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );
}
```

Обратите внимание, что в примере используется лямбда-выражение `[] (int& elem) { elem *= 2; }`, а не функция. Несмотря на то что этот выбор никак не влияет на сбой утверждения (аналогичная функция приведет примерно к такому же сбою), лямбда-выражения являются очень полезным инструментом для выполнения задач с объектами функций. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../cpp/lambda-expressions-in-cpp.md).

## <a name="iterators-going-out-of-scope"></a>Итераторы выходят за пределы области

Проверка итератора отладки также приводит к тому, что переменная итератора, объявленная в цикле **for** , находится вне области действия, когда заканчивается область цикла **for** .

```cpp
// iterator_debugging_4.cpp
// compile by using: /EHsc /MDd
#include <vector>
#include <iostream>
int main() {
   std::vector<int> v {10, 15, 20};

   for (std::vector<int>::iterator i = v.begin(); i != v.end(); ++i)
      ;   // do nothing
   --i;   // C2065
}
```

## <a name="destructors-for-debug-iterators"></a>Деструкторы для отладочных итераторов

Отладочные итераторы имеют нетривиальные деструкторы. Если деструктор не выполняется, но память объекта освобождается, может произойти нарушение прав доступа и повреждение данных. Рассмотрим следующий пример.

```cpp
// iterator_debugging_5.cpp
// compile by using: /EHsc /MDd
#include <vector>
struct base {
   // TO FIX: uncomment the next line
   // virtual ~base() {}
};

struct derived : base {
   std::vector<int>::iterator m_iter;
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}
   ~derived() {}
};

 int main() {
   std::vector<int> vect( 10 );
   base * pb = new derived( vect.begin() );
   delete pb;  // doesn't call ~derived()
   // access violation
}
```

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)
