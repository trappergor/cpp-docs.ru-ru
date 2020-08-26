---
title: Конструкторы (C++)
ms.date: 12/27/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: f5340f2e56a367734293d661d9d89eb0db522fd2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842056"
---
# <a name="constructors-c"></a>Конструкторы (C++)

Чтобы настроить способ инициализации элементов класса или вызвать функции при создании объекта класса, определите *конструктор*. Конструкторы имеют имена, совпадающие с именами классов, и не имеют возвращаемых значений. Можно определить столько перегруженных конструкторов, сколько необходимо для настройки инициализации различными способами. Как правило, конструкторы имеют открытый доступ, поэтому код за пределами определения класса или иерархии наследования может создавать объекты класса. Но можно также объявить конструктор как **`protected`** или **`private`** .

При необходимости конструкторы могут получить список инициализации элемента. Это более эффективный способ инициализации членов класса, чем назначение значений в теле конструктора. В следующем примере показан класс `Box` с тремя перегруженными конструкторами. Последние два списка инициализации элементов use:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    explicit Box(int i) : m_width(i), m_length(i), m_height(i) // member init list
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}

    int Volume() { return m_width * m_length * m_height; }

private:
    // Will have value of 0 when default constructor is called.
    // If we didn't zero-init here, default constructor would
    // leave them uninitialized with garbage values.
    int m_width{ 0 };
    int m_length{ 0 };
    int m_height{ 0 };
};
```

При объявлении экземпляра класса компилятор выбирает конструктор для вызова на основе правил разрешения перегрузки:

```cpp
int main()
{
    Box b; // Calls Box()

    // Using uniform initialization (preferred):
    Box b2 {5}; // Calls Box(int)
    Box b3 {5, 8, 12}; // Calls Box(int, int, int)

    // Using function-style notation:
    Box b4(2, 4, 6); // Calls Box(int, int, int)
}
```

- Конструкторы могут быть объявлены как **`inline`** , [явные](#explicit_constructors) **`friend`** или [constexpr](#constexpr_constructors).
- Конструктор может инициализировать объект, объявленный как **`const`** , **`volatile`** или **`const volatile`** . Объект станет **`const`** после завершения конструктора.
- Чтобы определить конструктор в файле реализации, присвойте ему полное имя с любой другой функцией-членом: `Box::Box(){...}` .

## <a name="member-initializer-lists"></a><a name="member_init_list"></a> Списки инициализаторов членов

Конструктор может дополнительно иметь список инициализаторов членов, который инициализирует члены класса перед выполнением тела конструктора. (Обратите внимание, что список инициализаторов членов не то же самое, что и *Список инициализаторов* типа [std \<T> :: initializer_list](../standard-library/initializer-list-class.md).)

Использование списка инициализаторов членов предпочтительнее, чем назначение значений в теле конструктора, так как он непосредственно Инициализирует элемент. В следующем примере показан список инициализаторов членов, состоящий из всех выражений **идентификаторов (аргументов)** после двоеточия:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Идентификатор должен ссылаться на член класса; он инициализируется значением аргумента. Аргумент может быть одним из параметров конструктора, вызовом функции или [std:: initializer_list \<T> ](../standard-library/initializer-list-class.md).

**`const`** члены и члены ссылочного типа должны быть инициализированы в списке инициализаторов членов.

В списке инициализаторов должны быть сделаны вызовы для параметризованных конструкторов базового класса, чтобы гарантировать, что базовый класс полностью инициализирован до выполнения производного конструктора.

## <a name="default-constructors"></a><a name="default_constructors"></a> Конструкторы по умолчанию

*Конструкторы по умолчанию* обычно не имеют параметров, но могут иметь параметры со значениями по умолчанию.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Конструкторы по умолчанию являются одной из [специальных функций элементов](special-member-functions.md). Если в классе не объявлен ни один конструктор, компилятор предоставляет неявный **`inline`** конструктор по умолчанию.

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int Volume() {return m_width * m_height * m_length;}
private:
    int m_width { 0 };
    int m_height { 0 };
    int m_length { 0 };
};

int main() {
    Box box1; // Invoke compiler-generated constructor
    cout << "box1.Volume: " << box1.Volume() << endl; // Outputs 0
}
```

Если вы полагаетесь на неявный конструктор по умолчанию, обязательно инициализируйте элементы в определении класса, как показано в предыдущем примере. Без этих инициализаторов члены будут неинициализированы, а вызов Volume () создаст значение мусора. Как правило, рекомендуется инициализировать элементы таким образом, даже если не полагается на неявный конструктор по умолчанию.

Можно запретить компилятору создавать неявный конструктор по умолчанию, определив его как [Удаленный](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

Созданный компилятором конструктор по умолчанию будет определен как удаленный, если какие-либо члены класса не являются конструируемым по умолчанию. Например, все члены типа класса и их члены типа класса должны иметь доступ к конструктору по умолчанию и деструкторам, которые доступны. Все элементы данных ссылочного типа, а также **`const`** члены класса должны иметь инициализатор членов по умолчанию.

При вызове конструктора, созданного компилятором по умолчанию, и попытке использовать круглые скобки выдается предупреждение:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Это пример проблемы Most Vexing Parse (наиболее неоднозначного анализа). Поскольку выражение примера можно интерпретировать как объявление функции или как вызов конструктора по умолчанию и в связи с тем, что средства синтаксического анализа C++ отдают предпочтение объявлениям перед другими действиями, данное выражение обрабатывается как объявление функции. Дополнительные сведения см. в разделе [досадной Parse](https://en.wikipedia.org/wiki/Most_vexing_parse).

В случае явного объявления конструкторов компилятор не предоставляет конструктор по умолчанию:

```cpp
class Box {
public:
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
private:
    int m_width;
    int m_length;
    int m_height;

};

int main(){

    Box box1(1, 2, 3);
    Box box2{ 2, 3, 4 };
    Box box3; // C2512: no appropriate default constructor available
}
```

Если у класса нет конструктора по умолчанию, массив объектов этого класса не может быть создан только с помощью синтаксиса двух квадратных скобок. Например, в представленном выше блоке кода массив Boxes не может быть объявлен следующим образом:

```cpp
Box boxes[3]; // C2512: no appropriate default constructor available
```

Однако можно использовать набор списков инициализаторов для инициализации массива объектов Box:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Дополнительные сведения см. в разделе [инициализаторы](initializers.md).

## <a name="copy-constructors"></a><a name="copy_and_move_constructors"></a> Конструкторы копий

*Конструктор копии* Инициализирует объект, копируя значения элементов из объекта того же типа. Если все члены класса являются простыми типами, такими как скалярные значения, конструктор копий, созданный компилятором, достаточно, и вам не нужно определять собственный. Если для класса требуется более сложная инициализация, необходимо реализовать пользовательский конструктор копии. Например, если член класса является указателем, необходимо определить конструктор копии, чтобы выделить новую память и скопировать значения из объекта, указывающего на другой объект. Созданный компилятором конструктор копий просто копирует указатель, так что новый указатель по-прежнему указывает на расположение в памяти другого.

Конструктор копии может иметь одну из следующих сигнатур:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

При определении конструктора копии необходимо также определить оператор присваивания копирования (=). Дополнительные сведения см. в разделе конструкторы [присваивания](assignment.md) и [копирования и операторы присваивания копирования](copy-constructors-and-copy-assignment-operators-cpp.md).

Вы можете запретить копирование объекта, определив конструктор копии как удаленный:

```cpp
    Box (const Box& other) = delete;
```

Попытка копирования объекта приводит к ошибке *C2280: попытка ссылки на удаленную функцию*.

## <a name="move-constructors"></a><a name="move_constructors"></a> Конструкторы перемещения

*Конструктор перемещения* — это специальная функция-член, которая перемещает владение данными существующего объекта в новую переменную без копирования исходных данных. Он принимает в качестве первого параметра ссылку rvalue, а все дополнительные параметры должны иметь значения по умолчанию. Конструкторы перемещения могут значительно повысить эффективность программы при передаче больших объектов.

```cpp
Box(Box&& other);
```

Компилятор выбирает конструктор перемещения в определенных ситуациях, где объект инициализируется другим объектом того же типа, который будет уничтожен и больше не нуждается в его ресурсах. В следующем примере показан один случай, когда конструктор перемещения выбирается с помощью разрешения перегрузки. В конструкторе, который вызывает `get_Box()` , возвращаемое значение является *xValue* (значение срока действия). Она не назначается какой-либо переменной, поэтому она собирается выйти из области. Чтобы создать мотивацию для этого примера, пусть Box имеет большой вектор строк, который представляет его содержимое. Вместо копирования вектора и его строк конструктор Move "украсть" из поля "Box Expires", чтобы вектор теперь принадлежал новому объекту. Вызов `std::move` является необходимым, поскольку оба `vector` `string` класса и реализуют собственные конструкторы перемещения.

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

class Box {
public:
    Box() { std::cout << "default" << std::endl; }
    Box(int width, int height, int length)
       : m_width(width), m_height(height), m_length(length)
    {
        std::cout << "int,int,int" << std::endl;
    }
    Box(Box& other)
       : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        std::cout << "copy" << std::endl;
    }
    Box(Box&& other) : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        m_contents = std::move(other.m_contents);
        std::cout << "move" << std::endl;
    }
    int Volume() { return m_width * m_height * m_length; }
    void Add_Item(string item) { m_contents.push_back(item); }
    void Print_Contents()
    {
        for (const auto& item : m_contents)
        {
            cout << item << " ";
        }
    }
private:
    int m_width{ 0 };
    int m_height{ 0 };
    int m_length{ 0 };
    vector<string> m_contents;
};

Box get_Box()
{
    Box b(5, 10, 18); // "int,int,int"
    b.Add_Item("Toupee");
    b.Add_Item("Megaphone");
    b.Add_Item("Suit");

    return b;
}

int main()
{
    Box b; // "default"
    Box b1(b); // "copy"
    Box b2(get_Box()); // "move"
    cout << "b2 contents: ";
    b2.Print_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

Если класс не определяет конструктор перемещения, компилятор создает неявный экземпляр, если не существует объявленного пользователем конструктора копии, оператора присваивания копирования, оператора присваивания перемещения или деструктора. Если явный или неявный конструктор перемещения не определен, операции, в которых в противном случае использовался конструктор перемещения, используют вместо этого конструктор копий. Если класс объявляет конструктор перемещения или оператор присваивания перемещения, неявно объявленный конструктор копии определяется как удаленный.

Неявно объявленный конструктор перемещения определяется как удаленный, если какие-либо члены, являющиеся типами классов, не имеют деструктора или компилятор не может определить, какой конструктор использовать для операции перемещения.

Дополнительные сведения о написании нетривиальных конструкторов перемещения см. в разделе [конструкторы перемещения и операторы присваивания перемещения (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly-defaulted-and-deleted-constructors"></a><a name="explicitly_defaulted_and_deleted_constructors"></a> Явно заданные по умолчанию и удаленные конструкторы

Можно явно заключать конструкторы копирования, конструкторы *по умолчанию* , конструкторы перемещения, операторы присваивания копирования, операторы присваивания перемещения и деструкторы. Вы можете явно *Удалить* все специальные функции элементов.

```cpp
class Box
{
public:
    Box2() = delete;
    Box2(const Box2& other) = default;
    Box2& operator=(const Box2& other) = default;
    Box2(Box2&& other) = default;
    Box2& operator=(Box2&& other) = default;
    //...
};
```

Дополнительные сведения см. в разделе [явно заданные по умолчанию и удаленные функции](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr-constructors"></a><a name="constexpr_constructors"></a> конструкторы constexpr

Конструктор может быть объявлен как [constexpr](constexpr-cpp.md) , если

- Он либо объявляется по умолчанию, либо, в противном случае, удовлетворяет всем условиям для [функций constexpr](constexpr-cpp.md#constexpr_functions) в целом;
- класс не имеет виртуальных базовых классов;
- Каждый из параметров имеет [тип литерала](trivial-standard-layout-and-pod-types.md#literal_types);
- тело не является блоком функции try;
- все нестатические элементы данных и подобъекты базового класса инициализируются;
- Если класс имеет (a) объединение с вариантными членами или (b) имеет анонимные объединения, то инициализируется только один из членов Union.
- Каждый нестатический элемент данных типа класса, а все подобъекты базового класса имеют конструктор constexpr

## <a name="initializer-list-constructors"></a><a name="init_list_constructors"></a> Конструкторы списка инициализаторов

Если конструктор принимает в качестве параметра значение [std: \<T\> : initializer_list](../standard-library/initializer-list-class.md) , а все другие параметры имеют аргументы по умолчанию, этот конструктор будет выбран в разрешении перегрузки при создании экземпляра класса с помощью прямой инициализации. Можно использовать initializer_list для инициализации любого участника, который может принять его. Например, предположим, что класс Box (показан ранее) имеет `std::vector<string>` элемент `m_contents` . Вы можете предоставить конструктор следующим образом:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Затем создайте объекты Box следующим образом:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit-constructors"></a><a name="explicit_constructors"></a> Явные конструкторы

Если у класса имеется конструктор с одним параметром, или у всех параметров, кроме одного, имеются значения по умолчанию, тип параметра можно неявно преобразовать в тип класса. Например, если у класса `Box` имеется конструктор, подобный следующему:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

то возможно инициализировать объект Box следующим образом:

```cpp
Box b = 42;
```

Или передать целое значение функции, принимающей объект Box:

```cpp
class ShippingOrder
{
public:
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}

private:
    Box m_box;
    double m_postage;
}
//elsewhere...
    ShippingOrder so(42, 10.8);
```

В некоторых случаях подобные преобразования могут быть полезны, однако чаще всего они могут привести к незаметным, но серьезным ошибкам в вашем коде. В качестве общего правила следует использовать **`explicit`** ключевое слово в конструкторе (и определяемых пользователем операторах) для предотвращения такого рода неявного преобразования типов:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Когда конструктор является явным, эта строка вызывает ошибку компилятора: `ShippingOrder so(42, 10.8);`.  Дополнительные сведения см. в разделе [преобразования определяемого пользователем типа](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order-of-construction"></a><a name="order_of_construction"></a> Порядок создания

Конструктор выполняет свою работу в следующем порядке.

1. Вызывает конструкторы базовых классов и членов в порядке объявления.

1. Если класс является производным от виртуальных базовых классов, конструктор инициализирует указатели виртуальных базовых классов объекта.

1. Если класс имеет или наследует виртуальные функции, конструктор инициализирует указатели виртуальных функций объекта. Указатели виртуальных функций указывают на таблицу виртуальных функций класса, чтобы обеспечить правильную привязку вызовов виртуальных функций к коду.

1. Выполняет весь код в теле функции.

В следующем примере показан порядок, в котором конструкторы базовых классов и членов вызываются в конструкторе для производного класса. Сначала вызывается конструктор базового класса, затем инициализируются члены базового класса в порядке их появления в объявлении класса. После этого вызывается конструктор производного класса.

```cpp
#include <iostream>

using namespace std;

class Contained1 {
public:
    Contained1() { cout << "Contained1 ctor\n"; }
};

class Contained2 {
public:
    Contained2() { cout << "Contained2 ctor\n"; }
};

class Contained3 {
public:
    Contained3() { cout << "Contained3 ctor\n"; }
};

class BaseContainer {
public:
    BaseContainer() { cout << "BaseContainer ctor\n"; }
private:
    Contained1 c1;
    Contained2 c2;
};

class DerivedContainer : public BaseContainer {
public:
    DerivedContainer() : BaseContainer() { cout << "DerivedContainer ctor\n"; }
private:
    Contained3 c3;
};

int main() {
    DerivedContainer dc;
}
```

Появятся следующие выходные данные.

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Конструктор производного класса всегда вызывает конструктор базового класса, чтобы перед выполнением любых дополнительных операций иметь в своем распоряжении полностью созданные базовые классы. Конструкторы базовых классов вызываются в порядке наследования — например, если `ClassA` является производным от класса `ClassB` , производного от, то `ClassC` `ClassC` сначала вызывается конструктор, затем `ClassB` конструктор, а затем `ClassA` конструктор.

Если базовый класс не имеет конструктор по умолчанию, в конструкторе производного класса необходимо указать параметры конструктора базового класса.

```cpp
class Box {
public:
    Box(int width, int length, int height){
       m_width = width;
       m_length = length;
       m_height = height;
    }

private:
    int m_width;
    int m_length;
    int m_height;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){
        m_label = label;
    }
private:
    string m_label;
};

int main(){

    const string aLabel = "aLabel";
    StorageBox sb(1, 2, 3, aLabel);
}
```

Если конструктор создает исключение, то удаление выполняется в порядке, обратном созданию.

1. Отменяется код в теле функции конструктора.

1. Объекты базовых классов и объекты-члены удаляются в порядке, обратном объявлению.

1. Если конструктор не является делегирующим, удаляются все полностью созданные объекты базовых классов и объекты-члены. Однако поскольку сам объект создан не полностью, деструктор не выполняется.

## <a name="derived-constructors-and-extended-aggregate-initialization"></a><a name="extended_aggregate"></a> Производные конструкторы и расширенная агрегатная инициализация

Если конструктор базового класса не является открытым, но доступен для производного класса, то в режиме **/std: c++ 17** в Visual Studio 2017 и более поздних версиях нельзя использовать пустые фигурные скобки для инициализации объекта производного типа.

В следующем примере показана соответствующая реакция на событие в C++14:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

В C++17 `Derived` теперь считается агрегатным типом. Это означает, что инициализация `Base` через закрытый конструктор по умолчанию происходит непосредственно как часть расширенного правила агрегатной инициализации. Закрытый конструктор `Base` ранее вызывался через конструктор `Derived`, и это работало успешно благодаря объявлению дружественных отношений.

В следующем примере показано поведение C++ 17 в Visual Studio 2017 и более поздних версиях в **/std: режим c++ 17** :

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Конструкторы для классов с несколькими наследованиями

Если класс является производным от нескольких базовых классов, конструкторы базовых классов вызываются в том порядке, в котором они перечислены в объявлении производного класса.

```cpp
#include <iostream>
using namespace std;

class BaseClass1 {
public:
    BaseClass1() { cout << "BaseClass1 ctor\n"; }
};
class BaseClass2 {
public:
    BaseClass2() { cout << "BaseClass2 ctor\n"; }
};
class BaseClass3 {
public:
    BaseClass3() { cout << "BaseClass3 ctor\n"; }
};
class DerivedClass : public BaseClass1,
                     public BaseClass2,
                     public BaseClass3
                     {
public:
    DerivedClass() { cout << "DerivedClass ctor\n"; }
};

int main() {
    DerivedClass dc;
}
```

Должны выводиться следующие выходные данные:

```Output
BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor
```

## <a name="delegating-constructors"></a><a name="delegating_constructors"></a> Делегирование конструкторов

*Делегирующий конструктор* вызывает другой конструктор в том же классе для выполнения некоторой работы по инициализации. Это полезно, если у вас есть несколько конструкторов, которые должны выполнять одинаковую работу. Можно написать основную логику в одном конструкторе и вызвать ее из других. В следующем тривиальном примере Box (int) делегирует свою работу Box (int, int, int):

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```

Объект, созданный конструкторами, полностью инициализируется сразу после выполнения любого конструктора. Дополнительные сведения см. в разделе [Делегирование конструкторов](../cpp/delegating-constructors.md).

## <a name="inheriting-constructors-c11"></a><a name="inheriting_constructors"></a> Наследование конструкторов (C++ 11)

Производный класс может наследовать конструкторы от прямого базового класса с помощью объявления, **`using`** как показано в следующем примере:

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    Base() { cout << "Base()" << endl; }
    Base(const Base& other) { cout << "Base(Base&)" << endl; }
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }

private:
    int num;
    char letter;
};

class Derived : Base
{
public:
    // Inherit all constructors from Base
    using Base::Base;

private:
    // Can't initialize newMember from Base constructors.
    int newMember{ 0 };
};

int main()
{
    cout << "Derived d1(5) calls: ";
    Derived d1(5);
    cout << "Derived d1('c') calls: ";
    Derived d2('c');
    cout << "Derived d3 = d2 calls: " ;
    Derived d3 = d2;
    cout << "Derived d4 calls: ";
    Derived d4;
}

/* Output:
Derived d1(5) calls: Base(int)
Derived d1('c') calls: Base(char)
Derived d3 = d2 calls: Base(Base&)
Derived d4 calls: Base()*/
```

::: moniker range=">=vs-2017"

**Visual Studio 2017 и более поздние версии**: **`using`** инструкция в режиме **/std: c++ 17** предоставляет все конструкторы из базового класса, за исключением тех, которые имеют идентичную сигнатуру для конструкторов в производном классе. Обычно, если в производном классе не объявляются новые данные-члены или конструкторы, оптимальным решением будет использовать наследуемые конструкторы. См. также [усовершенствования в Visual Studio 2017 версии 15,7](../overview/cpp-conformance-improvements.md?view=vs-2017#improvements_157).

::: moniker-end

Шаблон класса может наследовать все конструкторы от аргумента типа, если этот тип определяет базовый класс:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

Производный класс не может наследовать от нескольких базовых классов, если у этих базовых классов есть конструкторы с идентичными сигнатурами.

## <a name="constructors-and-composite-classes"></a><a name="constructors_in_composite_classes"></a> Конструкторы и составные классы

Классы, содержащие члены типа класса, называются *составными классами*. При создании члена типа класса составного класса конструктор вызывается перед собственным конструктором класса. Если у содержащегося класса нет конструктора по умолчанию, необходимо использовать список инициализации в конструкторе составного класса. В предыдущем примере `StorageBox` при присвоении типу переменной-члена `m_label` нового класса `Label` необходимо вызвать конструктор базового класса и инициализировать переменную `m_label` в конструкторе `StorageBox`:

```cpp
class Label {
public:
    Label(const string& name, const string& address) { m_name = name; m_address = address; }
    string m_name;
    string m_address;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, Label label)
        : Box(width, length, height), m_label(label){}
private:
    Label m_label;
};

int main(){
// passing a named Label
    Label label1{ "some_name", "some_address" };
    StorageBox sb1(1, 2, 3, label1);

    // passing a temporary label
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });

    // passing a temporary label as an initializer list
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});
}
```

## <a name="in-this-section"></a>В этом разделе

- [Конструкторы копий и операторы присваивания копий](copy-constructors-and-copy-assignment-operators-cpp.md)
- [Конструкторы перемещения и операторы присваивания перемещением](move-constructors-and-move-assignment-operators-cpp.md)
- [Делегирующие конструкторы](delegating-constructors.md)

## <a name="see-also"></a>См. также раздел

[Классы и структуры](classes-and-structs-cpp.md)
