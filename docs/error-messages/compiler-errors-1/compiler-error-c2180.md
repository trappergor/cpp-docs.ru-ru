---
title: Ошибка компилятора C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 16fcf15eb29743f74bbf2edcb1016f2e15228e5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553326"
---
# <a name="compiler-error-c2180"></a>Ошибка компилятора C2180

управляющее выражение имеет тип type

Управляющее выражение в `if`, `while`, `for` или инструкция `do` — это выражение, приведенное к `void`. Чтобы устранить эту проблему, измените управляющее выражение на то, что создает `bool` или тип, который можно преобразовать в `bool`.

Следующий пример приводит к возникновению ошибки C2180:

```
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```