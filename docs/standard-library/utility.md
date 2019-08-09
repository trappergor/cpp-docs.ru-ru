---
title: '&lt;utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: eaae94bcffcda6e113001dd7070bcc80e7c14d09
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458077"
---
# <a name="ltutilitygt"></a>&lt;utility&gt;

Определяет типы, функции и операторы стандартной библиотеки C++, которые помогают создавать пары объектов и управлять ими, что удобно, когда два объекта должны рассматриваться как один.

## <a name="requirements"></a>Требования

**Заголовок:** \<utility>

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Пары широко используются в стандартной библиотеке C++. Они используются как аргументы и возвращаемые значения для различных функций и как типы элементов для контейнеров, таких как [класс map](../standard-library/map-class.md) и [класс multimap](../standard-library/multimap-class.md). \<map> автоматически включает заголовок \<utility> для управления их элементами, которые представляют собой пары "ключ — значение".

> [!NOTE]
> Заголовок служебной > использует инструкцию `#include <initializer_list>`. \< Он также ссылается `class tuple` как определено в \<> кортежа.

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|||
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|Формат с плавающей запятой для преобразования примитивных чисел.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Класс, который заключает в оболочку тип элемента `pair`.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Класс, который заключает в оболочку счетчик элементов `pair`.|

### <a name="objects"></a>Объекты

|||
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)||
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)||
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)||
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)||

### <a name="functions"></a>Функции

|||
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|Возвращает тип.|
|[деклвал](../standard-library/utility-functions.md#declval)|Вычисление сокращенного выражения.|
|[exchange](../standard-library/utility-functions.md#exchange)|Присваивает новое значение объекту и возвращает его старое значение.|
|[forward](../standard-library/utility-functions.md#forward)|Не позволяет изменить ссылочный тип (`lvalue` или `rvalue`) аргумента при точной пересылке.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|Функция, которая возвращает элемент из объекта `pair`.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Вспомогательная функция шаблона, которую можно использовать для построения объектов типа `pair` на основе типов данных, переданных в качестве параметров.|
|[move](../standard-library/utility-functions.md#move)|Возвращает переданный аргумент в виде ссылки `rvalue`.|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[swap](../standard-library/utility-functions.md#swap)|Меняет местами элементы двух объектов `pair`.|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Преобразует значение в символьную строку.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|Проверяет неравенство объекта pair слева от оператора объекту pair справа от оператора.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Проверяет равенство объекта pair слева от оператора объекту pair справа от оператора.|
|[оператор\<](../standard-library/utility-operators.md#op_lt)|Проверяет, меньше ли объект pair слева от оператора объекта pair справа от оператора.|
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, что объект pair слева от оператора меньше или равен объекту pair справа от оператора.|
|[оператор>](../standard-library/utility-operators.md#op_gt)|Проверяет, больше ли объект pair слева от оператора объекта pair справа от оператора.|
|[оператор>=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, больше или равен ли объект pair слева от оператора объекту pair справа от оператора.|

### <a name="structs"></a>Структуры

|||
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|Структура, используемая `from_chars`для.|
|[identity](../standard-library/identity-structure.md)|Структура, предоставляющая определение типа как параметр шаблона.|
|[in_place_t](../standard-library/in-place-t-struct.md)|Также включает структуры `in_place_type_t` и `in_place_index_t`.|
|[integer_sequence](../standard-library/integer-sequence-class.md)|Представляет последовательность целых чисел.|
|[pair](../standard-library/pair-structure.md)|Тип, позволяющий обрабатывать два объекта как один объект.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Тип, используемый для сохранения отдельного конструктора и перегрузки функции.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|Структура, используемая `to_chars`для.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
