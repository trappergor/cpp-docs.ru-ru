---
title: Ошибка компилятора C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 5c8e33e3760a29e8bff4280cdb4452c15cd32f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754762"
---
# <a name="compiler-error-c2624"></a>Ошибка компилятора C2624

локальные классы нельзя использовать для объявления переменных "extern"

Нельзя использовать локальный класс или структуру для объявления переменных `extern`.

Следующий пример приводит к возникновению ошибки C2624:

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```
