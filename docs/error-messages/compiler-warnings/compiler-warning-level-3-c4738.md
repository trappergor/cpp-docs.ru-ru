---
title: Предупреждение компилятора (уровень 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: 5162a03b213b35913ed1fc7f39360796ccf2c4a0
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189400"
---
# <a name="compiler-warning-level-3-c4738"></a>Предупреждение компилятора (уровень 3) C4738

хранение результатов в памяти в 32-разрядном формате с плавающей запятой, возможно снижение производительности

C4738 предупреждает о том, что результат присваивания, приведения, переданного аргумента или другой операции может быть округлен или что при выполнении операции были исчерпаны регистры и требуется использовать память (Сброс). Это может привести к снижению производительности.

Чтобы устранить это предупреждение и избежать округления, Скомпилируйте с параметром [/FP: Fast](../../build/reference/fp-specify-floating-point-behavior.md) или используйте `double` вместо `float`.

Чтобы устранить это предупреждение и избежать нехватки регистров, измените порядок вычислений и измените использование встраивания.

Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4738:

```cpp
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