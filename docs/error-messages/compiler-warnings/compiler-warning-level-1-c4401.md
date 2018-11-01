---
title: Предупреждение компилятора (уровень 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c7e6cf8a52288d895b74481678dc91fee387a6a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455423"
---
# <a name="compiler-warning-level-1-c4401"></a>Предупреждение компилятора (уровень 1) C4401

«битовое поле»: член является битовым полем

Встроенный код ассемблера пытается получить доступ к члену битового поля. Встроенная сборка нет доступа к членами-битовыми полями, поэтому используется последняя граница упаковки перед члена битового поля.

Чтобы устранить это предупреждение, приведите битовое поле, в соответствующий тип прежде чем использовать его во встроенный код ассемблера. Следующий пример приводит к возникновению ошибки C4401:

```
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```