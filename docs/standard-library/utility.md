---
title: '&lt;utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 3e3904bda2a20392724f86df2443cd71a14a1ad6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525132"
---
# <a name="ltutilitygt"></a>&lt;utility&gt;

Определяет типы, функции и операторы стандартной библиотеки C++, которые помогают создавать пары объектов и управлять ими, что удобно, когда два объекта должны рассматриваться как один.

## <a name="syntax"></a>Синтаксис

```cpp
#include <utility>
```

## <a name="remarks"></a>Примечания

Пары широко используются в стандартной библиотеке C++. Они используются как аргументы и возвращаемые значения для различных функций и как типы элементов для контейнеров, таких как [класс map](../standard-library/map-class.md) и [класс multimap](../standard-library/multimap-class.md). \<map> автоматически включает заголовок \<utility> для управления их элементами, которые представляют собой пары "ключ — значение".

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Класс, который заключает в оболочку тип элемента `pair`.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Класс, который заключает в оболочку счетчик элементов `pair`.|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[forward](../standard-library/utility-functions.md#forward)|Не позволяет изменить ссылочный тип (`lvalue` или `rvalue`) аргумента при точной пересылке.|
|[get](../standard-library/utility-functions.md#get)|Функция, которая возвращает элемент из объекта `pair`.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Вспомогательная функция шаблона, которую можно использовать для построения объектов типа `pair` на основе типов данных, переданных в качестве параметров.|
|[move](../standard-library/utility-functions.md#move)|Возвращает переданный аргумент в виде ссылки `rvalue`.|
|[swap](../standard-library/utility-functions.md#swap)|Меняет местами элементы двух объектов `pair`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|Проверяет неравенство объекта pair слева от оператора объекту pair справа от оператора.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Проверяет равенство объекта pair слева от оператора объекту pair справа от оператора.|
|[оператор<](../standard-library/utility-operators.md#op_lt)|Проверяет, меньше ли объект pair слева от оператора объекта pair справа от оператора.|
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, что объект pair слева от оператора меньше или равен объекту pair справа от оператора.|
|[оператор>](../standard-library/utility-operators.md#op_gt)|Проверяет, больше ли объект pair слева от оператора объекта pair справа от оператора.|
|[оператор>=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, больше или равен ли объект pair слева от оператора объекту pair справа от оператора.|

### <a name="structs"></a>Структуры

|||
|-|-|
|[identity](../standard-library/identity-structure.md)||
|[pair](../standard-library/pair-structure.md)|Тип, позволяющий обрабатывать два объекта как один объект.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
