---
title: Класс hash_compare
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 4fb44a371630a66275f6ef59a0bf66b4cb73a71f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689560"
---
# <a name="hash_compare-class"></a>Класс hash_compare

Шаблон класса описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash_map, hash_multimap, hash_set или hash_multiset — как **объект параметров** признаков по умолчанию для упорядочивания и хэширования содержащихся в них элементов.

## <a name="syntax"></a>Синтаксис

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Заметки

Каждый ассоциативный хэш-контейнер хранит объект-признаки типа `Traits` (параметр шаблона). Можно наследовать класс от специализации hash_compare, чтобы выборочно переопределить некоторые функции и объекты, или можно предоставить собственную версию этого класса, если выполняются определенные минимальные требования. В частности, для объекта hash_comp типа `hash_compare<Key, Traits>` для перечисленных выше контейнеров требуется следующее поведение:

- Для всех значений `key` типа `Key` вызов **hash_comp**(`key`) выступает в качестве хэш-функции, которая выдает распределение значений типа `size_t`. Функция, предоставленная hash_compare, возвращает `key`.

- Для любого значения `key1` типа `Key`, который предшествует `key2` в последовательности и имеет то же значение хэша (значение, возвращаемое хэш-функцией), **hash_comp**(`key2`, `key1`) имеет значение false. Функция должна выложить общее упорядочивание значений типа `Key`. Функция, предоставляемая функцией hash_compare, возвращает *comp*(`key2`, `key1`) `,`, где *comp* — это сохраненный объект типа `Traits`, который можно указать при построении объекта hash_comp. Для типа параметра `Traits` по умолчанию `less<Key>` ключи сортировки никогда не уменьшаются в значении.

- Целочисленная константа `bucket_size` указывает среднее количество элементов на "сегмент" (запись хэш-таблицы), которые контейнер должен не превысить. Это значение должно быть больше нуля. Значение, предоставленное hash_compare, равно 4.

- Целочисленная константа `min_buckets` указывает минимальное количество контейнеров, которые должны храниться в хэш-таблице. Оно должно быть степенью числа два и больше нуля. Значение, предоставленное hash_compare, равно 8.

## <a name="example"></a>Пример

Примеры объявления и использования hash_compare см. в примерах [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) и [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset).

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
