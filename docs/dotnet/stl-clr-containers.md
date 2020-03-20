---
title: Контейнеры STL/CLR
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
ms.openlocfilehash: bfdbbeb735f98f77046790e21c19dd2d21b9d5c6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544841"
---
# <a name="stlclr-containers"></a>Контейнеры STL/CLR

Библиотека STL/CLR состоит из контейнеров, которые похожи на те, которые находятся в C++ стандартной библиотеке, но выполняются в управляемой среде .NET Framework. Она не является актуальной с реальной C++ стандартной библиотекой и поддерживается для поддержки прежних версий.

В этом документе представлен обзор контейнеров STL/CLR, таких как требования к элементам контейнера, типы элементов, которые можно вставлять в контейнеры, а также проблемы владения элементами в контейнерах. Там, где это необходимо, упоминаются различия между собственной C++ стандартной библиотекой и STL/CLR.

## <a name="requirements-for-container-elements"></a>Требования для элементов контейнеров

Все элементы, вставленные в контейнеры STL/CLR, должны соблюдать определенные рекомендации. Дополнительные сведения см. в разделе [требования для элементов контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md).

## <a name="valid-container-elements"></a>Допустимые элементы контейнера

Контейнеры STL/CLR могут содержать один из двух типов элементов:

- Дескрипторы ссылочных типов.

- Ссылочные типы.

- Неупакованные типы значений.

Упакованные типы значений нельзя вставлять в любые контейнеры STL/CLR.

### <a name="handles-to-reference-types"></a>Дескрипторы ссылочных типов

Можно вставить маркер в ссылочный тип в контейнер STL/CLR. Обработчик C++ , предназначенный для среды CLR, аналогичен указателю в собственном C++виде. Дополнительные сведения см. [в разделе Оператор Handle to Object (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md).

#### <a name="example"></a>Пример

В следующем примере показано, как вставить маркер в объект Employee в [cliext:: Set](../dotnet/set-stl-clr.md).

```cpp
// cliext_container_valid_reference_handle.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
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

Также можно вставить ссылочный тип (а не обработчик в ссылочный тип) в контейнер STL/CLR. Основное отличие заключается в том, что при удалении контейнера ссылочных типов деструктор вызывается для всех элементов внутри этого контейнера. В контейнере дескрипторов ссылочных типов деструкторы для этих элементов вызываться не будут.

#### <a name="example"></a>Пример

В следующем примере показано, как вставить объект Employee в `cliext::set`.

```cpp
// cliext_container_valid_reference.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
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

### <a name="unboxed-value-types"></a>Неупакованные типы значений

Можно также вставить неупакованный тип значения в контейнер STL/CLR. Неупакованный тип значения — это тип значения, который не был *упакован* в ссылочный тип.

Элемент типа значения может быть одним из стандартных типов значений, таких как `int`, или может быть определяемым пользователем типом значения, например `value class`. Дополнительные сведения см. в разделе [классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md) .

#### <a name="example"></a>Пример

Следующий пример изменяет первый пример, делая тип значения классом Employee. Затем этот тип значения вставляется в `cliext::set` точно так же, как в первом примере.

```cpp
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

При попытке вставить маркер в тип значения в контейнер создается [Ошибка компилятора C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) .

### <a name="performance-and-memory-implications"></a>Влияние производительности и памяти

При определении необходимости использования дескрипторов для ссылочных типов или типов значений в качестве элементов контейнера необходимо учитывать несколько факторов. Если вы решили использовать типы значений, помните, что копия элемента выполняется каждый раз при вставке элемента в контейнер. Для небольших объектов это не должно быть проблемой, но если вставляемые объекты велики, производительность может снизиться. Кроме того, при использовании типов значений невозможно одновременно сохранить один элемент в нескольких контейнерах, так как каждый контейнер будет иметь собственную копию элемента.

Если вместо этого вы решили использовать дескрипторы для ссылочных типов, производительность может увеличиться из-за необязательного создания копии элемента при его вставке в контейнер. Кроме того, в отличие от типов значений, один и тот же элемент может существовать в нескольких контейнерах. Однако если вы решили использовать дескрипторы, необходимо убедиться, что дескриптор является допустимым, а объект, на который он ссылается, не был удален в другой части программы.

## <a name="ownership-issues-with-containers"></a>Проблемы владения контейнерами

Контейнеры в STL/CLR работают в семантике значений. Каждый раз при вставке элемента в контейнер вставляется копия этого элемента. Если требуется получить семантику, подобную ссылке, можно вставить в объект маркер, а не сам объект.

При вызове метода Clear или Erase контейнера объектов обработки объекты, на которые ссылаются дескрипторы, не освобождаются из памяти. Необходимо либо явно удалить объект, либо, поскольку эти объекты находятся в управляемой куче, разрешить сборщику мусора освободить память после того, как она определит, что объект больше не используется.

## <a name="see-also"></a>См. также:

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
