---
title: Руководство. Определение и использование классов и структур (C++/CLI)
description: Создание и использование определяемых пользователем типов классов и структур в коде C++/CLI.
ms.date: 09/25/2020
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 17d0885d42febc1d2789c8711b54a76066ee8176
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414585"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Руководство. Определение и использование классов и структур (C++/CLI)

В этой статье показано, как определить и использовать определяемые пользователем ссылочные типы и типы значений в C++/CLI.

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a> Создание экземпляра объекта

Ссылочные типы (ref) можно создавать только в управляемой куче, а не в стеке или в собственной куче. Экземпляры типов значений можно создавать в стеке или в управляемой куче.

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

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> Неявно абстрактные классы

Невозможно создать экземпляр *неявно абстрактного класса* . Класс неявно является абстрактным, если:

- базовый тип класса является интерфейсом, и
- класс не реализует все функции члена интерфейса.

Возможно, не удастся создать объекты из класса, производного от интерфейса. Причиной может быть то, что класс неявно является абстрактным. Дополнительные сведения о абстрактных классах см. в разделе [abstract](../extensions/abstract-cpp-component-extensions.md).

В следующем примере кода показано, что `MyClass` класс не может быть создан, поскольку функция `MyClass::func2` не реализована. Чтобы включить для примера компиляцию, раскомментируйте `MyClass::func2` .

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

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a> Видимость типов

Можно управлять видимостью типов среды CLR. При указании ссылки на сборку вы управляете отображением типов в сборке или их невидимостью за пределами сборки.

`public` Указывает, что тип является видимым для любого исходного файла, содержащего `#using` директиву для сборки, содержащей тип.  `private` Указывает, что тип не виден для исходных файлов, содержащих `#using` директиву для сборки, содержащей тип. Однако закрытые типы видимы в одной сборке. По умолчанию видимость класса — `private` .

По умолчанию перед Visual Studio 2005 собственные типы имели открытый доступ за пределами сборки. Включите [Предупреждение компилятора (уровень 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) , чтобы увидеть, где неправильно используются частные машинные типы. Используйте директиву pragma [make_public](../preprocessor/make-public.md) , чтобы предоставить открытый доступ к собственному типу в файле исходного кода, который нельзя изменить.

Дополнительные сведения см. в разделе [Директива using](../preprocessor/hash-using-directive-cpp.md).

В следующем примере показано, как объявить типы и указать их доступность, а затем получить доступ к этим типам внутри сборки. Если на сборку, имеющую закрытые типы, ссылаются с помощью `#using` , видимы только открытые типы в сборке.

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

**Выходные данные**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

Теперь давайте Перепишем предыдущий пример, чтобы он был создан в виде библиотеки DLL.

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

В следующем примере показано, как получить доступ к типам за пределами сборки. В этом примере клиент использует компонент, созданный в предыдущем примере.

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

**Выходные данные**

```Output
in Public_Class
```

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a> Видимость элементов

Доступ к члену открытого класса можно сделать в той же сборке, которая отличается от доступа к ней извне сборки с помощью пар описателей доступа **`public`** , **`protected`** и **`private`**

В этой таблице перечислены результаты различных описателей доступа.

|Описатель|Действие|
|---------------|------------|
|`public`|Элемент доступен внутри сборки и за ее пределами. Дополнительные сведения см. в статье [`public`](../cpp/public-cpp.md).|
|`private`|Член недоступен как внутри, так и за пределами сборки.  Дополнительные сведения см. в статье [`private`](../cpp/private-cpp.md).|
|`protected`|Член доступен внутри и вне сборки, но только в производных типах. Дополнительные сведения см. в статье [`protected`](../cpp/protected-cpp.md).|
|`internal`|Член является общедоступным внутри сборки, но закрыт за пределами сборки. `internal` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](../extensions/context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)).|
|`public protected` -или- `protected public`|Член является общедоступным внутри сборки, но защищен за пределами сборки.|
|`private protected` -или- `protected private`|Элемент защищен внутри сборки, но закрыт за пределами сборки.|

В следующем примере показан открытый тип, который содержит члены, объявленные с помощью различных описателей доступа. Затем он показывает доступ к членам внутри сборки.

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

**Выходные данные**

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

Теперь давайте создадим предыдущий пример в виде библиотеки DLL.

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

В следующем примере используется компонент, созданный в предыдущем примере. В нем показано, как получить доступ к членам за пределами сборки.

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

**Выходные данные**

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

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> Открытые и закрытые машинные классы

На собственный тип можно ссылаться из управляемого типа.  Например, функция в управляемом типе может принимать параметр, тип которого является структурой машинного кода.  Если управляемый тип и функция открыты в сборке, то собственный тип также должен быть открытым.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Затем создайте файл исходного кода, который использует собственный тип:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Теперь скомпилируйте клиент:

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

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a> Статические конструкторы

Тип CLR (например, класс или структура) может иметь статический конструктор, который можно использовать для инициализации статических элементов данных.  Статический конструктор вызывается не чаще, и вызывается до первого доступа к статическому члену типа.

Конструктор экземпляра всегда запускается после статического конструктора.

Компилятор не может встроеет вызов конструктора, если класс имеет статический конструктор. Компилятор не может встроеет вызов любой функции-члена, если класс является типом значения, имеет статический конструктор и не имеет конструктора экземпляра. Среда CLR может подставляемь вызов, но компилятор не может.

Определите статический конструктор как закрытую функцию-член, так как она должна вызываться только средой CLR.

Дополнительные сведения о статических конструкторах см. [в разделе инструкции. Определение статического конструктора интерфейса (C++/CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .

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

**Выходные данные**

```Output
in static constructor
10
11
```

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a> Семантика `this` указателя

Если вы используете C++ \КЛИ для определения типов, **`this`** указатель в ссылочном типе имеет тип *Handle*. **`this`** Указатель в типе значения имеет тип " *внутренний указатель*".

Эти различные семантики **`this`** указателя могут вызвать непредвиденное поведение при вызове индексатора по умолчанию. В следующем примере показан правильный способ доступа к индексатору по умолчанию как для ссылочного типа, так и для типа значения.

Дополнительные сведения см. [в статье оператор Handle to Object (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) и [interior_ptr (C++/CLI)](../extensions/interior-ptr-cpp-cli.md) .

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

**Выходные данные**

```Output
10.89
10.89
```

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> Функции скрытия по подписи

В стандартном C++ функция в базовом классе скрывается функцией, имеющей то же имя в производном классе, даже если функция производного класса не имеет такого же вида или количества параметров. Она называется семантикой *скрытия по имени* . В ссылочном типе функция в базовом классе только скрывается функцией в производном классе, если оба имени и список параметров одинаковы. Она называется семантикой *скрытия по подписи* .

Класс считается классом скрытия подписи, если все его функции помечены в метаданных как `hidebysig` . По умолчанию все классы, создаваемые в, **`/clr`** имеют `hidebysig` функции. Если класс содержит `hidebysig` функции, компилятор не скрывает функции по имени в каких-либо прямых базовых классах, но если компилятор встречает класс скрытия по имени в цепочке наследования, он продолжит это поведение скрытия по имени.

При использовании семантики скрытия сигнатуры при вызове функции для объекта компилятор определяет самый производный класс, содержащий функцию, которая может удовлетворить вызов функции. Если в классе имеется только одна функция, которая удовлетворяет вызов, компилятор вызывает эту функцию. Если в классе имеется несколько функций, которые могут удовлетворить вызов, компилятор использует правила разрешения перегрузки для определения вызываемой функции. Дополнительные сведения о правилах перегрузки см. в разделе перегрузка [функций](../cpp/function-overloading.md).

Для вызова данной функции функция в базовом классе может иметь сигнатуру, которая делает его немного более подходящие, чем функция в производном классе. Однако если функция была явно вызвана для объекта производного класса, вызывается функция в производном классе.

Поскольку возвращаемое значение не считается частью сигнатуры функции, функция базового класса становится скрытой, если она имеет то же имя и принимает тот же вид и число аргументов, что и функция производного класса, даже если она отличается от типа возвращаемого значения.

В следующем примере показано, что функция в базовом классе не скрыта функцией в производном классе.

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

**Выходные данные**

```Output
Base::Test
```

В следующем примере показано, что компилятор Microsoft C++ вызывает функцию в наиболее производном классе, даже если преобразование требуется для сопоставления с одним или несколькими параметрами — и не вызывает функцию в базовом классе, которая лучше соответствует вызову функции.

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

**Выходные данные**

```Output
Derived::Test2
```

В следующем примере показано, как можно скрыть функцию, даже если базовый класс имеет ту же сигнатуру, что и производный класс.

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

**Выходные данные**

```Output
Derived::Test4
97
```

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a> Конструкторы копий

Стандарт C++ говорит о том, что конструктор копий вызывается при перемещении объекта, так что объект создается и уничтожается по тому же адресу.

Однако если функция, скомпилированная в MSIL, вызывает собственную функцию, где собственный класс (или несколько) передается по значению, а собственный класс имеет конструктор копии или деструктор, конструктор копии не вызывается и объект уничтожается по адресу, отличному от того, где он был создан. Такое поведение может вызвать проблемы, если класс имеет указатель на себя или если код отслеживает объекты по адресу.

Дополнительные сведения см. в разделе [/CLR (компиляция среды CLR)](../build/reference/clr-common-language-runtime-compilation.md).

В следующем примере показано, когда конструктор копии не создается.

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

**Выходные данные**

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

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> Деструкторы и методы завершения

Деструкторы в ссылочном типе выполняют детерминированную очистку ресурсов. Методы завершения удаляют неуправляемые ресурсы и могут вызываться либо детерминированно деструктором, либо недетерминированными сборщиком мусора. Дополнительные сведения о деструкторах в стандартном C++ см. в разделе [деструкторы](../cpp/destructors-cpp.md).

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Сборщик мусора среды CLR удаляет неиспользуемые управляемые объекты и освобождает их память, когда они больше не требуются. Однако тип может использовать ресурсы, которые сборщик мусора не знает, как выпустить. Эти ресурсы называются *неуправляемыми* ресурсами (например, собственными дескрипторами файлов). Рекомендуется освободить все неуправляемые ресурсы в методе завершения. Сборщик мусора освобождает управляемые ресурсы недетерминированным образом, поэтому в методе завершения нельзя ссылаться на управляемые ресурсы. Это связано с тем, что сборщик мусора уже удалил их.

Метод завершения Visual C++ не совпадает с <xref:System.Object.Finalize%2A> методом. (В документации среды CLR метод Finalize и используется как <xref:System.Object.Finalize%2A> синоним). <xref:System.Object.Finalize%2A>Метод вызывается сборщиком мусора, который вызывает каждый метод завершения в цепочке наследования класса. В отличие от деструкторов Visual C++, вызов метода завершения производного класса не приводит к тому, что компилятор вызывает метод завершения во всех базовых классах.

Поскольку компилятор Microsoft C++ поддерживает детерминированный выпуск ресурсов, не пытайтесь реализовать <xref:System.IDisposable.Dispose%2A> <xref:System.Object.Finalize%2A> методы или. Однако если вы знакомы с этими методами, вот как Visual C++ метод завершения и деструктор, вызывающий метод завершения, сопоставляется с <xref:System.IDisposable.Dispose%2A> шаблоном:

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

Управляемый тип может также использовать управляемые ресурсы, которые желательно выпустить в детерминированном виде. Сборщик мусора не должен освобождать объект недетерминированным образом в некоторый момент после того, как объект больше не требуется. Детерминированный выпуск ресурсов может значительно повысить производительность.

Компилятор Microsoft C++ позволяет определение деструктора для детерминированной очистки объектов. Используйте деструктор, чтобы освободить все ресурсы, которые нужно выпустить в детерминированном виде.  Если имеется метод завершения, вызовите его из деструктора, чтобы избежать дублирования кода.

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

Если код, использующий тип, не вызывает деструктор, сборщик мусора в конечном итоге освобождает все управляемые ресурсы.

Наличие деструктора не подразумевает наличия метода завершения. Однако присутствие метода завершения предполагает, что необходимо определить деструктор и вызвать метод завершения из этого деструктора. Этот вызов обеспечивает детерминированный выпуск неуправляемых ресурсов.

Вызов деструктора подавляет — с помощью <xref:System.GC.SuppressFinalize%2A> — финализации объекта. Если деструктор не вызывается, метод завершения типа в конечном итоге будет вызываться сборщиком мусора.

Можно повысить производительность, вызвав деструктор для детерминированной очистки ресурсов объекта, вместо того, чтобы позволить среде CLR недетерминированно завершать объект.

Код, написанный на Visual C++ и скомпилированный с помощью, **`/clr`** выполняет деструктор типа, если:

- Объект, созданный с помощью семантики стека, выходит за пределы области. Дополнительные сведения см. в разделе [Семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md).

- Во время создания объекта выдается исключение.

- Объект является членом объекта, деструктор которого выполняется.

- Оператор [Delete](../cpp/delete-operator-cpp.md) вызывается для маркера ([Handle to Object оператор (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)).

- Вы явно вызываете деструктор.

Если клиент, написанный на другом языке, использует ваш тип, деструктор вызывается следующим образом:

- При вызове <xref:System.IDisposable.Dispose%2A> .

- При вызове метода для `Dispose(void)` типа.

- Значение, если тип выходит за пределы области действия в **`using`** инструкции C#.

Если вы не используете семантику стека для ссылочных типов и создаете объект ссылочного типа в управляемой куче, используйте синтаксис [try-finally](../cpp/try-finally-statement.md) , чтобы убедиться, что исключение не мешает запуску деструктора.

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

Если у вашего типа есть деструктор, компилятор создает `Dispose` метод, реализующий <xref:System.IDisposable> . Если тип, который записывается в Visual C++ и имеет деструктор, который используется на другом языке, вызов `IDisposable::Dispose` для этого типа вызывает вызов деструктора типа. Если тип используется клиентом Visual C++, вызывать его напрямую нельзя `Dispose` , вместо этого вызывайте деструктор с помощью **`delete`** оператора.

Если у типа есть метод завершения, компилятор создает `Finalize(void)` метод, который переопределяет <xref:System.Object.Finalize%2A> .

Если тип содержит либо метод завершения, либо деструктор, компилятор создает `Dispose(bool)` метод в соответствии с шаблоном разработки. (Дополнительные сведения см. в разделе [шаблон удаления](/dotnet/standard/design-guidelines/dispose-pattern)). Вы не можете явно создавать или вызывать `Dispose(bool)` в Visual C++.

Если тип имеет базовый класс, который соответствует шаблону разработки, деструкторы для всех базовых классов вызываются при вызове деструктора для производного класса. (Если тип написан на Visual C++, компилятор гарантирует, что типы реализуют этот шаблон.) Иными словами, деструктор ссылочного класса привязывается к его основам и элементам, как указано в стандарте C++. Во-первых, выполняется деструктор класса. Затем деструкторы для своих членов запускаются в противоположном порядке, в котором они были созданы. Наконец, деструкторы для своих базовых классов запускаются в противоположном порядке, в котором они были созданы.

Деструкторы и методы завершения не допускаются внутри типов значений или интерфейсов.

Метод завершения может быть определен или объявлен только в ссылочном типе. Как и конструктор, и деструктор, метод завершения не имеет возвращаемого типа.

После запуска метода завершения объекта также вызываются методы завершения в любых базовых классах, начиная с наименее производного типа. Методы завершения для элементов данных не автоматически присоединяются к методу завершения класса.

Если метод завершения удаляет собственный указатель в управляемом типе, необходимо убедиться, что ссылки на или через собственный указатель не были преждевременно собраны. Вызовите деструктор для управляемого типа вместо использования <xref:System.GC.KeepAlive%2A> .

Во время компиляции можно определить, имеет ли тип метод завершения или деструктор. Дополнительные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

В следующем примере показаны два типа: один, содержащий неуправляемые ресурсы, а другой — управляемые ресурсы, которые освобождаются детерминированным образом.

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

[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)
