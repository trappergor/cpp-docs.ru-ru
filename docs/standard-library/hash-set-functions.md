---
title: Функции &lt;hash_set&gt;
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: d7df6b3c5dc0d0d493d17b3e9995bc4758ffd6d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370588"
---
# <a name="lthash_setgt-functions"></a>Функции &lt;hash_set&gt;

|||
|-|-|
|[Своп](#swap)|[своп (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a><a name="swap"></a>Своп

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Выполняет обмен элементами между двумя объектами hash_set.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
В hash_set, предусматривающие обмен элементами, или hash_set элементы которой должны быть обменены на те из hash_set *слева.*

*Левой*\
В hash_set элементы которого должны быть обменяны с теми из hash_set *право*.

### <a name="remarks"></a>Remarks

Функция `swap` шаблона — это алгоритм, специализирующийся `left.`на`right`классе контейнеров hash_set для выполнения [своп](../standard-library/hash-set-class.md#swap)функции элемента (). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_set::swap](../standard-library/hash-set-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a>своп (hash_multiset)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Обменивает местами элементы двух объектов hash_multiset.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Hash_multiset предоставление элементов для замены, или hash_multiset, элементы которых должны быть обменены с теми из hash_multiset *слева*.

*Левой*\
Hash_multiset, элементы которого должны быть обменяны с теми из hash_multiset *правы.*

### <a name="remarks"></a>Remarks

Функция `swap` шаблона — это алгоритм, специализирующийся `left.`на`right`классе контейнеров hash_multiset для выполнения [своп](../standard-library/hash-multiset-class.md#swap)функции элемента (). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также раздел

[<hash_set>](../standard-library/hash-set.md)
