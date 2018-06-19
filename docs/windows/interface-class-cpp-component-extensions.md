---
title: интерфейс класса (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- interface_CPP
dev_langs:
- C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c081abc457d025ca2818c887deeb5baf4c4de7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880863"
---
# <a name="interface-class--c-component-extensions"></a>interface class (расширения компонентов C++)
Объявляет интерфейс.  Сведения о собственном интерфейсы см [__interface](../cpp/interface.md).  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Синтаксис**  
  
```  
  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
 **Параметры**  
  
 *interface_access*  
 Доступность интерфейса за пределами сборки.  Возможными значениями являются **открытый** и `private`.  Значение по умолчанию — `private`.  Интерфейсы не могут иметь *interface_access* спецификатор.  
  
 *name*  
 Имя интерфейса.  
  
 *inherit_access*  
 Доступность *base_interface*.  Единственным разрешается специальных возможностей, для базового интерфейса `public` (по умолчанию).  
  
 *base_interface* (необязательно)  
 Базовый интерфейс для интерфейса *имя*.  
  
 **Заметки**  
  
 **Структура интерфейса** эквивалентно **класс интерфейса**.  
  
 Интерфейс может содержать объявления для функций, события и свойства.  Все члены интерфейса быть открытым. Интерфейс может также содержать статические данные-члены, функции, события и свойства, и эти статические члены должны быть объявлены в интерфейсе.  
  
 Интерфейс определяет реализации класса. Интерфейс не является классом и классы только могут реализовывать интерфейсы. Если класс определяет функции, объявленной в интерфейсе, функция реализована, не переопределен. Таким образом поиск имени не включает членов интерфейса.  
  
 Класс или структура, производный от интерфейса необходимо реализовать все члены интерфейса. При реализации интерфейса *имя* также должен реализовывать интерфейсы в `base_interface` списка.  
  
 Дополнительные сведения:  
  
-   [Статический конструктор интерфейса](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Универсальные интерфейсы (Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 Сведения о других типов среды CLR см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Можно обнаружить во время компиляции, если тип является интерфейсом с `__is_interface_class(type)`. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 В среде разработки можно получить справку F1 на эти ключевые слова, выделение ключевое слово (`interface class`, например) и нажать клавишу F1.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 (Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 (Отсутствуют комментарии для этой возможности языка, которая применяется только в среде CLR).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показано, как интерфейс можно определить поведение функции часов.  
  
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
  
 **Вывод**  
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 **Пример**  
  
 В следующем примере кода показаны два способа реализации функций с такой же сигнатурой, объявленных в нескольких интерфейсах и использования этих интерфейсов в классе.  
  
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
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)