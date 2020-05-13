---
title: лямбда-выражения constexpr вC++
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 9467d9e404204012df6461adacd5dc4cdbdfe71d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179579"
---
# <a name="constexpr-lambda-expressions-in-c"></a>лямбда-выражения constexpr вC++

**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): лямбда-выражение может быть объявлено как **constexpr** или использоваться в константном выражении, если инициализация каждого элемента данных, который он захватывает или вводит, разрешена в константном выражении.

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

Лямбда-выражение является неявно **constexpr** , если его результат удовлетворяет требованиям функции **constexpr** :

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Если лямбда-выражение является неявно или явно и преобразуется в указатель **функции, то**результирующая функция также является **constexpr**:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>См. также раздел

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Объекты функции в стандартной библиотеке C++](../standard-library/function-objects-in-the-stl.md)<br/>
[Вызов функции](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)
