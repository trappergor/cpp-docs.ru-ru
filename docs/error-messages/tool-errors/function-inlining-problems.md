---
title: Проблемы при встраивании функций
ms.date: 11/04/2016
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
ms.openlocfilehash: cb4653bd2f03683b9abad1eea0e9ffa88222090e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184246"
---
# <a name="function-inlining-problems"></a>Проблемы при встраивании функций

Если вы используете функцию встраивания, необходимо:

- Выполните встроенные функции, реализованные в файле заголовка, который вы включаете.

- Включить встраивание в заголовочный файл.

```cpp
// LNK2019_function_inline.cpp
// compile with: /c
// post-build command: lib LNK2019_function_inline.obj
#include <stdio.h>
struct _load_config_used {
   void Test();
   void Test2() { printf("in Test2\n"); }
};

void _load_config_used::Test() { printf("in Test\n"); }
```

Затем:

```cpp
// LNK2019_function_inline_2.cpp
// compile with: LNK2019_function_inline.lib
struct _load_config_used {
   void Test();
   void Test2();
};

int main() {
   _load_config_used x;
   x.Test();
   x.Test2();   // LNK2019
}
```

Если используется директива компилятора `#pragma inline_depth`, убедитесь, что задано значение 2 или более. Значение, равное нулю, отключает встраивание. Также убедитесь, что вы используете параметры компилятора **/Ob1** или **/Ob2** .

Смешивание встроенных и невстроенных параметров компиляции в разных модулях иногда может вызвать проблемы. Если C++ библиотека создается с включенной функцией встраивания в ([/Ob1](../../build/reference/ob-inline-function-expansion.md) или [/Ob2](../../build/reference/ob-inline-function-expansion.md)), но соответствующий заголовочный файл, описывающий функции, отключен (параметр не ЗАДАН), возникнет ошибка LNK2001. Функции не встроены в код из файла заголовка, но поскольку они не находятся в файле библиотеки, адрес для разрешения ссылки отсутствует.

Аналогично, проект, использующий функцию встраивания, еще определяет функции в cpp-файле, а не в файле заголовка, также возникает LNK2019. Файл заголовка включается везде, где это уместно, но функции встроены только в том случае, если CPP-файл проходит через компилятор; Таким образом, компоновщик видит функции как неразрешенные внешние при использовании в других модулях.

```cpp
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

И потом

```cpp
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

И потом

```cpp
// LNK2019_FIP_2.cpp
// compile with: LNK2019_FIP.cpp
// LNK2019 expected
#include "LNK2019_FIP.h"
int main() {
   testclass testclsObject;

   // module cannot see the implementation of PublicStatMemFunc1
   testclsObject.PublicStatMemFunc1();
}
```

## <a name="see-also"></a>См. также раздел

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
