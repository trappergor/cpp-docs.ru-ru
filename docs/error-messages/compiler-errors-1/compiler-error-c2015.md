---
title: Ошибка компилятора C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: d761dfde26cce9c99ccd4c3e6fd86ae1d6e16ddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573281"
---
# <a name="compiler-error-c2015"></a>Ошибка компилятора C2015

слишком много знаков в константе

Символьная константа содержит более двух знаков. Ограничение составляет один символ в стандартных и двумя длинные символьные константы.

Escape-последовательности, например \t, преобразуется в один символ.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2015:

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Пример

C2015 также может возникнуть при использовании расширения Microsoft символьные константы, преобразуются в целые числа.  Следующий пример приводит к возникновению ошибки C2015:

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```