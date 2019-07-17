---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: ce6e005990d05676fb20752b5808d32ec88dd7b3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241541"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Определяет шаблон `tuple`, экземпляры которого содержат объекты различных типов.

## <a name="requirements"></a>Требования

**Заголовок:** \<tuple>

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[Класс tuple](../standard-library/tuple-class.md)|Создает последовательность элементов фиксированной длины.|
|[Класс tuple_element](../standard-library/tuple-element-class-tuple.md)|Заключает в оболочку тип элемента `tuple`.|
|[Класс tuple_size](../standard-library/tuple-size-class-tuple.md)|Создает оболочку для счетчика элементов `tuple`.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>Объекты

|||
|-|-|
|[псевдоним типа tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Сравнение `tuple` объектов, равенство.|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Сравнение `tuple` объектов, неравенство.|
|[оператор<](../standard-library/tuple-operators.md#op_lt)|Сравнение `tuple` объектов, меньше.|
|[оператор<=](../standard-library/tuple-operators.md#op_lt_eq)|Сравнение `tuple` объектов, меньше или равно.|
|[оператор>](../standard-library/tuple-operators.md#op_gt)|Сравнение `tuple` объектов, больше.|
|[оператор>=](../standard-library/tuple-operators.md#op_gt_eq)|Сравнение `tuple` объектов, больше или равно.|

### <a name="functions"></a>Функции

|||
|-|-|
|[apply](../standard-library/tuple-functions.md#apply)|Вызывает функцию с кортеж.|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|Создает кортеж из ссылки.|
|[get](../standard-library/tuple-functions.md#get)|Возвращает элемент из объекта `tuple`.|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|Сокращение, чтобы сделать `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Создает `tuple` из значений элементов.|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|Создает `tuple` из ссылок на элементы.|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|Создает объект кортежа с использованием ряда элементов типа.|

## <a name="see-also"></a>См. также

[\<array>](../standard-library/array.md)<br/>
