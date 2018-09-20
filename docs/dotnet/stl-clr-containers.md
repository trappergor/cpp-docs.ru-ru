---
title: Контейнеры STL/CLR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 40fe43accafb6fa9e217f5d7835d7533e7674e72
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418558"
---
# <a name="stlclr-containers"></a>Контейнеры STL/CLR

Библиотека STL/CLR имеет те же контейнеры, найденные в стандартной библиотеке C++, но запускается в управляемой среде платформы .NET Framework. Если вы уже знакомы со стандартной библиотекой C++, STL/CLR — это лучший способ продолжать использовать свои навыки, которые вы уже разработали при обновлении кода к целевому объекту общеязыковой среды выполнения (CLR).

Этот документ предоставляет обзор контейнеров STL/CLR, например требования к элементам контейнера, типы элементов, можно вставить в контейнерах, что владение проблемы с элементами в контейнерах. При необходимости указаны различия между собственного стандартной библиотеки C++ и STL/CLR.

## <a name="requirements-for-container-elements"></a>Требования для элементов контейнеров

Все элементы, вставленные в контейнеры стандартной библиотеки C++ должен соответствовать определенным правилам. Дополнительные сведения см. в разделе [требования к элементам контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md).

## <a name="valid-container-elements"></a>Недопустимый контейнер элементов

Контейнеры STL/CLR могут содержать один из двух типов элементов:

- Обрабатывает для ссылки на типы.

- Ссылочные типы.

- Упакованных типов значений.

Упакованные типы значений нельзя вставлять в любой из контейнеров STL/CLR.

### <a name="handles-to-reference-types"></a>Дескрипторы для ссылочных типов

Дескриптор ссылочного типа можно вставить в контейнер STL/CLR. Дескриптор в C++, предназначенной для среды CLR является аналогом указатель на традиционном C++. Дополнительные сведения см. в разделе [оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).

#### <a name="example"></a>Пример

Следующий пример демонстрирует вставку дескриптор объекта сотрудника в [cliext::set](../dotnet/set-stl-clr.md).

```
// cliext_container_valid_reference_handle.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // C++ Standard Library containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All C++ Standard Library containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All C++ Standard Library containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All C++ Standard Library containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee^ empl1419 = gcnew Employee();
    empl1419->Name = L"Darin Lockert";
    empl1419->EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee^>^ emplSet = gcnew set<Employee^>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="reference-types"></a>Ссылочные типы

Это также можно вставить в контейнер STL/CLR ссылочного типа (а не дескриптор ссылочного типа). Основное различие состоит в том, что при удалении контейнера ссылочных типов, деструктор вызывается для всех элементов внутри контейнера. В контейнере, который обрабатывает запросы к ссылочным типам будет не вызваны деструкторы для этих элементов.

#### <a name="example"></a>Пример

Следующий пример демонстрирует вставку объекта сотрудника в `cliext::set`.

```
// cliext_container_valid_reference.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // C++ Standard Library containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All C++ Standard Library containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All C++ Standard Library containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All C++ Standard Library containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="unboxed-value-types"></a>Упакованных типов значений

Вы также можете вставить в контейнер STL/CLR неупакованный тип значения. Неупакованный тип значения является типом значения, которое не было *упакованных* в ссылочный тип.

Элемент типа значение может быть один из типов стандартное значение, например `int`, или он может быть типом значения, определяемые пользователем, например `value class`. Дополнительные сведения см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)

#### <a name="example"></a>Пример

В следующем примере изменяется первый пример, сделав сотрудника класса типом значения. Этот тип значение затем вставляется в `cliext::set` так же, как и в первом примере.

```
// cliext_container_valid_valuetype.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

value class Employee
{
public:
    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl.EmployeeNumber, empl.Name);
    }

    return 0;
}
```

Если попытаться вставить в контейнер, дескриптор типа значения [Ошибка компилятора C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) создается.

### <a name="performance-and-memory-implications"></a>Производительность и ограничения памяти

Следует учесть несколько факторов, определяя, следует ли использовать маркеры для ссылок на типы или типы значений как элементы контейнера. Если вы решили использовать типы значений, помните, что будет создана копия элемента каждый раз, когда элемент вставляется в контейнер. Для небольших объектов это не должно быть проблемой, но если большие объекты вставкой, может наблюдаться снижение производительности. Кроме того Если вы используете типы значений, вы не сможете сохранить один элемент в несколько контейнеров в то же время, так как каждый контейнер будет иметь собственную копию элемента.

Если вы решили использовать маркеры для ссылки на типы, вместо этого, производительность может возрасти, так как нет необходимости для создания копии элемента при его вставке в контейнере. Кроме того в отличие от с типами значений, и тот же элемент может существовать в нескольких контейнерах. Тем не менее если вы решили использовать маркеры, необходимо соблюдать осторожность, чтобы убедиться, что дескриптор является допустимым и что он ссылается на объект не был удален в другом месте в программе.

## <a name="ownership-issues-with-containers"></a>Проблемы владения с контейнерами

Контейнеры STL/CLR работать на семантику значений. Каждый раз при вставке элемента в контейнер, вставляется копию этого элемента. Если вы хотите получить ссылку с семантикой, можно вставить дескриптор для объекта, а не сам объект.

Когда вызов в незашифрованном виде, или удалить метод контейнер объектов дескриптора, объекты, на которые указывают дескрипторы не освобождаются из памяти. Вам необходимо явно удалить объект, или, так как эти объекты находятся в управляемой куче, позволяя сборщику мусора для освобождения памяти, в том случае, когда он определяет, что объект больше не используется.

## <a name="see-also"></a>См. также

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)