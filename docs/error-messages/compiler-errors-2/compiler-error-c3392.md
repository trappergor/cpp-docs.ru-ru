---
title: Ошибка компилятора C3392
ms.date: 11/04/2016
f1_keywords:
- C3392
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
ms.openlocfilehash: 72bdef1b3344b3d69ba0d014f92a85e9381de4b3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779538"
---
# <a name="compiler-error-c3392"></a>Ошибка компилятора C3392

"аргумент_типа": недопустимый аргумент типа для универсального параметра "параметр" универсального типа "универсальный_тип"; должен быть открытый конструктор без параметров

Экземпляр универсального типа создается неправильным образом. Проверьте определение типа. Дополнительные сведения см. в разделе [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере используется C# для создания компонента, который содержит универсальный тип, который имеет определенные ограничения, которые не поддерживаются при создании универсальных типов в C + +/ CLI. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Если компонент C3392.dll доступен, в следующем примере возникает C3392.

```cpp
// C3392_b.cpp
// Compile by using: cl /clr C3392_b.cpp
#using <C3392.dll>

ref class R { R(int) {} };
ref class N { N() {} };

value class V {};

ref class N2 { public: N2() {} };
ref class R2 { public: R2() {} };

int main () {
   GR<R^, V, N^>^ gr1;   // C3392
   GR<R^, V, N2^>^ gr1a; // OK

   GR<R^, N^, N^>^ gr3;  // C3392
   GR<R^, V, N2^>^ gr3a; // OK

   GR<R^, V, R^>^ gr4;   // C3392
   GR<R^, V, R2^>^ gr4a; // OK
}
```