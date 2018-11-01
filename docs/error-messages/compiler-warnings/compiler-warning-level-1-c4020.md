---
title: Компилятор предупреждение (уровень 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482034"
---
# <a name="compiler-warning-level-1-c4020"></a>Компилятор предупреждение (уровень 1) C4020

«функция»: слишком много фактических параметров

Число фактических параметров в вызове функции превышает количество формальных параметров в прототипе или определении функции. Компилятор передает избыточные фактические параметры в соответствии с соглашение о вызове функции.

Следующий пример приводит к возникновению ошибки C4020:

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Возможное решение

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```