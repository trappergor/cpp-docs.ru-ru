---
title: Указатель this
ms.date: 11/04/2016
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
ms.openlocfilehash: c90a843ba978a98c1c61d9e096d62b85256ab0c4
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678331"
---
# <a name="this-pointer"></a>Указатель this

**Это** является указателем, доступен только в нестатических функциях-членах из **класс**, **структуры**, или **объединение** типа. Он указывает на объект, для которого вызывается функция-член. Статические функции-члены не имеют **это** указатель.

## <a name="syntax"></a>Синтаксис

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>Примечания

Объекта **это** указатель не является частью самого объекта и не отражается в результате **sizeof** инструкции в объекте. Вместо этого при вызове нестатической функции-члена для объекта компилятор передает адрес объекта в функцию в качестве скрытого аргумента. Например, при вызове следующей функции

```cpp
myDate.setMonth( 3 );
```

можно интерпретировать следующим образом:

```cpp
setMonth( &myDate, 3 );
```

Адрес объекта доступен из функции-члена как **это** указатель. Большинство вариантов использования **это** являются неявными. Допустимо, хоть это и необязательно, чтобы явным образом использовать **это** при ссылке на члены класса. Пример:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are equivalent
   (*this).month = mn;
}
```

Выражение `*this` обычно используется для возврата текущего объекта из функции-члена.

```cpp
return *this;
```

**Это** указатель также используется для защиты от рекурсивной ссылки:

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
>  Так как **это** указатель неизменяемый, назначения **это** не допускаются. Более ранних реализациях C++ допускается назначения **это**.

В некоторых случаях **это** напрямую используется указатель — например, для работы с данными, ссылающиеся на себя структурами, где требуется адрес текущего объекта.

## <a name="example"></a>Пример

```cpp
// this_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

class Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( const Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( const Buf &otherbuf )
{
    if( &otherbuf != this )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *this;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-this-pointer"></a>Тип указателя this

**Это** в объявлении функции, можно изменить тип указателя **const** и **volatile** ключевые слова. Для того чтобы объявить функцию с атрибутами, имеющими одно или оба этих ключевых слова, добавьте нужные ключевые слова после списка аргументов функции.

Рассмотрим следующий пример.

```cpp
// type_of_this_pointer1.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Предыдущий код объявляет функцию-член, `X`, в котором **это** указатель рассматривается как **const** указатель на **const** объекта. Комбинации *cv-mod-list* параметры могут использоваться, но они всегда изменяют объект, на которые указывают **это**, а не **это** сам указатель. Таким образом, в следующем примере объявляется функция `X`; **это** указатель находится **const** указатель на **const** объекта:

```cpp
// type_of_this_pointer2.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Тип **это** функции в члене описывается следующим синтаксисом, где *cv квалификаторов* определяется исходя из декларатора функций-членов и может быть **const**или **volatile** (или оба), и *типа класса* — это имя класса:

*тип класса [cv квалификаторов]* **&#42; const это**

Другими словами **это** всегда является указателем const; не может быть переназначен.  **Const** или **volatile** квалификаторы, используемые в объявлении функции-члена применяются к экземпляру класса, на которые указывают **это** в рамках этой функции.

В следующей таблице приведены дополнительные сведения о том, как работают эти модификаторы.

### <a name="semantics-of-this-modifiers"></a>Значение модификаторов

|Модификатор|Значение|
|--------------|-------------|
|**const**|Не удается изменить элемент данных; не удается вызвать функции-члены, которые не являются **const**.|
|**volatile**|Данные-члены загружаются из памяти при каждом обращении. Ряд оптимизаций отключается.|

Это ошибка для передачи **const** объекта на функцию-член, не **const**. Аналогичным образом, является ошибкой для передачи **volatile** объекта на функцию-член, не **volatile**.

Член функции, объявленные как **const** не может изменять данные-члены — в таких функциях **это** указатель — это указатель на **const** объекта.

> [!NOTE]
>  Конструкторы и деструкторы не могут объявляться как **const** или **volatile**. Тем не менее, их можно вызывать для **const** или **volatile** объектов.

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)