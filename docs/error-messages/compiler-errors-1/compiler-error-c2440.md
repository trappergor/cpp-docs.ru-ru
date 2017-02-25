---
title: "Ошибка компилятора C2440 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2440"
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# Ошибка компилятора C2440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"преобразование" : не удается выполните преобразование из "типа1" в "тип2"  
  
 Компилятору не удается выполнить преобразование из `type1` в `type2`.  
  
## Пример  
 Ошибка C2440 может возникать при попытке инициализации неконстантных `char*` \(или `wchar_t*`\) с помощью строкового литерала в коде C\+\+, когда указан параметр компилятора [\/Zc: strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md).  В C тип строкового литерала — это массив `char`, но в C\+\+, это массив `const` `char`.  В следующем примере появляется ошибка C2440:  
  
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
  
## Пример  
 Ошибка C2440 также может возникать при попытке преобразования указателя на член к типу void\*.  Следующий пример приводит к возникновению ошибки C2440.  
  
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
  
## Пример  
 Ошибка C2440 может также возникать при попытке приведения из типа, который объявлен с опережением, но не определен.  В следующем примере появляется ошибка C2440:  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## Пример  
 Ошибки C2440 в строках 15 и 16 следующего примера сопровождаются сообщением `Incompatible calling conventions for UDT return value`. UDT — это тип, определенный пользователем, например класс, структура или объединение. Эти виды ошибок несовместимости возникают, когда соглашение о вызове для пользовательского типа, указанного в качестве типа возвращаемого значения в предварительном объявлении, не соответствует реальному соглашению о вызове пользовательского типа и при задействовании указателя на функцию.  
  
 В примере приводятся предварительные объявления структуры и функции, возвращающей эту структуру; компилятор предполагает, что для структуры используется соглашение о вызове C\+\+.  Затем следует определение структуры, для которого по умолчанию используется соглашение о вызове C.  Поскольку соглашение о вызове, используемое для структуры, неизвестно компилятору до момента считывания всей структуры целиком, то для структуры при ее использовании в качестве типа возвращаемого значения функции `get_c2` предполагается соглашение о вызове C\+\+.  
  
 За структурой следует объявление другой функции, возвращающей структуру, но в этом месте компилятор уже знает, что для структуры используется соглашение о вызове C\+\+.  Аналогичным образом указатель на функцию, возвращающую структуру, определяется после определения структуры, поэтому компилятор знает, что для структуры используется соглашение о вызове C\+\+.  
  
 Чтобы устранить ошибку C2440, возникающую из\-за несовместимости соглашений о вызове, функции, возвращающие значения пользовательских типов, следует объявлять после определения пользовательских типов.  
  
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
  
## Пример  
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
  
## Пример  
 Ошибка C2440 также может возникать при неправильном использовании пользовательского преобразования.  Дополнительные сведения о пользовательских преобразованиях см. в разделе [Заданные пользователем преобразования](../../dotnet/user-defined-conversions-cpp-cli.md).  В следующем примере появляется ошибка C2440:  
  
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
  
## Пример  
 Ошибка C2440 также может возникать при попытке создания экземпляра массива Visual C\+\+ типа <xref:System.Array>.  Для получения дополнительной информации см. [Массивы](../../windows/arrays-cpp-component-extensions.md).  Следующий пример приводит к возникновению ошибки C2440.  
  
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
  
## Пример  
 Ошибка C2440 также может возникать из\-за изменений в функциональности атрибутов.  Следующий пример приводит к возникновению ошибки C2440.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## Пример  
 Компилятор Visual C\+\+ больше не разрешает [Оператор const\_cast](../Topic/const_cast%20Operator.md) выполнять приведение при компиляции исходного кода, использующего параметр компиляции **\/clr**.  
  
 Чтобы устранить эту ошибку C2440, используйте правильный оператор приведения типа.  Для получения дополнительной информации см. [Операторы приведения](../../cpp/casting-operators.md).  
  
 В следующем примере появляется ошибка C2440:  
  
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
  
## Пример  
 Ошибка C2440 также может возникать при использовании параметра **\/clr:oldSyntax**:  
  
```cpp  
// c2440h.cpp  
// compile with: /clr:oldSyntax  
__gc class Base {};  
__gc class Derived : public Base {};  
int main() {  
   Derived *d = new Derived;  
   Base *b = d;  
   d = const_cast<Derived*>(b);   // C2440  
   d = dynamic_cast<Derived*>(b);   // OK  
}  
```