---
title: Функции &lt;hash_set&gt;
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 2fbc05c16ba6629397bbb07bab30cb9315a16e1f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883851"
---
# <a name="lthash_setgt-functions"></a>Функции &lt;hash_set&gt;

|||
|-|-|
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  swap

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_set](../standard-library/unordered-set-class.md).

Выполняет обмен элементами между двумя объектами hash_set.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*справа*\
Hash_set, предоставляющая элементы для переключения, или hash_set, элементы которого должны быть заменены элементами hash_set *Left*.

*left*\
Hash_set, элементы которой должны быть заменены элементами hash_set *right*.

### <a name="remarks"></a>Remarks

Функция шаблона `swap` — это алгоритм, специализированный для класса контейнера hash_set для выполнения функции-члена `left.`[Swap](../standard-library/hash-set-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_set::swap](../standard-library/hash-set-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="swap_hash_multiset"></a>  swap (hash_multiset)

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_set](../standard-library/unordered-set-class.md).

Меняет местами элементы двух объектов hash_multiset.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*справа*\
Hash_multiset, предоставляющая элементы для переключения, или hash_multiset, элементы которого должны быть заменены элементами hash_multiset *Left*.

*left*\
Hash_multiset, элементы которой должны быть заменены элементами hash_multiset *right*.

### <a name="remarks"></a>Remarks

Функция шаблона `swap` — это алгоритм, специализированный для класса контейнера hash_multiset для выполнения функции-члена `left.`[Swap](../standard-library/hash-multiset-class.md#swap)(`right`). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона

**template \<class T> void swap(T&, T&),**

в классе алгоритма работает путем назначения и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также раздел

[<hash_set>](../standard-library/hash-set.md)
