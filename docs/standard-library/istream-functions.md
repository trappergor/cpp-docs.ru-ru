---
title: Функции &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: fc512558969bc25d2b16afa2b93219e13d0b28ca
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458764"
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

*слева*\
Поток.

*Правильно*\
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

### <a name="remarks"></a>Примечания

Манипулятор извлекает и отбрасывает все элементы `ch`, для которого [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**) имеет значение true.

Функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) при обнаружении конца файла при извлечении элементов. Он возвращает *_Istr*.

### <a name="example"></a>Пример

См. раздел [оператор>>](../standard-library/istream-operators.md#op_gt_gt) с примером использования `ws`.

## <a name="see-also"></a>См. также

[\<istream>](../standard-library/istream.md)
