---
title: Ошибка компилятора C2259 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: bcb7b24bb39ba204653d2a99d6bc1d3e5d8142b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2259"></a>Ошибка компилятора C2259
«класс»: не удается создать экземпляр абстрактного класса  
  
 Код объявляет экземпляр абстрактного класса или структуры.  
  
 Не удается создать экземпляр класса или структуры с одного или нескольких чистые виртуальные функции. Для создания экземпляров объектов производного класса, производный класс должен переопределять каждую чисто виртуальную функцию.  
  
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
  
 Каждый раз, когда производный от интерфейса и реализации методов интерфейса в производном классе, кроме public разрешения на доступ, может появиться C2259.  Это происходит потому, что компилятор ожидает реализации в производном классе, общий доступ к методов интерфейса. При реализации функции-члены для интерфейса с более строгими разрешениями доступа, компилятор не учитывает их как реализации методов, определенных в интерфейсе, который в свою очередь, делает производный класс абстрактный класс.  
  
 Существует два способа решения этой проблемы:  
  
-   Сделайте открытым и позволить реализованные методы разрешения на доступ.  
  
-   Используйте оператор разрешения области для методов интерфейса реализации в производном классе для уточнения имени реализованный метод с именем интерфейса.  
  
 Ошибка C2259 также может произойти в результате совместимости, выполненной в Visual C++ 2005 **/Zc: wchar_t** теперь по умолчанию включен. В этом случае можно устранить путем компиляции с C2599 **/Zc:wchar_t-**, чтобы получить поведение предыдущих версий. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
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
