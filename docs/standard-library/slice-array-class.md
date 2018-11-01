---
title: Класс slice_array
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 9577447b2201c1c9e53192b99abad1979f45d15f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467221"
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

Класс описывает объект, который хранит ссылку на объект класса [valarray](../standard-library/valarray-class.md)**\<Type>** вместе с объектом класса [slice](../standard-library/slice-class.md), который описывает последовательность элементов для выбора из объекта **valarray\<Type**.

Класс шаблона создается неявно с помощью определенных операций valarray и не может использоваться непосредственно в программе. Оператор индекса среза использует внутренний вспомогательный класс шаблона:

`slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

При создании `slice_array<Type>` только путем написания выражения вида [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at), для среза `sl` объекта valarray `va`. Функции-члены класса slice_array ведут себя как соответствующие сигнатуры функций, заданные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов. Последовательность, управляемая классом slice_array, определяется тремя параметрами конструктора среза: индексом первого элемента в срезе, количеством элементов и расстоянием между элементами. Массив slice_array, вырезанный из valarray `va` объявленные **va**[ `slice`(2, 5, 3)] выбирает элементы с индексами 2, 5, 8, 11 и 14 из `va`. Чтобы процедура была действительной, индексы должны быть действительными.

## <a name="example"></a>Пример

Пример объявления и использования класса slice_array см. в разделе [slice::slice](../standard-library/slice-class.md#slice).

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
