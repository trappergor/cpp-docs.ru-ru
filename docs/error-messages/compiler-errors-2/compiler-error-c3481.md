---
title: Ошибка компилятора C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 1719e9f1d3328be083f745498e6f4ad772b0b52a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755243"
---
# <a name="compiler-error-c3481"></a>Ошибка компилятора C3481

var: переменная, передаваемая в лямбда-выражение, не найдена

Компилятору не удалось найти определение переменной, которая передается в список передаваемых параметров в лямбда-выражении.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите переменную из списка передаваемых параметров в лямбда-выражении.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3481, так как переменная `n` не определена:

```cpp
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
