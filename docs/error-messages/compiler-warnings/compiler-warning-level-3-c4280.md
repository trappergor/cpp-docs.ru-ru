---
title: Предупреждение компилятора (уровень 1) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: 6a3daa9903cbf983ddc19538a154d9717a2f9f0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618937"
---
# <a name="compiler-warning-level-3-c4280"></a>Предупреждение компилятора (уровень 1) C4280

«operator ->» был через тип «тип»

Код неправильно разрешает **operator ->** вызывать самого себя.

Следующий пример приводит к возникновению ошибки C4280:

```
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```