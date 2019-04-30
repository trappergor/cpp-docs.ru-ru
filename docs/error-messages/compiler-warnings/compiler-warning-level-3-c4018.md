---
title: Компилятор предупреждение (уровень 3) C4018
ms.date: 11/04/2016
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
ms.openlocfilehash: 6436f62a06cbe931ca5b42751d60507f21675c5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402376"
---
# <a name="compiler-warning-level-3-c4018"></a>Компилятор предупреждение (уровень 3) C4018

«выражение»: несоответствие со знаком и без

Сравнивает номер со знаком и без знака требуется компилятору преобразовать значение со знаком в числа без знака.

Чтобы устранить это предупреждение, приведен один из двух типов при тестировании типов со знаком и без знака.

Следующий пример приводит к возникновению ошибки C4018:

```
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```