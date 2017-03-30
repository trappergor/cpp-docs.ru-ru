---
title: "Ошибка компилятора C2440 | Документы Microsoft"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: d2855f44e05e095f8e1e5cf992eacaafcbe8464d
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-error-c2440"></a>Ошибка компилятора C2440
«Преобразование»: невозможно преобразовать из «тип1» в «тип2»  
  
Компилятору не удается преобразовать `type1` для `type2`.  
  
## <a name="example"></a>Пример  
C2440 может возникать при попытке инициализировать неконстантной `char*` (или `wchar_t*`) с помощью строкового литерала в коде на языке C++ при параметр компилятора соответствия [/Zc: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) имеет значение. В языке C тип строкового литерала — массив `char`, но в C++ это массив `const char`. В следующем примере возникает ошибка C2440:  
  
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
 Ошибка C2440 также может возникать при попытке выполнить приведение от типа, который объявлен только вперед, но не определен. В следующем примере возникает ошибка C2440:  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>Пример  
 Ошибки C2440 в строках 15 и 16 следующего примера дополнены `Incompatible calling conventions for UDT return value` сообщения. Объект *определяемого пользователем ТИПА* имеет определяемый пользователем тип, например класс, структура или объединение. Эти виды ошибок несовместимости возникают при указании соглашение о вызовах определяемого пользователем типа в тип возвращаемого значения опережающего объявления конфликтует с фактическое соглашение о вызовах определяемого пользователем типа и при задействовании указателя.  
  
 В примере сначала существует упреждающие объявления структуры и функции, возвращающий структуру; компилятор предполагает, что для структуры используется соглашение о вызове C++. Далее определение структуры, для которого по умолчанию использует C соглашение о вызовах. Так как компилятор не знает соглашение о вызовах структуры до момента считывания всей структуры соглашение о вызовах для структуры в тип возвращаемого значения `get_c2` также считается C++.  
  
 Структура следуют объявление другой функции, возвращающий структуру, но на этом этапе компилятор знает, что структура соглашение о вызовах C++. Аналогичным образом указатель на функцию, возвращающую структуру, определяется после определения структуры, чтобы компилятор знает, что для структуры используется соглашение о вызове C++.  
  
 Чтобы устранить C2440, возникающее из-за несовместимости соглашений о вызове, объявления функций, возвращающих определяемого пользователем ТИПА после определение определяемого пользователем ТИПА.  
  
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
 Ошибка C2440 также может возникать при неправильном использовании пользовательского преобразования. Например, когда оператор преобразования был определен как `explicit`, компилятор не может использовать его в неявное преобразование. Дополнительные сведения о пользовательских преобразований см. в разделе [пользовательских преобразований (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). В следующем примере возникает ошибка C2440:  
  
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
 Ошибка C2440 также может возникать при попытке создания экземпляра массива Visual C++, тип которого является <xref:System.Array>.</xref:System.Array>  Дополнительные сведения см. в разделе [массивы](../../windows/arrays-cpp-component-extensions.md).  Следующий пример приводит к возникновению ошибки C2440:  
  
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
 Ошибка C2440 также может возникать из-за изменения в функциональности атрибутов.  Следующий пример приводит к возникновению ошибки C2440.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>Пример  
 Компилятор Visual C++ не допускает [оператор const_cast](../../cpp/const-cast-operator.md) вниз при приведении исходный код, который использует **/CLR** компилируется программирования.  
  
 Чтобы устранить это C2440, используйте подходящий оператор приведения. Дополнительные сведения см. в разделе [операторы приведения](../../cpp/casting-operators.md).  
  
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
Ошибка C2440 может возникать из-за изменений совместимости для компилятора в Visual Studio 2015 с обновлением 3. Ранее, компилятор неверную интерпретацию определенных уникальных выражений с тем же типом при определении шаблону для `static_cast` операции. Теперь компилятор различает типы правильно и код полагались на предыдущем `static_cast` разрывается поведении. Чтобы устранить эту проблему, измените аргумента шаблона соответствует типу параметра шаблона, или использовать `reinterpret_cast` или приведение в стиле.
  
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

2017 и более поздней версии Visual Studio правильно возникают ошибки компилятора, связанные с создания объекта, с помощью списков инициализаторов, которые не были перехватываются в Visual Studio 2015 и может привести к сбою или не определено поведение во время выполнения. Согласно N4594 13.3.1.7p1 в инициализации копии списка компилятор должен учитывать явный конструктор для разрешения перегрузки, но должен выдавать ошибку, если эта перегрузка выбирается на самом деле.
Следующие два примера кода компилируются в Visual Studio 2015, но не в Visual Studio 2017.

```
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Чтобы исправить эту ошибку, следует использовать прямую инициализацию:

```
A a1{ 1 };
const A& a2{ 1 };
```

## <a name="example"></a>Пример
### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы при построении класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Это может привести к сбою или непредсказуемому поведению среды выполнения. В следующем примере компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017 г. и более поздних версий:

```
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Чтобы исправить эту ошибку, объявите оператор int() как константу.

