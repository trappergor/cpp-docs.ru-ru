---
title: Ошибка компилятора C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 11d5a0a86ba399e28a641fa490f19be020db2d9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527430"
---
# <a name="compiler-error-c2087"></a>Ошибка компилятора C2087

«Идентификатор»: отсутствует индекс

В определении массива с несколькими индексами отсутствует значение индекса для выше, чем одно измерение.

Следующий пример приводит к возникновению ошибки C2087:

```
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

Возможное решение

```
// C2087b.cpp
int main() {
   char b[4][5];
}
```