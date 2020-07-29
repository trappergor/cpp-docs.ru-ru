---
title: лямбда-выражения constexpr в C++
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 24c70732093447649b3cfb460f63b2181efdf806
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213350"
---
# <a name="constexpr-lambda-expressions-in-c"></a>лямбда-выражения constexpr в C++

**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): лямбда-выражение может быть объявлено как **`constexpr`** или использоваться в константном выражении, когда инициализация каждого элемента данных, который он захватывает или вводит, разрешена в константном выражении.

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

Лямбда-выражение неявно, **`constexpr`** если его результат удовлетворяет требованиям **`constexpr`** функции:

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Если лямбда-выражение является неявно или явным **`constexpr`** и преобразуется в указатель функции, то результирующая функция также будет иметь **`constexpr`** следующее:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Объекты функций в стандартной библиотеке C++](../standard-library/function-objects-in-the-stl.md)<br/>
[Вызов функции](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)
