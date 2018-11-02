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
ms.openlocfilehash: fa498f4acbb151eab4321bcddc6af027ee266237
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636778"
---
# <a name="ltostreamgt-functions"></a>Функции &lt;ostream&gt;

Это глобальный шаблон функции, определенные в &lt;ostream&gt;. Для функций-членов см. в разделе [класс basic_ostream](basic-ostream-class.md) документации.

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

*Elem*<br/>
Тип элемента.

*Ostr*<br/>
Объект типа **basic_ostream**.

*Tr*<br/>
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ расширить](../standard-library/basic-ios-class.md#widen)(«\n»)), а затем вызывает *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

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

*Elem*<br/>
Тип элемента.

*Ostr*<br/>
Объект типа `basic_ostream`.

*Tr*<br/>
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Elem*(«\0»)). Он возвращает *Ostr*.

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

*Elem*<br/>
Тип элемента.

*Ostr*<br/>
Объект типа `basic_ostream`.

*Tr*<br/>
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Манипулятор вызывает *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

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

*Elem*<br/>
Тип элемента.

*Tr*<br/>
Признаки символа.

*left*<br/>
Ссылка lvalue на объект `basic_ostream`.

*right*<br/>
Ссылка lvalue на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Функция шаблона `swap` выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)
