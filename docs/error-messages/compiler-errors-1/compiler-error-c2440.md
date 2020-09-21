---
title: Ошибка компилятора C2440
ms.date: 03/28/2017
f1_keywords:
- C2440
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
ms.openlocfilehash: 74c5032338b3f4cf30bdb75bdf070cee7b67ce58
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742116"
---
# <a name="compiler-error-c2440"></a>Ошибка компилятора C2440

"преобразование": невозможно преобразовать из "тип1" в "тип2"

Компилятору не удается выполнить преобразование из `type1` в `type2` .

Ошибка C2440 может возникать при попытке инициализировать неконстантный **`char*`** (или `wchar_t*` ) с помощью строкового литерала в коде C++, когда задан параметр соответствия компилятора [/Zc: strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) . В C тип строкового литерала является массивом **`char`** , но в C++ это массив `const char` .

## <a name="examples"></a>Примеры

Этот пример приводит к возникновению ошибки C2440:

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

Ошибка C2440 также может возникать при попытке преобразовать указатель на член в void *. Следующий пример приводит к возникновению ошибки C2440:

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

Ошибка C2440 также может возникать при попытке приведения из типа, который был только что объявлен, но не определен. Этот пример приводит к возникновению ошибки C2440:

```cpp
// c2440a.cpp
struct Base { }; // Defined

struct Derived; // Forward declaration, not defined

Base * func(Derived * d) {
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'
}
```

Ошибки C2440 в строках 15 и 16 следующего образца задаются вместе с `Incompatible calling conventions for UDT return value` сообщением. *UDT* — это определяемый пользователем тип, например класс, структура или объединение. Эти ошибки несовместимости вызываются, когда соглашение о вызовах определяемого пользователем типа, указанного в типе возвращаемого значения прямого объявления, конфликтует с фактическим соглашением о вызовах определяемого пользователем типа и при вовлечении указателя функции.

В примере сначала имеются прямые объявления для структуры и функции, возвращающей структуру. компилятор предполагает, что в структуре используется соглашение о вызовах C++. Далее следует определение структуры, которое по умолчанию использует соглашение о вызовах C. Так как компилятор не знает соглашение о вызовах структуры до тех пор, пока не завершит считывание всей структуры, то соглашение о вызовах для структуры в возвращаемом типе `get_c2` также предполагается как C++.

За структурой следует другое объявление функции, возвращающее структуру, но на этом этапе компилятор знает, что соглашением о вызовах структуры является C++. Аналогично, указатель функции, возвращающий структуру, определяется после определения структуры, чтобы компилятор знал, что в этой структуре используется соглашение о вызовах C++.

Чтобы устранить ошибку C2440 из-за несовместимых соглашений о вызовах, объявите функции, возвращающие определяемый пользователем тип после определения определяемого пользователем типа.

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

Ошибка C2440 также может возникать при присваивании нуля внутреннему указателю:

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

Ошибка C2440 также может возникать при неправильном использовании определяемого пользователем преобразования. Например, если оператор преобразования определен как **`explicit`** , компилятор не может использовать его при неявном преобразовании. Дополнительные сведения о пользовательских преобразованиях см. в разделе пользовательские [преобразования (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Этот пример приводит к возникновению ошибки C2440:

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

Ошибка C2440 также может возникать при попытке создать экземпляр Visual C++ массива, тип которого — <xref:System.Array> .  Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](../../extensions/arrays-cpp-component-extensions.md) (Массивы (C++/CLI и C++/CX)).  Следующий пример приводит к возникновению ошибки C2440:

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

Ошибка C2440 также может возникать из-за изменений в компоненте Attributes.  Следующий пример приводит к возникновению ошибки C2440.

```cpp
// c2440f.cpp
// compile with: /LD
[ module(name="PropDemoLib", version=1.0) ];   // C2440
// try the following line instead
// [ module(name="PropDemoLib", version="1.0") ];
```

Компилятор Microsoft C++ больше не разрешает [оператору const_cast](../../cpp/const-cast-operator.md) выполнить приведение, если компилируется исходный код, использующий программирование **/CLR** .

Чтобы устранить ошибку C2440, используйте правильный оператор CAST. Дополнительные сведения см. в разделе [операторы приведения](../../cpp/casting-operators.md).

Этот пример приводит к возникновению ошибки C2440:

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

Ошибка C2440 может возникать из-за изменений соответствия компилятора в Visual Studio 2015 с обновлением 3. Ранее компилятор неправильно обрабатывал некоторые отдельные выражения как один и тот же тип при определении совпадения шаблона для **`static_cast`** операции. Теперь компилятор различает типы правильно, и код, который использовался в предыдущем **`static_cast`** поведении, будет нарушен. Чтобы устранить эту проблему, измените аргумент шаблона так, чтобы он соответствовал типу параметра шаблона, или используйте **`reinterpret_cast`** приведение типа или в стиле C.

Этот пример приводит к возникновению ошибки C2440:

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

### <a name="copy-list-initialization"></a>Инициализация копии списка

Visual Studio 2017 и более поздние версии вызовут ошибки компилятора, связанные с созданием объектов, с помощью списков инициализаторов, которые не были перехвачены в Visual Studio 2015 и могут привести к сбоям или неопределенному поведению во время выполнения. В C++ 17 копирование-список-инициализация компилятору необходимо рассмотреть явный конструктор для разрешения перегрузки, но при этом должен вызвать ошибку, если эта перегрузка фактически выбрана.

Следующий пример компилируется в Visual Studio 2015, но не в Visual Studio 2017.

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

### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы при построении класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Это может привести к сбою или непредсказуемому поведению среды выполнения. Следующий пример компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017 и более поздних версиях:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Чтобы исправить эту ошибку, объявите оператор int() как константу.
