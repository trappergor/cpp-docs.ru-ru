---
title: Ошибка компилятора C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2fcaecd6be35e2ae6822133930b48b6bbf02aafe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027588"
---
# <a name="compiler-error-c3485"></a>Ошибка компилятора C3485

определение лямбда-выражения не может содержать cv-квалификаторы

Нельзя использовать квалификатор `const` или `volatile` как часть определения лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите квалификатор `const` или `volatile` из определения лямбда-выражения.

## <a name="example"></a>Пример

Приведенный ниже пример приводит к возникновению ошибки C3485, так как в нем квалификатор `const` используется как часть определения лямбда-выражения.

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)