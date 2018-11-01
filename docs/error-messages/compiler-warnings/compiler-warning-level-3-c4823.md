---
title: Предупреждение компилятора (уровень 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: 28d490c341c4d14c2e6c03e13007b5a8be423622
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625921"
---
# <a name="compiler-warning-level-3-c4823"></a>Предупреждение компилятора (уровень 3) C4823

«функция»: использует закрепленные указатели, но очистки семантика не включены. Рассмотрите возможность использования/EHa

Отменить закрепление объекта в управляемой куче, на которые указывает закрепляющий указатель, объявленный в области видимости блока, компилятор имитирует поведение деструкторы локальных классов «выдающих себя за» что закрепляющий указатель имеет деструктор, который. Чтобы обеспечить вызов деструктора после возникновения исключения, необходимо включить очистку объектов, что можно сделать с помощью [/EHsc](../../build/reference/eh-exception-handling-model.md).

Можно также вручную отменить закрепление объекта и пропустить это предупреждение.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4823.

```
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
