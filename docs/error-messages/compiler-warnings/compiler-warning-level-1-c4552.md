---
title: Предупреждение компилятора (уровень 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 8435abc60a7ba93800858b22cfd4c5e1778f8587
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186118"
---
# <a name="compiler-warning-level-1-c4552"></a>Предупреждение компилятора (уровень 1) C4552

"operator": оператор не имеет результата; ожидаемый оператор с побочным действием

Если оператор выражения имеет оператор без побочных эффектов, как в верхней части выражения, это, вероятно, является ошибкой.

Чтобы переопределить это предупреждение, заключите выражение в круглые скобки.

Следующий пример приводит к возникновению ошибки C4552:

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
