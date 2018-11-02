---
title: Ошибка компилятора C2669
ms.date: 11/04/2016
f1_keywords:
- C2669
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
ms.openlocfilehash: 7944ced947ba1d7c8b10172560ce6237a554e236
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649674"
---
# <a name="compiler-error-c2669"></a>Ошибка компилятора C2669

функции-члена не разрешается в анонимном объединении

[Анонимные объединения](../../cpp/unions.md#anonymous_unions) не могут иметь функции-члены.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2669:

```cpp
// C2669.cpp
struct X {
   union {
      int i;
      void f() {   // C2669, remove function
         i = 0;
      }
   };
};
```
