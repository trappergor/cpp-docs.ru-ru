---
title: Ошибка компилятора C2057
ms.date: 11/04/2016
f1_keywords:
- C2057
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
ms.openlocfilehash: bdcf97ab6ea877af4e0713fc96ffd38f299e8234
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741453"
---
# <a name="compiler-error-c2057"></a>Ошибка компилятора C2057

требуется константное выражение

Контекст требует константное выражение, то есть выражение, значение которого известно во время компиляции.

Компилятору необходимо знать размер типа во время компиляции, чтобы выделить пространство для экземпляра этого типа.

## <a name="examples"></a>Примеры

В следующем примере показано возникновение ошибки C2057 и приводятся сведения по ее устранению.

```cpp
// C2057.cpp
int i;
int b[i];   // C2057 - value of i is unknown at compile time
int main() {
   const int i = 8;
   int b[i]; // OK - value of i is fixed and known to compiler
}
```

Язык C имеет более строгие правила относительно константных выражений.  В следующем примере показано возникновение ошибки C2057 и приводятся сведения по ее устранению.

```c
// C2057b.c
#define ArraySize1 10
int main() {
   const int ArraySize2 = 10;
   int h[ArraySize2];   // C2057 - C does not allow variables here
   int h[ArraySize1];   // OK - uses preprocessor constant
}
```
