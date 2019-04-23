---
title: Ошибка компилятора C3487
ms.date: 11/04/2016
f1_keywords:
- C3487
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
ms.openlocfilehash: 01f8a1bd74ed2b7a3150afae5b46128c6f5b0ca2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028416"
---
# <a name="compiler-error-c3487"></a>Ошибка компилятора C3487

"тип возвращаемого значения": все возвращаемые выражения в лямбда-выражении должны иметь один и тот же тип: ранее использовался "тип возвращаемого значения"

Лямбда-выражение должно указывать тип возвращаемого значения, если оно содержит один оператор return. Если лямбда-выражение содержит несколько операторов return, они должны быть одного типа.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите конечный тип возвращаемого значения для лямбда-выражения. Убедитесь, что все возвращаемые типа лямбда-выражения относятся к одному типу или могут быть неявно преобразованы в тип возвращаемого значения.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3487, так как типы возвращаемого значения лямбда-выражения не совпадают:

```
// C3487.cpp
// Compile by using: cl /c /W4 C3487.cpp

int* test(int* pi) {
   // To fix the error, uncomment the trailing return type below
   auto odd_pointer = [=]() /* -> int* */ {
      if (*pi % 2)
         return pi;
      return nullptr; // C3487 - nullptr is not an int* type
   };
   return odd_pointer();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)