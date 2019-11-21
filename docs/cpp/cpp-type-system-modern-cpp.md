---
title: C++ type system
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1f12f7505438dc995aaf8a045fd903488e9ff092
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246601"
---
# <a name="c-type-system"></a>C++ type system

The concept of *type* is very important in C++. Каждая переменная, аргумент функции и возвращаемое значение функции должны иметь тип, чтобы их можно было скомпилировать. Кроме того, перед вычислением каждого выражения (включая литеральные значения) компилятор неявно назначает ему тип. Some examples of types include **int** to store integral values, **double** to store floating-point values (also known as *scalar* data types), or the Standard Library class [std::basic_string](../standard-library/basic-string-class.md) to store text. You can create your own type by defining a **class** or **struct**. Тип определяет объем памяти, выделяемой для переменной (или результата выражения), типы значений, которые могут храниться в этой переменной, способ интерпретации значений (например, битовые шаблоны), и операции, допустимые с переменной. Эта статья содержит неформальный обзор основных особенностей системы типов C++.

## <a name="terminology"></a>Терминология

**Variable**: The symbolic name of a quantity of data so that the name can be used to access the data it refers to throughout the scope of the code where it is defined. In C++, *variable* is generally used to refer to instances of scalar data types, whereas instances of other types are usually called *objects*.

**Object**: For simplicity and consistency, this article uses the term *object* to refer to any instance of a class or structure, and when it is used in the general sense includes all types, even scalar variables.

**POD type** (plain old data): This informal category of data types in C++ refers to types that are scalar (see the Fundamental types section) or are *POD classes*. Класс POD не содержит статических данных-членов, которые не являются типами POD, а также не содержит пользовательских конструкторов, пользовательских деструкторов или пользовательских операторов присваивания. Кроме того, класс POD не имеет виртуальных функций, базового класса и ни закрытых, ни защищенных нестатических данных-членов. Типы POD часто используются для внешнего обмена данными, например с модулем, написанным на языке С (в котором имеются только типы POD).

## <a name="specifying-variable-and-function-types"></a>Указание типов переменных и функций

C++ is a *strongly typed* language and it is also *statically-typed*; every object has a type and that type never changes (not to be confused with static data objects).
**When you declare a variable** in your code, you must either specify its type explicitly, or use the **auto** keyword to instruct the compiler to deduce the type from the initializer.
**When you declare a function** in your code, you must specify the type of each argument and its return value, or **void** if no value is returned by the function. Исключением является использование шаблонов функции, которые допускают аргументы произвольных типов.

После объявления переменной изменить ее тип впоследствии уже невозможно. Однако можно скопировать значения переменной или возвращаемое значение функции в другую переменную другого типа. Such operations are called *type conversions*, which are sometimes necessary but are also potential sources of data loss or incorrectness.

При объявлении переменной типа POD настоятельно рекомендуется инициализировать ее, т. е. указать начальное значение. Пока переменная не инициализирована, она имеет "мусорное" значение, определяемое значениями битов, которые ранее были установлены в этом месте памяти. Необходимо учитывать эту особенность языка C++, особенно при переходе с другого языка, который обрабатывает инициализацию автоматически. При объявлении переменной типа, не являющегося классом POD, инициализация обрабатывается конструктором.

В следующем примере показано несколько простых объявлений переменных с небольшим описанием для каждого объявления. В примере также показано, как компилятор использует сведения о типе, чтобы разрешить или запретить некоторые последующие операции с переменной.

```cpp
int result = 0;              // Declare and initialize an integer.
double coefficient = 10.8;   // Declare and initialize a floating
                             // point value.
auto name = "Lady G.";       // Declare a variable and let compiler
                             // deduce the type.
auto address;                // error. Compiler cannot deduce a type
                             // without an intializing value.
age = 12;                    // error. Variable declaration must
                             // specify a type or use auto!
result = "Kenny G.";         // error. Can’t assign text to an int.
string result = "zero";      // error. Can’t redefine a variable with
                             // new type.
int maxValue;                // Not recommended! maxValue contains
                             // garbage bits until it is initialized.
```

## <a name="fundamental-built-in-types"></a>Базовые (встроенные) типы

В отличие от некоторых других языков, в C++ нет универсального базового типа, от которого наследуются все остальные типы. The language includes many *fundamental types*, also known as *built-in types*. This includes numeric types such as **int**, **double**, **long**, **bool**, plus the **char** and **wchar_t** types for ASCII and UNICODE characters, respectively. Most fundamental types (except **bool**, **double**, **wchar_t** and related types) all have unsigned versions, which modify the range of values that the variable can store. For example, an **int**, which stores a 32-bit signed integer, can represent a value from -2,147,483,648 to 2,147,483,647. An **unsigned int**, which is also stored as 32-bits, can store a value from 0 to 4,294,967,295. Общее количество возможных значений в каждом случае одинаково, отличается только диапазон.

Базовые типы распознаются компилятором, в котором предусмотрены встроенные правила, управляющие операциями, выполняемыми с такими типами, а также преобразованием в другие базовые типы. For a complete list of built-in types and their size and numeric limits, see [Fundamental Types](../cpp/fundamental-types-cpp.md).

На следующем рисунке показаны относительные размеры встроенных типов:

![Size in bytes of built&#45;in types](../cpp/media/built-intypesizes.png "Size in bytes of built&#45;in types")

В следующей таблице перечислены наиболее часто используемые базовые типы:

|Type|Размер|Добавление примечаний|
|----------|----------|-------------|
|int|4 байта|Выбор по умолчанию для целочисленных значений.|
|двойная|8 байт|Выбор по умолчанию для значений с плавающей запятой.|
|bool|1 байт|Представляет значения, которые могут быть или true, или false.|
|char|1 байт|Используйте для символов ASCII в старых строках в стиле C или в объектах std::string, которые никогда не будут преобразовываться в Юникод.|
|wchar_t|2 байта|Представляет "расширенные" символы, которые могут быть представлены в формате Юникод (UTF-16 в Windows, в других операционных системах возможно другое представление). Это символьный тип, используемый в строках типа `std::wstring`.|
|unsigned&nbsp;char|1 байт|В C++ нет встроенного типа `byte`.  Для представления байтовых значений используйте тип unsigned char.|
|unsigned int|4 байта|Вариант по умолчанию для битовых флагов.|
|длинное длинное|8 байт|Представляет очень большие целочисленные значения.|

## <a name="the-void-type"></a>Тип void

The **void** type is a special type; you cannot declare a variable of type **void**, but you can declare a variable of type __void \*__ (pointer to **void**), which is sometimes necessary when allocating raw (un-typed) memory. However, pointers to **void** are not type-safe and generally their use is strongly discouraged in modern C++. In a function declaration, a **void** return value means that the function does not return a value; this is a common and acceptable use of **void**. While the C language required functions that have zero parameters to declare **void** in the parameter list, for example, `fou(void)`, this practice is discouraged in modern C++ and should be declared `fou()`. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>Квалификатор типа const

Любой встроенный или пользовательский тип может квалифицироваться ключевым словом const. Additionally, member functions may be **const**-qualified and even **const**-overloaded. The value of a **const** type cannot be modified after it is initialized.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

The **const** qualifier is used extensively in function and variable declarations and "const correctness" is an important concept in C++; essentially it means to use **const** to guarantee, at compile time, that values are not modified unintentionally. For more information, see [const](../cpp/const-cpp.md).

A **const** type is distinct from its non-const version; for example, **const int** is a distinct type from **int**. You can use the C++ **const_cast** operator on those rare occasions when you must remove *const-ness* from a variable. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Строковые типы

Strictly speaking, the C++ language has no built-in string type; **char** and **wchar_t** store single characters - you must declare an array of these types to approximate a string, adding a terminating null value (for example, ASCII `'\0'`) to the array element one past the last valid character (also called a *C-style string*). Строки в стиле C требовали написания гораздо большего объема кода или использования внешних библиотек служебных функций. But in modern C++, we have the Standard Library types `std::string` (for 8-bit **char**-type character strings) or `std::wstring` (for 16-bit **wchar_t**-type character strings). These C++ Standard Library containers can be thought of as native string types because they are part of the standard libraries that are included in any compliant C++ build environment. Просто используйте директиву `#include <string>`, чтобы эти типы были доступны в программе. (If you are using MFC or ATL, the CString class is also available, but is not part of the C++ standard.) The use of null-terminated character arrays (the C-style strings previously mentioned) is strongly discouraged in modern C++.

## <a name="user-defined-types"></a>Пользовательские типы

When you define a **class**, **struct**, **union**, or **enum**, that construct is used in the rest of your code as if it were a fundamental type. Он имеет известный размер в памяти, и в его отношении действуют определенные правила проверки во время компиляции и во время выполнения в течение срока использования программы. Основные различия между базовыми встроенными типами и пользовательскими типами указаны ниже:

- Компилятор не имеет встроенных сведений о пользовательском типе. It learns of the type when it first encounters the definition during the compilation process.

- Пользователь определяет, какие операции можно выполнять с типом и как его можно преобразовать в другие типы, задавая (через перегрузку) соответствующие операторы, либо в виде членов класса, либо в виде функций, не являющихся членами. For more information, see [Function Overloading](function-overloading.md)

## <a name="pointer-types"></a>типы указателей

Как и самые ранние версии языка C, язык C++ по-прежнему позволяет объявить переменную типа указателя с помощью специального декларатора `*` (звездочка). Тип указателя хранит адрес расположения в памяти, в котором хранится фактическое значение данных. In modern C++, these are referred to as *raw pointers*, and are accessed in your code through special operators `*` (asterisk) or `->` (dash with greater-than). This is called *dereferencing*, and which one that you use depends on whether you are dereferencing a pointer to a scalar or a pointer to a member in an object. Работа с типами указателя долгое время была одним из наиболее трудных и непонятных аспектов разработки программ на языках C и C++. This section outlines some facts and practices to help use raw pointers if you want to, but in modern C++ it’s no longer required (or recommended) to use raw pointers for object ownership at all, due to the evolution of the [smart pointer](../cpp/smart-pointers-modern-cpp.md) (discussed more at the end of this section). Все еще полезно и безопасно использовать необработанные указатели для отслеживания объектов, но если требуется использовать их для владения объектом, необходимо делать это с осторожностью и после тщательного анализа процедуры создания и уничтожения объектов, которые им принадлежат.

Первое, что необходимо знать, — это то, что при объявлении переменной необработанного указателя выделяется только память, необходимая для хранения адреса расположения памяти, на который будет ссылаться указатель при разыменовывании. Allocation of the memory for the data value itself (also called *backing store*) is not yet allocated. Другими словами, объявив переменную необработанного указателя, вы создаете переменную адреса памяти, а не фактическую переменную данных. Разыменовывание переменной указателя до проверки того, что она содержит действительный адрес в резервном хранилище, приведет к неопределенному поведению (обычно неустранимой ошибке) программы. В следующем примере демонстрируется подобная ошибка:

```cpp
int* pNumber;       // Declare a pointer-to-int variable.
*pNumber = 10;      // error. Although this may compile, it is
                    // a serious error. We are dereferencing an
                    // uninitialized pointer variable with no
                    // allocated memory to point to.
```

Пример разыменовывает тип указателя без выделения памяти для хранения фактических целочисленных данных или без выделенного допустимого адреса памяти. В следующем коде исправлены эти ошибки:

```cpp
    int number = 10;          // Declare and initialize a local integer
                              // variable for data backing store.
    int* pNumber = &number;   // Declare and initialize a local integer
                              // pointer variable to a valid memory
                              // address to that backing store.
...
    *pNumber = 41;            // Dereference and store a new value in
                              // the memory pointed to by
                              // pNumber, the integer variable called
                              // "number". Note "number" was changed, not
                              // "pNumber".
```

В исправленном примере кода используется локальной память стека для создания резервного хранилища, на который указывает указатель `pNumber`. Базовый тип используется для простоты. In practice, the backing store for pointers are most often user-defined types that are dynamically-allocated in an area of memory called the *heap* (or *free store*) by using a **new** keyword expression (in C-style programming, the older `malloc()` C runtime library function was used). Once allocated, these variables are usually referred to as objects, especially if they are based on a class definition. Memory that is allocated with **new** must be deleted by a corresponding **delete** statement (or, if you used the `malloc()` function to allocate it, the C runtime function `free()`).

However, it is easy to forget to delete a dynamically-allocated object- especially in complex code, which causes a resource bug called a *memory leak*. По этой причине в современном С++ настоятельно не рекомендуется использовать необработанные указатели. It is almost always better to wrap a raw pointer in a [smart pointer](../cpp/smart-pointers-modern-cpp.md), which will automatically release the memory when its destructor is invoked (when the code goes out of scope for the smart pointer); by using smart pointers you virtually eliminate a whole class of bugs in your C++ programs. В следующем примере предположим, что `MyClass` — это пользовательский тип, который имеет открытый метод `DoSomeWork();`

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

For more information about smart pointers, see [Smart Pointers](../cpp/smart-pointers-modern-cpp.md).

For more information about pointer conversions, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

For more information about pointers in general, see [Pointers](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Типы данных Windows

В классическом программировании Win32 на языке C и C++ для указания типов параметров и возвращаемых значений в большинстве функций используются специально предназначенные для Windows определения typedef и макросы #define (определенные в `windef.h`). These Windows data types are mostly just special names (aliases) given to C/C++ built-in types. For a complete list of these typedefs and preprocessor definitions, see [Windows Data Types](/windows/win32/WinProg/windows-data-types). Некоторые из этих определений typedef, например HRESULT и LCID, удобны и содержат полезные сведения. Другие, такие как INT, не имеют особого смысла и просто являются псевдонимами для базовых типов C++. Прочие типы данных Windows имеют имена, которые сохранились с эпохи программирования на языке C для 16-разрядных процессоров, и не имеют смысла или значения на современном оборудовании или в современных операционных системах. There are also special data types associated with the Windows Runtime Library, listed as [Windows Runtime base data types](/windows/win32/WinRT/base-data-types). В современном языке C++ в целом рекомендуется использовать базовые типы C++, за исключением случаев, когда тип Windows сообщает некоторые дополнительные сведения о том, как следует интерпретировать значение.

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения о системе типов C++ см. в следующих разделах.

|||
|-|-|
|[Типы значений](../cpp/value-types-modern-cpp.md)|Describes *value types* along with issues relating to their use.|
|[Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Описание типовых проблем преобразования типов и способов их избежать.|

## <a name="see-also"></a>См. также

[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
