---
title: Ошибка компилятора C3390
description: Ошибка компилятора Microsoft C++ C3390, причины и способы их устранения.
ms.date: 09/26/2020
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 467b379d7f5a349a217b566dc55b28d5fbd789da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414364"
---
# <a name="compiler-error-c3390"></a>Ошибка компилятора C3390

> "*Type_arg*": недопустимый аргумент типа для универсального параметра "*param*" универсального "*generic_type*", должен быть ссылочным типом

Экземпляр универсального типа создается неправильным образом. Проверьте определение типа.

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в статье [Универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В первом примере используется C# для создания компонента, содержащего универсальный тип. Этот тип имеет определенные ограничения, которые не поддерживаются при создании универсальных типов в C++/CLI. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Если компонент C3390.dll доступен, следующий пример приводит к возникновению ошибки C3390.

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK - do this instead
}
```
