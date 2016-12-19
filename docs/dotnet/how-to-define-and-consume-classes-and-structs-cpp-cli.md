---
title: "Практическое руководство: определение и использование классов и структур (C++-CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "структуры [C++]"
  - "классы [C++], создание экземпляров"
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Определение и использование классов и структур (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье показано, как определять и использовать пользовательские ссылочные типы и типы значений в [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  
  
##  <a name="a-namebkmkcontentsa-contents"></a><a name="BKMK_Contents"></a> Содержание  
 [При создании объектов](#BKMK_Object_instantiation)  
  
 [Неявно абстрактные классы](#BKMK_Implicitly_abstract_classes)  
  
 [Видимость типов](#BKMK_Type_visibility)  
  
 [Видимость членов](#BKMK_Member_visibility)  
  
 [Открытые и закрытые собственных классов](#BKMK_Public_and_private_native_classes)  
  
 [Статические конструкторы](#BKMK_Static_constructors)  
  
 [Семантика этого указателя](#BKMK_Semantics_of_the_this_pointer)  
  
 [Функции скрываются по подписи](#BKMK_Hide_by_signature_functions)  
  
 [Конструктор копии.](#BKMK_Copy_constructors)  
  
 [Деструкторы и методы завершения](#BKMK_Destructors_and_finalizers)  
  
##  <a name="a-namebkmkobjectinstantiationa-object-instantiation"></a><a name="BKMK_Object_instantiation"></a> При создании объектов  
 Ссылку (ref) типы и типы значений могут быть созданы только в управляемой куче, не в стеке или в собственной куче.  
  
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
  
##  <a name="a-namebkmkimplicitlyabstractclassesa-implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> Неявно абстрактные классы  
  *Неявно абстрактного класса* не может быть создан. Класс является абстрактным неявно, если базовый тип класса является интерфейсом и не реализует все функции-члены этого интерфейса.  
  
 Если не удается создать объекты из класса, производного от интерфейса, причина может быть, что данный класс является абстрактным неявно. Дополнительные сведения об абстрактных классах см. в разделе [абстрактный](../windows/abstract-cpp-component-extensions.md).  
  
 В следующем примере кода показано, что `MyClass` класс нельзя создать, так как функция `MyClass::func2` не реализована. Чтобы включить в примере для компиляции, раскомментируйте `MyClass::func2`.  
  
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
  
##  <a name="a-namebkmktypevisibilitya-type-visibility"></a><a name="BKMK_Type_visibility"></a> Видимость типов  
 Можно задать видимость типов среды выполнения (CLR), чтобы при ссылке на сборку типы в сборке может быть видимым или невидимым за пределами сборки.  
  
 `public` Указывает, что тип является видимым в исходный файл, содержащий `#using` директив для сборки, содержащей тип.  `private` Указывает, что тип не является видимым для исходных файлов, содержащих `#using` директив для сборки, содержащей тип. Тем не менее закрытые типы видны в пределах той же сборки. По умолчанию — видимость для класса `private`.  
  
 По умолчанию до Visual C++ 2005 собственные типы были открытыми за пределами сборки. Включить [Предупреждение компилятора (уровень 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) помогают определить, где закрытый собственные типы используются неправильно. Используйте [make_public](../preprocessor/make-public.md) директиву pragma, чтобы предоставить открытый доступ к собственный тип в файле исходного кода, которые нельзя изменить.  
  
 Дополнительные сведения см. в разделе [# директива using](../preprocessor/hash-using-directive-cpp.md).  
  
 Следующий пример показано, как объявлять типы и указать их доступности, а затем доступ к этим типам в сборке. Конечно, если ссылки на сборку, которая имеет закрытые типы используется `#using`, только открытые типы в сборке являются видимыми.  
  
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
  
 **Выходные данные**  
  
```Output  
in Public_Class  
in Private_Class  
in Private_Class_2  
```  
  
 Теперь давайте перепишем предыдущий пример, чтобы он встроен в виде библиотеки DLL.  
  
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
  
 Следующий пример показано, как доступ к типам за пределами сборки. В этом примере клиент использует компонент, который встроен в предыдущем примере.  
  
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
  
 **Выходные данные**  
  
```Output  
in Public_Class  
```  
  
##  <a name="a-namebkmkmembervisibilitya-member-visibility"></a><a name="BKMK_Member_visibility"></a> Видимость членов  
 Выполненные доступа члена открытого класса из той же сборки отличается от доступа к нему из вне сборки с помощью пары описатели доступа `public`, `protected`, и `private`  
  
 В следующей таблице перечислены влияние различные описатели доступа:  
  
|класса хранения|Действие|  
|---------------|------------|  
|public|Член доступен внутри и за пределами сборки.  В разделе [открытый](../cpp/public-cpp.md) Подробнее.|  
|private|Член недоступен, внутри ни за пределами сборки.  В разделе [частного](../Topic/private%20\(C++\).md) Подробнее.|  
|protected|Член доступен внутри и вне сборки, но только для производных типов.  В разделе [защищенных](../Topic/protected%20\(C++\).md) Подробнее.|  
|internal|Член открытыми внутри сборки, но закрытый за пределами сборки.  `internal` — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).|  
|открытые защищенных - или - защищенный общий|Член открытыми внутри сборки, но защищенного за пределами сборки.|  
|закрытый защищенных - или - защищенный закрытый|Член является защищенным внутри сборки, но закрытый за пределами сборки.|  
  
 В следующем примере показан открытый тип, который содержит члены, объявленные с различные уровни доступности и затем показывает доступ к участникам внутри сборки.  
  
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
  
 Теперь создадим предыдущий пример как библиотеку DLL.  
  
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
  
##  <a name="a-namebkmkpublicandprivatenativeclassesa-public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> Открытые и закрытые собственных классов  
 Собственный тип можно ссылаться из управляемого типа.  Например параметр с типом собственного структура может принимать функция в управляемом типе.  Если управляемый тип и функции являются открытыми в сборке, затем собственный тип должны также быть открытыми.  
  
```  
  
// native type  
public struct N {  
   N(){}  
   int i;  
};  
```  
  
 Затем создайте файл исходного кода, который использует собственный тип:  
  
```  
  
// compile with: /clr /LD  
#include "mcppv2_ref_class3.h"  
// public managed type  
public ref struct R {  
   // public function that takes a native type  
   void f(N nn) {}  
};  
```  
  
 Теперь можно Скомпилируйте клиент:  
  
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
  
##  <a name="a-namebkmkstaticconstructorsa-static-constructors"></a><a name="BKMK_Static_constructors"></a> Статические конструкторы  
 Тип CLR — например, класса или структуры, может иметь статический конструктор, который можно использовать для инициализации элементов статических данных.  Статический конструктор вызывается только один раз и вызывается перед любой статический член типа осуществляется в первый раз.  
  
 Конструктор экземпляра всегда выполняется после статический конструктор.  
  
 Если класс имеет статический конструктор, компилятор не встроенный вызов конструктора.  Компилятор не встроенный вызов функции-члена, если класс является типом значения, имеет статический конструктор и не имеет конструктор экземпляра.  Среда CLR может вводить вызов, но компилятор не может.  
  
 Определение статического конструктора как закрытая функция-член, поскольку он должен вызываться только средой CLR.  
  
 Дополнительные сведения о статических конструкторах см. в разделе [Практическое руководство: определение статического конструктора интерфейса (C + +/ CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .  
  
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
  
 **Выходные данные**  
  
```Output  
in static constructor  
10  
11  
```  
  
##  <a name="a-namebkmksemanticsofthethispointera-semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a> Семантика этого указателя  
 При использовании Visual C++ для определения типов, `this` указатель в ссылочный тип имеет тип «маркер».  `this` Указатель на тип значения имеет тип «внутренний указатель».  
  
 Эти разные семантики `this` указатель может вызвать неожиданное поведение при вызове индексатора по умолчанию. В следующем примере показано правильное способ доступа к индексатору по умолчанию ссылочного типа и типа значения.  
  
 Дополнительные сведения см. в разделе .  
  
-   [Оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)  
  
-   [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [Практическое руководство: использование индексированных свойств](../misc/how-to-use-indexed-properties.md)  
  
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
  
 **Выходные данные**  
  
```Output  
10.89  
10.89  
```  
  
##  <a name="a-namebkmkhidebysignaturefunctionsa-hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> Функции скрываются по подписи  
 В стандартном языке C++ функция в базовом классе скрыт функцией, которая имеет то же имя в производном классе, даже если функция производного класса не имеют одинаковый номер или тип параметров. Это называется *Скрыть по имени* семантику. В ссылочный тип функция в базовом классе можно только скрыть, функция в производном классе, если имя и список параметров совпадают. Это называется *скрываются по подписи* семантику.  
  
 Класс считается класса скрываются по подписи, когда все его функции отмечены в метаданных как `hidebysig`. По умолчанию все классы, созданные в **/CLR** имеют `hidebysig` функции. Тем не менее класс, который компилируется с помощью **/CLR: oldSyntax** не имеет `hidebysig` функции; вместо этого они скрыты по имени функции. Если класс имеет `hidebysig` функций, компилятор не скрывает функции по имени в прямых базовых классов, но если компилятор обнаруживает скрыть по имени класса в цепочке наследования, он продолжает это поведение скрытия по имени.  
  
 При использовании семантики скрываются по подписи при вызове функции для объекта, компилятор определяет наиболее производный класс, который содержит функцию, которая может удовлетворить вызов функции. Если имеется только одна функция в классе, который может успешно выполнить вызов, компилятор вызывает эту функцию. Если имеется более одной функции в классе, который может успешно выполнить вызов, компилятор использует перегрузку правила разрешения, чтобы определить, какую функцию вызвать. Дополнительные сведения о правилах перегрузка см [перегрузки функции](../cpp/function-overloading.md).  
  
 Для вызова данной функции функции в базовом классе могут иметь сигнатуру, которая упрощает соответствие немного лучше, чем функция в производном классе. Тем не менее если функция явно вызван на объект производного класса, вызывается функция в производном классе.  
  
 Поскольку возвращаемое значение не считается частью сигнатуры функции, функции базового класса является скрытым, если он имеет то же имя и принимает то же количество и тип аргументов как функция производного класса, даже если оно отличается в тип возвращаемого значения.  
  
 В следующем примере показано, что функция в базовом классе не скрыто функция в производном классе.  
  
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
  
 **Выходные данные**  
  
```Output  
Base::Test  
```  
  
 В следующем примере показано, что компилятор Visual C++ вызывает функцию в наиболее производного класса, даже если преобразование требуется сопоставить один или несколько параметров и не вызвать функцию в базовом классе, который лучше подходит для вызова функции.  
  
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
  
 **Выходные данные**  
  
```Output  
Derived::Test2  
```  
  
 Ниже приведен пример, можно скрыть функцию, даже если базовый класс имеет ту же сигнатуру, как и производный класс.  
  
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
  
 **Выходные данные**  
  
```Output  
Derived::Test4  
97  
```  
  
 В следующем примере определяется компонент, который компилируется с помощью **/CLR: oldSyntax**. Классы, определенные с помощью управляемых расширений для C++ имеют функции-члены скрыть по имени.  
  
```  
  
// compile with: /clr:oldSyntax /LD  
using namespace System;  
public __gc struct Base0 {  
   void Test() {   
      Console::WriteLine("in Base0::Test");  
   }  
};  
  
public __gc struct Base1 : public Base0 {  
   void Test(int i) {   
      Console::WriteLine("in Base1::Test");  
   }  
};  
```  
  
 Следующий пример использует компонент, который встроен в предыдущем примере. Обратите внимание как скрываются по подписи функции не применяется к базовые классы для типов, которые скомпилированы с помощью **/CLR: oldSyntax**.  
  
```  
  
// compile with: /clr:oldSyntax /LD  
// compile with: /clr  
using namespace System;  
#using "hide_by_signature_4.dll"  
  
ref struct Derived : public Base1 {  
   void Test(int i, int j) {   
      Console::WriteLine("Derived::Test");  
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   t->Test(8, 8);   // OK  
   t->Test(8);   // OK  
   t->Test();   // C2661  
}  
```  
  
##  <a name="a-namebkmkcopyconstructorsa-copy-constructors"></a><a name="BKMK_Copy_constructors"></a> Конструктор копии.  
 Стандарт C++ указывает, что конструктор копии, который вызывается при перемещении объекта таким образом, что объект создается и уничтожается в тот же адрес.  
  
 Однако, если **/CLR** используется для компиляции и функцию, которая компилируется в машинный код функции, где собственный класс вызовы MSIL — или более одного — передается по значению и где собственный класс имеет конструктор копии или деструктор, конструктора копии не вызывается и объект уничтожается в разные адреса которой он был создан. Это может вызвать проблемы, если класс имеет указатель в самого себя, или если код отслеживает объекты по адресу.  
  
 Для получения дополнительной информации см. [/clr (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 В следующем примере показано, когда конструктор копии не создается.  
  
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
  
##  <a name="a-namebkmkdestructorsandfinalizersa-destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> Деструкторы и методы завершения  
 Деструктор ссылочного типа выполняют детерминированная Очистка ресурсов. Методы завершения очистки неуправляемых ресурсов и может вызываться детерминированного, деструктор или случайным образом сборщиком мусора. Сведения о деструкторах в стандартном языке C++ см. в разделе [деструкторы](../cpp/destructors-cpp.md).  
  
```  
class classname {  
   ~classname() {}   // destructor  
   ! classname() {}   // finalizer  
};  
```  
  
 Поведение деструкторов в управляемый класс Visual C++ отличается от управляемых расширений для C++. Дополнительные сведения об этом изменении см. в разделе [изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md).  
  
 Сборщик мусора CLR удаляет неиспользуемые управляемые объекты и освобождает память, когда они больше не требуются. Однако тип может использовать ресурсы, которые сборщик мусора не знает, как освободить. Эти ресурсы известны как неуправляемые ресурсы (обрабатывает собственный файл, например). Мы рекомендуем, что вы освобождает все неуправляемые ресурсы в методе завершения. Так как управляемые ресурсы освобождены случайным образом сборщиком мусора, небезопасно для ссылки на управляемые ресурсы в методе завершения поскольку возможно, что сборщик мусора уже удалила, управляемых ресурсов.  
  
 Метод завершения Visual C++ не является таким же, как <xref:System.Object.Finalize%2A> метод. (Документация CLR использует метод завершения и <xref:System.Object.Finalize%2A> метод как синонимы).  <xref:System.Object.Finalize%2A> метод вызывается сборщиком мусора, который вызывает каждый метод завершения в цепочке наследования класса. В отличие от Visual C++ деструкторы вызов метода завершения производного класса не вызывает компилятор должен вызывать метод завершения в все базовые классы.  
  
 Так как компилятор Visual C++ поддерживает детерминированного освобождения ресурсов, не пытается реализовать <xref:System.IDisposable.Dispose%2A> или <xref:System.Object.Finalize%2A> методы. Тем не менее, если вы знакомы с этими методами, вот финализатор Visual C++ и деструктор, который вызывает метод завершения сопоставление <xref:System.IDisposable.Dispose%2A> шаблон:  
  
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
  
 Управляемый тип может также использовать управляемые ресурсы, которые вы хотите детерминированного выпуска, а не оставить сборщику мусора освобождать случайным образом в некоторый момент после объект больше не требуется. Детерминированного освобождения ресурсов может значительно повысить производительность.  
  
 Компилятор Visual C++ позволяет определять деструктор детерминированного очистки объектов. Чтобы освободить все ресурсы, которые нужно освободить детерминированного используйте деструктор.  Если метод завершения, вызовите его из деструктора, чтобы избежать дублирования кода.  
  
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
  
 Если код, который использует тип не вызывает деструктор, сборщик мусора в конечном счете освобождает все ресурсы, управляемые.  
  
 Наличие деструктор не подразумевает наличие метода завершения. Тем не менее метода завершения предполагает, что необходимо определить деструктор и вызывает метод завершения из деструктора. Это обеспечивает для детерминированного освобождения неуправляемых ресурсов.  
  
 Подавляет вызов деструктора — с помощью <xref:System.GC.SuppressFinalize%2A>— финализации объекта. Если деструктор не вызван, метод завершения для этого типа в конечном итоге вызываться сборщиком мусора.  
  
 Детерминированного освобождение ресурсов вашего объекта путем вызова деструктора может повысить производительность по сравнению с предоставлением CLR случайным образом финализации объекта.  
  
 Код, который на языке Visual C++ и скомпилированных с помощью **/CLR** выполняется деструктор типа, если:  
  
-   Объект, который создается с помощью семантики стека выходит за пределы области. Дополнительные сведения см. в разделе [семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
-   Исключение во время создания объекта.  
  
-   Объект входит в объекте, деструктор которого выполняется.  
  
-   Можно вызвать [Удаление](../cpp/delete-operator-cpp.md) оператор маркер ([оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).  
  
-   Деструктор вызывается явно.  
  
 Если клиент, написанный на другом языке, потребляется типа, деструктор вызывается следующим образом:  
  
-   При вызове <xref:System.IDisposable.Dispose%2A>.  
  
-   При вызове `Dispose(void)` типа.  
  
-   Если тип выходит за пределы области в C# `using` инструкции.  
  
 При создании объекта ссылочного типа в управляемой куче (не с помощью семантики стека для ссылочных типов), используйте [try-finally](../cpp/try-finally-statement.md) синтаксис, чтобы убедиться, что исключение не запрещает деструктор работает.  
  
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
  
 Если тип содержит деструктор, компилятор создает `Dispose` метод, который реализует <xref:System.IDisposable>. Если тип, который создается на языке Visual C++ и деструктор, взятые из другого языка, вызов метода `IDisposable::Dispose` этого типа вызывается деструктор этого типа для вызова. Если тип потребляется из клиента Visual C++, нельзя вызывать непосредственно `Dispose`; вместо этого вызова деструктора с помощью `delete` оператор.  
  
 Если тип имеет метод завершения, компилятор создает `Finalize(void)` метода, который переопределяет <xref:System.Object.Finalize%2A>.  
  
 Если тип имеет метод завершения или деструктор, компилятор создает `Dispose(bool)` метод в соответствии с шаблоном проектирования. (Подробнее см. в разделе [Шаблон удаления](../Topic/Dispose%20Pattern.md)). Нельзя явно создавать или вызвать `Dispose(bool)` в Visual C++.  
  
 Если тип имеет базовый класс, соответствующий шаблону проектирования, деструкторы для всех базовых классов вызываются в том случае, когда вызывается деструктор для производного класса. (Если тип создается на языке Visual C++, компилятор гарантирует, что ваши типы реализации этого шаблона.) Другими словами, деструктор ссылочного класса связан его базовых классов и членов в соответствии со стандартом C++ — первый деструктор класса является выполнения, то деструкторы для членов, в обратном порядке, в котором они были созданы и, наконец, деструкторы для его базовых классов в обратном порядке, в котором они были созданы.  
  
 Деструкторы и методы завершения не допускается внутри типы значений и интерфейсы.  
  
 Только финализатор может быть определен или объявлен в ссылочный тип. Как конструктор и деструктор метод завершения не имеет возвращаемого типа.  
  
 После выполнения метода завершения объекта финализаторы в базовых классах, также называются, начиная с наименее производного типа. Методы завершения для элементов данных не передается контроллеру автоматически, метод завершения класса.  
  
 Если финализатор удаляет собственный указатель в управляемом типе, необходимо убедиться, что ссылки или через собственный указатель не собираются по преждевременно; вызова деструктора для управляемого типа вместо <xref:System.GC.KeepAlive%2A>.  
  
 Во время компиляции можно обнаружить, является ли тип имеет метод завершения или деструктор. Дополнительные сведения см. в разделе [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 В следующем примере показано два типа, имеющего неуправляемые ресурсы, а другой управляемые ресурсы, которые выпускаются детерминированного.  
  
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