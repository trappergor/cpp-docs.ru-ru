---
title: Предупреждение компилятора (уровень 1 и уровень 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: fa3326bd5ab495dbc4c54130bb168422eb827dce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463223"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Предупреждение компилятора (уровень 1 и уровень 4) C4700

> неинициализированная локальная переменная "*имя*" используется

Локальная переменная *имя* был *используется*, то есть считывание, до того, как оно было назначено значение. В C и C++ локальные переменные не инициализируются по умолчанию. Неинициализированные переменные могут содержать любое значение, и их применение приводит к неопределенному поведению. Предупреждение C4700 почти всегда указывает на ошибку, что может привести к непредсказуемым результатам или происходит аварийный сбой программы.

Чтобы устранить эту проблему, можно инициализировать локальные переменные, если они объявлены, или назначить значение к ним, прежде чем они используются. Функция может использоваться для инициализации переменной, передаваемый в качестве ссылочного параметра, или если адрес передается как параметр-указатель.

## <a name="example"></a>Пример

Этот пример приводит к возникновению ошибки C4700, когда переменные t, u и v используются, прежде чем они инициализируются и показывает, какие значения сборки мусора, которая может привести. Переменные x, y и z не вызвать предупреждение, так как они инициализируются перед использованием:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

Когда этот код является выполнения, t, u и v не инициализированы и выходные данные для s будет непредсказуемым:

```Output
Value in s: 37816963
Value in w: 42
```
