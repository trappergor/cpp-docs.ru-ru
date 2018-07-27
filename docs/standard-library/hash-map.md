---
title: '&lt;hash_map&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caae1a52c36c5d21e55e90a821b280f2face7ede
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959778"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Этот заголовок устарел. Вместо этого [ \<unordered_map >](unordered-map.md).

Определяет контейнер шаблонных классов hash_map и hash_multimap и их поддерживаемые шаблоны.

## <a name="syntax"></a>Синтаксис

> #<a name="include-hashmap"></a>включить < hash_map >

### <a name="operators"></a>Операторы

|Версия hash_map|Версия hash_multimap|Описание:|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[Operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Проверяет неравенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|
|[ operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[ operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Проверяет равенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|Версия hash_map|Версия hash_multimap|Описание:|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Меняет местами элементы двух объектов hash_map или hash_multimap.|

### <a name="classes"></a>Классы

|Класс|Описание:|
|-|-|
|[Класс hash_compare](hash-compare-class.md)|Описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash_map hash_multimap, hash_set или hash_multiset — по умолчанию `Traits` объект параметра для упорядочивания и хэширования элементов в них.|
|[Класс value_compare](value-compare-class.md)|Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.|
|[Класс hash_map](hash-map-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет отсортированный уникальный ключ и связанное с ним значение.|
|[Класс hash_multimap](hash-multimap-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет ключ, значение которого не должно быть уникальным, и связанное с ним значение.|

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Ссылки на файлы заголовков](cpp-standard-library-header-files.md)
[потокобезопасность в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)
[Справочник по библиотеке C++ Standard](cpp-standard-library-reference.md)
