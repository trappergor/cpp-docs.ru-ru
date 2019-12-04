---
title: Ошибка компилятора C2259
ms.date: 11/04/2016
f1_keywords:
- C2259
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
ms.openlocfilehash: 403d674eae696eb42a837aef9d6e97c4b5b8f6c2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758792"
---
# <a name="compiler-error-c2259"></a>Ошибка компилятора C2259

"класс": не удается создать экземпляр абстрактного класса

Код объявляет экземпляр абстрактного класса или структуры.

Нельзя создать экземпляр класса или структуры с одной или несколькими чисто виртуальными функциями. Для создания экземпляров объектов производного класса производный класс должен переопределять каждую чистую виртуальную функцию.

Дополнительные сведения см. в разделе [неявно абстрактные классы](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).

Следующий пример приводит к возникновению ошибки C2259:

```cpp
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

Всякий раз, когда вы наследуете от интерфейса и реализуете методы интерфейса в производном классе с разрешениями на доступ, отличными от Public, вы можете получить C2259.  Это происходит потому, что компилятору требуется открытый доступ к методам интерфейса, реализованным в производном классе. При реализации функций членов для интерфейса с более ограниченными разрешениями на доступ компилятор не учитывает их реализации для методов интерфейса, определенных в интерфейсе, что, в свою очередь, делает производный класс абстрактным.

Существует два возможных способа решения проблемы.

- Сделайте разрешения доступа открытыми для реализованных методов.

- Используйте оператор разрешения области для методов интерфейса, реализованных в производном классе, чтобы уточнить реализованное имя метода именем интерфейса.

C2259 также может возникнуть в результате действий по согласованности, выполненных в Visual Studio 2005, параметр **/Zc: wchar_t** теперь включен по умолчанию. В этой ситуации C2599 можно разрешить либо путем компиляции с помощью **/Zc: wchar_t-** , чтобы получить поведение предыдущих версий, либо, желательно, путем обновления типов так, чтобы они были совместимыми. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

Следующий пример приводит к возникновению ошибки C2259:

```cpp
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

```cpp
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
