---
title: 'Практическое: определение и использование делегатов (C + +/ CLI) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5c31ad0d98addfd6cadcc54cccf78e842a98304e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397485"
---
# <a name="how-to-define-and-use-delegates-ccli"></a>Практическое руководство. Определение и использование делегатов (C++/CLI)

В этой статье показано, как определить и использовать делегатов в C + +/ CLI.

Несмотря на то, что платформа .NET Framework предоставляет ряд делегаты, иногда может потребоваться определить новые делегаты.

В следующем примере кода определяется делегат с именем `MyCallback`. Код обработки событий — функция, которая вызывается при возникновении этого нового делегата, должен иметь тип возвращаемого значения `void` и принимать <xref:System.String> ссылку.

Функция main используется статический метод, который определяется `SomeClass` для создания экземпляра `MyCallback` делегировать. Делегат становится альтернативного метода вызова этой функции, как показано с отправкой строки «single» для объекта делегата. Далее, дополнительные экземпляры `MyCallback` связаны друг с другом и затем выполняются с одного вызова объекта делегата.

```cpp
// use_delegate.cpp
// compile with: /clr
using namespace System;

ref class SomeClass
{
public:
   static void Func(String^ str)
   {
      Console::WriteLine("static SomeClass::Func - {0}", str);
   }
};

ref class OtherClass
{
public:
   OtherClass( Int32 n )
   {
      num = n;
   }

   void Method(String^ str)
   {
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",
         str, num);
   }

   Int32 num;
};

delegate void MyCallback(String^ str);

int main( )
{
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);
   callback("single");

   callback += gcnew MyCallback(SomeClass::Func);

   OtherClass^ f = gcnew OtherClass(99);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   f = gcnew OtherClass(100);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   callback("chained");

   return 0;
}
```

```Output
static SomeClass::Func - single
static SomeClass::Func - chained
static SomeClass::Func - chained
OtherClass::Method - chained, num = 99
OtherClass::Method - chained, num = 100
```

В следующем образце кода показано, как делегат связывается с членом класса значений.

```cpp
// mcppv2_del_mem_value_class.cpp
// compile with: /clr
using namespace System;
public delegate void MyDel();

value class A {
public:
   void func1() {
      Console::WriteLine("test");
   }
};

int main() {
   A a;
   A^ ah = a;
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a
   f();
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);
   f2();
}
```

```Output
test
test
```

## <a name="how-to-compose-delegates"></a>Как создание делегатов

Можно использовать "`-`" оператор, чтобы удалить делегат из составного делегата.

```cpp
// mcppv2_compose_delegates.cpp
// compile with: /clr
using namespace System;

delegate void MyDelegate(String ^ s);

ref class MyClass {
public:
   static void Hello(String ^ s) {
      Console::WriteLine("Hello, {0}!", s);
   }

   static void Goodbye(String ^ s) {
      Console::WriteLine("  Goodbye, {0}!", s);
   }
};

int main() {

   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);
   MyDelegate ^ c = a + b;
   MyDelegate ^ d = c - a;

   Console::WriteLine("Invoking delegate a:");
   a("A");
   Console::WriteLine("Invoking delegate b:");
   b("B");
   Console::WriteLine("Invoking delegate c:");
   c("C");
   Console::WriteLine("Invoking delegate d:");
   d("D");
}
```

**Вывод**

```Output
Invoking delegate a:
Hello, A!
Invoking delegate b:
  Goodbye, B!
Invoking delegate c:
Hello, C!
  Goodbye, C!
Invoking delegate d:
  Goodbye, D!
```

## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>Передача delegate ^ в неуправляемую функцию, ожидающую указатель на функцию

Из управляемого компонента можно вызвать функцию машинного кода с помощью функции параметры-указатели где функция в машинном коде затем можно вызвать функцию-член управляемого компонента делегата.

Этот пример создает DLL-файл, который экспортирует функции в машинном коде:

```cpp
// delegate_to_native_function.cpp
// compile with: /LD
#include < windows.h >
extern "C" {
   __declspec(dllexport)
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {
      mgdFunc("Call to Managed Function");
   }
}
```

Следующий пример использует DLL-файл и передает дескриптор делегата неуправляемую функцию, ожидающую указатель на функцию.

```cpp
// delegate_to_native_function_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

delegate void Del(String ^s);
public ref class A {
public:
   void delMember(String ^s) {
      Console::WriteLine(s);
   }
};

[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]
extern "C" void nativeFunction(Del ^d);

int main() {
   A ^a = gcnew A;
   Del ^d = gcnew Del(a, &A::delMember);
   nativeFunction(d);   // Call to native function
}
```

**Вывод**

```Output
Call to Managed Function
```

## <a name="to-associate-delegates-with-unmanaged-functions"></a>Чтобы Связывание делегатов с неуправляемыми функциями

Чтобы связать делегат с собственной функции, необходимо собственного функция была заключена в управляемом типе и объявления функции, вызываемой с помощью `PInvoke`.

```cpp
// mcppv2_del_to_umnangd_func.cpp
// compile with: /clr
#pragma unmanaged
extern "C" void printf(const char*, ...);
class A {
public:
   static void func(char* s) {
      printf(s);
   }
};

#pragma managed
public delegate void func(char*);

ref class B {
   A* ap;

public:
   B(A* ap):ap(ap) {}
   void func(char* s) {
      ap->func(s);
   }
};

int main() {
   A* a = new A;
   B^ b = gcnew B(a);
   func^ f = gcnew func(b, &B::func);
   f("hello");
   delete a;
}
```

**Вывод**

```Output
hello
```

## <a name="to-use-unbound-delegates"></a>Чтобы использовать несвязанные делегаты

Непривязанного делегата можно использовать, чтобы передать экземпляр типа, функция которого вы хотите вызвать при вызове делегата.

Несвязанные делегаты особенно полезно в том случае, если вы хотите пройти по объектам в коллекции — с помощью [для каждого из них в](../dotnet/for-each-in.md) ключевые слова и вызовите функцию-член для каждого экземпляра.

Вот как можно объявить, создать экземпляр, и вызов привязан и несвязанные делегаты:

|Действие|Привязать делегатов|Несвязанные делегаты|
|------------|---------------------|-----------------------|
|Объявления|Сигнатура делегата должна соответствовать сигнатуре функции, которую вы хотите вызвать через делегат.|Сигнатура делегата первый параметр является типом `this` для объекта, необходимо вызвать.<br /><br /> После первого параметра сигнатура делегата должна соответствовать сигнатуре функции, которую вы хотите вызвать через делегат.|
|Создать экземпляр|При создании экземпляра делегата связанный, можно указать функцию экземпляра, или функцию-член глобальной или статической.<br /><br /> Чтобы указать функцию экземпляра, первый параметр является экземпляром типа, функция-член, которого вы хотите вызвать, и второй параметр – адрес функции, которую необходимо вызвать.<br /><br /> Если вы хотите вызвать функцию-член глобальной или статической, просто передайте имя глобальной функции или имя статическую функцию-член.|При создании экземпляра несвязанного делегата, просто передайте адрес функции, которые вы хотите вызвать.|
|Вызов|При вызове связанный делегат, просто передаете параметры, которые требуются сигнатуре делегата.|Так же, как границы делегировать, но помните, что первый параметр должен быть экземпляром объекта, который содержит функцию, которую вы хотите вызвать.|

В этом примере показано, как объявить, создать и вызвать несвязанные делегаты.

```cpp
// unbound_delegates.cpp
// compile with: /clr
ref struct A {
   A(){}
   A(int i) : m_i(i) {}
   void Print(int i) { System::Console::WriteLine(m_i + i);}

private:
   int m_i;
};

value struct V {
   void Print() { System::Console::WriteLine(m_i);}
   int m_i;
};

delegate void Delegate1(A^, int i);
delegate void Delegate2(A%, int i);

delegate void Delegate3(interior_ptr<V>);
delegate void Delegate4(V%);

delegate void Delegate5(int i);
delegate void Delegate6();

int main() {
   A^ a1 = gcnew A(1);
   A% a2 = *gcnew A(2);

   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);
   // delegate takes a handle
   Unbound_Delegate1(a1, 1);
   Unbound_Delegate1(%a2, 1);

   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);
   // delegate takes a tracking reference (must deference the handle)
   Unbound_Delegate2(*a1, 1);
   Unbound_Delegate2(a2, 1);

   // instantiate a bound delegate to an instance member function
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);
   Bound_Del(1);

   // instantiate value types
   V v1 = {7};
   V v2 = {8};

   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);
   Unbound_Delegate3(&v1);
   Unbound_Delegate3(&v2);

   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);
   Unbound_Delegate4(v1);
   Unbound_Delegate4(v2);

   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);
   Bound_Delegate3();
}
```

**Вывод**

```Output
2
3
2
3
2
7
8
7
8
7
```

В приведенном ниже примере показано, как использовать несвязанные делегаты и [для каждого из них в](../dotnet/for-each-in.md) ключевые слова для прохода по объектам в коллекции и вызвать функцию-член для каждого экземпляра.

```cpp
// unbound_delegates_2.cpp
// compile with: /clr
using namespace System;

ref class RefClass {
   String^ _Str;

public:
   RefClass( String^ str ) : _Str( str ) {}
   void Print() { Console::Write( _Str ); }
};

delegate void PrintDelegate( RefClass^ );

int main() {
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );

   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );

   for ( int i = 0; i < a->Length; ++i )
      a[i] = gcnew RefClass( i.ToString() );

   for each ( RefClass^ R in a )
      d( R );

   Console::WriteLine();
}
```

Этот пример создает непривязанного делегата для функции доступа свойства:

```cpp
// unbound_delegates_3.cpp
// compile with: /clr
ref struct B {
   property int P1 {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }

private:
   int m_i;
};

delegate void DelBSet(B^, int);
delegate int DelBGet(B^);

int main() {
   B^ b = gcnew B;

   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);
   delBSet(b, 11);

   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);
   System::Console::WriteLine(delBGet(b));
}
```

**Вывод**

```Output
11
```

Ниже приведен пример, как вызывать делегат многоадресной рассылки, где один экземпляр привязан и один экземпляр освобождается.

```cpp
// unbound_delegates_4.cpp
// compile with: /clr
ref class R {
public:
   R(int i) : m_i(i) {}

   void f(R ^ r) {
      System::Console::WriteLine("in f(R ^ r)");
   }

   void f() {
      System::Console::WriteLine("in f()");
   }

private:
   int m_i;
};

delegate void Del(R ^);

int main() {
   R ^r1 = gcnew R(11);
   R ^r2 = gcnew R(12);

   Del^ d = gcnew Del(r1, &R::f);
   d += gcnew Del(&R::f);
   d(r2);
};
```

**Вывод**

```Output
in f(R ^ r)
in f()
```

В приведенном ниже примере показано, как создать и вызвать несвязанного универсального делегата.

```cpp
// unbound_delegates_5.cpp
// compile with: /clr
ref struct R {
   R(int i) : m_i(i) {}

   int f(R ^) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

value struct V {
   int f(V%) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

generic <typename T>
delegate int Del(T t);

generic <typename T>
delegate int DelV(T% t);

int main() {
   R^ hr = gcnew R(7);
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));

   V v;
   v.m_i = 9;
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );
}
```

**Вывод**

```Output
12
14
```

## <a name="see-also"></a>См. также

[delegate (расширения компонентов C++)](../windows/delegate-cpp-component-extensions.md)