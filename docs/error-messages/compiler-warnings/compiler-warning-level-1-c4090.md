---
title: Предупреждение компилятора (уровень 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: 88ed48e9bf7057c55ee4004ca1bb1eb18cd4be51
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626163"
---
# <a name="compiler-warning-level-1-c4090"></a>Предупреждение компилятора (уровень 1) C4090

"операция": разные квалификаторы "модификатор"

Переменная, используемая в операции, определяется с помощью указанного модификатора, который предотвращает его изменение без обнаружения компилятором. Выражение компилируется без изменения.

Это предупреждение может быть вызвано тем, что указатель на **константу** или элемент `volatile` назначен указателю, не объявленному как указатель на **const** или `volatile`.

Это предупреждение выдается для программ на языке C. В C++ программе компилятор выдает ошибку Ошибка: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Следующий пример приводит к возникновению ошибки C4090:

```c
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