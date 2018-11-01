---
title: Ошибка компилятора C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: 98014fec77ce47fa4c484645f401e615f1470e2f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446297"
---
# <a name="compiler-error-c3866"></a>Ошибка компилятора C3866

отсутствует список аргументов функции вызова

Внутри нестатической функцией-членом вызов деструктора или метода завершения не имеет список аргументов.

Следующий пример приводит к возникновению ошибки C3866:

```
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```