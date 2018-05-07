---
title: 'Как: определение и использование классов и структур (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d8356d96b0193566814c0d52173a03a3a79d08d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Практическое руководство. Определение и использование классов и структур (C++/CLI)
В этой статье показано, как определение и использование определяемых пользователем ссылочных типов и типов значений в C + +/ CLI.  
  
##  <a name="BKMK_Contents"></a> Описание  
 [При создании объектов](#BKMK_Object_instantiation)  
  
 [Неявно абстрактные классы](#BKMK_Implicitly_abstract_classes)  
  
 [Видимость типов](#BKMK_Type_visibility)  
  
 [Видимость членов](#BKMK_Member_visibility)  
  
 [Открытые и закрытые собственных классов](#BKMK_Public_and_private_native_classes)  
  
 [Статические конструкторы](#BKMK_Static_constructors)  
  
 [Семантика этого указателя](#BKMK_Semantics_of_the_this_pointer)  
  
 [Скрыть сигнатурой функции](#BKMK_Hide_by_signature_functions)  
  
 [Конструкторы копии](#BKMK_Copy_constructors)  
  
 [Деструкторы и методы завершения](#BKMK_Destructors_and_finalizers)  
  
##  <a name="BKMK_Object_instantiation"></a> При создании объектов  
 Типы ссылку (ref) и типы значений могут быть созданы только в управляемой куче, не помещается в стек или в собственной куче.  
  
```  
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
 *Неявно абстрактного класса* не может быть создан. Класс является абстрактным неявно, если базовый тип класса является интерфейсом, а класс не реализует все функции-члены интерфейса.  
  
 Если не удается создать объекты из класса, который является производным от интерфейса, причина может оказаться, что класс является абстрактным неявно. Дополнительные сведения об абстрактных классах см. в разделе [абстрактный](../windows/abstract-cpp-component-extensions.md).  
  
 В следующем примере кода показано, что `MyClass` класса не может быть создан, поскольку функция `MyClass::func2` не реализована. Чтобы включить для компиляции примера, раскомментируйте `MyClass::func2`.  
  
```  
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
 Можно управлять видимостью типов среды выполнения (CLR), поэтому, при ссылке на сборку типы в сборке может быть видимым или невидимым за пределами сборки.  
  
 `public` Указывает, что тип является видимым для любого исходного файла, содержащего `#using` директив для сборки, содержащей тип.  `private` Указывает, что тип не является видимым для исходных файлов, содержащих `#using` директив для сборки, содержащей тип. Тем не менее закрытые типы, видимые в пределах той же сборки. По умолчанию — видимость для класса `private`.  
  
 По умолчанию до Visual C++ 2005 собственные типы были открытым за пределами сборки. Включить [Предупреждение компилятора (уровень 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) помогают определить, где закрытый собственных типов используются неправильно. Используйте [make_public](../preprocessor/make-public.md) pragma, чтобы предоставить открытый доступ собственный тип в файле исходного кода, которые нельзя изменить.  
  
 Дополнительные сведения см. в разделе [# директива using](../preprocessor/hash-using-directive-cpp.md).  
  
 Следующий пример показано, как объявлять типы и укажите их доступности, а затем получить доступ к эти типы в сборке. Конечно, если ссылки на сборку, которая имеет закрытые типы используется `#using`, видны только открытые типы в сборке.  
  
```  
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
  
 Теперь давайте перепишите предыдущего примера таким образом, чтобы он построен как DLL.  
  
```  
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
  
 Следующий образец кода демонстрируется доступ к типы за пределами сборки. В этом образце клиент использует компонент, который встроен в предыдущем примере.  
  
```  
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
 Можно внести доступа члена открытого класса из той же сборки отличается от доступа к нему из за пределы данной сборки с помощью пары описатели доступа `public`, `protected`, и `private`  
  
 В следующей таблице перечислены действия различные описатели доступа:  
  
|Описатель|Действие|  
|---------------|------------|  
|public|Член доступен внутри и вне сборки.  В разделе [открытый](../cpp/public-cpp.md) для получения дополнительной информации.|  
|private|Член недоступен, ни внутри, ни вне сборки.  В разделе [закрытый](../cpp/private-cpp.md) для получения дополнительной информации.|  
|protected|Член доступен внутри и вне сборки, но только для производных типов.  В разделе [защищенных](../cpp/protected-cpp.md) для получения дополнительной информации.|  
|internal|Член является открытые внутри сборки, но закрытый за пределами сборки.  `internal` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).|  
|открытые защищенных - или - защищенных public|Член является открытые внутри сборки, однако защищены за пределами сборки.|  
|закрытый защищенных - или - защищенный закрытый|Член является защищенным внутри сборки, но закрытый за пределами сборки.|  
  
 В следующем примере показан открытый тип, который содержит члены, которые должны быть объявлены с разные уровни доступности и затем показывает доступ к участникам внутри сборки.  
  
```  
  
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
  
 Теперь создадим предыдущего образца как библиотеку DLL.  
  
```  
  
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
  
 Следующий пример использует компонент, который создан в предыдущем примере и тем самым показано, как получить доступ к членам за пределами сборки.  
  
```  
  
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
  
##  <a name="BKMK_Public_and_private_native_classes"></a> Открытые и закрытые собственных классов  
 Собственный тип можно ссылаться из управляемого типа.  Например функции в управляемом типе может занять параметр с типом собственном структуры.  Если управляемый тип и функцию, открытый в сборке, затем собственный тип должен также быть открытыми.  
  
```  
  
// native type  
public struct N {  
   N(){}  
   int i;  
};  
```  
  
 Создайте файл исходного кода, который использует собственный тип:  
  
```  
  
// compile with: /clr /LD  
#include "mcppv2_ref_class3.h"  
// public managed type  
public ref struct R {  
   // public function that takes a native type  
   void f(N nn) {}  
};  
```  
  
 Теперь скомпилируйте клиента:  
  
```  
  
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
 Тип CLR — например, класса или структуры, могут иметь статический конструктор, который можно использовать для инициализации статических элементов данных.  Статический конструктор вызывается только один раз и вызывается перед любой статический член типа осуществляется в первый раз.  
  
 Конструктор экземпляра всегда выполняется после завершения статический конструктор.  
  
 Компилятор не может выполнить подстановку вызов конструктора, если класс имеет статический конструктор.  Компилятор не может выполнить подстановку вызов функции-члена, если данный класс является типом значения, имеет статический конструктор и не имеет конструктора экземпляра.  Среда CLR может вводить вызов, но компилятор не может.  
  
 Определите статический конструктор как закрытая функция-член, поскольку он должен вызываться только средой CLR.  
  
 Дополнительные сведения о статических конструкторов см. в разделе [как: определение статического конструктора интерфейса (C + +/ CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .  
  
```  
  
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
 При использовании Visual C++ для определения типов, `this` указатель в ссылочный тип имеет тип «маркер». `this` Указатель типа значения имеет тип «внутренний указатель».  
  
 Эти разные семантики `this` указатель может привести к непредвиденному поведению при вызове индексатора по умолчанию. В следующем примере показано правильный способ доступа к индексатору по умолчанию ссылочного типа и типа значения.  
  
 Дополнительные сведения см. в разделе .  
  
-   [Оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
```  
  
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
  
##  <a name="BKMK_Hide_by_signature_functions"></a> Скрыть сигнатурой функции  
 В стандартном языке C++ функция в базовом классе скрыто функцией, которая имеет то же имя в производном классе, даже если функция производного класса не имеют одинаковый номер или тип параметров. Это называется *скрыть по имени* семантику. В ссылочный тип функция в базовом классе можно только скрываться функция в производном классе, если имя и список параметров совпадают. Это называется *скрываются по подписи* семантику.  
  
 Класс считается класса скрываются по подписи, если все его функции помечены в метаданных как `hidebysig`. По умолчанию все классы, созданные в **/CLR** имеют `hidebysig` функции. Если класс имеет `hidebysig` функции, компилятор не скрывает функции по имени в прямых базовых классов, но если компилятор обнаруживает скрыть по имени класса в цепочке наследования, он по-прежнему этого поведения скрыть по имени.  
  
 В семантике скрыть сигнатурой Если функция вызывается для объекта, компилятор определяет наиболее производного класса, содержащего функцию, которая может удовлетворить вызов функции. Если имеется только одна функция в классе, который могут удовлетворять вызова метода, компилятор вызывает данную функцию. Если имеется более одной функции в классе, который могут удовлетворять вызов, компилятор использует перегрузку правила разрешения, чтобы определить, какие функции для вызова. Дополнительные сведения о правилах перегрузка см. в разделе [перегрузка функций](../cpp/function-overloading.md).  
  
 Для вызова данной функции функции в базовом классе могут иметь сигнатуру, которая становится немного лучшее соответствие, чем функция в производном классе. Тем не менее если на объект производного класса явного вызова функции, вызывается функция в производном классе.  
  
 Поскольку возвращаемое значение не считается частью сигнатуры функции, функции базового класса является скрытым, если он имеет то же имя и принимает одно и то же количество и тип аргументов, как функция производного класса, даже если он отличается тем, тип возвращаемого значения.  
  
 В следующем примере показано, что функция в базовом классе не скрыт функция в производном классе.  
  
```  
  
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
  
 Следующий пример показывает, что компилятор Visual C++ вызывает функцию в наиболее производного класса, даже если преобразование требуется сопоставить один или несколько параметров и не вызвать функцию в базовом классе, который лучше подходит для вызова функции.  
  
```  
  
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
  
 Ниже приведен пример, можно скрыть функции, даже если базовый класс имеет ту же сигнатуру, как и производный класс.  
  
```  
  
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
 Стандарт C++ указывает, что конструктор копии, который вызывается при перемещении объекта, таким образом, что объект создается и уничтожается по одному адресу.  
  
 Тем не менее, когда **/CLR** используется для компиляции и функции, скомпилированные в MSIL вызывает собственный работать там, где экземпляр собственного класса, или более одного — передается по значению, а также где собственный класс имеет конструктор копии или деструктор, нет копии вызов конструктора и уничтожении объекта, на котором он был создан отличный от адреса. Это может вызвать проблемы, если класс имеет указатель в самого себя или если код отслеживает объекты по адресу.  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 В следующем образце показано, когда конструктор копии не создается.  
  
```  
  
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
 Деструкторы в ссылочный тип выполнения детерминированным очистку ресурсов. Методы завершения очистки неуправляемых ресурсов и может быть вызван детерминированного деструктором или случайным образом при сборке мусора. Сведения о деструкторах в стандартном языке C++ см. в разделе [деструкторы](../cpp/destructors-cpp.md).  
  
```  
class classname {  
   ~classname() {}   // destructor  
   ! classname() {}   // finalizer  
};  
```  
  
 Поведение деструкторов в управляемом классе Visual C++ отличается от управляемых расширений для C++. Дополнительные сведения об этом изменении см. в разделе [изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md).  
  
 Сборщик мусора CLR удаляет неиспользуемые управляемые объекты и освобождает память, когда они больше не требуются. Однако тип может использовать ресурсы, которые сборщик мусора не знает, как освободить. Эти ресурсы называются неуправляемые ресурсы (дескрипторы файлов, например). Мы рекомендуем, что вы освобождает все неуправляемые ресурсы, в методе завершения. Поскольку случайным образом освободить управляемые ресурсы сборщиком мусора, небезопасно для ссылки на управляемые ресурсы в методе завершения так, как это возможно, сборщик мусора уже очищены, управляемый ресурс.  
  
 Метод завершения Visual C++ не является таким же, как <xref:System.Object.Finalize%2A> метод. (Документации CLR используется метод завершения и <xref:System.Object.Finalize%2A> метод как синоним). <xref:System.Object.Finalize%2A> Метод вызывается сборщиком мусора, который вызывает каждый метод завершения в цепочке наследования класса. В отличие от Visual C++ деструкторы вызов метода завершения производного класса не вызывает компилятор для вызова метода завершения всех базовых классов.  
  
 Так как компилятор Visual C++ поддерживает детерминированного освобождения ресурсов, не пытается реализовать <xref:System.IDisposable.Dispose%2A> или <xref:System.Object.Finalize%2A> методы. Тем не менее, если вы знакомы с этими методами, вот способ сопоставления метода завершения Visual C++ и деструктор, который вызывает метод завершения для <xref:System.IDisposable.Dispose%2A> шаблон:  
  
```  
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
  
 Управляемый тип может также использовать управляемые ресурсы, которые вы хотите использовать для детерминированного освобождения и не оставляйте сборщику мусора освободить случайным образом в некоторой точке после объект больше не требуется. Детерминированного освобождения ресурсов может значительно повысить производительность.  
  
 Компилятор Visual C++ позволяет определять деструктор для детерминированного освобождения объектов. Позволяет освободить все ресурсы, которые для детерминированного освобождения деструктор.  При наличии в методе завершения следует вызовите из деструктора, чтобы избежать дублирования кода.  
  
```  
  
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
  
 Если код, который использует тип не вызывает деструктор, сборщик мусора в конечном итоге освобождает все ресурсы, управляемые.  
  
 Наличие деструктор не подразумевает наличие метода завершения. Тем не менее метода завершения предполагает, что необходимо определить деструктор и вызвать метод завершения из деструктора. Это обеспечивает для детерминированного освобождения неуправляемых ресурсов.  
  
 Подавляет вызов деструктора, с помощью <xref:System.GC.SuppressFinalize%2A>— финализацию объекта. Если деструктор не вызван, метод завершения для этого типа в конечном итоге будет вызываться сборщиком мусора.  
  
 Детерминированного освобождение ресурсов, объекта путем вызова деструктора может повысить производительность по сравнению с позволяя случайным образом финализации объекта CLR.  
  
 Код, который на языке Visual C++ и скомпилированных с помощью **/CLR** выполняется тип деструктор, если:  
  
-   Объект, который создается с использованием семантики стека выходит за пределы области. Дополнительные сведения см. в разделе [семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
-   Исключение во время создания объекта.  
  
-   Объект входит в объекте, деструктор которого выполняется.  
  
-   Можно вызвать [удаление](../cpp/delete-operator-cpp.md) оператор маркер ([оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).  
  
-   Вы явным образом вызовите деструктор.  
  
 Если ваш тип обрабатывается клиентом, который написан на другом языке, деструктор вызывается следующим образом:  
  
-   Во время вызова <xref:System.IDisposable.Dispose%2A>.  
  
-   Во время вызова `Dispose(void)` на тип.  
  
-   Если тип выходит за пределы области в C# `using` инструкции.  
  
 При создании объекта ссылочного типа в управляемой куче (не с помощью семантики стека для ссылочных типов), используйте [try-finally](../cpp/try-finally-statement.md) синтаксис, чтобы убедиться, что исключение не запрещает деструктор выполняется.  
  
```  
  
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
  
 Если тип имеет деструктор, компилятор создает `Dispose` метод, который реализует <xref:System.IDisposable>. Если тип, который написан на Visual C++ и нет деструктора, взятые из другого языка, вызов метода `IDisposable::Dispose` вызывает деструктора типа для вызова этого типа. Если тип потребляется из клиента Visual C++, нельзя вызывать непосредственно `Dispose`; вместо этого вызовите деструктор с помощью `delete` оператор.  
  
 Если тип имеет метод завершения, компилятор создает `Finalize(void)` , переопределяющий метод <xref:System.Object.Finalize%2A>.  
  
 Если тип имеет метод завершения или деструктор, компилятор создает `Dispose(bool)` метод согласно шаблону проектирования. (Сведения см. в разделе [шаблон Dispose](/dotnet/standard/design-guidelines/dispose-pattern)). Нельзя явно создавать или вызвать `Dispose(bool)` в Visual C++.  
  
 Если тип имеет базовый класс, соответствующий шаблону проектирования, деструкторы для всех базовых классов вызываются в том случае, когда вызывается деструктор для производного класса. (Тип написан на Visual C++, компилятор гарантирует, что к типам Реализуйте этот шаблон.) Другими словами, деструктор ссылочного класса связан его базовых классов и членов в соответствии со стандартом C++ — первый деструктор класса является выполнения, то деструкторы для ее членов в обратном направлении порядка, в котором они были созданы, и, наконец, деструкторы для его базовых классов, в порядке, в котором они были созданы в обратном направлении.  
  
 Деструкторы и методы завершения не разрешены в тип значения или интерфейсы.  
  
 Метод завершения можно только определен или объявлен в ссылочный тип. Как конструктор и деструктор метод завершения не имеет возвращаемого типа.  
  
 После запуска метода завершения объекта методы завершения во всех базовых классах также называются, начиная с наименее производного типа. Методы завершения для членов данных не соединяются автоматически для, метод завершения класса.  
  
 Если метод завершения удаляет собственный указатель в управляемом типе, необходимо убедиться, что ссылки или через собственный указатель не собираются преждевременно; Вызовите деструктор вместо использования управляемого типа <xref:System.GC.KeepAlive%2A>.  
  
 Во время компиляции можно обнаружить, является ли тип имеет метод завершения или деструктор. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Следующий пример показывает два типа, имеющего неуправляемые ресурсы, а другой управляемые ресурсы, которые выпускаются детерминировано.  
  
```  
  
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
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)