---
title: Функции &lt;ostream&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 494c750ec80000ef9090824e0436f6e443593847
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107618"
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
