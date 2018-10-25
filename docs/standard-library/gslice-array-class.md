---
title: Класс gslice_array | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::gslice_array
dev_langs:
- C++
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f88957ac4c9ce14d05a71c266607e499c512541
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059042"
---
# <a name="gslicearray-class"></a>Класс gslice_array

Внутренний, вспомогательный класс шаблона, который поддерживает общие объекты срезов, предоставляя операции между массивами подмножеств, заданные общим срезом valarray.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class gslice_array : public gsplice {
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

Этот класс описывает объект, который хранит ссылку на объект `va` класса [valarray](../standard-library/valarray-class.md)**\<тип >**, вместе с объектом `gs` класса [ gslice](../standard-library/gslice-class.md) который описывает последовательность элементов для выбора из `valarray<Type>` объекта.

При создании `gslice_array<Type>` только путем написания выражения вида [va&#91;gs&#93;](../standard-library/valarray-class.md#op_at). Функции-члены класса gslice_array ведут себя как соответствующие сигнатуры функций, заданные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов.

Класс шаблона создается неявно с помощью определенных операций valarray и не может использоваться непосредственно в программе. Вместо этого оператором индекса среза используется внутренний вспомогательный класс шаблона:

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` ( **constgslice&**).

При создании `gslice_array<Type>` только путем написания выражения вида `va[gsl]`, для среза `gsl` объекта valarray `va`. Функции-члены класса gslice_array ведут себя как соответствующие сигнатуры функций, заданные для `valarray<Type>`, за исключением того, что затрагивается только последовательность выбранных элементов. Последовательность, управляемая классом gslice_array, определяется тремя параметрами конструктора среза: индексом первого элемента в первом срезе, количеством элементов в каждом срезе и расстояние между элементами в каждом срезе.

В следующем примере:

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

Чтобы процедура была действительной, индексы должны быть действительными.

## <a name="example"></a>Пример

Пример объявления и использования класса slice_array см. в разделе [gslice::gslice](../standard-library/gslice-class.md#gslice).

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
