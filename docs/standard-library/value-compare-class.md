---
title: Класс value_compare
ms.date: 11/04/2016
f1_keywords:
- value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: 0e057a6229c903402a51b34a8f4e844e80ace187
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452371"
---
# <a name="valuecompare-class"></a>Класс value_compare

Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.

## <a name="syntax"></a>Синтаксис

```cpp
class value_compare
    : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
        const value_type& left,
        const value_type& right) const
    {
        return (comp(left.first, right.first));
    }

protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>Примечания

Критерий сравнения, предоставляемый value_compare `value_types` между целыми элементами, содержащимся в hash_map, вызывается путем сравнения ключей соответствующих элементов с помощью вспомогательной конструкции класса. Оператор функции-члена использует объект `comp` типа `key_compare` , хранящийся в объекте функции, предоставляемом функцией value_compare, для сравнения компонентов с ключевыми порядками сортировки двух элементов.

Для объектов hash_set и hash_multiset, которые представляют собой простые контейнеры, в которых значения ключей идентичны значениям элементов, value_compare эквивалентно `key_compare`; для объектов hash_map и hash_multimap это не так, так как элементы типа `pair` не эквивалентны значению ключа элемента.

## <a name="example"></a>Пример

Пример определения и использования value_compare см. в разделе [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp).

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Структура binary_function](../standard-library/binary-function-struct.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
