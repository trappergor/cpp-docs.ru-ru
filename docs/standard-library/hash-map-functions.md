---
title: Функции &lt;hash_map&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 12ceb799ccf0944b8f0e8d48975da25c39f22505
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100954"
---
# <a name="lthashmapgt-functions"></a>Функции &lt;hash_map&gt;

|||
|-|-|
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  swap (hash_map)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Меняет местами элементы двух hash_map.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Hash_map, элементы которого должны быть заменены карты *левой*.

*left*<br/>
Hash_map, элементы которого должны быть заменены карты *правой*.

### <a name="remarks"></a>Примечания

Функция-шаблон является специальным алгоритмом для схемы hash_map класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="swap"></a>  swap

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_multimap](../standard-library/unordered-multimap-class.md).

Меняет местами элементы двух hash_multimap.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Hash_multimap, элементы которого должны быть заменены карты *левой*.

*left*<br/>
Hash_multimap, элементы которого должны быть заменены карты *правой*.

### <a name="remarks"></a>Примечания

Функция-шаблон является специальным алгоритмом для схемы hash_multimap класса контейнера для выполнения функции-члена `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **template \<class T> void swap(T&, T&)**, в файле заголовка алгоритма работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

## <a name="see-also"></a>См. также

[<hash_map>](../standard-library/hash-map.md)<br/>
