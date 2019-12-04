---
title: Ошибка компилятора C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 0eacb6ce6426674d23fc78596ead3730f46ae370
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743046"
---
# <a name="compiler-error-c3485"></a>Ошибка компилятора C3485

определение лямбда-выражения не может содержать cv-квалификаторы

Нельзя использовать квалификатор `const` или `volatile` как часть определения лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите квалификатор `const` или `volatile` из определения лямбда-выражения.

## <a name="example"></a>Пример

Приведенный ниже пример приводит к возникновению ошибки C3485, так как в нем квалификатор `const` используется как часть определения лямбда-выражения.

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
