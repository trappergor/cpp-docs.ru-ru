---
title: Класс slice_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 358348a57b823fcea82cd296967c83778819361d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688963"
---
# <a name="slice_array-class"></a>Класс slice_array

Внутренний, вспомогательный шаблон класса, поддерживающий объекты-срезы путем предоставления операций между массивами подмножества, определяемыми срезом valarray.

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

## <a name="remarks"></a>Заметки

Класс описывает объект, который хранит ссылку на объект класса [valarray](../standard-library/valarray-class.md) **\<Type>** вместе с объектом класса [slice](../standard-library/slice-class.md), который описывает последовательность элементов для выбора из объекта **valarray\<Type**.

Шаблон класса создается косвенно определенными valarray операциями и не может использоваться непосредственно в программе. Внутренний, вспомогательный шаблон класса, используемый оператором подстрочного индекса:

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

Объект `slice_array<Type>` создается только путем написания выражения формы с форматом [&#91;SL&#93;](../standard-library/valarray-class.md#op_at), для среза `sl` valarray `va`. Функции-члены класса slice_array ведут себя так же, как и соответствующие сигнатуры функций, определенные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов. Последовательность, управляемая классом slice_array, определяется тремя параметрами конструктора среза: индексом первого элемента в срезе, количеством элементов и расстоянием между элементами. Slice_array, вырезаемый из valarray `va` объявленный по **ва**[`slice` (2, 5, 3)], выбирает элементы с индексами 2, 5, 8, 11 и 14 от `va`. Чтобы процедура была действительной, индексы должны быть действительными.

## <a name="example"></a>Пример

Пример объявления и использования класса slice_array см. в разделе [slice::slice](../standard-library/slice-class.md#slice).

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
