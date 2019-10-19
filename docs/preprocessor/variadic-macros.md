---
title: Variadic макросы
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: de4d3a7f03f613cb058e564664f01837df23aefb
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587884"
---
# <a name="variadic-macros"></a>Variadic макросы

Макросы с переменным числом аргументов напоминают собой функции и могут содержать переменное число аргументов.

## <a name="remarks"></a>Заметки

Чтобы использовать макросы Variadic, многоточие можно указать в качестве окончательного формального аргумента в определении макроса, а идентификатор замены `__VA_ARGS__` может использоваться в определении для вставки дополнительных аргументов.  `__VA_ARGS__` заменяются всеми аргументами, соответствующими многоточию, включая запятые между ними.

Стандарт C указывает, что в многоточие должен быть передан хотя бы один аргумент, чтобы макрос не разрешился в выражение с завершающей запятой. Традиционная реализация C++ Майкрософт подавляет завершающую запятую, если с многоточием не передаются аргументы. Если задан параметр компилятора `/experimental:preprocessor`, конечная запятая не подавляется.

## <a name="example"></a>Пример

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>См. также

[Макросы (C/C++)](../preprocessor/macros-c-cpp.md)
