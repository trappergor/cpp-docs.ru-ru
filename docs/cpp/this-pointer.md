---
title: Указатель this
description: Указатель this — это созданный компилятором указатель на текущий объект в нестатических функциях-членах.
ms.date: 01/22/2020
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- this
- class
- struct
- union
- sizeof
- const
- volatile
ms.openlocfilehash: 58bba2edd7a457c624b747b5a65d209995852848
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518339"
---
# <a name="opno-locthis-pointer"></a>Указатель this

Указатель **this** является указателем, доступным только в нестатических функциях-членах типа **class** , **struct** или **union** . Он указывает на объект, для которого вызывается функция-член. Статические функции-члены не имеют указателя **this** .

## <a name="syntax"></a>Синтаксис

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>Заметки

Указатель **this** объекта не является частью самого объекта. Он не отражается в результатах оператора **sizeof** объекта. При вызове нестатической функции-члена для объекта компилятор передает адрес объекта в функцию в виде скрытого аргумента. Например, при вызове следующей функции

```cpp
myDate.setMonth( 3 );
```

может интерпретироваться как:

```cpp
setMonth( &myDate, 3 );
```

Адрес объекта доступен в функции-члене в качестве указателя **this** . Большинство используемых указателей **this** являются неявными. Он является юридическим, хотя и ненужным, для использования явного **this** при ссылке на членов class. Например:

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

Указатель **this** также используется для защиты от самостоятельной ссылки:

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
> Поскольку указатель **this** является неизменяемым, присваивания указателю **this** не разрешены. Более ранние реализации C++ разрешенного присваивания **this** .

Иногда указатель **this** используется напрямую, например для управления самостоятельными структурами данных, где требуется адрес текущего объекта.

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

## <a name="type-of-the-opno-locthis-pointer"></a>Тип указателя this

Тип указателя **this** можно изменить в объявлении функции с помощью ключевых слов **const** и **volatile** . Чтобы объявить функцию, имеющую один из этих атрибутов, добавьте ключевые слова после списка аргументов функции.

Рассмотрим пример.

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

В приведенном выше коде объявляется функция-член, `X`, в которой указатель **this** обрабатывается как указатель **const** на объект **const** . Можно использовать сочетания параметров *ОПС-mod-list* , но они всегда изменяют объект, на который указывает указатель **this** , а не сам указатель. Следующее объявление объявляет функцию `X`, где указатель **this** является **const** указателем на объект **const** :

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

Тип **this** в функции-члене описан в следующем синтаксисе. *Список «ОПС-квалификатор»* определяется на основе декларатора функции-члена. Это может быть **const** или **volatile** (или и то, и другое). *class-Type* — имя class:

[*ОПС-квалификатор-List*] *class* **\* const this**

Иными словами, указатель **this** всегда является указателем const. Его нельзя назначить.  Квалификаторы **const** или **volatile** , используемые в объявлении функции члена, применяются к class экземпляру **this** точек указателя в области этой функции.

В следующей таблице приведены дополнительные сведения о том, как работают эти модификаторы.

### <a name="semantics-of-opno-locthis-modifiers"></a>Семантика модификаторов this

|Модификатор|Смысл|
|--------------|-------------|
|**const**|Не удается изменить данные элемента; не удается вызвать функции члена, которые не **const** .|
|**volatile**|Данные элементов загружаются из памяти при каждом доступе к ним; отключает некоторые оптимизации.|

Передача **constного** объекта в функцию-член, которая не **const** , является ошибкой.

Аналогично, также возникает ошибка передачи объекта **volatile** в функцию-член, которая не **volatile** .

Функции-члены, объявленные как **const** не могут изменять данные элементов — в таких функциях **this** указатель является указателем на объект **const** .

> [!NOTE]
> Конструкторы и деструкторы не могут быть объявлены как **const** или **volatile** . Однако они могут вызываться для **const** или **volatile** объектов.

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)
