---
title: Предупреждение компилятора (уровень 1) C4805
ms.date: 11/04/2016
f1_keywords:
- C4805
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
ms.openlocfilehash: 3bbce2529b208b764fa28bad1d67e1bbb38ec127
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662752"
---
# <a name="compiler-warning-level-1-c4805"></a>Предупреждение компилятора (уровень 1) C4805

"операция": небезопасное смешение типа "тип" и типа "тип" в операции

Это предупреждение выдается для операций сравнения значений [bool](../../cpp/bool-cpp.md) и [int](../../c-language/integer-types.md). При компиляции следующего примера будет выдано предупреждение C4805:

```
// C4805.cpp
// compile with: /W1
int main() {
   int i = 1;
   bool b = true;

   if (i == b) {   // C4805, comparing bool and int variables
   }
}
```