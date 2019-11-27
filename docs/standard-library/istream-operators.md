---
title: Операторы &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 5ac5c61488530f99cdad38ca1bfca365b6ac0f8c
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890177"
---
# <a name="ltistreamgt-operators"></a>Операторы &lt;istream&gt;

## <a name="op_gt_gt"></a> operator&gt;&gt;

Извлекает символы и строки из потока.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Параметры

\ *CH*
Символ.

*Istr*\
Поток.

\ *str*
Строка.

*val* \
Тип.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Заметки

Класс `basic_istream` также определяет несколько операторов извлечения. Дополнительные сведения см. в разделе [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

Шаблон функции:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

Извлекает до `N - 1` элементов и сохраняет их в массиве, начиная с *str*. Если `Istr.`ная [Ширина](../standard-library/ios-base-class.md#width) больше нуля, *N* имеет `Istr.width`; в противном случае это размер самого крупного массива `Elem`, который может быть объявлен. Функция всегда сохраняет значение `Elem()` после извлеченных элементов, которые он хранит. Извлечение останавливается на раннем конце файла, на символ со значением `Elem(0)` (который не извлекается) или на любом элементе (который не извлекается), который будет отклонен [WS](../standard-library/istream-functions.md#ws). Если функция не извлекает элементы, она вызывает `Istr.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`. В любом случае он вызывает `Istr.width(0)` и возвращает значение *ISTR*.

**Примечание по безопасности** Строка, завершающаяся нулем, извлекаемая из входного потока, не должна превышать размер строки *целевого буфера.* Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

Шаблон функции:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Извлекает элемент, если это возможно, и сохраняет его в *CH*. В противном случае он вызывает `is.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`. В любом случае возвращается *ISTR*.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

Возвращает `Istr >> ( char * ) str`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

Возвращает `Istr >> ( char * ) str`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Шаблон функции:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

Возвращает `Istr >> val` (и преобразует ссылку rvalue в `Istr` в качестве значения lvalue в процессе).

### <a name="example"></a>Пример

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>См. также

[\<istream>](../standard-library/istream.md)
