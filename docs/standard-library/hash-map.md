---
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: 5a7ea891a314d69b8bc3378edce9fa0de2d89ace
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159500"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Этот заголовок устарел. Вместо этого [ \<unordered_map >](unordered-map.md).

Определяет контейнер шаблонных классов hash_map и hash_multimap и их поддерживаемые шаблоны.

## <a name="syntax"></a>Синтаксис

```
#include <hash_map>
```

### <a name="operators"></a>Операторы

|Версия hash_map|Версия hash_multimap|Описание|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Проверяет неравенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|
|[ operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[ operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Проверяет равенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|Версия hash_map|Версия hash_multimap|Описание|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Меняет местами элементы двух объектов hash_map или hash_multimap.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс hash_compare](hash-compare-class.md)|Описывает объект, который может использоваться любым ассоциативным контейнером хэша — hash_map hash_multimap, hash_set или hash_multiset — по умолчанию `Traits` объект параметра для упорядочивания и хэширования элементов в них.|
|[Класс value_compare](value-compare-class.md)|Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.|
|[Класс hash_map](hash-map-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет отсортированный уникальный ключ и связанное с ним значение.|
|[Класс hash_multimap](hash-multimap-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет ключ, значение которого не должно быть уникальным, и связанное с ним значение.|

## <a name="requirements"></a>Требования

**Заголовок:** \<hash_map>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](cpp-standard-library-reference.md)
