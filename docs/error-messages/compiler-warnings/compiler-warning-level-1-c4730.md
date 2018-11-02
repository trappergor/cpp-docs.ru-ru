---
title: Предупреждение компилятора (уровень 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: 4da60194deaeac3c79f8c3e9be3bd87d91bc7ca2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487039"
---
# <a name="compiler-warning-level-1-c4730"></a>Предупреждение компилятора (уровень 1) C4730

«main»: смешение _m64 и с плавающей запятой, выражения могут стать неправильный код

Функция использует [__m64](../../cpp/m64.md) и **float**/**двойные** типов. Так как MMX и с плавающей точкой регистры одного и того же физического пространство регистров (не могут использоваться одновременно), с помощью `__m64` и **float**/**двойные** типы в одном функция может привести к повреждению данных, возможно, вызывая исключение.

Для безопасного использования `__m64` типов и типов с плавающей запятой в той же функции, каждая инструкция, которая использует один из типов должны быть разделены **_m_empty()** (для MMX) или **_m_femms()** (для 3DNow!) внутренние.

Следующий пример приводит к возникновению ошибки C4730:

```
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