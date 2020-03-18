---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: 6b67434d36146de87a124fc02f49971425943dc5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447275"
---
# <a name="ltlistgt"></a>&lt;list&gt;

Определяет список шаблонов классов контейнеров и несколько вспомогательных шаблонов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <list>
```

> [!NOTE]
> Библиотека \<списка > также использует инструкцию `#include <initializer_list>`.

## <a name="members"></a>Члены

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|Проверяет неравенство объекта-списка слева от оператора объекту-списку справа от оператора.|
|[оператор<](../standard-library/list-operators.md#op_lt)|Проверяет, меньше ли объект-список слева от оператора, чем объект-список справа от оператора.|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|Проверяет, что объект-список слева от оператора меньше или равен объекту-списку справа от оператора.|
|[operator==](../standard-library/list-operators.md#op_eq_eq)|Проверяет, равен ли объект-список слева от оператора объекту-списку справа от оператора.|
|[operator>](../standard-library/list-operators.md#op_gt)|Проверяет, больше ли объект-список слева от оператора, чем объект-список справа от оператора.|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|Проверяет, что объект-список слева от оператора больше или равен объекту-списку справа от оператора.|

### <a name="functions"></a>Функции

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|Меняет местами элементы двух списков.|

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс list](../standard-library/list-class.md)|Шаблон класса последовательностей контейнеров, который сохраняет свои элементы в линейном упорядочении и позволяет выполнять операции вставки и удаления в любом расположении в последовательности.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
