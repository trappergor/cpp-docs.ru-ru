---
title: Макрос со списками аргументов переменных
ms.date: 11/04/2016
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 0674359b8f620c2b5023ce2ef75b4e247ae765f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547459"
---
# <a name="variadic-macros"></a>Макрос со списками аргументов переменных

Макросы с переменным числом аргументов напоминают собой функции и могут содержать переменное число аргументов.

## <a name="remarks"></a>Примечания

Чтобы использовать макросы с переменным числом аргументов, кнопку с многоточием может быть указан как последнего формального аргумента в определение макроса и идентификатор замены `__VA_ARGS__` может использоваться в определении для вставки дополнительных аргументов.  `__VA_ARGS__` заменяется всеми аргументами, которые соответствуют многоточию, включая запятые между ними.

В стандарте C указывается, что многоточию должен быть передан по меньшей мере один аргумент, чтобы в конце разрешенного макросом выражения не находилась запятая.  Реализация Visual C++ подавляет запятую в конце выражения, если многоточию не переданы аргументы.

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