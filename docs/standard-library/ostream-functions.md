---
title: "Функции &lt;ostream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 4693e33563048807cdef1c81cb4d47d4fb455137
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt-functions"></a>Функции &lt;ostream&gt;

Это глобальный шаблон функции, определенные в &lt;ostream&gt;. Для функций-членов, в разделе [класс basic_ostream](basic-ostream-class.md) документации.

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

*Elem*  
Тип элемента.

*Ostr*  
Объект типа **basic_ostream**.

*Tr*  
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ Увеличьте ширину](../standard-library/basic-ios-class.md#widen)(«\n»)), а затем вызывает *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

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

*Elem*  
Тип элемента.

*Ostr*  
Объект типа **basic_ostream**.

*Tr*  
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Elem*(«\0»)). Он возвращает *Ostr*.

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

*Elem*  
Тип элемента.

*Ostr*  
Объект типа **basic_ostream**.

*Tr*  
Признаки символа.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

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

Меняет местами значения двух **basic_ostream** объектов.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Параметры

*Elem*  
Тип элемента.

*Tr*  
Признаки символа.

*left*  
Ссылка lvalue на **basic_ostream** объекта.

*right*  
Ссылка lvalue на **basic_ostream** объекта.

### <a name="remarks"></a>Примечания

Функция шаблона **swap** выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)  
