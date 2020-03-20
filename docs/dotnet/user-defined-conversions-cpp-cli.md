---
title: заданные пользователем преобразования (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: bb7a30382bc586f4d324d47ef6e6757fac83f5ae
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545135"
---
# <a name="user-defined-conversions-ccli"></a>заданные пользователем преобразования (C++/CLI)

В этом разделе обсуждаются пользовательские преобразования (UDC), если один из типов в преобразовании является ссылкой или экземпляром типа значения или ссылочного типа.

## <a name="implicit-and-explicit-conversions"></a>Явные и неявные преобразования

Определяемое пользователем преобразование может быть либо неявным, либо явным.  Если преобразование не приводит к утрате информации, то значение UDC должно быть неявным. В противном случае должна быть определена явная UDC.

Конструктор собственного класса можно использовать для преобразования ссылки или типа значения в собственный класс.

Дополнительные сведения о преобразованиях см. в разделе Преобразование [упаковки](../extensions/boxing-cpp-component-extensions.md) и преобразования [Standard](../cpp/standard-conversions.md).

```cpp
// mcpp_User_Defined_Conversions.cpp
// compile with: /clr
#include "stdio.h"
ref class R;
class N;

value class V {
   static operator V(R^) {
      return V();
   }
};

ref class R {
public:
   static operator N(R^);
   static operator V(R^) {
      System::Console::WriteLine("in R::operator N");
      return V();
   }
};

class N {
public:
   N(R^) {
      printf("in N::N\n");
   }
};

R::operator N(R^) {
   System::Console::WriteLine("in R::operator N");
   return N(nullptr);
}

int main() {
   // Direct initialization:
   R ^r2;
   N n2(r2);   // direct initialization, calls constructor
   static_cast<N>(r2);   // also direct initialization

   R ^r3;
   // ambiguous V::operator V(R^) and R::operator V(R^)
   // static_cast<V>(r3);
}
```

**Выходные данные**

```Output
in N::N
in N::N
```

## <a name="convert-from-operators"></a>Операторы "преобразования из"

Операторы Convert-from создают объект класса, в котором оператор определен из объекта какого-либо другого класса.

Standard C++ не поддерживает операторы Convert-from; для C++ этой цели в стандарте используются конструкторы. Однако при использовании типов CLR Visual C++ предоставляет синтаксическую поддержку для вызова операторов Convert-from.

Чтобы обеспечить взаимодействие с другими CLS-совместимыми языками, может потребоваться заключить каждый определенный пользователем унарный конструктор для заданного класса с помощью соответствующего оператора Convert-from.

Операторы Convert и from:

- Должны быть определены как статические функции.

- Может быть либо неявным (для преобразований, которые не теряют точность, например Short-to-int), либо явным, если возможна потеря точности.

- Должен возвращать объект содержащего класса.

- Должен иметь тип "from" как единственный тип параметра.

В следующем образце показан неявный и явный оператор преобразования, определяемый пользователем (UDC).

```cpp
// clr_udc_convert_from.cpp
// compile with: /clr
value struct MyDouble {
   double d;

   MyDouble(int i) {
      d = static_cast<double>(i);
      System::Console::WriteLine("in constructor");
   }

   // Wrap the constructor with a convert-from operator.
   // implicit UDC because conversion cannot lose precision
   static operator MyDouble (int i) {
      System::Console::WriteLine("in operator");
      // call the constructor
      MyDouble d(i);
      return d;
   }

   // an explicit user-defined conversion operator
   static explicit operator signed short int (MyDouble) {
      return 1;
   }
};

int main() {
   int i = 10;
   MyDouble md = i;
   System::Console::WriteLine(md.d);

   // using explicit user-defined conversion operator requires a cast
   unsigned short int j = static_cast<unsigned short int>(md);
   System::Console::WriteLine(j);
}
```

**Выходные данные**

```Output
in operator
in constructor
10
1
```

## <a name="convert-to-operators"></a>Операторы Convert-to

Операторы Convert-to преобразуют объект класса, в котором оператор определен другим объектом. В следующем примере показан неявный оператор преобразования с преобразованием в, определяемый пользователем:

```cpp
// clr_udc_convert_to.cpp
// compile with: /clr
using namespace System;
value struct MyInt {
   Int32 i;

   // convert MyInt to String^
   static operator String^ ( MyInt val ) {
      return val.i.ToString();
   }

   MyInt(int _i) : i(_i) {}
};

int main() {
   MyInt mi(10);
   String ^s = mi;
   Console::WriteLine(s);
}
```

**Выходные данные**

```Output
10
```

Явный определяемый пользователем оператор преобразования-преобразования подходит для преобразований, которые могут привести к потере данных каким-либо образом. Чтобы вызвать явный оператор Convert-to, необходимо использовать приведение.

```cpp
// clr_udc_convert_to_2.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   d.d = 10.3;
   System::Console::WriteLine(d.d);
   int i = 0;
   i = static_cast<int>(d);
   System::Console::WriteLine(i);
}
```

**Выходные данные**

```Output
10.3
10
```

## <a name="to-convert-generic-classes"></a>Преобразование универсальных классов

Универсальный класс можно преобразовать в T.

```cpp
// clr_udc_generics.cpp
// compile with: /clr
generic<class T>
public value struct V {
   T mem;
   static operator T(V v) {
      return v.mem;
   }

   void f(T t) {
      mem = t;
   }
};

int main() {
   V<int> v;
   v.f(42);
   int i = v;
   i += v;
   System::Console::WriteLine(i == (42 * 2) );
}
```

**Выходные данные**

```Output
True
```

Конструктор преобразования принимает тип и использует его для создания объекта.  Конструктор преобразования вызывается только с прямой инициализацией; приведения не будут вызывать конструкторы преобразования. По умолчанию для типов CLR конструкторы преобразования являются явными.

```cpp
// clr_udc_converting_constructors.cpp
// compile with: /clr
public ref struct R {
   int m;
   char c;

   R(int i) : m(i) { }
   R(char j) : c(j) { }
};

public value struct V {
   R^ ptr;
   int m;

   V(R^ r) : ptr(r) { }
   V(int i) : m(i) { }
};

int main() {
   R^ r = gcnew R(5);

   System::Console::WriteLine( V(5).m);
   System::Console::WriteLine( V(r).ptr);
}
```

**Выходные данные**

```Output
5
R
```

В этом примере кода неявная функция статического преобразования делает то же самое, что и явный конструктор преобразования.

```
public value struct V {
   int m;
   V(int i) : m(i) {}
   static operator V(int i) {
      V v(i*100);
      return v;
   }
};

public ref struct R {
   int m;
   R(int i) : m(i) {}
   static operator R^(int i) {
      return gcnew R(i*100);
   }
};

int main() {
   V v(13);   // explicit
   R^ r = gcnew R(12);   // explicit

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);

   // explicit ctor can't be called here: not ambiguous
   v = 5;
   r = 20;

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);
}
```

**Выходные данные**

```Output
13
12
500
2000
```

## <a name="see-also"></a>См. также:

[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)
