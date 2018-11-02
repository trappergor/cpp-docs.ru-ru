---
title: Ошибка компилятора C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526367"
---
# <a name="compiler-error-c2466"></a>Ошибка компилятора C2466

не удается выделить память для массива постоянного нулевого размера

Массив выделен или объявлен с нулевой размер. Константное выражение размер массива должен быть целым числом больше нуля. Объявление массива с нулевым индексом допускается только для класса, структуры или члена объединения и только с расширениями Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Следующий пример приводит к возникновению ошибки C2466:

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```