---
title: "constexpr лямбда-выражения в C++ | Документы Microsoft"
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
caps.latest.revision: "0"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 307ce6ab87ca36de561ebcf1ad8bd30eb73e4192
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr лямбда-выражения в C++
**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): лямбда-выражение может быть объявлен как `constexpr` или использовать в выражении contant при инициализации каждого элемента данных, чтобы он захватывает или вводит может в константном выражении.  

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
Лямбда-выражение неявно является `constexpr` если его результат не соответствует требованиям `constexpr` функции:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Если лямбда-выражение, явно или неявно `constexpr`и преобразовать его в указатель на функцию, полученная функция также `constexpr`:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Объекты функций в стандартной библиотеке C++](../standard-library/function-objects-in-the-stl.md)   
 [Вызов функции](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)