---
title: "Ошибка компилятора C2259 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2259"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2259"
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2259
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Класс": невозможно создать экземпляр абстрактного класса  
  
 В коде объявляется экземпляр абстрактного класса или структуры.  
  
 Нельзя создавать экземпляры класса или структуры с одной или несколькими чисто виртуальными функциями.  Чтобы создать экземпляры объектов производного класса, производный класс должен переопределить все чисто виртуальные функции.  
  
 Дополнительные сведения см. в разделе [Неявно абстрактные классы](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
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
  
 Ошибка C2259 может возникать при наследовании от интерфейса и реализации методов интерфейса в производном классе, к которому не разрешен общий доступ.  Это связано с тем, что компилятор ожидает общий доступ к методам интерфейса, реализованным в производном классе.  Если функция\-член реализуется для интерфейса с более строгими ограничениями доступа, компилятор не рассматривает их как реализации методов, определенных в интерфейсе, в результате чего производный класс становится абстрактным.  
  
 Существует два способа решения проблемы:  
  
-   Можно предоставить общий доступ к реализованным методам.  
  
-   С помощью оператора разрешения области для методов интерфейсов, реализованных в производном классе, можно определить имя реализованного метода как имя интерфейса.  
  
 Ошибка C2259 также может произойти в результате действий по обеспечению совместимости с Visual C\+\+ 2005: параметр **\/Zc:wchar\_t** теперь по умолчанию включен.  В данной ситуации ошибку C2599 можно устранить путем компиляции с параметром **\/Zc:wchar\_t\-**, чтобы получить поведение предыдущих версий. Более предпочтительным способом является обновление типов, которое позволит обеспечить их совместимость.  Дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
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
  
 Следующий пример приводит к возникновению ошибки C2259:  
  
```  
// C2259d.cpp  
// compile with: /clr:oldSyntax  
public __gc __interface MyInterface {  
   void MyMethod();  
};  
  
__gc class MyDerivedClass : public MyInterface {  
// Uncomment the following line to resolve.  
// public:  
   void MyMethod() {};  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass *instance = new MyDerivedClass();   // C2259  
}  
```