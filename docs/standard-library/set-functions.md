---
title: Функции &lt;set&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: 7
manager: ghogen
ms.openlocfilehash: 29579adf6b9556635862985b324e27ebea416bc0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltsetgt-functions"></a>Функции &lt;set&gt;

|||
|-|-|
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|

## <a name="swap"></a>  swap  (map)

Обмен элементами между двумя наборами.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

`right` Набор, предоставляющий элементы, которые следует поменять местами или набор, элементы которого должны поменяться местами с элементами набора `left`.

`left` Набор, элементы которого должны поменяться местами с элементами набора `right`.

### <a name="remarks"></a>Примечания

Функция-шаблон является специальным алгоритмом, специализированным на классе контейнера, который настроен выполнять функцию-член `left.`[swap](../standard-library/set-class.md#swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

`template` \< **classT**> **void swap**( **T&**, **T&**)

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для класса-члена [set::swap](../standard-library/set-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="swap_multiset"></a>  swap  (multiset)

Меняет местами элементы двух мультинаборов.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

`right` Multiset, предоставляющий элементы, которые следует поменять местами или мультинабора, элементы которого должны поменяться местами с элементами мультинабор `left`.

`left` Multiset, элементы которого должны поменяться местами с элементами мультинабор `right`.

### <a name="remarks"></a>Примечания

Функция-шаблон является алгоритмом, специализированном на мультинаборе класса контейнеров для выполнения функции-члена `left.`[swap](../standard-library/multiset-class.md#swap)( `right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

`template` \< **classT**> **void swap**( **T&**, **T&**)

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для класса-члена [multiset::swap](../standard-library/multiset-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также

[\<set>](../standard-library/set.md)<br/>
