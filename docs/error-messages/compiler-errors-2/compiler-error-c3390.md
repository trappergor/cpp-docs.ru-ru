---
title: Ошибка компилятора C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 3f1149d4584a0ea3d0061a3ec4e2b77830603ef2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778739"
---
# <a name="compiler-error-c3390"></a>Ошибка компилятора C3390

"аргумент_типа": недопустимый аргумент типа для универсального параметра "параметр" для универсального "универсальный_тип", должен быть ссылочный тип

Экземпляр универсального типа создается неправильным образом.  Проверьте определение типа.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В первом образце используется C# создать компонент, который содержит универсальный тип, который имеет определенные ограничения, которые не поддерживаются при создании универсальных типов в C++/CLR. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Когда C3390.dll компонент станет доступным, следующий пример приводит к возникновению ошибки C3390.

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK
}
```