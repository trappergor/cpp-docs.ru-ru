---
title: Предупреждение компилятора (уровень 4) C4725
ms.date: 11/04/2016
f1_keywords:
- C4725
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
ms.openlocfilehash: c86d1a5351adf5ba29752613f2301a11fb1b93ce
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989520"
---
# <a name="compiler-warning-level-4-c4725"></a>Предупреждение компилятора (уровень 4) C4725

инструкция может оказаться неправильной на некоторых процессорах Pentium

Код содержит инструкцию встроенной сборки, которая может возвратить неточные результаты на некоторых микропроцессорах Pentium.

Следующий пример приводит к возникновению ошибки C4725.

```cpp
// C4725.cpp
// compile with: /W4
// processor: x86
double m32fp = 2.0003e-17;

void f() {
   __asm
   {
      FDIV m32fp   // C4725
   }
}

int main() {
}
```
