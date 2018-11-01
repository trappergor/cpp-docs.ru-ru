---
title: Предупреждение компилятора (уровень 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 1fb2dc7fd4bc685e457898b47c513c21009146ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585553"
---
# <a name="compiler-warning-level-1-c4552"></a>Предупреждение компилятора (уровень 1) C4552

«operator»: оператор не имеет результата; требуется оператор с побочным действием

Если выражение содержит оператор побочные эффекты отсутствуют в верхней части выражения, она, вероятно, является ошибкой.

Чтобы переопределить это предупреждение, поместите выражение в скобках.

Следующий пример приводит к возникновению ошибки C4552:

```
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```