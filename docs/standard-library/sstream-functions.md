---
title: Функции &lt;sstream&gt;
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 707d35123797b84b2b7cef1d1cfd9005e4becb1c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425133"
---
# <a name="ltsstreamgt-functions"></a>Функции &lt;sstream&gt;

||
|-|
|[swap](#sstream_swap)|

## <a name="sstream_swap"></a>  swap

Меняет местами значения двух объектов `sstream`.

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*left*|Ссылка на объект `sstream`.|
|*right*|Ссылка на объект `sstream`.|

### <a name="remarks"></a>Remarks

Функция шаблона выполняет метод `left.swap(right)`.

## <a name="see-also"></a>См. также раздел

[\<sstream>](../standard-library/sstream.md)
