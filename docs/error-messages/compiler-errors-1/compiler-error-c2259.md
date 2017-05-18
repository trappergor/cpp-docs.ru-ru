---
title: "Ошибка компилятора C2259 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2259
dev_langs:
- C++
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0837d8f5e48ccf0de0ba8630801667da2ddb6bfa
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2259"></a>Ошибка компилятора C2259
«класс»: не удается создать экземпляр абстрактного класса  
  
 В коде объявляется экземпляр абстрактного класса или структуры.  
  
 Не удается создать экземпляр класса или структуры с одной или более чистые виртуальные функции. Для создания экземпляров объектов производного класса, производного класса необходимо переопределить все чисто виртуальные функции.  
  
 Дополнительные сведения см. в разделе [неявно абстрактные классы](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 Следующий пример приводит к возникновению ошибки C2259:  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 При наследовании от интерфейса и реализации методов интерфейса в производном классе с разрешениями доступа являются открытыми, может появиться ошибка C2259.  Это происходит потому, что компилятор ожидает методы интерфейса реализации в производном классе, общий доступ к. При реализации функции-члены для интерфейса с более строгими ограничениями доступа, компилятор не учитывает их как реализации методов, определенных в интерфейсе, который в свою очередь, делает производный класс абстрактный класс.  
  
 Существует два способа решения проблемы:  
  
-   Сделайте общедоступным для реализованные методы разрешения на доступ.  
  
-   Используйте оператор разрешения области для методов интерфейса реализации в производном классе для уточнения имени реализованный метод с именем интерфейса.  
  
 Ошибка C2259 также может произойти в результате работы по стандартизации, выполненной в Visual C++ 2005 **/Zc:** теперь по умолчанию включен. В этой ситуации ошибку C2599 можно устранить путем компиляции с **/Zc:wchar_t-**, чтобы получить поведение предыдущих версий. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 Следующий пример приводит к возникновению ошибки C2259:  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 Следующий пример приводит к возникновению ошибки C2259:  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  

