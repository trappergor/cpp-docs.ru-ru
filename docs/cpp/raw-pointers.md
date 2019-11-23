---
title: НеобработанныеC++указатели ()
description: Использование необработанных указателей вC++
ms.date: 11/19/2019
helpviewer_keywords:
- pointers [C++]
ms.openlocfilehash: 9ea498c254bc37dc8dc550232127cb2db3bc0886
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74250688"
---
# <a name="raw-pointers-c"></a>НеобработанныеC++указатели ()

Указатель — это тип переменной, которая хранит адрес объекта в памяти и используется для доступа к этому объекту. *Необработанный указатель* — это указатель, время существования которого не контролируется инкапсулированным объектом, например [интеллектуальным указателем](smart-pointers-modern-cpp.md). Необработанному указателю может быть присвоен адрес другой переменной, не являющейся указателем, или ему может быть присвоено значение [nullptr](nullptr.md). Указатель, которому не присвоено значение, содержит случайные данные.

Указатель может также быть *разыменован* для получения значения объекта, на который он указывает. *Оператор доступа к членам* предоставляет доступ к членам объекта.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address

```

Указатель может указывать на типизированный объект или на **void**. Когда программа выделяет новый объект в [куче](https://wikipedia.org/wiki/Heap) в памяти, он получает адрес этого объекта в виде указателя. Такие указатели называются *указателями-владельцами*; для явного удаления выделенного в куче объекта, когда он больше не нужен, необходимо использовать указатель-владелец (или его копию). Сбой при удалении памяти приводит к *утечке памяти* и отображению этого расположения памяти, недоступного для любой другой программы на компьютере. Дополнительные сведения см. в разделе [операторы new и DELETE](new-and-delete-operators.md).

```cpp

    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

Указатель (если он не объявлен как **const**) можно увеличить или уменьшить, чтобы он указывал на новое место в памяти. Это называется *арифметикой указателей* и используется в программировании в стиле C для итерации элементов в массивах или других структурах данных. Невозможно создать указатель **const** для указания на другое место в памяти, и в этом смысле очень похоже на [ссылку](references-cpp.md). Дополнительные сведения см. в разделе [указатели const и volatile](const-and-volatile-pointers.md).

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    const char* str = "Hello world";

    const int c = 1;
    const int* pconst = &c; // declare a non-const pointer to const int
    const int c2 = 2;
    pconst = &c2;  // OK pconst itself isn't const
    const int* const pconst2 = &c; 
    // pconst2 = &c2; // Error! pconst2 is const.
```

В 64-разрядных операционных системах указатель имеет размер 64 бит; размер указателя системы определяет, сколько памяти она может иметь. Все копии точки указателя на одно и то же место в памяти. Указатели (вместе со ссылками) широко используются C++ для передачи больших объектов в функции и из них, поскольку обычно гораздо эффективнее копировать 64-разрядный адрес объекта, чем копирование всего объекта. При определении функции указывайте параметры-указатели как **константы** , если только вы не хотите, чтобы функция изменила объект. Как правило, **константные** ссылки являются предпочтительным способом передачи объектов в функции, если только значение объекта не может быть **nullptr**.

[Указатели на функции](#pointers_to_functions) позволяют передавать функции другим функциям и использоваться для обратных вызовов в программировании в стиле C. В C++ современных для этой цели используются [лямбда-выражения](lambda-expressions-in-cpp.md) .

## <a name="initialization-and-member-access"></a>Доступ к инициализации и членам

В следующем примере показано, как объявить необработанный указатель и инициализировать его с помощью объекта, выделенного в куче, и как его использовать. В нем также показаны некоторые опасности, связанные с необработанными указателями. (Помните, что это программирование в стиле C и не современный C++!)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
void func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
void func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use new to allocate and initialize memory
    MyClass* pmc = new MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std:: cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(mc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*mc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>Арифметические и массивные указатели

Указатели и массивы тесно связаны друг с друга. Когда массив передается в функцию по значению, он передается в качестве указателя на первый элемент. В следующем примере показаны следующие важные свойства указателей и массивов.

- Оператор `sizeof` возвращает общий размер массива в байтах
- чтобы определить количество элементов, разделите общее число байтов на размер одного элемента.
- когда массив передается в функцию, он *декайс* к типу указателя
- Оператор `sizeof` при применении к указателю возвращает размер указателя, 4 байта на x86 или 8 байт в x64

```cpp
#include <iostream>

void func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

Для указателей, не являющихся константами, можно выполнять определенные арифметические операции, чтобы они указывали на новое место в памяти. Указатель можно увеличить и уменьшить с помощью операторов **++** , **+=** , **-=** и **--** . Этот метод можно использовать в массивах и особенно полезен в буферах нетипизированных данных. Значение **void\*** увеличивается на размер типа **char** (1 байт). Типизированный указатель увеличивается по размеру типа, на который он указывает.

В следующем примере показано, как можно использовать арифметические действия с указателями для доступа к отдельным пикселям точечного рисунка в Windows. Обратите внимание на использование операторов **New** и **Delete**и оператор разыменования. 

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    constexpr int bufferSize = 30000;
    unsigned char* buffer = new unsigned char[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned char* begin = &buffer[0];
    unsigned char* end = &buffer[0] + bufferSize;
    unsigned char* p = begin;
    constexpr int pixelWidth = 3;
    constexpr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned char).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<char*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<char*>(&header), sizeof(header));
    wf.write(reinterpret_cast<char*>(begin), bufferSize);

    delete[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="void-pointers"></a>пустые * указатели

Указатель на **void** просто указывает на расположение необработанной памяти. Иногда необходимо использовать **пустые\*** указатели, например при передаче между C++ кодом и функциями C. 

Если типизированный указатель приводится к указателю типа void, содержимое области памяти не изменяется, но сведения о типе теряются, поэтому нельзя выполнять операции увеличения или уменьшения. Расположение в памяти может быть приведено, например, от MyClass * к void * и обратно в MyClass *. Такие операции по сути подвержены ошибкам, и для их предотвращения необходимо иметь большое значение. Современная C++ не рекомендует использовать указатели void, если это не обязательно.

```cpp

//func.c
void func(void* data, int length)
{
    char* c = (char*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    void func(void* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = new MyClass{10, "Marian"};
    void* p = static_cast<void*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator new to allocate untyped memory block
    void* pvoid = operator new(1000);
    for(char* c = static_cast<char*>(pvoid); pvoid < &pvoid + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers_to_functions"></a>Указатели на функции

В программировании в стиле C указатели функций используются в основном для передачи функций другим функциям. В этом сценарии вызывающий объект может настроить поведение функции, не изменяя ее. В современных C++ [лямбда-выражения](lambda-expressions-in-cpp.md) обеспечивают те же возможности, что и более строгая типизация, и другие преимущества.

Объявление указателя на функцию указывает сигнатуру, которую должна иметь функция, на которую должен быть указан объект.

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
void (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

В следующем примере показана функция `combine`, которая принимает в качестве параметра любую функцию, которая принимает `std::string` и возвращает `std::string`. В зависимости от функции, которая передается в `combine`, она будет либо в начале, либо при добавлении строки.

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>См. также:

[Смарт-указатели](smart-pointers-modern-cpp.md)
[оператор косвенного обращения: *](indirection-operator-star.md)<br/>
[Оператор address-of: &](address-of-operator-amp.md)</br>
[Добро пожаловать обратно вC++](welcome-back-to-cpp-modern-cpp.md)
