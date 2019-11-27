---
title: Предупреждение компилятора (уровень 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: b1e4da53c1f4e109e56c6fe734bc65786ad6cf75
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541603"
---
# <a name="compiler-warning-level-4-c4125"></a>Предупреждение компилятора (уровень 4) C4125

десятичная цифра в конце восьмеричной escape-последовательности

При вычислении компилятором восьмеричного числа десятичная цифра не учитывается и принимается за символ.

## <a name="example"></a>Пример

```cpp
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

Если цифра 9 должна рассматриваться как символ, исправьте пример следующим образом:

```cpp
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```