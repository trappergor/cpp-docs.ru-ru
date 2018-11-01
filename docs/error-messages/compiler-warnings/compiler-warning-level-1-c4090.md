---
title: Предупреждение (уровень 1) C4090 компилятора
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: b47d0bfbb6eab24fbe811d3e4f79b6bd86b3bb11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462378"
---
# <a name="compiler-warning-level-1-c4090"></a>Предупреждение (уровень 1) C4090 компилятора

«Операция»: квалификаторы различных «модификатор»

Переменная, которая используется в операции, определяется с помощью указанного модификатора, предотвращает его изменение без обнаружения компилятором. Выражение компилируется без изменений.

Это предупреждение может возникать при создании указателя на **const** или `volatile` не объявлен как указатель на указатель назначен элемент **const** или `volatile`.

Это предупреждение выдается для программ C. В программе на C++ компилятор выдает ошибку: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Следующий пример приводит к возникновению ошибки C4090:

```
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```