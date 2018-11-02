---
title: Ошибка компилятора C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: ca9e2d272a5e9ab8fd69094bc1633dbd6ea2c3e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624705"
---
# <a name="compiler-error-c3498"></a>Ошибка компилятора C3498

«var»: нельзя записать переменную, имеющую управляемый или WinRTtype

Нельзя записать переменную, имеющую управляемый тип или тип среды выполнения Windows в лямбда-выражении.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Передайте управляемую переменную или переменную среды выполнения Windows в список параметров лямбда-выражения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3498, так как переменная, имеющая управляемый тип, присутствует в списке записи лямбда-выражения:

```
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

```
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

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)