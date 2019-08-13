---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: f3b4896a3cb4774e46b36480dd9769fa131fc287
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957178"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Определяет класс шаблонов контейнеров `optional` и некоторые вспомогательные шаблоны.

## <a name="requirements"></a>Требования

**Заголовок:** \<необязательный >

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Проверяет, равен ли объект другому объекту.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|Проверяет, не равен ли объект другому объекту.|
|[оператор<](../standard-library/optional-operators.md#op_lt)|Проверяет, что объект слева меньше объекта справа.|
|[оператор<=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева меньше или равен объекту справа.|
|[оператор>](../standard-library/optional-operators.md#op_gt)|Проверяет, что объект слева больше объекта справа.|
|[оператор>=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева больше или равен объекту справа.|

> [!NOTE]
> Помимо реляционных сравнений, \<необязательные > операторы также поддерживают сравнение с **нуллопт** и `T`.

### <a name="functions"></a>Функции

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Делает объект необязательным.|
|[swap](../standard-library/optional-functions.md#swap)|Меняет местами содержащиеся значения двух `optional` объектов.|

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|hash|Возвращает хэш содержащегося объекта.|
|[необязательный класс](../standard-library/optional-class.md)|Описывает объект, который может или не может содержать значение.|
|[Структура nullopt_t](../standard-library/nullopt-t-structure.md)|Описывает объект, который не удерживает значение.|
|[класс bad_optional_access](../standard-library/bad-optional-access-class.md)|Описывает объект, вызываемый как исключение для сообщения о попытке доступа к значению, которое отсутствует.|

### <a name="objects"></a>Объекты

|||
|-|-|
|[нуллопт](../standard-library/optional-functions.md#nullopt)|Экземпляр `nullopt_t` для сравнений.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
