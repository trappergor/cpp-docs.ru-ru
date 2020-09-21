---
title: Ошибка компилятора C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 5453009e1c2bd091ed3507f3c43bd7fcecd33abc
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743104"
---
# <a name="compiler-error-c2015"></a>Ошибка компилятора C2015

слишком много символов в константе

Символьная константа содержит более двух символов. Ограничение — один символ для стандартных символьных констант и два символа для длинных символьных констант.

Escape-последовательность, например \t, преобразуется в один символ.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2015:

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

C2015 также может возникать при использовании расширения Майкрософт, символьные константы, преобразованные в целые числа.  Следующий пример приводит к возникновению ошибки C2015:

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
