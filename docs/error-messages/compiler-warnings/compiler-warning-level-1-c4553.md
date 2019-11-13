---
title: Предупреждение компилятора (уровень 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: a2d5e52e565878011b2439792c721eeb57cdd20a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966329"
---
# <a name="compiler-warning-level-1-c4553"></a>Предупреждение компилятора (уровень 1) C4553

"operator": оператор не имеет результата; Вы предполагали "operator"?

Если оператор выражения имеет оператор без побочных эффектов, как в верхней части выражения, это, вероятно, является ошибкой.

Следующий пример приводит к возникновению ошибки C4553:

```cpp
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```