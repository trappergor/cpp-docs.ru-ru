---
title: "interface class (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "interface_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "класс интерфейса - ключевое слово"
  - "interface struct - ключевое слово"
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: 30
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interface class (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявляет интерфейс  Дополнительные сведения об собственных интерфейсах см. в разделе [\_\_interface](../Topic/__interface.md).  
  
## Все среды выполнения  
 **Синтаксис**  
  
```  
  
        interface_access interface class  name :  inherit_access base_interface {};  
interface_access interface struct name :  inherit_access base_interface {};  
```  
  
 **Параметры**  
  
 *interface\_access*  
 Доступность интерфейса за пределами сборки.  Возможные значения **public** и `private`. `private` по умолчанию.  Вложенные интерфейсы не могут иметь описатель *interface\_access*.  
  
 *name*  
 Имя интерфейса.  
  
 *inherit\_access*  
 Доступность *base\_interface*.  Единственной разрешенной доступностью базового интерфейса является `public` \(по умолчанию\).  
  
 *base\_interface* \(необязательно\)  
 Базовый интерфейс для интерфейса *name*.  
  
 **Примечания**  
  
 **interface struct** эквивалентна **interface class**.  
  
 Интерфейс может содержать объявления для функций, событий и свойств.  Все члены интерфейса имеют общую доступность.  Интерфейс может также содержать статические данные\-члены, функции, события и свойства, и эти статические члены должны определяться в интерфейсе.  
  
 Интерфейс определяет как класс может быть реализован.  Интерфейс не является классом, а классы могут только реализовывать интерфейсы.  Когда класс определяет функцию, объявленную в интерфейсе, функция реализуется, а не переопределяется.  Поэтому поиск имени не включает члены интерфейса.  
  
 Класс или структура, которая является производной от интерфейса, должна реализовывать все члены интерфейса.  При реализации *name* интерфейса необходимо также реализовать интерфейсы в списке `base_interface`.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Статический конструктор интерфейса](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Универсальные интерфейсы \(Visual C\+\+\)](../Topic/Generic%20Interfaces%20\(Visual%20C++\).md)  
  
 Сведения о других типах CLR см. в разделе [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Можно определить во время компиляции, является ли тип интерфейсом с помощью `__is_interface_class(``type``)`.  Для получения дополнительной информации см. [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 В среде разработки можно получить справку F1 по этим ключевым словам, выделив ключевое слово \(например,`interface class`\) и нажав клавишу F1.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде выполнения Windows\).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде CLR\).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода показано, как интерфейс может определять поведение функции clock.  
  
```  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **Output**  
  
  **в функции 3**  
 **в функции 2**  
 **в функции 1**  
 **8**  
 **OnClick: 7, 3.14159**  
 **в функции 1** **Пример**  
  
 В следующем примере кода показаны два способа реализации функций с одной и той же сигнатурой, объявленных в нескольких интерфейсах, и где эти интерфейсы используются классом.  
  
```  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)