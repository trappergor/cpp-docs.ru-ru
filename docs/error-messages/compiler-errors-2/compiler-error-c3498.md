---
title: Ошибка компилятора C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: 771e8c72ab4386bb45a11983318f412e784f5bc9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738106"
---
# <a name="compiler-error-c3498"></a>Ошибка компилятора C3498

"var": невозможно записать переменную с управляемым или Винрттипе

Нельзя записать переменную, имеющую управляемый тип или тип среды выполнения Windows в лямбда-выражении.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Передайте управляемую переменную или переменную среды выполнения Windows в список параметров лямбда-выражения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3498, так как переменная, имеющая управляемый тип, присутствует в списке записи лямбда-выражения:

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

## <a name="example"></a>Пример

Следующий пример разрешает C3498, передав управляемую переменную `s` в список параметров лямбда-выражения:

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
