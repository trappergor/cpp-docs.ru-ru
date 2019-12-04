---
title: Ошибка компилятора C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: e50aaeac4a9f02cf3e67c25a08afdc2df0f1c62f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738015"
---
# <a name="compiler-error-c3499"></a>Ошибка компилятора C3499

заданное лямбда-выражение с возвращаемым типом void не может возвращать значение

Компилятор создает эту ошибку, когда лямбда-выражение, которое указывает `void` в качестве типа возвращаемого значения, возвращает значение; или когда лямбда-выражение содержит несколько операторов и возвращает значение, но не указывает его тип.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не возвращайте значение из лямбда-выражения.

- Либо укажите тип возвращаемого значения лямбда-выражения.

- Либо объедините операторы, которые составляют текст лямбда-выражения, в один оператор.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3499, так как текст лямбда-выражения содержит несколько инструкций и возвращает значение, но лямбда-выражение не указывает тип возвращаемого значения:

```cpp
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

## <a name="example"></a>Пример

В следующем примере показано два возможных способа устранения ошибки C3499. В первом решении указывается тип возвращаемого значения лямбда-выражения. Во втором решении объединяются операторы, которые составляют лямбда-выражение, в один оператор.

```cpp
// C3499b.cpp

int main()
{
   // Possible resolution 1:
   // Provide the return type of the lambda expression.
   [](int x) -> int { int n = x * 2; return n; } (5);

   // Possible resolution 2:
   // Combine the statements that make up the body of
   // the lambda expression into a single statement.
   [](int x) { return x * 2; } (5);
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
