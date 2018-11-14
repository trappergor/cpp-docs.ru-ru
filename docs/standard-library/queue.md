---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: ed1960dffa4bfe8b1ae4105f9f31943fa7a30212
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525059"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

Определяет классы шаблонов priority_queue и очереди, а также несколько вспомогательных шаблонов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <queue>
```

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/queue-operators.md#op_neq)|Проверяет неравенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор<](../standard-library/queue-operators.md#op_lt)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|Проверяет равенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор>](../standard-library/queue-operators.md#op_gt)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[оператор>=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс queue](../standard-library/queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к переднему и заднему элементам некоторого базового типа контейнера.|
|[Класс priority_queue](../standard-library/priority-queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к верхнему элементу некоторого базового типа контейнера, который всегда является самым большим.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
