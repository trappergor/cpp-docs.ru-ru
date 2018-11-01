---
title: Предупреждение компилятора (уровень 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0cf9aef8f68ca5972fd3d7886cd8061b88d043ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442566"
---
# <a name="compiler-warning-level-1-c4717"></a>Предупреждение компилятора (уровень 1) C4717

«функция»: рекурсия на всех путях, функция вызовет переполнение стека среды выполнения

Каждый путь через функцию содержит вызов функции. Поскольку нет способа для выхода из функции без предварительного вызова функции, сама рекурсивно, функция никогда не завершает работу.

Следующий пример приводит к возникновению ошибки C4717:

```
// C4717.cpp
// compile with: /W1 /c
// C4717 expected
int func(int x) {
   if (x > 1)
      return func(x - 1); // recursive call
   else {
      int y = func(0) + 1; // recursive call
      return y;
   }
}

int main(){
   func(1);
}
```