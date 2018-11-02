---
title: Компилятор предупреждение (уровень 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 09b6e5b8dc984b35df7de96f5cf8610f2b0f16af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536647"
---
# <a name="compiler-warning-level-3-c4839"></a>Компилятор предупреждение (уровень 3) C4839

> Нестандартное использование класса*тип*"как аргумент для функции с переменным числом аргументов

Классы или структуры, которые передаются в функцию с переменным числом аргументов, такие как `printf` должен быть тривиально копируемым. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

Это предупреждение будет доступно в Visual Studio 2017.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4839:

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function
}
```

Чтобы исправить эту ошибку, можно вызвать функцию-член, возвращающую тип, доступный для простого копирования,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Для строк, созданных и управляемых с помощью `CStringW`, предоставленный `operator LPCWSTR()` следует использовать для приведения `CStringW` объекта к указателю C, ожидаемому строкой формата.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```