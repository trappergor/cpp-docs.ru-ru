---
title: Предупреждение компилятора (уровень 1) C4750
ms.date: 11/04/2016
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 35b57cf88bf9f9a170a05af890632316b7030838
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052399"
---
# <a name="compiler-warning-level-1-c4750"></a>Предупреждение компилятора (уровень 1) C4750

"идентификатор": функция с _alloca() включена в цикл

Функция "идентификатор" принудительно выполняет встраиваемую подстановку функции [_alloca](../../c-runtime-library/reference/alloca.md) в цикле, что может привести к переполнению стека при выполнении цикла.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что функция "идентификатор" не будет изменена с помощью описателя [__forceinline](../../cpp/inline-functions-cpp.md) .

1. Убедитесь, что функция "идентификатор" не содержит функцию [_alloca](../../c-runtime-library/reference/alloca.md) , которая включена в цикл.

1. Не указывайте параметр компиляции [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md)или [/Og](../../build/reference/og-global-optimizations.md) .

1. Поместите функцию [_alloca](../../c-runtime-library/reference/alloca.md) в [инструкцию try-except](../../cpp/try-except-statement.md) , которая будет перехватывать переполнение стека.

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

## <a name="see-also"></a>См. также

[_alloca](../../c-runtime-library/reference/alloca.md)