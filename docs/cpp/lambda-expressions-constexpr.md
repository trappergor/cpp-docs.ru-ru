---
title: constexpr лямбда-выражения в C++ | Документация Майкрософт
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b78fa3de7777ffc6702902cf967a405595caf12f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408207"
---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr лямбда-выражения в C++
**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): лямбда-выражение может быть объявлен как **constexpr** или использовать в выражении констант при инициализации каждого элемент данных, он фиксирует или вводит допускается в константном выражении.  

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
Лямбда-выражения является неявно **constexpr** Если результат не соответствует требованиям **constexpr** функции:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Если лямбда-выражение неявно или явно **constexpr**и его преобразования в указатель на функцию, полученная функция также **constexpr**:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Объекты-функции в стандартной библиотеке C++](../standard-library/function-objects-in-the-stl.md)   
 [Вызов функции](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)