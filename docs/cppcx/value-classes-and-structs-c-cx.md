---
title: Классы и структуры значений (C++/CX)
ms.date: 12/30/2016
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
ms.openlocfilehash: 15d54d139f086ce5bb025aaeab145c71d33903c0
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381601"
---
# <a name="value-classes-and-structs-ccx"></a>Классы и структуры значений (C++/CX)

*Структура значений* или *класс значений* является совместимым с среда выполнения Windows модулем ("Обычная старая структура данных"). Она имеет фиксированный размер и состоит только из полей только; в отличие от класса ссылки, у нее нет свойств.

В следующих примерах показано, как объявлять и инициализировать структуры значений.

```

// in mainpage.xaml.h:
    value struct TestStruct
    {
        Platform::String^ str;
        int i;
    };

    value struct TestStruct2
    {
        TestStruct ts;
        Platform::String^ str;
        int i;
    };

// in mainpage.cpp:
    // Initialize a value struct with an int and String
    TestStruct ts = {"I am a TestStruct", 1};

    // Initialize a value struct that contains
    // another value struct, an int and a String
    TestStruct2 ts2 = {{"I am a TestStruct", 1}, "I am a TestStruct2", 2};

    // Initialize value struct members individually.
    TestStruct ts3;
    ts3.i = 108;
    ts3.str = "Another way to init a value struct.";
```

Когда переменная типа значения присваивается другой переменной, значение копируется, так что каждая из двух переменных содержит собственную копию данных. *Структура значения* — это структура фиксированного размера, которая содержит только открытые поля данных и объявляется с помощью **`value struct`** ключевого слова.

*Класс значений* , как и **`value struct`** , за исключением того, что его поля должны явно предоставлять открытый доступ. Он объявляется с помощью **`value class`** ключевого слова.

Структура значений или класс значений может содержать только поля с основными числовыми типами, классами Enum, `Platform::String^` или [Platform:: ibox \<T> ^ ](../cppcx/platform-ibox-interface.md) , где T — это числовой тип, класс или класс значения или структура. `IBox<T>^`Поле может иметь значение **`nullptr`** — это то, как C++ реализует концепцию *типов значений, допускающих значения NULL*.

Класс значения или структура значения, содержащие в качестве члена тип `Platform::String^` или `IBox<T>^` , не поддерживают `memcpy`.

Поскольку все члены класса **`value class`** или **`value struct`** являются открытыми и передаются в метаданные, стандартные типы C++ не допускаются в качестве членов. Это отличается от классов ссылок, которые могут содержать **`private`** или **`internal`** стандартные типы C++.

В следующем фрагменте кода типы `Coordinates` и `City` объявляются как структуры значения. Обратите внимание, что один из членов данных класса `City` принадлежит к типу `GeoCoordinates` . **`value struct`** Может содержать другие структуры значений в качестве членов.

[!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]

## <a name="parameter-passing-for-value-types"></a>Передача параметров для типов значений

Если параметром функции или метода является тип значения, он обычно передается по значению. Для больших объектов это может вызвать проблемы с производительностью. В Visual Studio 2013 и более ранних версиях типы значений в C++/CX всегда передавались по значению. В Visual Studio 2015 и последующих версиях типы значений можно передавать по значению или по ссылке.

Чтобы объявить параметр, который передает тип значения по значению, используйте код, аналогичный приведенному ниже:

```cpp
void Method1(MyValueType obj);
```

Чтобы объявить параметр, который передает тип значения по ссылке, используйте символ ссылки (&), как показано в следующем примере:

```cpp
void Method2(MyValueType& obj);
```

Тип в Method2 является ссылкой на MyValueType и работает так же, как ссылочный тип в стандартном C++.

При вызове Method1 из другого языка, например C#, не требуется использовать ключевое слово `ref` или `out` . При вызове Method2 используйте ключевое слово `ref` .

```
Method2(ref obj);
```

Также можно использовать символ указателя (*) для передачи типа значения по ссылке. Поведение по отношению к вызывающим объектам в других языках совпадает (вызывающие объекты в C# используют ключевое слово `ref` ), но в методе тип является указателем на тип значения.

## <a name="nullable-value-types"></a>Типы значений, допускающие значение NULL

Как упоминалось ранее, класс значения или структура значения могут иметь поле типа [Platform:: \<T> ^ ibox](../cppcx/platform-ibox-interface.md), например `IBox<int>^` . Такое поле может иметь любое числовое значение, допустимое для **`int`** типа, или может иметь значение **`nullptr`** . Поле, допускающее значение NULL, можно передать в качестве аргумента методу, параметр которого объявлен как необязательный, или в любой другой объект, в котором тип значения не обязательно должен иметь значение.

В следующем примере показано, каким образом выполняется инициализация структуры с полем, допускающим значение null.

```
public value struct Student
{
    Platform::String^ Name;
    int EnrollmentYear;
    Platform::IBox<int>^ GraduationYear; // Null if not yet graduated.
};
//To create a Student struct, one must populate the nullable type.
MainPage::MainPage()
{
    InitializeComponent();

    Student A;
    A.Name = "Alice";
    A.EnrollmentYear = 2008;
    A.GraduationYear = ref new Platform::Box<int>(2012);

    Student B;
    B.Name = "Bob";
    B.EnrollmentYear = 2011;
    B.GraduationYear = nullptr;

    IsCurrentlyEnrolled(A);
    IsCurrentlyEnrolled(B);
}
bool MainPage::IsCurrentlyEnrolled(Student s)
{
    if (s.GraduationYear == nullptr)
    {
        return true;
    }
    return false;
}
```

Саму структуру значений можно сделать допускающей значение null аналогичным образом, как показано в следующем примере.

```

public value struct MyStruct
{
public:
    int i;
    Platform::String^ s;
};

public ref class MyClass sealed
{
public:
    property Platform::IBox<MyStruct>^ myNullableStruct;
};
```

## <a name="see-also"></a>См. также

[Система типов (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)<br/>
[Классы и структуры ссылки (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md)
