---
title: Функции &lt;hash_set&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: ad8041ff6a4abab84272d2bbbdee290bfce4eff6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961881"
---
# <a name="lthashsetgt-functions"></a>Функции &lt;hash_set&gt;

|||
|-|-|
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  swap

> [!NOTE]
> Этот элемент API устарел. Альтернатива — [класс unordered_set](../standard-library/unordered-set-class.md).

Выполняет обмен элементами между двумя объектами hash_set.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*правом* hash_set, предоставляющий элементы для обмена местами, или hash_set, элементы которого должны быть заменены hash_set *левой*.

*слева* hash_set, элементы которого должны быть заменены hash_set *правой*.

### <a name="remarks"></a>Примечания

`swap` Функция-шаблон является специальным алгоритмом для hash_set класса контейнера для выполнения функции-члена `left.` [замены](../standard-library/hash-set-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_set::swap](../standard-library/hash-set-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="swap_hash_multiset"></a>  swap (hash_multiset)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Меняет местами элементы двух объектов hash_multiset.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*правом* hash_multiset, предоставляющий элементы для обмена местами, или hash_multiset, элементы которого должны быть заменены объекта hash_multiset *левой*.

*слева* hash_multiset, элементы которого должны быть заменены объекта hash_multiset *правой*.

### <a name="remarks"></a>Примечания

`swap` Функция-шаблон является специальным алгоритмом для объекта hash_multiset класса контейнера для выполнения функции-члена `left.` [замены](../standard-library/hash-multiset-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также

[<hash_set>](../standard-library/hash-set.md)<br/>
