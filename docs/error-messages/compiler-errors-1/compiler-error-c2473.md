---
title: Ошибка компилятора C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: 232f89a714d70c6914b73a370c5f658ff4283ab4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631794"
---
# <a name="compiler-error-c2473"></a>Ошибка компилятора C2473

"идентификатор": выглядит как определение функции, но без списка параметров.

Компилятор обнаружил код, похожий на функцию, но без списка параметров.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2473:

```
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```