---
title: "Ошибка C2280 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
dev_langs:
- C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af19f0a0c347ab0f898a3a3d72b8cca5cb07dad8
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2280"></a>Ошибка C2280 компилятора  
  
"*объявление*": попытка ссылки на удаленную функцию  
  
Компилятор обнаружил попытку ссылки `deleted` функции. Эта ошибка может вызываться вызов функции-члена, который был явным образом помечен как `= deleted` в исходном коде. Эта ошибка может также вызываться вызов неявного специальную функцию-член класса или структуры, автоматически объявленный и помечен как `deleted` компилятором. Дополнительные сведения о когда компилятор автоматически создает `default` или `deleted` специальных функций-членов, в разделе [специальные функции-члены](../../cpp/special-member-functions.md).  
  
## <a name="example-explicitly-deleted-functions"></a>Пример: Явное удаление функции  

Вызов явным образом `deleted` функция вызывает эту ошибку. Явно `deleted` функции-члена подразумевает, что класс или структура специально предназначен для предотвращения использования, поэтому, чтобы устранить эту проблему, следует изменить код, чтобы избежать его.  
  
```cpp  
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```  
  
## <a name="example-uninitialized-data-members"></a>Пример: Неинициализированные данные членов  
  
Неинициализированный члена ссылочного типа данных или `const` член данных заставляет компилятор неявно объявляют `deleted` конструктор по умолчанию. Чтобы устранить эту проблему, инициализируйте член данных при их объявлении.  
  
```cpp  
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```  
  
## <a name="example-reference-and-const-data-members"></a>Пример: Ссылка и const члены данных  
  
Объект `const` или члена данных ссылочного типа компилятор для объявления `deleted` оператор присваивания копии. После инициализации, эти элементы нельзя задать, поэтому простое копирование или перемещение не может работать. Чтобы устранить эту проблему, рекомендуется изменять логику для удаления назначения операции, которые вызывают ошибку.  
  
```cpp  
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes 
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```  
  
## <a name="example-movable-deletes-implicit-copy"></a>Пример: Доступные удаляет неявное копирования  
  
Если класс объявляет конструктор перемещения или оператор присваивания перемещения, но не объявляет конструктор копии явным образом, компилятор неявно объявляет конструктор копии и определяет его как `deleted`. Аналогично, если класс объявляет конструктор перемещения или оператор присваивания перемещения, но явно не объявлен оператор присваивания копии, компилятор неявно объявляет оператор присваивания копии и определяет его как `deleted`. Чтобы устранить эту проблему, необходимо явно объявить эти элементы.  
 
Когда появляется ошибка C2280 в связи с `unique_ptr`, это почти наверняка так, как вы пытаетесь вызвать его конструктор копий, который является `deleted` функции. Разработчиками предусмотрено `unique_ptr` не могут быть скопированы. Используйте конструктор перемещения для вместо передачи владения.  

```cpp  
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base  
{  
public:  
    base();  
    ~base(); 
    base(base&&); 
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this 
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};  

void copy(base *p)  
{  
    base b{*p};  // C2280
}  
```  

## <a name="example-variant-and-volatile-members"></a>Пример: Члены типа Variant и volatile  
  
Версии компилятора до Visual Studio 2015 с обновлением 2 были несоответствующих и созданный по умолчанию конструкторы и деструкторы для анонимных объединений. Они теперь неявно объявляются как `deleted`. Эти версии также можно использовать несоответствующих неявного определения `default` конструкторы копии и перемещения и `default` копирование и перемещение операторы присваивания в классов и структур, имеющих `volatile` переменных-членов. Компилятор теперь считает, что они должны иметь нетривиальных конструкторов и операторы присваивания и не генерирует `default` реализации. Если такой класс входит в объединения или анонимного объединения внутри класса, конструкторы копирования и перемещения и операторы присваивания копирования и перемещения объединения или класса неявно определяется как `deleted`. Чтобы устранить эту проблему, необходимо явно объявить необходимые специальные функции-члены.  
  
```cpp  
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {  
    A() = default;
    A(const A&);
};  

struct B {  
    union {  
        A a;  
        int i;  
    };
    // To fix this issue, declare the required 
    // special member functions:
    // B(); 
    // B(const B& b);
};  

int main() {
    B b1;  
    B b2(b1);  // C2280  
}
```  
  
## <a name="example-indirect-base-members-deleted"></a>Пример: Косвенных базовых-членов удален  
  
Версии компилятора до Visual Studio 2015 с обновлением 2 были несоответствующих и допускается в производном классе, чтобы вызвать член специальные функции косвенно полученные `private virtual` базовые классы. Если такой вызов выполняется, компилятор теперь выдает ошибку C2280.  
  
В этом примере класс `top` косвенно наследуется от частного виртуального `base`. В код, это делает члены `base` недоступной для `top`; объект типа `top` нельзя по умолчанию создается или удаляется. Чтобы устранить эту проблему в коде, в котором использовалось старое поведение компилятора, измените промежуточного класса для использования `protected virtual` производного или измените `top` класс использовать прямое наследование:  

```cpp  
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base  
{  
protected:  
    base();  
    ~base();  
};  

class middle : private virtual base {}; 
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};   

void destroy(top *p)  
{  
    delete p;  // C2280  
}  
```  
  
