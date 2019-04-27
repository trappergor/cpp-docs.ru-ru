---
title: Предупреждение компилятора (уровень 1) C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: e85bdc995fe16f91e2e9c734dacc65ca0b7b622d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182385"
---
# <a name="compiler-warning-level-1-c4405"></a>Предупреждение компилятора (уровень 1) C4405

«Идентификатор»: идентификатор является зарезервированным словом

Зарезервированное слово для встроенной сборки используется как имя переменной. Это может привести к непредсказуемым результатам. Чтобы устранить это предупреждение, следует Избегайте именования переменных с слова, зарезервированные для встроенной сборки. Следующий пример приводит к возникновению ошибки C4405:

```
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```