---
title: Ошибка компилятора C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 98c4bf43883d15cd17877d7146edf16a73c7ce46
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201108"
---
# <a name="compiler-error-c3391"></a>Ошибка компилятора C3391

"type_arg": недопустимый аргумент типа для универсального параметра "param" универсального "generic_type", должен быть типом значения, не допускающим значения NULL

Экземпляр универсального типа был создан неправильно. Проверьте определение типа. Дополнительные сведения см. в разделе <xref:System.Nullable> и [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере используется C# для создания компонента, содержащего универсальный тип, имеющий определенные ограничения, которые не поддерживаются при создании универсальных типов C++в/CLI. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Если компонент C3391. dll доступен, следующий пример приводит к возникновению ошибки C3391.

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```
