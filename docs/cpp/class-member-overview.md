---
title: Обзор членов класса
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: 02c5593d9fb5e72ee6b398c9637397ab26c9f3f2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229068"
---
# <a name="class-member-overview"></a>Обзор членов класса

Класс или структура состоит из членов. Действия, выполняемые классом, выполняются с помощью его функций-членов. Состояние, в котором он находится, хранится в его элементах данных. Инициализация членов выполняется конструкторами, а очистка, например освобождение памяти и освобождение ресурсов, выполняется деструкторами. В C++ 11 и более поздних версиях элементы данных можно (и обычно следует) инициализировать при объявлении.

## <a name="kinds-of-class-members"></a>Виды членов класса

Ниже приведен полный список категорий членов.

- [Специальные функции элементов](special-member-functions.md).

- [Общие сведения о функциях элементов](overview-of-member-functions.md).

- [Элементы данных](static-members-cpp.md) , включая встроенные типы и другие определяемые пользователем типы.

- Операторы

- [Вложенные объявления классов](nested-class-declarations.md) и.)

- [Объединения](unions.md)

- [Перечисления](../cpp/enumerations-cpp.md).

- [Битовые поля](../cpp/cpp-bit-fields.md).

- [Друзья](../cpp/friend-cpp.md).

- [Псевдонимы и определения типов](../cpp/aliases-and-typedefs-cpp.md).

    > [!NOTE]
    >  Дружественные объекты включены в этот список, поскольку они содержатся в объявлении класса. Однако они не являются истинными членами класса, поскольку они не находятся в области класса.

## <a name="example-class-declaration"></a>Пример объявления класса

В следующем примере показано объявление простого класса.

```cpp
// TestRun.h

class TestRun
{
    // Start member list.

    //The class interface accessible to all callers.
public:
    // Use compiler-generated default constructor:
    TestRun() = default;
    // Don't generate a copy constructor:
    TestRun(const TestRun&) = delete;
    TestRun(std::string name);
    void DoSomething();
    int Calculate(int a, double d);
    virtual ~TestRun();
    enum class State { Active, Suspended };

    // Accessible to this class and derived classes only.
protected:
    virtual void Initialize();
    virtual void Suspend();
    State GetState();

    // Accessible to this class only.
private:
    // Default brace-initialization of instance members:
    State _state{ State::Suspended };
    std::string _testName{ "" };
    int _index{ 0 };

    // Non-const static member:
    static int _instances;
    // End member list.
};

// Define and initialize static member.
int TestRun::_instances{ 0 };
```

## <a name="member-accessibility"></a>Доступность членов

Члены класса объявляются в списке членов. Список членов класса можно разделить на любое количество **`private`** **`protected`** **`public`** разделов и с помощью ключевых слов, известных как описатели доступа.  Двоеточие **:** должно следовать за спецификатором доступа.  Эти разделы не обязательно должны быть непрерывными, то есть любое из этих ключевых слов может отображаться в списке элементов несколько раз.  Ключевое слово назначает доступ всех членов до следующего описателя доступа или закрывающей фигурной скобки. Дополнительные сведения см. в разделе [Управление доступом к членам (C++)](../cpp/member-access-control-cpp.md).

## <a name="static-members"></a>Статические члены

Элемент данных может быть объявлен как статический, что означает, что все объекты класса имеют доступ к одной и той же его копии. Функция-член может быть объявлена как статическая, в этом случае она может обращаться только к статическим членам данных класса (и не имеет *этого* указателя). Дополнительные сведения см. в разделе [статические элементы данных](../cpp/static-members-cpp.md).

## <a name="special-member-functions"></a>Специальные функции-члены

Специальные функции-члены — это функции, которые автоматически создаются компилятором, если не указаны в исходном коде.

1. Конструктор по умолчанию.

1. Конструктор копии

1. **(C++ 11)** Конструктор перемещения

1. Оператор присваивания копированием

1. **(C++ 11)** Оператор присваивания перемещения

1. Деструктор

Дополнительные сведения см. в разделе [специальные функции элементов](../cpp/special-member-functions.md).

## <a name="memberwise-initialization"></a>Поэлементная инициализация

В C++ 11 и более поздних версиях деклараторы нестатических членов могут содержать инициализаторы.

```cpp
class CanInit
{
public:
    long num {7};       // OK in C++11
    int k = 9;          // OK in C++11
    static int i = 9; // Error: must be defined and initialized
                      // outside of class declaration.

    // initializes num to 7 and k to 9
    CanInit(){}

    // overwrites original initialized value of num:
    CanInit(int val) : num(val) {}
};
int main()
{
}
```

Если в конструкторе члену присваивается значение, оно заменяет то значение, каким он был инициализирован при объявлении.

Существует только один общий экземпляр статических данных-членов для всех объектов заданного типа классов. Статические данные-члены необходимо определить и инициализировать в области файлов. (Дополнительные сведения о статических элементах данных см. в разделе [статические элементы данных](../cpp/static-members-cpp.md).) В следующем примере показано, как выполнить эти инициализации:

```cpp
// class_members2.cpp
class CanInit2
{
public:
    CanInit2() {} // Initializes num to 7 when new objects of type
                 //  CanInit are created.
    long     num {7};
    static int i;
    static int j;
};

// At file scope:

// i is defined at file scope and initialized to 15.
// The initializer is evaluated in the scope of CanInit.
int CanInit2::i = 15;

// The right side of the initializer is in the scope
// of the object being initialized
int CanInit2::j = i;
```

> [!NOTE]
> Имя класса, `CanInit2`, должно предшествовать `i`, чтобы указать, что `i` определяется как член класса `CanInit2`.

## <a name="see-also"></a>См. также статью

[Классы и структуры](../cpp/classes-and-structs-cpp.md)
