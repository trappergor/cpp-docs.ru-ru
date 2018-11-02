---
title: Ошибка компилятора C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 0b342f8b878c48a77336fab4921cf4a668e248ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607058"
---
# <a name="compiler-error-c2462"></a>Ошибка компилятора C2462

«Идентификатор»: не удается определить тип в «выражении new»

Не удается определить тип в поле операнда `new` оператор. Поместите определение типа в отдельном выражении.

Следующий пример приводит к возникновению ошибки C2462:

```
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```