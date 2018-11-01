---
title: Ошибка компилятора C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 299a4e899a41bf47eec5eaf5b54d2307e557078e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614673"
---
# <a name="compiler-error-c2428"></a>Ошибка компилятора C2428

«Операция»: не разрешается с операндом типа «bool»

Оператор декремента нельзя применить к объектам типа `bool`.

Следующий пример приводит к возникновению ошибки C2428:

```
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```