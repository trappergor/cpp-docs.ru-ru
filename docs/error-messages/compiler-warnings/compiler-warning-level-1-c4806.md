---
title: Предупреждение компилятора (уровень 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: b6fc5708d4e2f9982ceaab57260f13e134e4d247
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578269"
---
# <a name="compiler-warning-level-1-c4806"></a>Предупреждение компилятора (уровень 1) C4806

"операция": небезопасная операция: значение типа "тип", приведенное к типу "тип", не может равняться данной константе

Это предупреждение выводится при использовании выражений вида `b == 3`, в которых операнд `b` имеет тип `bool`. В соответствии с правилами повышения значение типа `bool` приводится к типу `int`. Это допускается, однако операнд никогда не будет принимать значение **true**. Следующий пример приводит к возникновению предупреждения C4806:

```
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```