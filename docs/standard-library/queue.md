---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: ee35f880ddf40561cacb5c4d519f2e6291ad77a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689118"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

Определяет шаблоны классов priority_queue и Queue и несколько вспомогательных шаблонов.

## <a name="requirements"></a>Требования

**Заголовок:** \<queue>

**Пространство имен:** std

> [!NOTE]
> Библиотека \<queue > также использует инструкцию `#include <initializer_list>`.

## <a name="members"></a>Члены

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор!= ](../standard-library/queue-operators.md#op_neq)|Проверяет неравенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор<](../standard-library/queue-operators.md#op_lt)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|
|[оператор==](../standard-library/queue-operators.md#op_eq_eq)|Проверяет равенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор>](../standard-library/queue-operators.md#op_gt)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[оператор>=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс queue](../standard-library/queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к переднему и заднему элементам некоторого базового типа контейнера.|
|[Класс priority_queue](../standard-library/priority-queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к верхнему элементу некоторого базового типа контейнера, который всегда является самым большим.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
