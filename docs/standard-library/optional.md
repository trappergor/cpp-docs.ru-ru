---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: bce31811c98d351f3c561b3136d41f7ed23d13e0
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687260"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Определяет шаблон класса контейнера `optional` и несколько вспомогательных шаблонов.

## <a name="requirements"></a>Требования

**Заголовок:** \<optional >

**Пространство имен:** std

## <a name="members"></a>Члены

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор==](../standard-library/optional-operators.md#op_eq_eq)|Проверяет, равен ли объект другому объекту.|
|[оператор!= ](../standard-library/optional-operators.md#op_neq)|Проверяет, не равен ли объект другому объекту.|
|[оператор<](../standard-library/optional-operators.md#op_lt)|Проверяет, что объект слева меньше объекта справа.|
|[оператор<=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева меньше или равен объекту справа.|
|[оператор>](../standard-library/optional-operators.md#op_gt)|Проверяет, что объект слева больше объекта справа.|
|[оператор>=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, что объект слева больше или равен объекту справа.|

> [!NOTE]
> В дополнение к реляционным сравнениям \<optional операторы > также поддерживают сравнение с **нуллопт** и `T`.

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
