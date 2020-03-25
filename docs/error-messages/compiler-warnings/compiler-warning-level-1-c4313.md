---
title: Предупреждение компилятора (уровень 1) C4313
ms.date: 11/04/2016
f1_keywords:
- C4313
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
ms.openlocfilehash: 14ac938d62b4c5b6f22957268721aea9c3ffef22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163054"
---
# <a name="compiler-warning-level-1-c4313"></a>Предупреждение компилятора (уровень 1) C4313

function: описатель формата в строке формата конфликтует с количеством аргументов типа type

Существует конфликт между указанным форматом и переданным значением. Например, вы передали 64-разрядный параметр неполному описателю формата %d, который ожидает 32-разрядное целое число. Это предупреждение действует только при компиляции кода для 64-разрядных сред.

## <a name="example"></a>Пример

В следующем примере кода возникает ошибка C4313 при компиляции для 64-разрядных сред.

```cpp
// C4313.cpp
// Compile by using: cl /W1 C4313.cpp
#include <stdio.h>
int main() {
   int * pI = 0;
   printf("%d", pI);   // C4313 on 64-bit platform code
   // Try one of the following lines instead:
   // printf("%p\n", pI);
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information
}
```
