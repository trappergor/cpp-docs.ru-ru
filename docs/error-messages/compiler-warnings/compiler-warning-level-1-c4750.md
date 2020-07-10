---
title: Предупреждение компилятора (уровень 1) C4750
description: Описывает КОМПИЛЯТОРОМ MSVC предупреждение компилятора C4750 о возможном переполнении стека.
ms.date: 07/08/2020
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 9a22bdda407b02b8723b7198d62289d39f62792d
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180972"
---
# <a name="compiler-warning-level-1-c4750"></a>Предупреждение компилятора (уровень 1) C4750

> "*идентификатор*": функция с _alloca (), встроенная в цикл

## <a name="remarks"></a>Remarks

Функция "*идентификатор*" принудительно поддает встроенное расширение [`_alloca`](../../c-runtime-library/reference/alloca.md) функции в цикле, что может привести к переполнению стека при выполнении цикла.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что функция "*идентификатор*" не изменена с помощью [`__forceinline`](../../cpp/inline-functions-cpp.md) описателя.

1. Убедитесь, что функция "*идентификатор*" не содержит [`_alloca`](../../c-runtime-library/reference/alloca.md) функцию, содержащуюся в цикле.

1. Не указывайте [`/O1`](../../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/O2`](../../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/Ox`](../../build/reference/ox-full-optimization.md) параметр компиляции,, или [`/Og`](../../build/reference/og-global-optimizations.md) .

1. Поместите [`_alloca`](../../c-runtime-library/reference/alloca.md) функцию в [оператор try-except](../../cpp/try-except-statement.md) , который будет перехватывать переполнение стека.

## <a name="example"></a>Пример

В следующем примере кода `MyFunction` вызывается в цикле, и `MyFunction` вызывает функцию `_alloca` . Модификатор `__forceinline` вызывает встраиваемую подстановку функции `_alloca` .

```cpp
// c4750.cpp
// compile with: /O2 /W1 /c
#include <intrin.h>

char * volatile newstr;

__forceinline void myFunction(void) // C4750 warning
{
// The _alloca function does not require a __try/__except
// block because the example uses compiler option /c.
    newstr = (char * volatile) _alloca(1000);
}

int main(void)
{
    for (int i=0; i<50000; i++)
       myFunction();
    return 0;
}
```

## <a name="see-also"></a>См. также раздел

[_alloca](../../c-runtime-library/reference/alloca.md)
