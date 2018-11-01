---
title: Ошибка компилятора C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 637433ee22ee77a7106e3692a39eec9973d979c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608139"
---
# <a name="compiler-error-c2317"></a>Ошибка компилятора C2317

блок try, начинающийся в строке "номер", не имеет соответствующих блоков catch

Блок `try` должен иметь хотя бы один обработчик Catch.

Следующий пример приводит к возникновению ошибки C2317:

```
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

Возможное решение

```
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```