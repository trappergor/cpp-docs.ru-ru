---
title: __noop
ms.date: 11/04/2016
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 074ab4c6ea51c8b3a2543d9b43248a8da37567cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613019"
---
# <a name="noop"></a>__noop

**Блок, относящийся только к системам Microsoft**

`__noop` Встроенный указывает, что функцию следует игнорировать и проанализировать список аргументов, но не создать код для аргументов. Он предназначен для использования в глобальных отладки функций, принимающих переменное число аргументов.

Компилятор преобразует `__noop` встроенными в 0, во время компиляции.

## <a name="example"></a>Пример

В следующем коде показано, как использовать `__noop`.

```
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)