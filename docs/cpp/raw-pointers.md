---
title: Сырье указатели (КЗ)
description: Как использовать необработанные указатели в СЗ
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- void
- nullptr
- const
- char
- new
- delete
ms.openlocfilehash: 8ba188154d7395ce7be3878fa9dbee2fde08a130
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032100"
---
# <a name="raw-pointers-c"></a>Сырье указатели (КЗ)

*Указатель* — это тип переменной. Он хранит адрес объекта в памяти и используется для доступа к этому объекту. *Необработанный указатель* — это указатель, срок службы которого не контролируется инкапсулирующим объектом, [например, интеллектуальным указателем.](smart-pointers-modern-cpp.md) Сырой указатель может быть назначен адрес другой переменной, не указательной, [nullptr](nullptr.md)или он может быть назначен значением . Указатель, которому не было присвоено значение, содержит случайные данные.

Указатель также может быть *дессылкой* для получения значения объекта, на который он указывает. *Оператор доступа к членам* предоставляет доступ к членам объекта.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

Указатель может указывать на набранный объект или на **void**. Когда программа выделяет объект на [куче](https://wikipedia.org/wiki/Heap) памяти, она получает адрес этого объекта в виде указателя. Такие указатели называются *владеющими указателем.* Указатель владения (или его копия) должен использоваться для явного освобождения объекта, выделенного кучей, когда он больше не нужен. Неспособность освободить память приводит к *утечке памяти*и делает это местоположение памяти недоступным для любой другой программы на машине. Память, **new** выделенная с **delete** помощью, должна быть освобождена с помощью (или ** delete \[no).** Для получения дополнительной информации, [ new см. delete ](new-and-delete-operators.md)

```cpp
    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

Указатель (если он не объявлен **const** как) может быть приращен или decremented указать в другом месте в памяти. Эта операция называется *арифметической указателем.* Он используется в C-стиле программирования для итерации элементов в массивах или других структурах данных. Указатель **const** не может быть указать на другое местоположение памяти, и в этом смысле похож на [ссылку](references-cpp.md). Для получения дополнительной информации, [ const см.](const-and-volatile-pointers.md)

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

На 64-битных операционных системах указатель имеет размер 64 бита. Размер указателя системы определяет, сколько адресной памяти она может иметь. Все копии указателя указывают на одно и то же местоположение памяти. Указатели (наряду со ссылками) широко используются в СЗ для передачи более крупных объектов и из функций. Это потому, что часто более эффективно копировать адрес объекта, чем копировать весь объект. При определении функции укажите **const** параметры указателя, как если только вы не намереваетесь изменить объект. Как правило, **const** ссылки являются предпочтительным способом передачи объектов функциям, если только значение объекта **nullptr** возможно.

[Указатели на функции](#pointers_to_functions) позволяют передавать функции другим функциям и использоваться для "обратных вызовов" в программировании в стиле C. Для этой цели современная СЗ использует [выражения лямбда.](lambda-expressions-in-cpp.md)

## <a name="initialization-and-member-access"></a>Инициализация и доступ к членам

Следующий пример показывает, как объявить, инициализировать и использовать необработанный указатель. Это инициализированное использование, **new** чтобы указать объект, **delete** выделенный на кучу, которую вы должны явно. В примере также показаны некоторые из опасностей, связанных с необработанными указателями. (Помните, что этот пример C-стиль программирования, а не современные СЗ!)

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
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>Арифметика указателей и массивы

Указатели и массивы тесно связаны между собой. Когда массив передается по обозначение функции, он передается как указатель на первый элемент. Следующий пример демонстрирует следующие важные свойства указателей и массивов:

- `sizeof` оператор возвращает общий размер байтов массива
- для определения количества элементов, разделить общие байты на размер одного элемента
- когда массив передается функции, он *распадается* на тип указателя
- оператор `sizeof` при нанесении на указатель возвращает размер указателя, 4 байта на x86 или 8 байтов на x64

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

Некоторые арифметические операции могут бытьconst использованы на не-указатели, чтобы сделать их указывают на другое место памяти. Указатели приращены и decremented **++** **+=** с **-=** **--** помощью , и операторов. Этот метод может быть использован в массивах и особенно полезен в буферах нетипированных данных. A ** void ** приравня размером **char** (1 байт). Набранный указатель приравнизывается по размеру типа, на который он указывает.

Следующий пример показывает, как арифметика указателя может быть использована для доступа к отдельным пикселям в битной карте windows. Обратите внимание **new** на **delete** использование и , и dereference оператора.

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

## <a name="opno-locvoid-pointers"></a>voidуказатели на указы

Указатель, **void** чтобы просто указывает на место необработанной памяти. Иногда необходимо использовать ** void ** указатели, например, при прохождении между кодом СЗ и C-функциями.

При отлитом указателя на void указатель содержимое местоположения памяти остается неизменным. Тем не менее, информация типа теряется, так что вы не можете делать приращения или decrement операций. Местоположение памяти можно отлить, `MyClass*` например, от туда `void*` и обратно. `MyClass*` Такие операции по своей сути подвержены ошибкам и требуют большой осторожности, чтобы избежать ошибок. Современный СЗ не рекомендует void использовать указатели практически при любых обстоятельствах.

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
    char* pchar = static_cast<char*>(pvoid);
    for(char* c = pchar; c < pchar + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>Указатели на функции

В программировании в стиле C функции используются главным образом для передачи функций другим функциям. Этот метод позволяет вызывающему настроить поведение функции, не изменяя ее. В современных [выражениях Лямбда, лямбда](lambda-expressions-in-cpp.md) обеспечивают те же возможности с большей безопасностью типа и другими преимуществами.

Декларация указателя функции определяет подпись, которую функция указателя должна иметь:

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

В следующем примере `combine` показана функция, которая принимает `std::string` в качестве `std::string`параметра любую функцию, которая принимает и возвращает . В зависимости от функции, `combine`которая передается, он либо подготовит или придатит строку.

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

## <a name="see-also"></a>См. также раздел

[Интеллектуальные указатели](smart-pointers-modern-cpp.md)
[Оператор indirection:](indirection-operator-star.md)<br/>
[Оператор address-of: &](address-of-operator-amp.md)</br>
[Добро пожаловать обратно в СЗ](welcome-back-to-cpp-modern-cpp.md)
