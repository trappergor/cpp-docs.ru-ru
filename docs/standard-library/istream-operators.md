---
title: Операторы &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 05b10c27d8e0cf4c0300bb307d8b7ceda43ddb2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413311"
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

*CH*<br/>
Символ.

*ISTR*<br/>
Поток.

*str*<br/>
Строка.

*Val*<br/>
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

извлекает до *N* − 1 элементов и сохраняет их в массив, начиная с _ *Str*. Если `Istr`. [width](../standard-library/ios-base-class.md#width) больше нуля, *N* имеет значение `Istr`. **Ширина**; в противном случае это будет размер самого большого массива из `Elem` , могут быть объявлены. Функция всегда сохраняет значение `Elem()` после сохранения всех извлеченных элементов сохраняется. Извлечение останавливается досрочно при достижении конца файла, на символе со значением **Elem**(0) (который не извлекается), или на любом элементе (который не извлекается), который будет отклонен [ws](../standard-library/istream-functions.md#ws). Если функция не извлекает ни один элемент, она вызывает `Istr`. [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае она вызывает `Istr`. **Ширина**(0) и возвращает *Istr*.

**Примечание по безопасности** нулем строка, извлекаемая из входного потока не должна превышать размер буфера назначения *str*. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

Функция-шаблон:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Извлекает элемент, в том случае, если он возможен и сохраняет его в *Ch*. В противном случае она вызывает **is**. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае он возвращает *Istr*.

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

Возвращает `Istr >> val` (и преобразует ссылка rvalue на `Istr` для lvalue в процессе).

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

[\<istream>](../standard-library/istream.md)<br/>
