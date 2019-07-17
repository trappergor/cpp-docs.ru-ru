---
title: '&lt;Variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 7a812ccc3c8cb2a660c01ad2b17ea75b5d5c9542
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268446"
---
# <a name="ltvariantgt"></a>&lt;Variant&gt;

Variant-объект содержит и управляет значение. Если вариант содержит значение, это значение тип должен быть одним из типов аргументов шаблона, присвоенный variant. Эти аргументы шаблона, называются альтернативные варианты.

## <a name="requirements"></a>Требования

**Заголовок:** \<variant >

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator==](../standard-library/forward-list-operators.md#op_eq_eq)|Проверяет объект variant слева от оператора равен объекту variant справа от оператора.|
|[operator!=](../standard-library/forward-list-operators.md#op_neq)|Проверяет объект variant слева от оператора не равен объекту variant справа от оператора.|
|[оператор<](../standard-library/forward-list-operators.md#op_lt)|Проверяет variant-объект в левой части оператора меньше, чем variant объект справа от оператора.|
|[оператор<=](../standard-library/forward-list-operators.md#op_lt_eq)|Проверяет, вариант объект слева от оператора меньше или равен объекту variant справа от оператора.|
|[оператор>](../standard-library/forward-list-operators.md#op_gt)|Проверяет объект variant слева от оператора больше объекта variant справа от оператора.|
|[оператор>=](../standard-library/forward-list-operators.md#op_lt_eq)|Проверяет объект variant слева от оператора больше или равен объекту variant справа от оператора.|

### <a name="functions"></a>Функции

|||
|-|-|
|[get](../standard-library/variant-functions.md#get)|Возвращает разновидность объекта.|
|[get_if](../standard-library/variant-functions.md#get_if)|Получает тип variant объекта, если он существует.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|Вернуть **true** Если существует variant.|
|[swap](../standard-library/variant-functions.md#swap)|Меняет местами **variant**.|
|[посетите](../standard-library/variant-functions.md#visit)|Переходит к следующему **variant**.|

### <a name="classes"></a>Классы

|||
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Объекты, создаваемых для отчета недопустимое обращается к значению объекта variant.|
|[Variant](../standard-library/variant.md)|Объект, либо содержать значение одного из альтернативных типов, либо не имеет значения.|

### <a name="structs"></a>Структуры

|||
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|Альтернативный тип для типа variant делает конструируемым по умолчанию тип variant.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Используется для объектов типа variant.|
|[variant_size](../standard-library/variant-size-structure.md)|Используется для объектов типа variant.|

### <a name="objects"></a>Объекты

|||
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
