---
title: Ошибка компилятора C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: c624d3b0379d057b0ed566deffc2a0efcc324f88
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912864"
---
# <a name="compiler-error-c3390"></a>Ошибка компилятора C3390

"аргумент_типа": недопустимый аргумент типа для универсального параметра "параметр" для универсального "универсальный_тип", должен быть ссылочный тип

Экземпляр универсального типа создается неправильным образом.  Проверьте определение типа.  Дополнительные сведения см. в разделе [Универсальные типы](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В первом примере используется C# для создания компонента, содержащего универсальный тип с определенными ограничениями, которые не поддерживаются при создании универсальных типов C++в/CLR. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Если компонент C3390. dll доступен, следующий пример приводит к возникновению ошибки C3390.

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