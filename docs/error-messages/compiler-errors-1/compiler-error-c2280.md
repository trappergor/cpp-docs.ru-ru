---
title: Ошибка компилятора C2280 | Документация Майкрософт
ms.custom: ''
ms.date: 04/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
dev_langs:
- C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e71d801f2abaaf83ae1064551b40a5a5a6ba8964
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820611"
---
# <a name="compiler-error-c2280"></a>Ошибка компилятора C2280

"*объявление*': попытка ссылки на удаленную функцию

Компилятор обнаружил попытку для ссылки на `deleted` функции. Эта ошибка может быть вызвана с помощью вызова функции-члену был явно помечен как `= deleted` в исходном коде. Это ошибка также может быть вызвана путем вызова неявного специальная функция-член структуры или класса, который автоматически объявляется и помечен как `deleted` компилятором. Дополнительные сведения о когда компилятор автоматически создает `default` или `deleted` специальных функций-членов см. в разделе [специальных функций-членов](../../cpp/special-member-functions.md).

## <a name="example-explicitly-deleted-functions"></a>Пример: Явно удалены функции

Вызов, чтобы явным образом `deleted` функция вызывает эту ошибку. Явно `deleted` функция-член подразумевает, что класс или структура специально предназначен для предотвращения использования, поэтому, чтобы устранить эту проблему, следует изменить код, чтобы устранить ее.

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

## <a name="example-uninitialized-data-members"></a>Примеры: Неинициализированных данных элементов

Неинициализированный члена ссылочного типа данных или `const` данные-член заставляет компилятор неявно объявляют `deleted` конструктор по умолчанию. Чтобы устранить эту проблему, инициализируйте элемент данных, если он объявлен.

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

## <a name="example-reference-and-const-data-members"></a>Пример: Ссылки и const данные-члены

Объект `const` или члена данных ссылочного типа компилятор для объявления `deleted` оператор присваивания копии. После инициализации, эти члены не могут быть назначены, поэтому просто при помощи копирования или перемещения не может работать. Чтобы устранить эту проблему, мы рекомендуем изменить логику для удаления назначения операции, которые вызывают ошибку.

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

## <a name="example-movable-deletes-implicit-copy"></a>Пример: Movable удаляет неявное копирование

Если класс объявляет конструктор перемещения или оператор присваивания перемещения, но не объявляет конструктор копии явным образом, компилятор неявно объявляет конструктор копии и определяет его как `deleted`. Аналогичным образом, если класс объявляет конструктор перемещения или оператор присваивания перемещения, но не объявлен оператор присваивания копированием явным образом, компилятор неявно объявляет оператор присваивания копированием и определяет его как `deleted`. Чтобы устранить эту проблему, необходимо явно объявить эти члены.

При появлении ошибки C2280 в связи с `unique_ptr`, это почти наверняка так, как вы пытаетесь вызвать его конструктор копированием, который является `deleted` функции. По своей структуре `unique_ptr` не может быть скопирован. Используйте конструктор перемещения для вместо передачи владения.

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

Версии компилятора до Visual Studio 2015 с обновлением 2 были несоответствующих и созданный по умолчанию конструкторы и деструкторы для анонимных объединений. Они теперь неявно объявляются как `deleted`. Эти версии также допустимы несоответствующих неявное определение `default` конструкторы копии и перемещения и `default` скопируйте и операторов перемещения с присваиванием в классов и структур, имеющих `volatile` переменных-членов. Компилятор теперь учитывает их в имеют нетривиальные конструкторы и операторы присваивания и не генерирует `default` реализаций. Если такой класс входит в объединения или анонимного объединения внутри класса, конструкторы копирования и перемещения и операторы присваивания копирования и перемещения объединения или класса неявно определяется как `deleted`. Чтобы устранить эту проблему, необходимо явно объявить необходимые специальные функции-члены.

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

## <a name="example-indirect-base-members-deleted"></a>Пример: Базовые члены с косвенных удален

Версии компилятора до Visual Studio 2015 с обновлением 2 были несоответствующих и производному классу вызывать функции косвенно производным специальные член `private virtual` базовых классов. Теперь компилятор выдает ошибку C2280 при такой вызов.

В этом примере класс `top` косвенно наследуется от частного виртуального `base`. В код, в результате членами `base` ограничен доступ `top`; объект типа `top` невозможно по умолчанию создан или уничтожен. Чтобы устранить эту проблему в код, основанный на прежнем поведении компилятора, измените промежуточный класс для использования `protected virtual` наследования или изменение `top` использовать прямое наследование класса:

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
