---
title: Практическое руководство. Определение и использование классов и структур (C++выполняет)
ms.date: 09/12/2018
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 090259a4ad6b46eccf66dca6c99b4eb532b7ae5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387491"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Практическое руководство. Определение и использование классов и структур (C++выполняет)

В этой статье показано, как определение и использование определяемых пользователем ссылочных типов и типов значений в C++выполняет.

##  <a name="BKMK_Contents"></a> Описание

[При создании объектов](#BKMK_Object_instantiation)

[Неявно абстрактные классы](#BKMK_Implicitly_abstract_classes)

[Видимость типов](#BKMK_Type_visibility)

[Видимость членов](#BKMK_Member_visibility)

[Общедоступные и частные собственных классов](#BKMK_Public_and_private_native_classes)

[Статические конструкторы](#BKMK_Static_constructors)

[Семантика этого указателя](#BKMK_Semantics_of_the_this_pointer)

[Скрыть-функции со скрываемой сигнатурой](#BKMK_Hide_by_signature_functions)

[Конструкторы копии](#BKMK_Copy_constructors)

[Деструкторы и методы завершения](#BKMK_Destructors_and_finalizers)

##  <a name="BKMK_Object_instantiation"></a> При создании объектов

Типы ссылку (ref) могут быть созданы только в управляемой куче, не в стеке или в собственной куче. Типы значений могут быть созданы в стеке или управляемой кучи.

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

##  <a name="BKMK_Implicitly_abstract_classes"></a> Неявно абстрактные классы

*Неявно абстрактного класса* не может быть создан. Класс является абстрактным неявно, если базовый тип класса является интерфейсом, а класс не реализует все функции-члены этого интерфейса.

Если вы не сможете создать объекты из класса, который является производным от интерфейса, причина может быть, что данный класс является абстрактным неявно. Дополнительные сведения об абстрактных классах см. в разделе [абстрактный](../extensions/abstract-cpp-component-extensions.md).

В следующем примере кода показано, что `MyClass` класс не может быть создан, так как функция `MyClass::func2` не реализован. Чтобы включить в примере для компиляции, раскомментируйте `MyClass::func2`.

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

##  <a name="BKMK_Type_visibility"></a> Видимость типов

Можно управлять видимостью типов среды выполнения (CLR), поэтому, если ссылка на сборку задана типы в сборке может быть видимым или невидимым за пределами сборки.

`public` Указывает, что тип является видимым для любого исходного файла, содержащего `#using` директив для сборки, содержащей тип.  `private` Указывает, что тип не является видимым для исходных файлов, содержащих `#using` директив для сборки, содержащей тип. Тем не менее закрытые типы, видимые в пределах той же сборки. По умолчанию — видимость для класса `private`.

По умолчанию до Visual C++ 2005 собственные типы были открытый доступ за пределами сборки. Включить [Предупреждение компилятора (уровень 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) поможет увидеть, где частный собственных типов используются неправильно. Используйте [make_public](../preprocessor/make-public.md) директиву pragma, чтобы предоставить открытый доступ к собственный тип в файл исходного кода, которые нельзя изменить.

Дополнительные сведения см. в разделе [Директива using](../preprocessor/hash-using-directive-cpp.md).

Следующий пример показано, как объявлять типы и указать их доступность, а также получить доступ к эти типы в сборке. Конечно, если сборка, закрытых типов указывается с помощью `#using`только открытые типы в сборке являются видимыми.

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

Теперь давайте перепишем предыдущего примера, чтобы она создается как библиотеку DLL.

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

В приведенном ниже примере показано, как для доступа к типам за пределы данной сборки. В этом примере клиент использует компонент, который встроен в предыдущем примере.

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

##  <a name="BKMK_Member_visibility"></a> Видимость членов

Вы может упростить доступ к членом открытого класса из той же сборки отличается от доступа к нему из за пределов сборки с помощью пары описатели доступа `public`, `protected`, и `private`

В следующей таблице перечислены последствия различных описатели доступа:

|Описатель|Действие|
|---------------|------------|
|public|Элемент доступен внутри и вне сборки.  См. в разделе [открытый](../cpp/public-cpp.md) Дополнительные сведения.|
|private|Член недоступен, ни внутри, ни за пределы данной сборки.  См. в разделе [частного](../cpp/private-cpp.md) Дополнительные сведения.|
|protected|Элемент доступен внутри и вне сборки, но только для производных типов.  См. в разделе [защищенные](../cpp/protected-cpp.md) Дополнительные сведения.|
|internal|Член является общедоступной внутри сборки, но закрытый за пределы данной сборки.  `internal` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в разделе [контекстные ключевые слова](../extensions/context-sensitive-keywords-cpp-component-extensions.md).|
|открытый защищенный - или - защищенных public|Член является общедоступной внутри сборки, однако защищены за пределы данной сборки.|
|закрытый защищенный - или - защищенных private|Член является защищенным внутри сборки, но закрытый за пределы данной сборки.|

В следующем примере показан открытый тип, который содержит члены, которые были определены в разные уровни доступности и затем показывает доступ к объекту этих элементов из внутри сборки.

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

Теперь давайте создадим предыдущего примера как библиотеку DLL.

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

В следующем примере используется компонент, который создается в предыдущем примере и тем самым показано, как получить доступ к членам за пределами сборки.

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

##  <a name="BKMK_Public_and_private_native_classes"></a> Общедоступные и частные собственных классов

Собственный тип может ссылаться на управляемый тип.  Например функция в управляемом типе может принимать параметр с типом собственной структуры.  Если в сборке открыты управляемый тип и функцию, затем собственный тип должны также быть открытыми.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Создайте файл исходного кода, который использует собственный тип:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Теперь скомпилируйте клиента:

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

##  <a name="BKMK_Static_constructors"></a> Статические конструкторы

Тип CLR, например, класс или структура — может иметь статический конструктор, который может использоваться для инициализации статических элементов данных.  Статический конструктор вызывается не более одного раза и вызывается перед любой статический член типа осуществляется в первый раз.

Конструктор экземпляра всегда выполняется после статический конструктор.

Компилятор не может выполнить подстановку вызов конструктора, если класс имеет статический конструктор.  Компилятор не может выполнить подстановку вызов любой функции-члена, если данный класс является типом значения, имеет статический конструктор и не имеет конструктора экземпляра.  Среда CLR может вводить вызов, но компилятор не может.

Определите статический конструктор как закрытая функция-член, так как он должен вызываться только средой CLR.

Дополнительные сведения о статических конструкторов, см. в разделе [как: Определение статического конструктора интерфейса (C++выполняет)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .

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

##  <a name="BKMK_Semantics_of_the_this_pointer"></a> Семантика этого указателя

При использовании Visual C++ для определения типов, `this` указатель в ссылочный тип имеет тип «маркер». `this` Указатель на тип значения имеет тип «внутренний указатель».

Эти разные семантики `this` указатель может привести к непредвиденному поведению при вызове индексатор по умолчанию. В следующем примере правильный способ доступа к индексатору по умолчанию в ссылочного типа и типа значения.

Дополнительные сведения см. в разделе .

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

##  <a name="BKMK_Hide_by_signature_functions"></a> Скрыть-функции со скрываемой сигнатурой

В стандартном языке C++ функцию в базовом классе скрыт функцию, которая имеет то же имя в производном классе, даже если функция производного класса не имеют одинаковый номер или тип параметров. Это называется *скрыть по имени* семантику. В ссылочный тип функцию в базовом классе можно только скрыть, функция в производном классе, если имя и список параметров одинаковы. Этот процесс называется *по подписи* семантику.

Класс считается класс по подписи, когда все его функции отмечены в метаданных как `hidebysig`. По умолчанию, все классы, созданные в **/CLR** имеют `hidebysig` функции. Если класс имеет `hidebysig` функции, компилятор не скрывает функции по имени в прямых базовых классов, но если компилятор обнаруживает скрыть по имени класса в цепочке наследования, он продолжает это поведение скрытия по имени.

В семантике по подписи при вызове функции для объекта, компилятор определяет наиболее производного класса, содержащего функцию, которая может удовлетворить вызова функции. Если имеется только одна функция в классе, который могут удовлетворять вызов, компилятор вызывает эту функцию. Если имеется более одной функции в классе, который могут удовлетворять вызов, компилятор использует перегрузку правила разрешения, чтобы определить, какую функцию вызвать. Дополнительные сведения о правилах перегрузки, см. в разделе [перегрузка функций](../cpp/function-overloading.md).

Для вызова данной функции функции в базовом классе может иметь сигнатуру, которая становится немного лучше, чем функция в производном классе. Тем не менее если функция явно был вызван для объекта производного класса, вызывается функция в производном классе.

Так как возвращаемое значение не считается частью сигнатуры функции, функции базового класса является скрытым, если он имеет то же имя и принимает то же количество и тип аргументов, как функция производного класса, даже если он отличается в типе возвращаемого значения.

В следующем примере показано, что функция в базовом классе не скрыт с помощью функции в производном классе.

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

В приведенном ниже примере показано, что компилятор Visual C++ вызывает функцию в наиболее производный класс, даже если преобразование должен соответствовать один или несколько параметров и не вызывать функцию в базовом классе, который лучше подходит для вызова функции.

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

Следующий пример показывает, что это можно скрыть функции, даже если базовый класс имеет ту же сигнатуру, как и производный класс.

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

##  <a name="BKMK_Copy_constructors"></a> Конструкторы копии

Стандарт C++ указывает, что конструктор копии вызывается при перемещении объекта таким образом, что объект создается и уничтожается по тому же адресу.

Тем не менее, если **/CLR** используется для компиляции и функцию, которая компилируется в собственную функцию там, где собственного класса вызовы MSIL — или более одного — передается по значению и где собственный класс имеет конструктор копии и/или деструктора, копия конструктор вызывается и уничтожения объекта адресу, отличному от которой он был создан. Это может вызвать проблемы, если класс имеет указатель в самого себя, или если код отслеживает объекты по адресу.

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

В следующем образце показано, когда конструктор копии не создается.

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

##  <a name="BKMK_Destructors_and_finalizers"></a> Деструкторы и методы завершения

Деструкторы в ссылочный тип выполнения детерминированную очистку ресурсов. Методы завершения очистки неуправляемых ресурсов и могут вызываться детерминировано, деструктором или недетерминированным образом сборщиком мусора. Сведения о деструкторах в стандартном языке C++, см. в разделе [деструкторы](../cpp/destructors-cpp.md).

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Поведение деструкторов в управляемом классе Visual C++ отличается от управляемых расширений для C++. Дополнительные сведения об этом изменении см. в разделе [изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md).

Сборщик мусора CLR удаляет неиспользуемые управляемые объекты и освобождает память, когда они больше не требуются. Однако тип может использовать ресурсы, которые сборщик мусора не знает, как освободить. Эти ресурсы известны как неуправляемые ресурсы (собственные дескрипторы файлов, связанные, например). Мы рекомендуем выпускать все неуправляемые ресурсы, в методе завершения. Так как управляемые ресурсы освобождены недетерминированным образом сборщиком мусора, небезопасно для ссылки на управляемые ресурсы в методе завершения так, как это возможно, сборщик мусора уже удалила, управляемых ресурсов.

Метод завершения Visual C++ не является таким же, как <xref:System.Object.Finalize%2A> метод. (Документации по среде CLR используется метод завершения и <xref:System.Object.Finalize%2A> метод как синонимы). <xref:System.Object.Finalize%2A> Метод вызывается сборщиком мусора, который вызывает каждый метод завершения в цепочке наследования класса. В отличие от Visual C++ деструкторы вызов метода завершения производного класса не вызывает компилятору вызывать метод завершения подобным все базовые классы.

Так как компилятор Visual C++ поддерживает детерминированного освобождения ресурсов, не следует пытаться реализовать <xref:System.IDisposable.Dispose%2A> или <xref:System.Object.Finalize%2A> методы. Тем не менее, если вы знакомы с этими методами, вот как метода завершения Visual C++ и деструктор, который вызывает метод завершения сопоставляются <xref:System.IDisposable.Dispose%2A> шаблон:

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

Управляемый тип может также использовать управляемые ресурсы, которые вы хотите использовать для детерминированного освобождения и не оставляют сборщику мусора освободить недетерминированным образом в некоторый момент после объект больше не требуется. Детерминированного освобождения ресурсов может значительно повысить производительность.

Компилятор Visual C++ позволяет определять деструктор для детерминированной очистки объектов. Используйте деструктор для освобождения всех ресурсов, которые для детерминированного освобождения.  Если присутствует метод завершения, вызовите его из деструктора, чтобы избежать дублирования кода.

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

Если код, который использует ваш тип не вызывает деструктор, сборщик мусора в конечном счете освобождает все управляемые ресурсы.

Наличие деструктор не подразумевает наличие метода завершения. Тем не менее метода завершения предполагает, что необходимо определить деструктор и вызывать метод завершения из деструктора. Это обеспечивает для детерминированного освобождения неуправляемых ресурсов.

Подавляет вызова деструктора — с помощью <xref:System.GC.SuppressFinalize%2A>— финализации объекта. Если деструктор не вызван, метод завершения для данного типа в конечном итоге будет вызываться сборщиком мусора.

Детерминированной очистки ресурсов объекта путем вызова деструктора может повысить производительность по сравнению с позволяя недетерминированным образом финализации объекта среды CLR.

Код, который написан на Visual C++ и скомпилированные с помощью **/CLR** выполняется деструктор типа, если:

- Объект, который создается с помощью семантики стека выходит за пределы области. Дополнительные сведения см. в разделе [семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md).

- Во время конструирования объекта создается исключение.

- Объект входит в объект, деструктор которого выполняется.

- Вы вызываете [удалить](../cpp/delete-operator-cpp.md) оператор маркер ([оператор дескриптора объекта (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)).

- Вы явным образом вызовите деструктор.

Если ваш тип используется клиентом, который написан на другом языке, деструктор вызывается следующим образом:

- Во время вызова <xref:System.IDisposable.Dispose%2A>.

- Во время вызова `Dispose(void)` на тип.

- Если тип выходит за пределы области в C# `using` инструкции.

При создании объекта ссылочного типа в управляемой куче (не с помощью семантики стека для ссылочных типов), используйте [try-finally](../cpp/try-finally-statement.md) синтаксис, чтобы убедиться, что исключение не не деструктор применялось.

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

Если ваш тип содержит деструктор, компилятор создает `Dispose` метод, который реализует <xref:System.IDisposable>. Если тип, который создается на языке Visual C++ и содержит деструктор, использования из другого языка, вызов метода `IDisposable::Dispose` от конкретного типа вызывает деструктор типа для вызова. При использовании типа из клиента Visual C++, нельзя вызывать непосредственно `Dispose`; вместо этого вызова деструктора, используя `delete` оператор.

Если ваш тип имеет метод завершения, компилятор создает `Finalize(void)` метод, который переопределяет <xref:System.Object.Finalize%2A>.

Если тип имеет метод завершения или деструктор, компилятор создает `Dispose(bool)` метод, согласно шаблону проектирования. (Сведения см. в разделе [шаблон Dispose](/dotnet/standard/design-guidelines/dispose-pattern)). Нельзя явно создавать или вызвать `Dispose(bool)` в Visual C++.

Если тип имеет базовый класс, который соответствует шаблону проектирования, деструкторы для всех базовых классов вызываются в том случае, когда вызывается деструктор для производного класса. (Если ваш тип создается на языке Visual C++, компилятор гарантирует, что типы реализации этого шаблона.) Другими словами, деструктор ссылочного класса связан его базовых классов и членов, как указано в стандарте C++ — первый, деструктор класса является выполнение, то деструкторы для членов, в обратном порядке, в котором они были созданы, и, наконец деструкторы для его базовых классов, в обратном порядке, в котором они были созданы.

Деструкторы и методы завершения не разрешены в значения типов или интерфейсов.

Метод завершения может быть только определен или объявлен в ссылочный тип. Как конструктор и деструктор метод завершения не имеет возвращаемого типа.

После выполнения метода завершения объекта, методы завершения в базовых классах, также называются, начиная с наименьшим производным типом. Методы завершения для элементов данных не соединяются автоматически, метод завершения класса.

Если метод завершения удаляет собственный указатель в управляемом типе, необходимо убедиться, что ссылки, или через собственный указатель не собираются преждевременно; вызова деструктора в управляемый тип, вместо использования <xref:System.GC.KeepAlive%2A>.

Во время компиляции вы можете обнаружить, является ли тип имеет метод завершения или деструктор. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

В приведенном ниже примере показано два типа, имеющую неуправляемые ресурсы, а другой управляемые ресурсы, которые выпускаются детерминировано.

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

## <a name="see-also"></a>См. также

[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)<br/>
[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)
