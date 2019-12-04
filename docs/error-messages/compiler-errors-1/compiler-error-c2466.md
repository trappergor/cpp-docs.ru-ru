---
title: Ошибка компилятора C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: aba4de518b9296fadc4746540e4e738c74908617
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743826"
---
# <a name="compiler-error-c2466"></a>Ошибка компилятора C2466

невозможно выделить массив постоянного размера 0

Массив выделяется или объявляется нулевым размером. Константное выражение для размера массива должно быть целым числом больше нуля. Объявление массива с нулевым индексом является допустимым только для членов класса, структуры или объединения и только с расширениями Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Следующий пример приводит к возникновению ошибки C2466:

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
