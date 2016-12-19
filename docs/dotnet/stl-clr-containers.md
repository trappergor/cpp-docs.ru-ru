---
title: "Контейнеры STL/CLR | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "контейнеры, STL/CLR"
  - "STL/CLR, контейнеры"
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Контейнеры STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека STL\/CLR имеет те же контейнеры, которые находятся в стандартной библиотеке C\+\+ C, но она выполняется в управляемую среду платформы .NET Framework.  Если вы уже знакомы с библиотекой стандартных шаблонов \(STL\), STL\/CLR лучшим способом продолжить использование навыками, уже разработано пока обновление кода к целевому объекту среды CLR \(CLR\).  
  
 В этом документе содержатся общие сведения о контейнеров в STL\/CLR, например требования для элементов\-контейнеров, типов элементов, которые можно добавлять в контейнеры и проблемы владения с элементами в контейнерах.  При необходимости, разница между собственной библиотекой стандартных шаблонов и STL\/CLR упомяните.  
  
## Требования для элементов контейнеров  
 Все элементы, добавленные в контейнеров STL должны подчиняться некоторым рекомендациям.  Для получения дополнительной информации см. [Требования к элементам контейнера STL\/CLR](../Topic/Requirements%20for%20STL-CLR%20Container%20Elements.md).  
  
## Допустимые дочерние элементы  
 Контейнеры STL\/CLR могут содержать один из 2 типов элементов.  
  
-   Дескрипторы к ссылочным типам.  
  
-   Ссылочные типы.  
  
-   Две типы значения.  
  
 Нельзя типы значений упакованные вставкой в любые контейнеры STL\/CLR.  
  
### Дескрипторы к ссылочным типам  
 Можно вставить дескриптор ссылочному типу в контейнер STL\/CLR.  Дескриптор в C\+\+, на которую нацелен CLR аналогичн указатель в собственном C C\+\+.  Для получения дополнительной информации см. [Оператор дескриптора объекта \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### Пример  
 В следующем примере показано, как вставить дескриптор объекта сотрудника в [cliext::set](../dotnet/set-stl-clr.md).  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
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
  
### Ссылочные типы  
 Также можно вставить ссылочный тип \(а не дескриптор ссылочному типу\) в контейнер STL\/CLR.  Основное различие заключается в том, что когда контейнер ссылочных типов удален, деструктор вызывается для всех элементов, внутри контейнера.  В контейнере дескрипторов к ссылочным типам, не были бы вызываются деструкторы для этих элементов.  
  
#### Пример  
 В следующем примере показано, как вставить объект employees в `cliext::set`.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
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
  
### Две типы значений  
 Можно также вставить неупакованный тип значения в контейнер STL\/CLR.  Неупакованный тип значения типа значения, *не помещается в процессе* в ссылочный тип.  
  
 Элемент типа значения может быть одним из стандартных типов значений, например `int`, или может быть определяемым пользователем типом значения, например `value class`.  Дополнительные сведения см. в разделе [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
#### Пример  
 В следующем примере изменяется первый пример, выполнив классом сотрудника тип значения.  Этот тип значения затем вставляется в `cliext::set` так же, как и в первом примере.  
  
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
  
 При попытке вставить дескриптор тип значения в контейнер, [Ошибка компилятора C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) создается.  
  
### Влияние производительности и памяти  
 Следует учитывать несколько факторов, указывающее, использовать ли дескрипторы к ссылочным типам или типы значения как дочерние элементы.  Если решено использовать типы значений, помните, что копия элемента выполняется каждый раз, когда элемент вставляется в контейнер.  Для небольших объектов это не должно быть проблемой, но если, вставленные больших объектов, производительность может вытерпеть.  Кроме того, при использовании типы значений, невозможно сохранить один элемент в нескольких контейнерах одновременно, так как каждый контейнер будет иметь собственную копию элемента.  
  
 Если решено использовать дескрипторы к ссылочным типам вместо, может повысить производительность, поскольку нет необходимости сделать копию элемента, когда она вставляется в контейнер.  Кроме того, в отличие от типов значений, тот же элемент может существовать в нескольких контейнерах.  Однако если решено использовать дескрипторов, необходимо соблюдать осторожность, чтобы гарантировать, что дескриптор допустим и что он указывает на объект не удаляется в любом другом месте программы.  
  
## Проблемы владения с контейнерами  
 Контейнеры в рабочем STL\/CLR в семантике значение.  Каждый раз при вставке элемента в контейнер, копия этого элемента будут.  Если необходимо получить ссылку на похожую семантику, можно вставить дескриптор объекта, а не сам объект.  
  
 При вызове метода стираете очистка или контейнера объектов дескриптора, объекты, которые ссылаются на дескрипторы не удаляются из памяти.  Необходимо либо явно удалять объект, поскольку эти объекты находятся в управляемой куче, позволяет сборщику мусора освободить память, как только он указывает, что объект больше не используется.  
  
## См. также  
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)