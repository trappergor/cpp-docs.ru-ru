---
title: Ошибка компилятора C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: 3b2737bd67798fd467649be175d581ca551e1331
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770633"
---
# <a name="compiler-error-c3104"></a>Ошибка компилятора C3104

Недопустимый аргумент атрибута

Указан недопустимый аргумент для атрибута.

См. в разделе [типы параметров атрибутов](../../extensions/attribute-parameter-types-cpp-component-extensions.md) Дополнительные сведения.

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: при передаче управляемых массивов в настраиваемых атрибутов, тип массива больше не выводится из списка агрегатной инициализации. Компилятор теперь требует указать тип массива, а также список инициализаторов.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3104.

```
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3104.

```
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```
