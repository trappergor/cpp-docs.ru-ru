---
title: Предупреждение компилятора (уровень 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: a132dcc795d6055c854a5ad147940868fe4e088b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228782"
---
# <a name="compiler-warning-level-1-c4730"></a>Предупреждение компилятора (уровень 1) C4730

"Main": смешивание _m64 и выражений с плавающей точкой может привести к неправильному коду

Функция использует [__m64](../../cpp/m64.md) и **`float`** / **`double`** типы. Поскольку регистры MMX и с плавающей запятой используют одно и то же физическое пространство регистров (не могут использоваться одновременно), использование **`__m64`** **`float`** / **`double`** типов и в одной и той же функции может привести к повреждению данных, возможно, в результате исключения.

Чтобы безопасно использовать **`__m64`** типы и типы с плавающей запятой в одной и той же функции, каждая инструкция, использующая один из типов, должна разделяться **_m_empty ()** (для MMX) или **_m_femms ()** (для 3DNow!).

Следующий пример приводит к возникновению ошибки C4730:

```cpp
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```
