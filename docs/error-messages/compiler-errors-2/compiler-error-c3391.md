---
title: Ошибка компилятора C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 32ba1ca63a3a6fafa3290946a976e6845385126f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778288"
---
# <a name="compiler-error-c3391"></a>Ошибка компилятора C3391

«аргумент_типа»: недопустимый аргумент типа для универсального параметра «param» универсального «универсальный_тип», должен быть типом значения, не допускающие значения NULL

Экземпляр универсального типа создается неправильным образом. Проверьте определение типа. Дополнительные сведения см. в разделе <xref:System.Nullable> и [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере используется C# создать компонент, который содержит универсальный тип, который имеет определенные ограничения, которые не поддерживаются при создании универсальных типов в C++выполняет. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Когда C3391.dll компонент станет доступным, следующий пример приводит к возникновению ошибки C3391.

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