---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: 2e46b3997096c6e61f7dd6140131e3f10223b8e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399425"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Определяет шаблон `tuple`, экземпляры которого содержат объекты различных типов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <tuple>
```

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[tuple](../standard-library/tuple-class.md)|Создает последовательность элементов фиксированной длины.|
|[Класс tuple_element](../standard-library/tuple-element-class-tuple.md)|Заключает в оболочку тип элемента `tuple`.|
|[Класс tuple_size](../standard-library/tuple-size-class-tuple.md)|Создает оболочку для счетчика элементов `tuple`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Сравнение объектов `tuple`, равенство|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Сравнение объектов `tuple`, неравенство|
|[оператор<](../standard-library/tuple-operators.md#op_lt)|Сравнение объектов `tuple`, меньше|
|[оператор<=](../standard-library/tuple-operators.md#op_lt_eq)|Сравнение объектов `tuple`, меньше или равно|
|[оператор>](../standard-library/tuple-operators.md#op_gt)|Сравнение объектов `tuple`, больше|
|[оператор>=](../standard-library/tuple-operators.md#op_gt_eq)|Сравнение объектов `tuple`, больше или равно|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|Возвращает элемент из объекта `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Создает `tuple` из значений элементов.|
|[tie](../standard-library/tuple-functions.md#tie)|Создает `tuple` из ссылок на элементы.|

## <a name="see-also"></a>См. также

[\<array>](../standard-library/array.md)<br/>
