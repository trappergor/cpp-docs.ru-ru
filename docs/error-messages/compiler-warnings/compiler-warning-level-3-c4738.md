---
title: Предупреждение компилятора (уровень 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: 833546d20454e6104a2d5fcb272bf5bb9518ea44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460948"
---
# <a name="compiler-warning-level-3-c4738"></a>Предупреждение компилятора (уровень 3) C4738

хранение результатов в памяти в 32-разрядном формате с плавающей запятой, возможно снижение производительности

C4738 выдает предупреждение, что результат назначения, приведение к типу, передан аргумент, или другой операции может потребоваться округлить, или что операция не хватило регистров и необходимые для использования памяти. Это может привести к потере производительности.

Чтобы устранить это предупреждение и избежать округления, компиляцию с параметром [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) или использовать `double` вместо `float`.

Чтобы устранить это предупреждение и предотвратить нехватку регистры, изменить порядок вычисления и изменить использование встраивания

Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4738:

```
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```