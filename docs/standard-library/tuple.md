---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: a391a77ea65a203a7eddde12046c5df89a77194a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447158"
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
|[tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|`tuple` Сравнение объектов, равное.|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|`tuple` Сравнение объектов, не равно.|
|[оператор<](../standard-library/tuple-operators.md#op_lt)|`tuple` Сравнение объектов, меньше.|
|[оператор<=](../standard-library/tuple-operators.md#op_lt_eq)|`tuple` Сравнение объектов, меньше или равно.|
|[оператор>](../standard-library/tuple-operators.md#op_gt)|`tuple` Сравнение объектов, большее, чем.|
|[оператор>=](../standard-library/tuple-operators.md#op_gt_eq)|`tuple` Сравнение объектов, больше или равно.|

### <a name="functions"></a>Функции

|||
|-|-|
|[apply](../standard-library/tuple-functions.md#apply)|Вызывает функцию с кортежем.|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|Конструирует кортеж ссылок.|
|[get](../standard-library/tuple-functions.md#get)|Возвращает элемент из объекта `tuple`.|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|Краткая форма для создания `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Создает `tuple` из значений элементов.|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|Создает `tuple` из ссылок на элементы.|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|Конструирует объект кортежа с диапазоном элементов типа.|

## <a name="see-also"></a>См. также

[\<array>](../standard-library/array.md)
