---
title: Предупреждение компилятора (уровень 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 2c238dc16359583bf55f7590d2ce7c0363d66df7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198579"
---
# <a name="compiler-warning-level-3-c4839"></a>Предупреждение компилятора (уровень 3) C4839

> нестандартное использование класса "*Type*" в качестве аргумента функции Variadic

Классы или структуры, которые передаются в функцию Variadic, например `printf`, должны быть тривиально скопированы. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

Это предупреждение доступно начиная с Visual Studio 2017.

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

Для строк, созданных и управляемых с помощью `CStringW`, необходимо использовать предоставленный `operator LPCWSTR()` для приведения объекта `CStringW` к указателю C, ожидаемому строкой формата.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
