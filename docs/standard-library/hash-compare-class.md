---
title: Класс hash_compare | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92dce97754eccc8cd4f618db3ac3e23574fb54ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956586"
---
# <a name="hashcompare-class"></a>Класс hash_compare

Этот класс шаблона описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash_map hash_multimap, hash_set или hash_multiset — в качестве объекта параметра **Traits** по умолчанию для упорядочивания и хэширования элементов, которые он содержит.

## <a name="syntax"></a>Синтаксис

class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Примечания

Каждый ассоциативный контейнер хэша хранит объект признаков хэша типа `Traits` (параметр шаблона). Можно наследовать класс от специализации hash_compare, чтобы выборочно переопределить некоторые функции и объекты, или можно предоставить собственную версию этого класса, если выполняются определенные минимальные требования. В частности, для объекта hash_comp типа `hash_compare<Key, Traits>`, указанные выше контейнеры требуется следующее поведение:

- Для всех значений `key` типа `Key`, вызов **hash_comp**(`key`) служит хэш-функцией, которая создает распределение значений типа `size_t`. Функция, предоставленная hash_compare, возвращает `key`.

- Для любого значения `key1` типа `Key` , предшествующий `key2` в последовательности и имеет те же хэш-значение (возвращенное хэш-функции), **hash_comp**(`key2`, `key1`) имеет значение false. Функция должна применить общее упорядочивание к значениям типа `Key`. Функция, предоставленная hash_compare возвращает *comp*(`key2`, `key1`) `,` где *comp* — это хранимый объект типа `Traits` , можно указать, когда вы Создание объекта hash_comp. По умолчанию `Traits` тип параметра `less<Key>`, ключи сортировки никогда не уменьшаются.

- Целочисленная константа `bucket_size` указывает среднее количество элементов на «сегмент» (запись в хэш таблице), контейнер старайтесь не должно превышать. Это значение должно быть больше нуля. Значение, предоставленное hash_compare, равно 4.

- Целочисленная константа `min_buckets` указывает минимальное количество сегментов в хэш-таблице. Оно должно быть степенью числа два и больше нуля. Значение, предоставленное hash_compare, равно 8.

## <a name="example"></a>Пример

Примеры объявления и использования hash_compare см. в примерах [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) и [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset).

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
