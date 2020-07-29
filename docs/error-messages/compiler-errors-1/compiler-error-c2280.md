---
title: Ошибка компилятора C2280
ms.date: 04/25/2017
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
ms.openlocfilehash: 9ee5b8105241ee347812a0dcc083a4f1cc7dca49
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87208412"
---
# <a name="compiler-error-c2280"></a>Ошибка компилятора C2280

"*объявление*": попытка ссылки на удаленную функцию

Компилятор обнаружил попытку сослаться на `deleted` функцию. Эта ошибка может быть вызвана вызовом функции-члена, которая явно помечена как `= deleted` в исходном коде. Эта ошибка также может быть вызвана вызовом неявной специальной функции-члена структуры или класса, которая автоматически объявляется и помечается как `deleted` компилятор. Дополнительные сведения о том, когда компилятор автоматически создает **`default`** или `deleted` специальные функции элементов, см. в разделе [специальные функции элементов](../../cpp/special-member-functions.md).

## <a name="example-explicitly-deleted-functions"></a>Пример. явно удаленные функции

Вызов явной `deleted` функции вызывает эту ошибку. Явная `deleted` функция-член предполагает, что класс или структура преднамеренно спроектирована для предотвращения его использования, поэтому для устранения этой проблемы следует изменить код, чтобы избежать этого.

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

## <a name="example-uninitialized-data-members"></a>Пример: неинициализированные члены данных

Неинициализированный член данных ссылочного типа или **`const`** член данных приводит к тому, что компилятор неявно объявляет `deleted` конструктор по умолчанию. Чтобы устранить эту проблему, инициализируйте член данных при его объявлении.

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

## <a name="example-reference-and-const-data-members"></a>Пример: ссылочные и константные элементы данных

**`const`** Член данных ссылочного типа или указывает компилятору объявить `deleted` оператор присваивания копии. После инициализации эти члены не могут быть назначены, поэтому простое копирование или перемещение не может работать. Чтобы устранить эту проблему, мы рекомендуем изменить логику, чтобы удалить операции назначения, которые вызывают ошибку.

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

## <a name="example-movable-deletes-implicit-copy"></a>Пример: перемещаемый удаляет неявную копию

Если класс объявляет конструктор перемещения или оператор присваивания перемещения, но не объявляет конструктор копии явным образом, компилятор неявно объявляет конструктор копии и определяет его как `deleted` . Аналогично, если класс объявляет конструктор перемещения или оператор присваивания перемещения, но явно не объявляет оператор присваивания копирования, компилятор неявно объявляет оператор присваивания копирования и определяет его как `deleted` . Чтобы устранить эту проблему, необходимо явно объявить эти члены.

При появлении ошибки C2280 в соединении с `unique_ptr` , это почти наверняка обусловлено тем, что вы пытаетесь вызвать конструктор копии, который является `deleted` функцией. `unique_ptr`Не может быть скопировано по дизайну. Используйте конструктор Move, чтобы вместо этого передавать владение.

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

## <a name="example-variant-and-volatile-members"></a>Пример: элементы типа Variant и volatile

Версии компилятора до обновления 2 для Visual Studio 2015 были не согласованы и создали конструкторы и деструкторы по умолчанию для анонимных объединений. Теперь они неявно объявляются как `deleted` . Эти версии также позволяли неявное определение **`default`** конструкторов копирования и перемещения, а также **`default`** Операторы копирования и перемещения в классах и структурах, имеющих **`volatile`** переменные-члены. Компилятор рассматривает их как нетривиальные конструкторы и операторы присваивания, а также не создает **`default`** реализации. Если такой класс является членом объединения или анонимным объединением внутри класса, конструкторы копирования и перемещения, а также операторы копирования и перемещения Union или класса неявно определяются как `deleted` . Чтобы устранить эту проблему, необходимо явно объявить необходимые специальные функции элементов.

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

## <a name="example-indirect-base-members-deleted"></a>Пример: удаленные непрямые базовые члены

Версии компилятора до обновления 2 для Visual Studio 2015 не были согласованы и позволял производному классу вызывать специальные функции-члены косвенно производных `private virtual` базовых классов. Компилятор теперь выдает ошибку компилятора C2280, когда выполняется такой вызов.

В этом примере класс `top` косвенно является производным от частного виртуального `base` . В результате выполнения кода это делает элементы `base` недоступными для `top` ; объект типа `top` не может быть создан или удален по умолчанию. Чтобы устранить эту проблему в коде, который основан на старом поведении компилятора, измените промежуточный класс на использование `protected virtual` наследования или измените `top` класс для использования прямого наследования:

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
