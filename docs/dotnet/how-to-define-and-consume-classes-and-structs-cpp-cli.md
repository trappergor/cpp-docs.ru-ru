---
title: Практическое руководство. Определение и использование классов и структур (C++/CLI)
ms.date: 09/12/2018
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 5bec92ce2bd97f11723cdf59c58b7331b39565f2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370185"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Практическое руководство. Определение и использование классов и структур (C++/CLI)

В этой статье показано, как определять и потреблять определенные пользователем типы ссылок и типы значений в СЗ/CLI.

## <a name="contents"></a><a name="BKMK_Contents"></a>Содержимое

[Мгновенное восприятие объекта](#BKMK_Object_instantiation)

[Неявно абстрактные классы](#BKMK_Implicitly_abstract_classes)

[Тип видимости](#BKMK_Type_visibility)

[Видимость участников](#BKMK_Member_visibility)

[Государственные и частные родные классы](#BKMK_Public_and_private_native_classes)

[Статические конструкторы](#BKMK_Static_constructors)

[Семантика этого указателя](#BKMK_Semantics_of_the_this_pointer)

[Функции скрытия по подписи](#BKMK_Hide_by_signature_functions)

[Конструкторы копии](#BKMK_Copy_constructors)

[Деструкторов и финализаторов](#BKMK_Destructors_and_finalizers)

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a>Мгновенное восприятие объекта

Типы ссылок (рефери) могут быть мгновенно определены только на управляемой куче, а не в стеке или на родной куче. Типы значений могут быть мгновенно в стеке или управляемой кучи.

```cpp
// mcppv2_ref_class2.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;

   // nested class
   ref class MyClass2 {
   public:
      int i;
   };

   // nested interface
   interface struct MyInterface {
      void f();
   };
};

ref class MyClass2 : public MyClass::MyInterface {
public:
   virtual void f() {
      System::Console::WriteLine("test");
   }
};

public value struct MyStruct {
   void f() {
      System::Console::WriteLine("test");
   }
};

int main() {
   // instantiate ref type on garbage-collected heap
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass -> i = 4;

   // instantiate value type on garbage-collected heap
   MyStruct ^ p_MyStruct = gcnew MyStruct;
   p_MyStruct -> f();

   // instantiate value type on the stack
   MyStruct p_MyStruct2;
   p_MyStruct2.f();

   // instantiate nested ref type on garbage-collected heap
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;
   p_MyClass2 -> i = 5;
}
```

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a>Неявно абстрактные классы

Неявно *абстрактный класс* не может быть мгновенно. Класс неявно абстрактный, если базовый тип класса является интерфейсом и класс не выполняет все функции члена интерфейса.

Если вы не можете построить объекты из класса, полученного из интерфейса, причина может заключаться в том, что класс неявно абстрактный. Для получения дополнительной информации об абстрактных классах, [см.](../extensions/abstract-cpp-component-extensions.md)

Следующий пример кода показывает, что `MyClass` класс не может `MyClass::func2` быть мгновенно, поскольку функция не реализована. Для того, чтобы пример компилировать, без комментариев `MyClass::func2`.

```cpp
// mcppv2_ref_class5.cpp
// compile with: /clr
interface struct MyInterface {
   void func1();
   void func2();
};

ref class MyClass : public MyInterface {
public:
   void func1(){}
   // void func2(){}
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259
                                          // To resolve, uncomment MyClass::func2.
}
```

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a>Тип видимости

Можно контролировать видимость типов общего времени выполнения языка (CLR), чтобы при упоминании сборки типы в сборке могли быть видны или не были видны вне сборки.

`public`указывает на то, что тип виден `#using` любому исходного файла, содержащего директиву для сборки, содержащую тип.  `private`указывает на то, что тип не `#using` виден исходным файлам, содержащим директиву для сборки, содержащей тип. Однако частные типы видны в одной сборке. По умолчанию видимость для `private`класса .

По умолчанию до Visual Studio 2005, родние типы имели публичную доступность вне сборки. Включить [Предупреждение компилятора (уровень 1) C4692,](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) чтобы помочь вам увидеть, где частные типы назании используются неправильно. Используйте [make_public](../preprocessor/make-public.md) прагму, чтобы предоставить публичную доступность родному типу в файле исходного кода, который нельзя изменить.

Дополнительные сведения см. в разделе [Директива using](../preprocessor/hash-using-directive-cpp.md).

В следующем примере показано, как декларировать типы и указывать их доступность, а затем получить доступ к этим типам внутри сборки. Конечно, если сборка, которая имеет частные `#using`типы, ссылается с помощью, только общедоступные типы в сборке видны.

```cpp
// type_visibility.cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// default accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   Private_Class ^ b = gcnew Private_Class;
   b->Test();

   Private_Class_2 ^ c = gcnew Private_Class_2;
   c->Test();
}
```

**Вывод**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

Теперь давайте перепишем предыдущий образец так, чтобы он был построен как DLL.

```cpp
// type_visibility_2.cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside the assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// by default, accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};
```

В следующем примере показано, как получить доступ к типам вне сборки. В этом примере клиент потребляет компонент, встроенный в предыдущий пример.

```cpp
// type_visibility_3.cpp
// compile with: /clr
#using "type_visibility_2.dll"
int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   // private types not accessible outside the assembly
   // Private_Class ^ b = gcnew Private_Class;
   // Private_Class_2 ^ c = gcnew Private_Class_2;
}
```

**Вывод**

```Output
in Public_Class
```

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a>Видимость участников

Вы можете сделать доступ к члену публичного класса из одной и той же сборки отличается от `public`доступа `protected`к нему из-за пределов сборки, используя пары спецификаторов доступа, и`private`

В этой таблице кратко излагается влияние различных спецификаторов доступа:

|Описатель|Действие|
|---------------|------------|
|public|Участник доступен как внутри, так и за пределами сборки.  Дополнительную информацию можно узнать в [открытом доступе.](../cpp/public-cpp.md)|
|private|Участник недоступен ни внутри, ни за пределами сборки.  Дополнительную информацию можно узнать в [закрытом режиме.](../cpp/private-cpp.md)|
|protected|Участник доступен внутри и за пределами сборки, но только для производных типов.  Подробнее о [ней читайте в сообщении.](../cpp/protected-cpp.md)|
|internal|Член является общедоступным внутри собрания, но частным вне собрания.  `internal` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](../extensions/context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)).|
|охраняемых или охраняемых|Участник является общедоступным внутри собрания, но защищен за пределами собрания.|
|частные охраняемые или охраняемые частные|Участник защищен внутри сборки, но частный вне сборки.|

В следующем примере показан публичный тип, который имеет членов, которые объявляются с различными доступности, а затем показывает доступ этих членов изнутри сборки.

```cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();
   a->Protected_Public_Function();
   a->Public_Protected_Function();

   // accessible inside but not outside the assembly
   a->Internal_Function();

   // call protected functions
   b->Test();

   // not accessible inside or outside the assembly
   // a->Private_Function();
}
```

**Вывод**

```Output
in Public_Function
in Protected_Public_Function
in Public_Protected_Function
in Internal_Function
=======================
in function of derived class
in Protected_Function
in Protected_Private_Function
in Private_Protected_Function
exiting function of derived class
=======================
```

Теперь давайте построим предыдущий образец в качестве DLL.

```cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};
```

Следующий пример потребляет компонент, созданный в предыдущем образце, и, таким образом, показывает, как получить доступ к членам из-за пределов сборки.

```cpp
// compile with: /clr
#using "type_member_visibility_2.dll"
using namespace System;
// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Public_Function();
      Public_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();

   // call protected functions
   b->Test();

   // can't be called outside the assembly
   // a->Private_Function();
   // a->Internal_Function();
   // a->Protected_Private_Function();
   // a->Private_Protected_Function();
}
```

**Вывод**

```Output
in Public_Function
=======================
in function of derived class
in Protected_Function
in Protected_Public_Function
in Public_Protected_Function
exiting function of derived class
=======================
```

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a>Государственные и частные родные классы

Родной тип может быть отсылкой из управляемого типа.  Например, функция в управляемом типе может принимать параметр, тип которого является родной структурой.  Если управляемый тип и функция являются общедоступными в сборке, то родной тип также должен быть общедоступным.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Затем создайте исходный код, который потребляет родной тип:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Теперь составить клиент:

```cpp
// compile with: /clr
#using "mcppv2_ref_class3.dll"

#include "mcppv2_ref_class3.h"

int main() {
   R ^r = gcnew R;
   N n;
   r->f(n);
}
```

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a>Статические конструкторы

Тип CLR, например, класс или структура могут иметь статический конструктор, который может быть использован для инициализации статических членов данных.  Статический конструктор вызывается не чаще одного раза и вызывается до того, как в первый раз будет доступен какой-либо статический член типа.

Конструктор экземпляра всегда работает после статического конструктора.

Компилятор не может вставить вызов в конструктор, если класс имеет статический конструктор.  Компилятор не может вводить вызов в функцию какой-либо элемента, если класс является типом значения, имеет статический конструктор и не имеет конструктора экземпляра.  CLR может вставить вызов, но компилятор не может.

Определите статический конструктор как функцию частного члена, потому что он предназначен для вызова только CLR.

Для получения более подробной информации о статических конструкторах [см.](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref class MyClass {
private:
   static int i = 0;

   static MyClass() {
      Console::WriteLine("in static constructor");
      i = 9;
   }

public:
   static void Test() {
      i++;
      Console::WriteLine(i);
   }
};

int main() {
   MyClass::Test();
   MyClass::Test();
}
```

**Вывод**

```Output
in static constructor
10
11
```

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a>Семантика этого указателя

При использовании Visual C 'для определения `this` типов указатель в типе ссылки имеет тип "ручка". Указатель `this` в типе значения типа "внутренний указатель".

Эти различные семантики `this` указателя могут вызвать неожиданное поведение при вызове индекса по умолчанию. Следующий пример показывает правильный способ доступа к индексу по умолчанию как в типе рефа, так и в типе значения.

Дополнительные сведения см. в разделе

- [Оператор дескриптора объекта (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../extensions/interior-ptr-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      // accessing default indexer
      Console::WriteLine("{0}", this[3.3]);
   }
};

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      // accessing default indexer
      Console::WriteLine("{0}", this->default[3.3]);
   }
};

int main() {
   A ^ mya = gcnew A();
   B ^ myb = gcnew B();
   myb->Test();
}
```

**Вывод**

```Output
10.89
10.89
```

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a>Функции скрытия по подписи

В стандартном СЗ функция в базовом классе скрыта функцией, которая имеет то же имя в производном классе, даже если функция производного класса не имеет такого же количества или параметров. Это называется семантикой семантики *спрятки* по имени. В базовом типе функция в базовом классе может быть скрыта функцией в производном классе только в том случае, если и имя, и список параметров одинаковы. Это называется семантикой *прятки.*

Класс считается классом прятки, когда все его функции отмечены `hidebysig`в метаданных как . По умолчанию все классы, которые `hidebysig` создаются под **/clr,** имеют функции. Когда класс `hidebysig` имеет функции, компилятор не скрывает функции по имени в любых прямых базовых классах, но если компилятор сталкивается с классом прятки в цепочке наследования, он продолжает это поведение прятки по имени.

При семантике сеантики сеантики спрактификана, когда функция вызывается на объекте, компилятор определяет наиболее производный класс, содержащий функцию, которая может удовлетворить вызов функции. Если в классе есть только одна функция, которая может удовлетворить вызов, компилятор вызывает эту функцию. Если в классе есть несколько функций, которые могут удовлетворить вызов, компилятор использует правила разрешения перегрузки, чтобы определить, какую функцию вызывать. Для получения дополнительной информации [Function Overloading](../cpp/function-overloading.md)о правилах перегрузки см.

Для заданного вызова функции в базовом классе может иметься подпись, что делает ее немного лучшей, чем функция в производном классе. Однако, если функция была явно вызвана на объект производного класса, функция в производном классе называется.

Поскольку значение возврата не считается частью подписи функции, функция базового класса скрыта, если она имеет то же имя и принимает такое же количество и вид аргументов, что и функция производного класса, даже если она отличается по типу значения возврата.

Следующий пример показывает, что функция в базовом классе не скрыта функцией в производном классе.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test() {
      Console::WriteLine("Base::Test");
   }
};

ref struct Derived : public Base {
   void Test(int i) {
      Console::WriteLine("Derived::Test");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Test() in the base class will not be hidden
   t->Test();
}
```

**Вывод**

```Output
Base::Test
```

Следующий пример показывает, что компилятор Microsoft C' вызывает функцию в наиболее производном классе, даже если конверсия необходима, чтобы соответствовать одному или более параметрам, и не вызывать функцию в базовом классе, который лучше подходит для вызова функции.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test2(Single d) {
      Console::WriteLine("Base::Test2");
   }
};

ref struct Derived : public Base {
   void Test2(Double f) {
      Console::WriteLine("Derived::Test2");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Base::Test2 is a better match, but the compiler
   // calls a function in the derived class if possible
   t->Test2(3.14f);
}
```

**Вывод**

```Output
Derived::Test2
```

Следующий пример показывает, что можно скрыть функцию, даже если базовый класс имеет ту же подпись, что и производный класс.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   int Test4() {
      Console::WriteLine("Base::Test4");
      return 9;
   }
};

ref struct Derived : public Base {
   char Test4() {
      Console::WriteLine("Derived::Test4");
      return 'a';
   }
};

int main() {
   Derived ^ t = gcnew Derived;

   // Base::Test4 is hidden
   int i = t->Test4();
   Console::WriteLine(i);
}
```

**Вывод**

```Output
Derived::Test4
97
```

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a>Копирование конструкторов

Стандарт СЗЗ гласит, что конструктор копии вызывается при перемещении объекта, таким образом, что объект создается и уничтожается по тому же адресу.

Однако, когда **/clr** используется для компиляции и функция, которая компилируется на MSIL вызывает родную функцию, где родной класс или более одного передается по стоимости и где родной класс имеет конструктор копий и/или деструктор, ни один конструктор копирования не называется и объект разрушается по другому адресу, чем там, где он был создан. Это может привести к проблемам, если класс имеет указатель в себя, или если код отслеживает объекты по адресу.

Для получения дополнительной информации [см.](../build/reference/clr-common-language-runtime-compilation.md)

Следующий пример показывает, когда не генерируется конструктор копий.

```cpp
// compile with: /clr
#include<stdio.h>

struct S {
   int i;
   static int n;

   S() : i(n++) {
      printf_s("S object %d being constructed, this=%p\n", i, this);
   }

   S(S const& rhs) : i(n++) {
      printf_s("S object %d being copy constructed from S object "
               "%d, this=%p\n", i, rhs.i, this);
   }

   ~S() {
      printf_s("S object %d being destroyed, this=%p\n", i, this);
   }
};

int S::n = 0;

#pragma managed(push,off)
void f(S s1, S s2) {
   printf_s("in function f\n");
}
#pragma managed(pop)

int main() {
   S s;
   S t;
   f(s,t);
}
```

**Вывод**

```Output
S object 0 being constructed, this=0018F378
S object 1 being constructed, this=0018F37C
S object 2 being copy constructed from S object 1, this=0018F380
S object 3 being copy constructed from S object 0, this=0018F384
S object 4 being copy constructed from S object 2, this=0018F2E4
S object 2 being destroyed, this=0018F380
S object 5 being copy constructed from S object 3, this=0018F2E0
S object 3 being destroyed, this=0018F384
in function f
S object 5 being destroyed, this=0018F2E0
S object 4 being destroyed, this=0018F2E4
S object 1 being destroyed, this=0018F37C
S object 0 being destroyed, this=0018F378
```

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a>Деструкторов и финализаторов

Деструктора в справочном типе выполняют детерминированную очистку ресурсов. Финалисты очищают неуправляемые ресурсы и могут быть названы детерминированным детерминатором или недетерминированным сборщиком мусора. Для получения информации о деструкторах в стандартном СЗ [см.](../cpp/destructors-cpp.md)

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Поведение деструкторов в управляемом классе Visual C', отличается от управляемых расширений для СЗ. Для получения дополнительной информации об этом изменении [см.](../dotnet/changes-in-destructor-semantics.md)

Сборщик мусора CLR удаляет неиспользованные управляемые объекты и выпускает их память, когда они больше не требуются. Тем не менее, тип может использовать ресурсы, которые сборщик мусора не знает, как освободить. Эти ресурсы известны как неуправляемые ресурсы (например, на носителях файлов). Мы рекомендуем вам выпустить все неуправляемые ресурсы в finalizer. Поскольку управляемые ресурсы недетерминированы сборщиком мусора, небезопасно ссылаться на управляемые ресурсы в финализаторе, поскольку возможно, что сборщик мусора уже очистил этот управляемый ресурс.

Визуальный финализатор C ' не <xref:System.Object.Finalize%2A> то же самое, что метод. (документация CLR использует <xref:System.Object.Finalize%2A> финализатор и метод синонимично). Метод <xref:System.Object.Finalize%2A> вызывается сборщиком мусора, который вызывает каждого finalizer в цепочке наследования класса. В отличие от деструкторов Visual C', вызов финалиста производных классов не вызывает вызов компилятора для вызова финалиста во всех базовых классах.

Поскольку компилятор Microsoft C's поддерживает детерминированный выпуск <xref:System.IDisposable.Dispose%2A> <xref:System.Object.Finalize%2A> ресурсов, не пытайтесь реализовать или методы. Однако, если вы знакомы с этими методами, вот как визуальный финализатор и деструктор, <xref:System.IDisposable.Dispose%2A> который вызывает карту finalizer к шаблону:

```cpp
// Visual C++ code
ref class T {
   ~T() { this->!T(); }   // destructor calls finalizer
   !T() {}   // finalizer
};

// equivalent to the Dispose pattern
void Dispose(bool disposing) {
   if (disposing) {
      ~T();
   } else {
      !T();
   }
}
```

Управляемый тип может также использовать управляемые ресурсы, которые вы предпочли бы освободить детерминированно, и не оставлять сборщику мусора выпускать недетерминированный момент после того, как объект больше не требуется. Детерминированный высвобождение ресурсов может значительно повысить производительность.

Компилятор Microsoft C's позволяет определить деструктор для детерминированной очистки объектов. Используйте деструктор, чтобы освободить все ресурсы, которые вы хотите детерминировать.  Если доборщик присутствует, позвоните ему из деструктора, чтобы избежать дублирования кода.

```cpp
// compile with: /clr /c
ref struct A {
   // destructor cleans up all resources
   ~A() {
      // clean up code to release managed resource
      // ...
      // to avoid code duplication,
      // call finalizer to release unmanaged resources
      this->!A();
   }

   // finalizer cleans up unmanaged resources
   // destructor or garbage collector will
   // clean up managed resources
   !A() {
      // clean up code to release unmanaged resources
      // ...
   }
};
```

Если код, потребляемый в вашем типе, не вызывает деструктор, сборщик мусора в конечном итоге выпускает все управляемые ресурсы.

Наличие деструктора не означает наличие финалиста. Однако наличие finalizer подразумевает, что вы должны определить деструктор и вызвать финализатор из этого деструктора. Это обеспечивает детерминированное высвобождение неуправляемых ресурсов.

Вызов деструктора подавляет с <xref:System.GC.SuppressFinalize%2A>помощью -завершения объекта. Если деструктор не называется, финтизатор вашего типа в конечном итоге будет вызван сборщиком мусора.

Детерминационно очистка ресурсов объекта, вызывая деструктор может повысить производительность по сравнению с позволяя CLR недетерминированно завершить объект.

Код, написанный в Visual C и компилированный с помощью **/clr,** запускает деструктор типа, если:

- Объект, созданный с помощью семантики стека, выходит за рамки. Для получения более [C++ Stack Semantics for Reference Types](../dotnet/cpp-stack-semantics-for-reference-types.md)подробной информации см.

- Исключение выбрасывается при строительстве объекта.

- Объект является членом объекта, разрушаемый объект которого работает.

- Вы называете оператора [удаления](../cpp/delete-operator-cpp.md) на ручке[(Ручка к оператору объекта (яп.)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)).

- Вы явно называете деструктора.

Если ваш тип потребляется клиентом, написанным на другом языке, деструктор называется следующим образом:

- По вызову <xref:System.IDisposable.Dispose%2A>.

- По вызову `Dispose(void)` по типу.

- Если тип выходит за рамки в `using` выписке c's.

Если на управляемой куче создан объект эталонного типа (не используя семантику стека для типов ссылок), используйте синтаксис [try-finally,](../cpp/try-finally-statement.md) чтобы убедиться, что исключение не предотвращает запуск деструктора.

```cpp
// compile with: /clr
ref struct A {
   ~A() {}
};

int main() {
   A ^ MyA = gcnew A;
   try {
      // use MyA
   }
   finally {
      delete MyA;
   }
}
```

Если ваш тип имеет деструктор, компилятор `Dispose` генерирует <xref:System.IDisposable>метод, который реализуется. Если тип, написанный в Visual C и имеет деструктор, потребляемый `IDisposable::Dispose` с другого языка, вызов этого типа вызывает вызов деструктора типа. Когда тип потребляется от клиента Visual C, вы не `Dispose`можете напрямую позвонить; вместо этого позвоните в деструктор с помощью `delete` оператора.

Если ваш тип имеет финализатор, компилятор генерирует `Finalize(void)` метод, который переопределяет. <xref:System.Object.Finalize%2A>

Если тип имеет либо финализатор, либо деструктор, `Dispose(bool)` компилятор генерирует метод в соответствии с шаблоном проектирования. (Для получения информации [см. Шаблон распоряжаться).](/dotnet/standard/design-guidelines/dispose-pattern) Вы не можете явно `Dispose(bool)` автор или вызов в Visual C .

Если тип имеет базовый класс, соответствующий шаблону проектирования, то деструкторов для всех базовых классов вызываются при вызове деструктора для производного класса. (Если ваш тип записан в Visual C, компилятор гарантирует, что ваши типы реализуют этот шаблон.) Другими словами, деструктор цепи эталонного класса к его основаниям и членам, как указано в стандарте СЗ, сначала происходит деструктор класса, затем деструкторов для его членов в обратном порядке, в котором они были построены, и, наконец, деструкторов для своих базовых классов в обратном порядке, в котором они были построены.

Деструкторам и finalizers не допускаются внутри типов значений или интерфейсов.

Окончательный исключитель может быть определен или объявлен в типов ссылки. Как конструктор и деструктор, финализатор не имеет типа возврата.

После завершения финального запуска объекта также называются финализаторы в любых базовых классах, начиная с наименее производного типа. Финализаторы для участников данных не прикованы автоматически к финализатору класса.

Если финалист удаляет родной указатель в управляемом типе, необходимо убедиться, что ссылки на родной указатель не собираются преждевременно; вызова деструктора на управляемом типе вместо использования <xref:System.GC.KeepAlive%2A>.

Во время компилирования можно определить, есть ли тип для finalizer или деструктор. Дополнительные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

В следующем примере показаны два типа: один с неуправляемыми ресурсами, а другой — управляемые ресурсы, детерминированные.

```cpp
// compile with: /clr
#include <vcclr.h>
#include <stdio.h>
using namespace System;
using namespace System::IO;

ref class SystemFileWriter {
   FileStream ^ file;
   array<Byte> ^ arr;
   int bufLen;

public:
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),
                                     arr(gcnew array<Byte>(1024)) {}

   void Flush() {
      file->Write(arr, 0, bufLen);
      bufLen = 0;
   }

   ~SystemFileWriter() {
      Flush();
      delete file;
   }
};

ref class CRTFileWriter {
   FILE * file;
   array<Byte> ^ arr;
   int bufLen;

   static FILE * getFile(String ^ n) {
      pin_ptr<const wchar_t> name = PtrToStringChars(n);
      FILE * ret = 0;
      _wfopen_s(&ret, name, L"ab");
      return ret;
   }

public:
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}

   void Flush() {
      pin_ptr<Byte> buf = &arr[0];
      fwrite(buf, 1, bufLen, file);
      bufLen = 0;
   }

   ~CRTFileWriter() {
      this->!CRTFileWriter();
   }

   !CRTFileWriter() {
      Flush();
      fclose(file);
   }
};

int main() {
   SystemFileWriter w("systest.txt");
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");
}
```

## <a name="see-also"></a>См. также раздел

[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)<br/>
[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)
