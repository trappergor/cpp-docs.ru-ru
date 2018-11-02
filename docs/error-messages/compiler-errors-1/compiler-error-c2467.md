---
title: Ошибка компилятора C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: aa45cbb19519dea7bd5c8fb96abd2c76ea30a786
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598033"
---
# <a name="compiler-error-c2467"></a>Ошибка компилятора C2467

Недопустимое объявление анонимного «пользователь типа»

Вложенные определяемый пользователем тип был объявлен. Это ошибка, при компиляции исходного кода C с параметром совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) включен.

Следующий пример приводит к возникновению ошибки C2467:

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```