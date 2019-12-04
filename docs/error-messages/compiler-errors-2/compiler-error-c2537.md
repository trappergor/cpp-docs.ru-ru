---
title: Ошибка компилятора C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 0dfe9f88fcdfda1325150d480670777a4d42d896
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758636"
---
# <a name="compiler-error-c2537"></a>Ошибка компилятора C2537

"спецификатор": Недопустимая спецификация компоновки

Возможные причины.

1. Спецификатор компоновки не поддерживается. Поддерживается только описатель компоновки "C".

1. Компоновка "C" указана для более чем одной функции в наборе перегруженных функций. Такое использование недопустимо.

Следующий пример приводит к возникновению ошибки C2537:

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
