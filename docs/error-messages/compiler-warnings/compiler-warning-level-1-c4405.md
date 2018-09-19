---
title: Предупреждение компилятора (уровень 1) C4405 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4405
dev_langs:
- C++
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fce005153b9343b25e7de49b3e95a002381d0619
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061582"
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