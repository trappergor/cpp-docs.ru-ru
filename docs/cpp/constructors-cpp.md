---
title: Конструкторы (C++)
ms.date: 07/02/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: 98e4a35a362b659307d92e57d826e7ac85b9bd09
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552301"
---
# <a name="constructors-c"></a>Конструкторы (C++)

Для настройки, как инициализируются члены класса, или для вызова функций при создании объекта класса, определите *конструктор*. Конструкторы имеют имена, совпадающие с именами классов, и не имеют возвращаемых значений. Вы можете определить столько перегруженных конструкторов, при необходимости для настройки инициализации различными способами. Как правило конструкторы иметь доступность уровня public, чтобы код вне иерархии классов определение или наследования может создавать объекты класса. Но можно также объявить конструктор как **защищенные** или **частного**.

Конструкторы могут при необходимости принимать член списка init. Это более эффективный способ для инициализации класса элементов, чем назначение значений в теле конструктора. В следующем примере показано класс `Box` с тремя перегруженных конструктора. Последние два использовать списки инициализации членов:

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

При объявлении экземпляра класса, компилятор выбирает, какой конструктор для вызова на основе правил разрешения перегрузки:

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

- Конструкторы могут быть объявлены как **встроенного**, [явные](#explicit_constructors), **friend** или [constexpr](#constexpr_constructors).
- Конструктор может инициализировать объект, который был объявлен как **const**, **volatile** или **const volatile**. Объект становится **const** после завершения конструктора.
- Определение конструктора в файле реализации, ей полное имя как и в случае с любой другой функции-члена: `Box::Box(){...}`.

## <a name="member_init_list"></a> Списки инициализаторов членов

Конструктор может иметь список инициализации членов, которые инициализируют члены класса перед выполнением теле конструктора. (Обратите внимание, что список инициализации членов не то же самое *список инициализаторов* типа [std::initializer_list\<T >](../standard-library/initializer-list-class.md).)

Используя список инициализации членов предпочтительнее назначение значений в теле конструктора, так как он непосредственно инициализирует член. В следующем примере показан Инициализатор члена список состоит из всех **identifier(argument)** выражения, которая следует за двоеточием:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Идентификатор должен ссылаться на член класса; он инициализируется со значением аргумента. Аргумент может принимать одно из параметров конструктора, вызов функции или [std::initializer_list\<T >](../standard-library/initializer-list-class.md).

**const** члены и члены ссылочного типа должны быть инициализированы в списке инициализации членов.

Вызовы к конструкторам параметризованные базового класса следует выполнить в списке инициализаторов убедитесь, что перед выполнением конструктора производного полностью инициализации базового класса.

## <a name="default_constructors"></a> Конструкторы по умолчанию

*Конструкторы по умолчанию* обычно не имеют параметров, но они могут иметь параметры со значениями по умолчанию.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Конструкторы по умолчанию принадлежат к числу [специальных функций-членов](special-member-functions.md). Если конструкторы не объявлены в классе, компилятор предоставляет явный **встроенного** конструктор по умолчанию.

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

Если вы используете неявный конструктор по умолчанию, убедитесь в инициализации членов в определении класса, как показано в предыдущем примере. Без этих инициализаторов членов бы быть инициализировано и вызов Volume() даст значение сборки мусора. В общем случае рекомендуется для инициализации элементов таким образом, даже в том случае, если не полагаться на неявный конструктор по умолчанию.

Можно запретить создание неявный конструктор по умолчанию, определив его как компилятор [удалены](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

Конструктор по умолчанию, созданный компилятором будут определены как удаленные, если все члены класса не может быть конструируемым по умолчанию. Например все члены типа класса и их члены типа класса должен иметь конструктор по умолчанию и деструкторы, которые доступны. Все данные членов ссылочного типа, а также как **const** члены должны иметь инициализатор элементов по умолчанию.

При вызове конструктора по умолчанию, созданный компилятором и пытаетесь использовать скобки, то выдается предупреждение:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Это пример проблемы Most Vexing Parse (наиболее неоднозначного анализа). Поскольку выражение примера можно интерпретировать как объявление функции или как вызов конструктора по умолчанию и в связи с тем, что средства синтаксического анализа C++ отдают предпочтение объявлениям перед другими действиями, данное выражение обрабатывается как объявление функции. Дополнительные сведения см. в разделе [Most Vexing Parse](https://en.wikipedia.org/wiki/Most_vexing_parse).

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

Тем не менее можно использовать набор списков инициализаторов для инициализации массива объектов поле:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Дополнительные сведения см. в разделе [инициализаторы](initializers.md).

## <a name="copy_and_move_constructors"></a> Конструкторы копии

Объект *конструктор копии* инициализирует объект путем копирования значения членов из объекта того же типа. Если все простые типы, такие как скалярные значения членов класса, конструктор копии, создаваемые компилятором достаточно, и вам не нужно определять свои собственные. Если ваш класс требуются более сложные инициализации, необходимо реализовать конструктор пользовательских копий. Например если член класса является указателем затем необходимо определить конструктор копии, чтобы выделить новую память и скопируйте соответствующие значения с другой стороны, на который указывает на объект. Конструктор копии, создаваемые компилятором просто копирует указатель, таким образом, чтобы по-прежнему новый указатель указывает на другого расположение в памяти.

Конструктор копии может иметь одно из этих сигнатур:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

При определении конструктора копии, следует также определить оператор присваивания копированием (=). Дополнительные сведения см. в разделе [назначения](assignment.md) и [конструкторы копии и операторы присваивания копий](copy-constructors-and-copy-assignment-operators-cpp.md).

Вы можете запретить копируемых путем определения конструктора копии как удаленный объект:

```cpp
    Box (const Box& other) = delete;
```

Попытка скопировать объект создается ошибка *C2280: попытка ссылки на удаленную функцию*.

## <a name="move_constructors"></a> Конструкторы перемещения

Объект *конструктор перемещения* — это специальная функция-член, перемещает владения данными существующий объект в переменной без копирования исходных данных. Он принимает в качестве первого параметра ссылку rvalue и любые дополнительные параметры должны иметь значения по умолчанию. Конструкторы перемещения может значительно увеличить эффективность программы при передаче больших объектов. Конструктор перемещения принимает ссылку rvalue в качестве первого параметра. Другие параметры должны иметь значения по умолчанию.

```cpp
Box(Box&& other);
```

Компилятор выбирает конструктор перемещения в определенных ситуациях, где объект инициализирован другим объектом того же типа и больше не требуется уничтожить ресурсы. Следующий пример отображается один случай, если конструктор перемещения выбрана при разрешении перегрузки. Переменная *поле* возвращаемые get_Box() является *xvalue* (срок действия которых истекает значение) которого выходят из области видимости. Чтобы предоставить мотивация для этого примера, давайте поле больших вектор строк, представляющих его содержимое. Вместо копирования вектора и строк, конструктор перемещения «захватывает» его с истекающим сроком действия значение «поля», чтобы вектора теперь принадлежит новый объект. Вызов `std::move` является достаточно, поскольку оба `vector` и `string` классы реализуют собственные конструкторы перемещения.

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
    void Get_Contents()
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
    b2.Get_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

Если класс не определен конструктор перемещения, компилятор создает неявные один, если не конструктор копии объявлен пользователя, оператор присваивания копии, оператор присваивания перемещения или деструктора. Если определен конструктор без явной или неявной перемещения, операции, которые в противном случае будет использовать конструктор перемещения используйте конструктор копии. Если класс объявляет конструктор перемещения или оператор присваивания перемещения, конструктор копий неявно объявленную определен как удаленный.

Конструктор перемещения неявно объявленную определяется как удаленные, если все члены, которые относятся к типам классов, не хватает деструктор или компилятор не может определить, какой конструктор, используемый для операции перемещения.

Дополнительные сведения о способах создания не тривиальный конструктор перемещения см. в разделе [конструкторы перемещения и операторы присваивания перемещения (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly_defaulted_and_deleted_constructors"></a> Явно заданные и удаленные конструкторы

Вы можете явно *по умолчанию* конструкторы копии, конструкторы по умолчанию, конструкторы перемещения, операторы присваивания копий, перемещения, операторы присваивания и деструкторы. Вы можете явно *удалить* все специальные функции-члены.

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

Дополнительные сведения см. в разделе [явно установленные по умолчанию и удаленные функции](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr_constructors"></a> конструкторы constexpr

Конструктор может быть объявлен как [constexpr](constexpr-cpp.md) Если

- Это либо объявлен как установленные по умолчанию, иначе он удовлетворяет всем условиям для [функции constexpr](constexpr-cpp.md#constexpr_functions) в целом;
- класс имеет виртуальных базовых классов;
- Каждый из параметров является [типа литерала](trivial-standard-layout-and-pod-types.md#literal_types);
- текст не является блоком function try;
- инициализируются все нестатические данные-члены и вложенные объекты базового класса;
- Если класс (a) является объединением, наличие variant членов или (б) имеет анонимные объединения, инициализируется только один из членов объединения;
- Каждый член нестатических данных типа класса и все вложенные объекты базовых классов имеет конструктора constexpr

## <a name="init_list_constructors"></a> Конструкторов списка инициализаторов

Если конструктор принимает [std::initializer_list\<T\> ](../standard-library/initializer-list-class.md) как ее параметр и других параметров, иметь аргументы по умолчанию, этот конструктор будет выбран в разрешении перегрузки при класса экземпляры через прямой инициализации. Объект initializer_list можно использовать для инициализации любого члена, который может принять его. Предположим, например, класс поле (описано выше) имеет `std::vector<string>` член `m_contents`. Можно предоставить конструктор, подобный следующему:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

А затем создать поле объекты выглядят следующим образом:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> Явные конструкторы

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

В некоторых случаях подобные преобразования могут быть полезны, однако чаще всего они могут привести к незаметным, но серьезным ошибкам в вашем коде. Как правило, следует использовать **явные** ключевое слово в конструктор (и определяемые пользователем операторы), чтобы избежать подобных неявных преобразований типа:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Когда конструктор является явным, эта строка вызывает ошибку компилятора: `ShippingOrder so(42, 10.8);`.  Дополнительные сведения см. в разделе [заданных пользователем преобразований типа](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Порядок сборки

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

Выходные данные этого кода:

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Конструктор производного класса всегда вызывает конструктор базового класса, чтобы перед выполнением любых дополнительных операций иметь в своем распоряжении полностью созданные базовые классы. Конструкторы базовых классов вызываются в порядке наследования — например, если `ClassA` является производным от `ClassB`, который является производным от `ClassC`, `ClassC` конструктор вызывается во-первых, то `ClassB` конструктор, а затем `ClassA` конструктор.

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

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Конструкторы классов с множественным наследованием

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

## <a name="virtual_functions_in_constructors"></a> Виртуальные функции в конструкторах

Рекомендуется соблюдать осторожность при вызове виртуальных функций в конструкторах. Поскольку конструктор базового класса всегда вызывается перед конструктором производного класса, функция, вызываемая в конструкторе базового класса, является версией базового, а не производного класса. В следующем примере создание объекта `DerivedClass` приводит к выполнению реализации объекта `BaseClass` функции `print_it()` перед тем, как конструктор `DerivedClass` вызовет выполнение реализации `DerivedClass``print_it()`:

```cpp
#include <iostream>
using namespace std;

class BaseClass{
public:
    BaseClass(){
        print_it();
    }
    virtual void print_it() {
        cout << "BaseClass print_it" << endl;
    }
};

class DerivedClass : public BaseClass {
public:
    DerivedClass() {
        print_it();
    }
    virtual void print_it(){
        cout << "Derived Class print_it" << endl;
    }
};

int main() {

    DerivedClass dc;
}
```

Выходные данные этого кода:

```Output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> Делегирование конструкторов

Объект *делегирующий конструктор* вызывает другой конструктор в том же классе для выполнения некоторых операций инициализации. Это полезно в тех случаях, когда у вас есть несколько конструкторов, обладающих выполняют одинаковые функции. Можно написать основного приложения логики в один конструктор и вызвать его от других. В следующем примере тривиальным Box(int) делегирует Box(int,int,int) результатов своей работы:

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

Объект, созданный конструкторами, полностью инициализируется сразу после выполнения любого конструктора. Дополнительные сведения см. в разделе [единообразная инициализация и делегирование конструкторов](../cpp/uniform-initialization-and-delegating-constructors.md).

## <a name="inheriting_constructors"></a> Наследование конструкторов (C ++ 11)

Производный класс может наследовать конструкторы от прямого базового класса с помощью **с помощью** объявление, как показано в следующем примере:

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

**Visual Studio 2017 версии 15.7 и выше**: **С помощью** инструкции в **/std: c ++ 17** режим переводит в область видимости все конструкторы из базового класса, кроме тех, которые имеют одинаковую сигнатуру с конструкторов в производном классе. Обычно, если в производном классе не объявляются новые данные-члены или конструкторы, оптимальным решением будет использовать наследуемые конструкторы. См. также [улучшения в Visual Studio 2017 версии 15.7](../overview/cpp-conformance-improvements.md#improvements_157).

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

## <a name="constructors_in_composite_classes"></a> Конструкторы и составные классы

Классы, содержащие члены типа класса, называются *составные классы*. При создании члена типа класса составного класса конструктор вызывается перед собственным конструктором класса. Если у содержащегося класса нет конструктора по умолчанию, необходимо использовать список инициализации в конструкторе составного класса. В предыдущем примере `StorageBox` при присвоении типу переменной-члена `m_label` нового класса `Label` необходимо вызвать конструктор базового класса и инициализировать переменную `m_label` в конструкторе `StorageBox`:

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
