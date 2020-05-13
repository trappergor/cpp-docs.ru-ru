---
title: Функции &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 3d647c7b05a3868ec0359410cc0e703306b874ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363076"
---
# <a name="ltistreamgt-functions"></a>Функции &lt;istream&gt;

|||
|-|-|
|[Своп](#istream_swap)|[Ws](#ws)|

## <a name="swap"></a><a name="istream_swap"></a>Своп

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

*Левой*\
Поток.

*Правильно*\
Поток.

## <a name="ws"></a><a name="ws"></a>Ws

Пропускает пробелы в потоке.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Параметры

*_istr*\
Поток.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Remarks

Манипулятор извлекает и `ch` отбрасывает любые элементы, для которых [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**> > [(getloc).](../standard-library/ios-base-class.md#getloc) **is**( **ctype**\< **Elem**>:: **space**, **ch**) имеет значение true.

Функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) при обнаружении конца файла при извлечении элементов. Он *возвращается _Istr*.

### <a name="example"></a>Пример

См. раздел [оператор>>](../standard-library/istream-operators.md#op_gt_gt) с примером использования `ws`.

## <a name="see-also"></a>См. также раздел

[\<istream>](../standard-library/istream.md)
