---
title: Операторы &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: c10692194c80051b10ecbe776c7d23a03860d508
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447787"
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

*Канал*\
Символ.

*ISTR*\
Поток.

*str*\
Строка.

*Val*\
Тип.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Примечания

Класс `basic_istream` также определяет несколько операторов извлечения. Дополнительные сведения см. в разделе [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

Функция-шаблон:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

извлекает до *N* − 1 элементов и сохраняет их в массив, начиная с _ *Str*. Если `Istr`. [width](../standard-library/ios-base-class.md#width) больше нуля, *N* имеет значение `Istr`. **Ширина**; в противном случае это размер самого крупного массива `Elem` , который может быть объявлен. Функция всегда сохраняет значение `Elem()` после извлеченных элементов, которые он хранит. Извлечение останавливается досрочно при достижении конца файла, на символе со значением **Elem**(0) (который не извлекается), или на любом элементе (который не извлекается), который будет отклонен [ws](../standard-library/istream-functions.md#ws). Если функция не извлекает ни один элемент, она вызывает `Istr`. [SetState](../standard-library/basic-ios-class.md#setstate) (**failbit**). В любом случае она вызывает `Istr`. **Ширина** (0) и возвращает *ISTR*.

**Примечание по безопасности** Строка, завершающаяся нулем, извлекаемая из входного потока, не должна превышать размер строки *целевого буфера.* Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

Функция-шаблон:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Извлекает элемент, если это возможно, и сохраняет его в *CH*. В противном случае она вызывает **is**. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае возвращается *ISTR*.

Функция-шаблон:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

Возвращает `Istr >> ( char * ) str`.

Функция-шаблон:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Функция-шаблон:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

Возвращает `Istr >> ( char * ) str`.

Функция-шаблон:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Функция-шаблон:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

Возвращает `Istr >> val` (и преобразует `Istr` ссылку rvalue в значение lvalue в процессе).

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
