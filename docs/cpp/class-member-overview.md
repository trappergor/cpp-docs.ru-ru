---
title: Обзор членов класса
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: cb978434707a9a7808b3388fc541ce4e0d996b0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366680"
---
# <a name="class-member-overview"></a>Обзор членов класса

Класс или структура состоит из членов. Действия, выполняемые классом, выполняются с помощью его функций-членов. Состояние, в котором он находится, хранится в его элементах данных. Инициализация членов осуществляется конструкторами, а работы по очистке, такие как освобождение памяти и высвобождение ресурсов, выполняются деструктором. В C++ 11 и более поздних версиях элементы данных можно (и обычно следует) инициализировать при объявлении.

## <a name="kinds-of-class-members"></a>Виды членов класса

Ниже приведен полный список категорий членов.

- [Специальные функции участника](special-member-functions.md).

- [Обзор функций участников](overview-of-member-functions.md).

- [Члены данных,](static-members-cpp.md) включая встроенные типы и другие типы, определенные пользователями.

- Операторы

- [Nested класса деклараций](nested-class-declarations.md) и.)

- [Объединения](unions.md)

- [Цифры](../cpp/enumerations-cpp.md).

- [Полей бита](../cpp/cpp-bit-fields.md).

- [Друзья](../cpp/friend-cpp.md).

- [Прозвища и typedefs](../cpp/aliases-and-typedefs-cpp.md).

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

Члены класса объявляются в списке членов. Список участников класса может быть разделен на любое количество **частных,** **защищенных** и **публичных** разделов с использованием ключевых слов, известных как спецификации доступа.  Толстая **:** кишка: должна следовать спецификатору доступа.  Эти разделы не обязательно должны быть непрерывными, то есть любое из этих ключевых слов может отображаться в списке элементов несколько раз.  Ключевое слово назначает доступ всех членов до следующего описателя доступа или закрывающей фигурной скобки. Для получения более [Member Access Control (C++)](../cpp/member-access-control-cpp.md)подробной информации см.

## <a name="static-members"></a>Статические члены

Элемент данных может быть объявлен как статический, что означает, что все объекты класса имеют доступ к одной и той же его копии. Функция участника может быть объявлена статичной, и в этом случае она может получить доступ только к статическим членам данных класса (и не имеет *этого* указателя). Для получения дополнительной информации [см.](../cpp/static-members-cpp.md)

## <a name="special-member-functions"></a>Специальные функции-члены

Специальные функции-члены — это функции, которые автоматически создаются компилятором, если не указаны в исходном коде.

1. Конструктор по умолчанию.

1. Конструктор копии

1. **(КЗ11)** Перемещение конструктора

1. Оператор присваивания копированием

1. **(КЗ11)** Перемещение оператора назначения

1. Деструктор

Для получения дополнительной информации, см [Специальные функции участника](../cpp/special-member-functions.md).

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

Существует только один общий экземпляр статических данных-членов для всех объектов заданного типа классов. Статические данные-члены необходимо определить и инициализировать в области файлов. (Для получения дополнительной информации о членах статических данных [см.](../cpp/static-members-cpp.md) В следующем примере показано, как выполнить эти инициализации:

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

## <a name="see-also"></a>См. также раздел

[Классы и структуры](../cpp/classes-and-structs-cpp.md)
