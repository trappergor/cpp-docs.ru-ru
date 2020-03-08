---
title: Функции &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 8d93e46b0323058d93c6d0bd8c1ee566998aef61
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874840"
---
# <a name="ltostreamgt-functions"></a>Функции &lt;ostream&gt;

Это глобальные функции шаблонов, определенные в &lt;ostream&gt;. Сведения о функциях элементов см. в документации по [классу basic_ostream](basic-ostream-class.md) .

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

Завершает строку и очищает буфер.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элемента.

*Ostr*\
Объект типа **basic_ostream**.

*Tr*\
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *OSTR*. [Размещение](../standard-library/basic-ostream-class.md#put)(*OSTR*.[ Расширьте](../standard-library/basic-ios-class.md#widen)(' \n ')), а затем вызывает *OSTR*. [Сброс](../standard-library/basic-ostream-class.md#flush). Он возвращает *OSTR*.

### <a name="example"></a>Пример

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>концы

Завершает строку.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элемента.

*Ostr*\
Объект типа `basic_ostream`.

*Tr*\
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *OSTR*. [Размещение](../standard-library/basic-ostream-class.md#put)(*elem*(' \ 0 ')). Он возвращает *OSTR*.

### <a name="example"></a>Пример

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

Очищает буфер.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элемента.

*Ostr*\
Объект типа `basic_ostream`.

*Tr*\
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *OSTR*. [Сброс](../standard-library/basic-ostream-class.md#flush). Он возвращает *OSTR*.

### <a name="example"></a>Пример

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

Меняет местами значения двух объектов `basic_ostream`.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элемента.

*Tr*\
Признаки символа.

*left*\
Ссылка lvalue на объект `basic_ostream`.

*справа*\
Ссылка lvalue на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Функция шаблона `swap` выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также:

[\<ostream>](../standard-library/ostream.md)
