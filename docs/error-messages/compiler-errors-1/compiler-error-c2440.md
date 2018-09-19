---
title: Ошибка компилятора C2440 | Документация Майкрософт
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80107f3adf4b460fd2563026a1b7ff6ab6394167
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091222"
---
# <a name="compiler-error-c2440"></a>Ошибка компилятора C2440

«Преобразование»: невозможно преобразовать из «тип1» в «тип2»

Компилятор не может быть приведен с `type1` для `type2`.

## <a name="example"></a>Пример

Ошибка C2440 может возникать при попытке инициализировать отличный от const `char*` (или `wchar_t*`) с помощью строкового литерала в коде C++, когда параметр соответствия компилятора [/Zc: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) имеет значение. В C тип строкового литерала — массив `char`, но в C++, это массив `const char`. В следующем примере возникает ошибка C2440:

```cpp
// C2440s.cpp
// Build: cl /Zc:strictStrings /W3 C2440s.cpp
// When built, the compiler emits:
// error C2440: 'initializing' : cannot convert from 'const char [5]'
// to 'char *'
//        Conversion from string literal loses const qualifier (see
// /Zc:strictStrings)

int main() {
   char* s1 = "test"; // C2440
   const char* s2 = "tests"; // OK
}
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать при попытке преобразования указателя на член к void *. Следующий пример приводит к возникновению ошибки C2440:

```cpp
// C2440.cpp
class B {
public:
   void  f(){;}

   typedef void (B::*pf)();

   void f2(pf pf) {
       (this->*pf)();
       void* pp = (void*)pf;   // C2440
   }

   void f3() {
      f2(f);
   }
};
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать при попытке приведения из типа, который объявлен с опережением, но не определен. В следующем примере возникает ошибка C2440:

```cpp
// c2440a.cpp
struct Base { }; // Defined

struct Derived; // Forward declaration, not defined

Base * func(Derived * d) {
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'
}

```

## <a name="example"></a>Пример

Ошибки C2440 в строках 15 и 16 следующего примера сопровождаются `Incompatible calling conventions for UDT return value` сообщения. Объект *определяемого пользователем ТИПА* является определяемый пользователем тип, например класс, структура или объединение. Эти виды ошибок несовместимости возникают, когда соглашение о вызове определяемого пользователем типа указано в качестве типа возвращаемого опережающего объявления конфликтует со фактических вызовах определяемого пользователем типа и при задействовании указателя.

В примере сначала приводятся предварительные объявления структуры и функции, возвращающей эту структуру; компилятор предполагает, что для структуры используется соглашение о вызове C++. Далее является определение структуры, для которого по умолчанию использует C соглашение о вызовах. Поскольку компилятор не знает о вызовах структуры до момента считывания всей структуры целиком, соглашение о вызове для структуры в тип возвращаемого значения `get_c2` также предполагается, что C++.

Структуры следует объявление другой функции, возвращающей эту структуру, но на этом этапе компилятор знает, что структуры соглашение о вызовах C++. Аналогичным образом указатель на функцию, возвращающую структуру, определяется после определения структуры, чтобы компилятор знал, что для структуры используется соглашение о вызове C++.

Чтобы устранить ошибку C2440, возникающую из-за несовместимости соглашений о вызове, объявите функции, возвращающие определяемого пользователем ТИПА после определение определяемого пользователем ТИПА.

```cpp
// C2440b.cpp
struct MyStruct;

MyStruct get_c1();

struct MyStruct {
   int i;
   static MyStruct get_C2();
};

MyStruct get_C3();

typedef MyStruct (*FC)();

FC fc1 = &get_c1;   // C2440, line 15
FC fc2 = &MyStruct::get_C2;   // C2440, line 16
FC fc3 = &get_C3;

class CMyClass {
public:
   explicit CMyClass( int iBar)
      throw()   {
   }

   static CMyClass get_c2();
};

int main() {
   CMyClass myclass = 2;   // C2440
   // try one of the following
   // CMyClass myclass{2};
   // CMyClass myclass(2);

   int *i;
   float j;
   j = (float)i;   // C2440, cannot cast from pointer to int to float
}
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать при присваивании нулевого значения внутреннему указателю:

```cpp
// C2440c.cpp
// compile with: /clr
int main() {
   array<int>^ arr = gcnew array<int>(100);
   interior_ptr<int> ipi = &arr[0];
   ipi = 0;   // C2440
   ipi = nullptr;   // OK
}
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать при неправильном использовании пользовательского преобразования. Например, когда оператор преобразования был определен как `explicit`, компилятор не может использовать его в неявное преобразование. Дополнительные сведения о пользовательских преобразованиях см. в разделе [заданных пользователем преобразований (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). В следующем примере возникает ошибка C2440:

```cpp
// C2440d.cpp
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
   int i;
   i = d;   // C2440
   // Uncomment the following line to resolve.
   // i = static_cast<int>(d);
}
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать при попытке создания экземпляра массива Visual C++, тип которого является <xref:System.Array>.  Дополнительные сведения см. в разделе [массивы](../../windows/arrays-cpp-component-extensions.md).  Следующий пример приводит к возникновению ошибки C2440:

```cpp
// C2440e.cpp
// compile with: /clr
using namespace System;
int main() {
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440
   // try the following line instead
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));
}
```

## <a name="example"></a>Пример

Ошибка C2440 также может возникать из-за изменений в функциональности атрибутов.  Следующий пример приводит к возникновению ошибки C2440.

```cpp
// c2440f.cpp
// compile with: /LD
[ module(name="PropDemoLib", version=1.0) ];   // C2440
// try the following line instead
// [ module(name="PropDemoLib", version="1.0") ];
```

## <a name="example"></a>Пример

Компилятор Visual C++ не допускает [оператор const_cast](../../cpp/const-cast-operator.md) выполнять приведение при исходного кода, использующего **/CLR** программирование компилируется.

Чтобы устранить эту ошибку C2440, используйте правильный оператор приведения типа. Дополнительные сведения см. в разделе [операторы приведения](../../cpp/casting-operators.md).

В следующем примере возникает ошибка C2440:

```cpp
// c2440g.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};
int main() {
   Derived ^d = gcnew Derived;
   Base ^b = d;
   d = const_cast<Derived^>(b);   // C2440
   d = dynamic_cast<Derived^>(b);   // OK
}
```

## <a name="example"></a>Пример

Ошибка C2440 может возникать из-за изменения соответствия для компилятора в Visual Studio 2015 с обновлением 3. Ранее компилятор неправильно считаются некоторых уникальных выражений одного типа при определении соответствия шаблона для `static_cast` операции. Теперь компилятор различает типы правильно и код полагались на предыдущий `static_cast` поведение разрывается. Чтобы устранить эту проблему, измените аргумент шаблона, чтобы соответствовать типу параметра шаблона, или используйте `reinterpret_cast` или приведение в стиле C.

В следующем примере возникает ошибка C2440:

```cpp
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.

```

## <a name="example"></a>Пример

### <a name="copy-list-initialization"></a>Инициализация копии списка

Visual Studio 2017 и более поздних версий правильно возникают ошибки компилятора, связанные с созданием объектов с использованием списков инициализаторов, которые не обнаруживались в Visual Studio 2015 и могли приводить к сбоям или неопределенному поведению во время выполнения. В C ++ 17 copy-list-initialization компилятор должен учитывать явный конструктор для разрешения перегрузки, но должен выдавать ошибку, если эта перегрузка выбирается на самом деле.

В следующем примере компилируется в Visual Studio 2015, но не в Visual Studio 2017.

```cpp
// C2440j.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot
                         // convert from 'int' to 'const A &'
}
```

Чтобы исправить эту ошибку, следует использовать прямую инициализацию:

```cpp
// C2440k.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}
```

## <a name="example"></a>Пример

### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы при построении класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Это может привести к сбою или непредсказуемому поведению среды выполнения. В следующем примере компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017 и более поздних версий:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Чтобы исправить эту ошибку, объявите оператор int() как константу.
