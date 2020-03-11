---
title: Функции &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: fc512558969bc25d2b16afa2b93219e13d0b28ca
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874842"
---
# <a name="ltistreamgt-functions"></a>Функции &lt;istream&gt;

|||
|-|-|
|[swap](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  swap

Меняет местами элементы двух объектов-потоков.

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Поток.

*справа*\
Поток.

## <a name="ws"></a>  ws

Пропускает пробелы в потоке.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Параметры

*_Istr*\
Поток.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Remarks

Манипулятор извлекает и удаляет все элементы `ch`, для которых [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)). **имеет**значение ( **ctype**\< **elem**>:: **Space**, **CH**) равно true.

Функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) при обнаружении конца файла при извлечении элементов. Он возвращает *_Istr*.

### <a name="example"></a>Пример

См. раздел [оператор>>](../standard-library/istream-operators.md#op_gt_gt) с примером использования `ws`.

## <a name="see-also"></a>См. также раздел

[\<istream>](../standard-library/istream.md)
