---
title: Класс value_compare
ms.date: 11/04/2016
f1_keywords:
- value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: 4b7fff1bef091a9d47e6ea4dc0e53e86ce39ad7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627439"
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

Критерии сравнения, предоставляемом value_compare между `value_types` всех элементов, содержащихся в объекте hash_map, вытекают из сравнения между ключами соответствующих элементов во вспомогательном классе. Оператор функции-члена использует объект `comp` типа `key_compare` хранящиеся в объекте функции, предоставляемые для сравнения ключей сортировки компонентов для двух элементов.

Для объектов hash_set и hash_multiset, которые представляют собой простые контейнеры, в которых значения ключей идентичны значениям элементов, value_compare эквивалентно `key_compare`; для объектов hash_map и hash_multimap это не так, так как элементы типа `pair` не эквивалентны значению ключа элемента.

## <a name="example"></a>Пример

Пример определения и использования value_compare см. в разделе [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp).

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Структура binary_function](../standard-library/binary-function-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
