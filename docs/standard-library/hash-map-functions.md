---
title: Функции &lt;hash_map&gt;
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 7cb2e46f19bd30e3eb313cde867c6a055cb8bca5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370617"
---
# <a name="lthash_mapgt-functions"></a>Функции &lt;hash_map&gt;

|||
|-|-|
|[Своп](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap-hash_map"></a><a name="swap_hash_map"></a>своп (hash_map)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Меняет местами элементы двух hash_map.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
В hash_map элементы которого должны быть обменяны с теми из карты *слева*.

*Левой*\
В hash_map, элементы которых должны быть обменяны с теми из карты *право*.

### <a name="remarks"></a>Remarks

Функция-шаблон является специальным алгоритмом для схемы hash_map класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="swap"></a><a name="swap"></a>Своп

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Меняет местами элементы двух hash_multimap.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Hash_multimap элементы которого должны быть обменяны с теми из карты *слева*.

*Левой*\
Hash_multimap, элементы которого должны быть обменяны с теми из карты *право*.

### <a name="remarks"></a>Remarks

Функция-шаблон является специальным алгоритмом для схемы hash_multimap класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="see-also"></a>См. также раздел

[<hash_map>](../standard-library/hash-map.md)
