---
title: Ошибка компилятора C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 83b78336d74037b9f9f52da8327479f506db1ffc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751077"
---
# <a name="compiler-error-c2015"></a>Ошибка компилятора C2015

слишком много символов в константе

Символьная константа содержит более двух символов. Ограничение — один символ для стандартных символьных констант и два символа для длинных символьных констант.

Escape-последовательность, например \t, преобразуется в один символ.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2015:

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Пример

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
