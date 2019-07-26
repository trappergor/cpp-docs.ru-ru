---
title: Функции &lt;hash_map&gt;
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: efaa960d91c69d2157896adb4612c5dd36f00cff
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448737"
---
# <a name="lthashmapgt-functions"></a>Функции &lt;hash_map&gt;

|||
|-|-|
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  swap (hash_map)

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Меняет местами элементы двух hash_map.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект hash_map, элементы которого должны быть заменены на те, для которых необходимо использовать карту *слева*.

*слева*\
Объект hash_map, элементы которого должны быть заменены соответствующими элементами схемы *right*.

### <a name="remarks"></a>Примечания

Функция-шаблон является специальным алгоритмом для схемы hash_map класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/basic-ios-class.md#swap) *(right*). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)** , в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="swap"></a>  swap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_multimap](../standard-library/unordered-multimap-class.md).

Меняет местами элементы двух hash_multimap.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект hash_multimap, элементы которого должны быть заменены на те, для которых необходимо использовать карту *слева*.

*слева*\
Объект hash_multimap, элементы которого должны быть заменены соответствующими элементами схемы *right*.

### <a name="remarks"></a>Примечания

Функция-шаблон является специальным алгоритмом для схемы hash_multimap класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-multimap-class.md#swap) *(right*`)`. Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)** , в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="see-also"></a>См. также

[<hash_map>](../standard-library/hash-map.md)
