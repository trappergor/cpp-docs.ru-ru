---
title: Класс hash
ms.date: 11/04/2016
f1_keywords:
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
- thread/std::hash
- typeindex/std::hash
- vector/std::hash
- XSTDDEF/std::hash
- xstring/std::hash
helpviewer_keywords:
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
ms.openlocfilehash: 61446ab6b79496024d44a99fcf5f500bb871bb80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448818"
---
# <a name="hash-class"></a>Класс hash

Вычисляет хэш-код для значения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct hash {
    size_t operator()(Ty val) const;
};
```

## <a name="remarks"></a>Примечания

Объект функции определяет хэш-функцию для сопоставления значений типа *Ty* с распределением значений индекса. Элемент `operator()` возвращает хэш-код для *val*, который можно использовать с классами шаблонов для `unordered_map`, `unordered_multimap`, `unordered_set` и `unordered_multiset`. Стандартная библиотека предоставляет специализации для базовых типов: *Ty* может быть любым скалярным типом, включая типы указателей и типы перечислений. Кроме того, имеются специализации для типов библиотек `string`, `wstring`, `u16string`, `u32string`, `string_view`, `wstring_view`, `u16string_view`, `u32string_view`, `bitset`, `error_code`, `error_condition`, `optional`, `shared_ptr`, `thread`, `type_index`, `unique_ptr`, `variant` и `vector<bool>`.

## <a name="example"></a>Пример

```cpp
// std__functional__hash.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <unordered_set>

int main()
    {
    std::unordered_set<int, std::hash<int> > c0;
    c0.insert(3);
    std::cout << *c0.find(3) << std::endl;

    return (0);
    }
```

```Output
3
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<unordered_map>](../standard-library/unordered-map.md)\
[Класс unordered_multimap](../standard-library/unordered-multimap-class.md)\
[Класс unordered_multiset](../standard-library/unordered-multiset-class.md)\
[<unordered_set>](../standard-library/unordered-set.md)
