---
title: union
description: Описание стандартного union class типа C++ и ключевого слова, его использования и ограничений.
ms.date: 08/18/2020
f1_keywords:
- union_cpp
helpviewer_keywords:
- class type [C++], union as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
no-loc:
- union
- struct
- enum
- class
- static
ms.openlocfilehash: a4dc07df5e7858dffe62478509ee1d8dc759ce96
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722184"
---
# `union`

> [!NOTE]
> В C++ 17 и более поздних версиях `std::variant` class — это строго типизированная альтернатива для union .

**`union`**— Это определяемый пользователем тип, в котором все члены совместно используют одно и то же расположение в памяти. Это определение означает, что в любой момент времени объект union может содержать не более одного объекта из списка членов. Кроме того, это означает, что независимо от количества элементов union у пользователя всегда используется достаточно памяти для хранения самого большого элемента.

unionМожет быть полезен для экономии памяти при наличии большого количества объектов и ограниченной памяти. Тем не менее, union для правильной работы требуется дополнительные меры. Вы несете ответственность за обеспечение доступа к тому же назначенному Вами члену. Если какие-либо типы членов имеют нетривиальный Con struct или, то необходимо написать дополнительный код для явного struct и уничтожения этого члена. Прежде чем использовать union , определите, может ли проблема, которую вы пытаетесь решить, лучше выражаться с помощью базового class и производного class типов.

## <a name="syntax"></a>Синтаксис

> **`union`***`tag`* <sub>неявное согласие</sub> **`{`** *`member-list`***`};`**

### <a name="parameters"></a>Параметры

*`tag`*<br/>
Имя типа, присвоенное union .

*`member-list`*<br/>
Элементы, которые union может содержать.

## <a name="declare-a-no-locunion"></a>Объявите элемент union

Начните объявление объекта с union помощью **`union`** ключевого слова и заключите список членов в фигурные скобки:

```cpp
// declaring_a_union.cpp
union RecordType    // Declare a simple union type
{
    char   ch;
    int    i;
    long   l;
    float  f;
    double d;
    int *int_ptr;
};

int main()
{
    RecordType t;
    t.i = 5; // t holds an int
    t.f = 7.25; // t now holds a float
}
```

## <a name="use-a-no-locunion"></a>Используйте union

В предыдущем примере любой код, обращающийся к потребностям, должен union понять, какой элемент содержит данные. Наиболее распространенное решение этой проблемы называется *размеченные union *. Он заключает union в struct и включает enum член, указывающий тип элемента, который в настоящее время хранится в union . В следующем примере демонстрируется использование основного подхода:

```cpp
#include <queue>

using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    int StationId;
    time_t time;
    double current;
    double max;
    double min;
};

struct WindData
{
    int StationId;
    time_t time;
    int speed;
    short direction;
};

struct Input
{
    WeatherDataType type;
    union
    {
        TempData temp;
        WindData wind;
    };
};

// Functions that are specific to data types
void Process_Temp(TempData t) {}
void Process_Wind(WindData w) {}

void Initialize(std::queue<Input>& inputs)
{
    Input first;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    Input second;
    second.type = WeatherDataType::Wind;
    second.wind = { 204, 1418859354, 14, 27 };
    inputs.push(second);
}

int main(int argc, char* argv[])
{
    // Container for all the data records
    queue<Input> inputs;
    Initialize(inputs);
    while (!inputs.empty())
    {
        Input const i = inputs.front();
        switch (i.type)
        {
        case WeatherDataType::Temperature:
            Process_Temp(i.temp);
            break;
        case WeatherDataType::Wind:
            Process_Wind(i.wind);
            break;
        default:
            break;
        }
        inputs.pop();

    }
    return 0;
}
```

В предыдущем примере элемент в не union `Input` struct имеет имени, поэтому он называется *анонимным* union . Доступ к его членам можно получить напрямую, как если бы они были членами класса struct . Дополнительные сведения об использовании анонимных служб union см. в разделе [anonymous union ](#anonymous_unions) .

В предыдущем примере показана проблема, которую можно также решить с помощью class типов, производных от общего базового класса class . Код можно разветвление на основе типа среды выполнения каждого объекта в контейнере. Код может быть проще в обслуживании и понимании, но он также может быть медленнее, чем при использовании union . Кроме того, с union можно хранить несвязанные типы. unionПозволяет динамически изменять тип хранимого значения, не изменяя тип union самой переменной. Например, можно создать разнородный массив `MyUnionType` , элементы которого хранят различные значения различных типов.

В примере несложно неверно `Input` struct . Пользователь должен правильно использовать дискриминатор для доступа к члену, содержащему данные. Вы можете защититься от неправильного использования, сделав union **`private`** и предоставляя специальные функции доступа, как показано в следующем примере.

## <a name="unrestricted-no-locunion-c11"></a>Без ограничений union (c++ 11)

В C++ 03 и более ранних версий объект union может содержать не являющиеся static данными элементы, имеющие class тип, если тип не имеет пользователя Con struct OR, de struct or или операторы присваивания. В C++11 эти ограничения отсутствуют. Если включить такой элемент в union , компилятор автоматически помечает все специальные функции-члены, которые не предоставляются пользователем как **`deleted`** . Если объект union является анонимным union внутри class или struct , то любые специальные функции-члены объекта class или struct , не указанные пользователем, помечаются как **`deleted`** . В следующем примере показано, как справиться с этим вариантом. Один из членов union имеет член, который требует этой особой обработки:

```cpp
// for MyVariant
#include <crtdbg.h>
#include <new>
#include <utility>

// for sample objects and output
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct A
{
    A() = default;
    A(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    //...
};

struct B
{
    B() = default;
    B(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    vector<int> vec;
    // ...
};

enum class Kind { None, A, B, Integer };

#pragma warning (push)
#pragma warning(disable:4624)
class MyVariant
{
public:
    MyVariant()
        : kind_(Kind::None)
    {
    }

    MyVariant(Kind kind)
        : kind_(kind)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A();
            break;
        case Kind::B:
            new (&b_) B();
            break;
        case Kind::Integer:
            i_ = 0;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    ~MyVariant()
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            a_.~A();
            break;
        case Kind::B:
            b_.~B();
            break;
        case Kind::Integer:
            break;
        default:
            _ASSERT(false);
            break;
        }
        kind_ = Kind::None;
    }

    MyVariant(const MyVariant& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(other.a_);
            break;
        case Kind::B:
            new (&b_) B(other.b_);
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    MyVariant(MyVariant&& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(move(other.a_));
            break;
        case Kind::B:
            new (&b_) B(move(other.b_));
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
    }

    MyVariant& operator=(const MyVariant& other)
    {
        if (&other != this)
        {
            switch (other.kind_)
            {
            case Kind::None:
                this->~MyVariant();
                break;
            case Kind::A:
                *this = other.a_;
                break;
            case Kind::B:
                *this = other.b_;
                break;
            case Kind::Integer:
                *this = other.i_;
                break;
            default:
                _ASSERT(false);
                break;
            }
        }
        return *this;
    }

    MyVariant& operator=(MyVariant&& other)
    {
        _ASSERT(this != &other);
        switch (other.kind_)
        {
        case Kind::None:
            this->~MyVariant();
            break;
        case Kind::A:
            *this = move(other.a_);
            break;
        case Kind::B:
            *this = move(other.b_);
            break;
        case Kind::Integer:
            *this = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
        return *this;
    }

    MyVariant(const A& a)
        : kind_(Kind::A), a_(a)
    {
    }

    MyVariant(A&& a)
        : kind_(Kind::A), a_(move(a))
    {
    }

    MyVariant& operator=(const A& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(a);
        }
        else
        {
            a_ = a;
        }
        return *this;
    }

    MyVariant& operator=(A&& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(move(a));
        }
        else
        {
            a_ = move(a);
        }
        return *this;
    }

    MyVariant(const B& b)
        : kind_(Kind::B), b_(b)
    {
    }

    MyVariant(B&& b)
        : kind_(Kind::B), b_(move(b))
    {
    }

    MyVariant& operator=(const B& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(b);
        }
        else
        {
            b_ = b;
        }
        return *this;
    }

    MyVariant& operator=(B&& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(move(b));
        }
        else
        {
            b_ = move(b);
        }
        return *this;
    }

    MyVariant(int i)
        : kind_(Kind::Integer), i_(i)
    {
    }

    MyVariant& operator=(int i)
    {
        if (kind_ != Kind::Integer)
        {
            this->~MyVariant();
            new (this) MyVariant(i);
        }
        else
        {
            i_ = i;
        }
        return *this;
    }

    Kind GetKind() const
    {
        return kind_;
    }

    A& GetA()
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    const A& GetA() const
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    B& GetB()
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    const B& GetB() const
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    int& GetInteger()
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

    const int& GetInteger() const
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

private:
    Kind kind_;
    union
    {
        A a_;
        B b_;
        int i_;
    };
};
#pragma warning (pop)

int main()
{
    A a(1, "Hello from A");
    B b(2, "Hello from B");

    MyVariant mv_1 = a;

    cout << "mv_1 = a: " << mv_1.GetA().name << endl;
    mv_1 = b;
    cout << "mv_1 = b: " << mv_1.GetB().name << endl;
    mv_1 = A(3, "hello again from A");
    cout << R"aaa(mv_1 = A(3, "hello again from A"): )aaa" << mv_1.GetA().name << endl;
    mv_1 = 42;
    cout << "mv_1 = 42: " << mv_1.GetInteger() << endl;

    b.vec = { 10,20,30,40,50 };

    mv_1 = move(b);
    cout << "After move, mv_1 = b: vec.size = " << mv_1.GetB().vec.size() << endl;

    cout << endl << "Press a letter" << endl;
    char c;
    cin >> c;
}
```

Объект union не может хранить ссылку. Объект union также не поддерживает наследование. Это означает, что нельзя использовать в union качестве основы class или наследовать от другого class или иметь виртуальные функции.

## <a name="initialize-a-no-locunion"></a>Инициализация union

Можно объявить и инициализировать union в той же инструкции, назначив выражение, заключенное в фигурные скобки. Выражение вычисляется и присваивается первому полю union .

```cpp
#include <iostream>
using namespace std;

union NumericType
{
    short       iValue;
    long        lValue;
    double      dValue;
};

int main()
{
    union NumericType Values = { 10 };   // iValue = 10
    cout << Values.iValue << endl;
    Values.dValue = 3.1416;
    cout << Values.dValue << endl;
}
/* Output:
10
3.141600
*/
```

Объект `NumericType` union упорядочивается в память (по принципу концептуально), как показано на следующем рисунке.

![Хранение данных в числовом типе::: No-Loc (Union):::](../cpp/media/vc38ul1.png "Хранение данных в Нумериктипе::: No-Loc (Union):::") <br/>
Хранение данных в `NumericType`union

## <a name="anonymous-no-locunion"></a><a name="anonymous_unions"></a> Подключившихся union

Анонимный объект union объявлен без *`class-name`* или *`declarator-list`* .

> **`union  {`**  *`member-list`*  **`}`**

Имена, объявленные в анонимном режиме union , используются непосредственно, как и переменные, не являющиеся членами. Это означает, что имена, объявленные в анонимном режиме, union должны быть уникальными в окружающей области.

На анонимность union распространяются следующие дополнительные ограничения:

- Если он объявлен в области видимости файла или пространства имен, он также должен быть объявлен как **`static`** .

- Он может иметь только **`public`** члены; Having **`private`** и **`protected`** члены анонимно union создают ошибки.

- Он не может содержать функции элементов.

## <a name="see-also"></a>См. также

[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[`class`](../cpp/class-cpp.md)<br/>
[`struct`](../cpp/struct-cpp.md)
