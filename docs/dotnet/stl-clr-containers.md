---
title: "Контейнеры STL/CLR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1b8aa8ef5b1425d4aa41b1811dca5ec5d56acd1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-containers"></a>Контейнеры STL/CLR
Библиотека STL/CLR имеет те же контейнеры, которые находятся в стандартной библиотеке C++, но запускается в управляемой среде .NET Framework. Если вы уже знакомы с стандартной библиотеки C++, STL/CLR является лучшим способом для продолжения использования навыков, которые вы уже разработали при обновлении кода в целевой среде (CLR).  
  
 Этот документ предоставляет обзор контейнеры STL/CLR, такие как требования к элементам контейнера, типы элементов, которые можно вставлять в контейнеры, что владение проблемы с элементами в контейнерах. При необходимости упоминаются отличия собственного стандартной библиотеки C++ и STL/CLR.  
  
## <a name="requirements-for-container-elements"></a>Требования для элементов контейнеров  
 Все элементы, вставленные в контейнеры стандартной библиотеки C++ должен подчиняться определенным правилам. Дополнительные сведения см. в разделе [требования к элементам контейнера STL/CLR](../dotnet/requirements-for-stl-clr-container-elements.md).  
  
## <a name="valid-container-elements"></a>Недопустимый контейнер элементов  
 Контейнеры STL/CLR может содержать два типа элементов:  
  
-   Обрабатывает для ссылки на типы.  
  
-   Ссылочные типы.  
  
-   Упакованных типов значений.  
  
 Упакованные типы значений нельзя вставить в любой из контейнеров STL/CLR.  
  
### <a name="handles-to-reference-types"></a>Дескрипторы для ссылочных типов  
 Дескриптор ссылочного типа можно вставить в контейнер STL/CLR. Дескриптор в C++, предназначенной для среды CLR, аналогичен указатель в неуправляемом коде C++. Дополнительные сведения см. в разделе [оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### <a name="example"></a>Пример  
 Следующий пример иллюстрирует порядок вставки дескриптор объекта сотрудника в [cliext::set](../dotnet/set-stl-clr.md).  
  
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
 Можно также вставить ссылочного типа (а не дескриптор ссылочного типа) в контейнер STL/CLR. Основное различие состоит в том, что при удалении контейнера ссылочных типов, деструктор вызывается для всех элементов внутри контейнера. В контейнере дескрипторы для ссылочных типов может не вызваны деструкторы для этих элементов.  
  
#### <a name="example"></a>Пример  
 Следующий пример иллюстрирует порядок вставки объекта сотрудника в `cliext::set`.  
  
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
 Вы также можете вставить неупакованный тип значения в контейнер STL/CLR. Неупакованный тип значения является типом значения, который не был *упаковка-преобразование* в ссылочный тип.  
  
 Элемент типа значение может быть один из типов стандартное значение, например `int`, или он может быть типом значения, определяемые пользователем, например `value class`. Дополнительные сведения см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### <a name="example"></a>Пример  
 В следующем примере изменяется первый пример, делая сотрудника класс является типом значения. Этот тип значения затем вставляется в `cliext::set` так же, как и в первом примере.  
  
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
  
 При попытке вставить дескриптор типа значения в контейнере, [Ошибка компилятора C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) создается.  
  
### <a name="performance-and-memory-implications"></a>Влияние памяти и производительности  
 Следует учитывать несколько факторов при определении, следует ли использовать дескрипторы для ссылок на типы или типы значений, что элементы контейнера. Если вы решили использовать типы значений, помните, что копия элемента выполняется каждый раз, когда элемент вставляется в контейнер. Для небольших объектов это не должна быть проблемой, но если большие объекты, вставляемые, производительность может снизиться. Кроме того Если вы используете типы значений, невозможно сохранить один элемент в несколько контейнеров в то же время, так как каждый контейнер будет иметь свою собственную копию элемента.  
  
 Если принято решение использовать дескрипторы для вместо ссылки на типы, производительность может возрасти, так как он не требуется для создания копии элемента при его вставке в контейнере. Кроме того в отличие от типа значений элемент с таким же может существовать в разных контейнерах. Тем не менее если вы решили использовать маркеры, вы должны уделить особое внимание убедитесь, что дескриптор действителен, и что объект, который он ссылается на не удалена в другом месте программы.  
  
## <a name="ownership-issues-with-containers"></a>Проблемы владения с контейнерами  
 Контейнеры STL/CLR работать с семантикой значений. Каждый раз при вставке элемента в контейнер, вставляется копии этого элемента. Если вы хотите получить семантику ссылки like, вы можете вставить дескриптор для объекта, а не сам объект.  
  
 При выполняется вызов открытым текстом или удалить контейнер объектов дескриптор метода, объекты, которые указывают дескрипторы не будут освобождены из памяти. Вам необходимо явно удалить объект, или, так как эти объекты находятся в управляемой куче, позволяет сборщику мусора освободить память, когда он определяет, что объект больше не используется.  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)