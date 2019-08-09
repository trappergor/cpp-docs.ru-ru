---
title: Класс slice_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: cf33c5f627a88698c84947f9b803edaebccf5566
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450404"
---
# <a name="slicearray-class"></a>Класс slice_array

Внутренний, вспомогательный класс шаблона, который поддерживает объекты срезов, предоставляя операции между массивами подмножеств, заданные срезом valarray.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class slice_array : public slice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;
    void operator=(const Type& x) const;
    void operator*=(const valarray<Type>& x) const;
    void operator/=(const valarray<Type>& x) const;
    void operator%=(const valarray<Type>& x) const;
    void operator+=(const valarray<Type>& x) const;
    void operator-=(const valarray<Type>& x) const;
    void operator^=(const valarray<Type>& x) const;
    void operator&=(const valarray<Type>& x) const;
    void operator|=(const valarray<Type>& x) const;
    void operator<<=(const valarray<Type>& x) const;
    void operator>>=(const valarray<Type>& x) const;
    // The rest is private or implementation defined
}
```

## <a name="remarks"></a>Примечания

Класс описывает объект, который хранит ссылку на объект класса [valarray](../standard-library/valarray-class.md) **\<Type>** вместе с объектом класса [slice](../standard-library/slice-class.md), который описывает последовательность элементов для выбора из объекта **valarray\<Type**.

Класс шаблона создается неявно с помощью определенных операций valarray и не может использоваться непосредственно в программе. Оператор индекса среза использует внутренний вспомогательный класс шаблона:

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

`slice_array<Type>` Объект создается только путем написания выражения формы с форматом `sl` [&#91;SL&#93;](../standard-library/valarray-class.md#op_at), для среза valarray `va`. Функции-члены класса slice_array ведут себя так же, как и соответствующие сигнатуры `valarray<Type>`функций, определенные для, за исключением того, что затрагивается только последовательность выбранных элементов. Последовательность, управляемая классом slice_array, определяется тремя параметрами конструктора среза: индексом первого элемента в срезе, количеством элементов и расстоянием между элементами. Slice_array вырезание из valarray `va` , объявленного по `slice` **ва**[(2, 5, 3)], выбирает элементы с индексами 2, 5, 8, 11 `va`и 14 от. Чтобы процедура была действительной, индексы должны быть действительными.

## <a name="example"></a>Пример

Пример объявления и использования класса slice_array см. в разделе [slice::slice](../standard-library/slice-class.md#slice).

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
