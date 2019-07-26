---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 83a0ad52735f92d731dafb32ad1be5a8278776b4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447186"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Определяет класс шаблона контейнера необязательно и несколько вспомогательных шаблонов.

## <a name="requirements"></a>Требования

**Заголовок:** \<необязательный >

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Проверяет равенство объекта `optional` слева от оператора объекту `optional` справа от оператора.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|Проверяет неравенство объекта `optional` слева от оператора объекту `optional` справа от оператора.|
|[оператор<](../standard-library/optional-operators.md#op_lt)|Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.|
|[оператор<=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.|
|[оператор>](../standard-library/optional-operators.md#op_gt)|Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.|
|[оператор>=](../standard-library/optional-operators.md#op_lt_eq)|Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.|

> [!NOTE]
> Помимо реляционных сравнений, \<необязательные > операторы также поддерживают сравнение с **нуллопт** и `T`.

### <a name="functions"></a>Функции

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Делает объект необязательным.|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[hash]()||
|[необязательный класс](../standard-library/optional-class.md)|Описывает объект, который может или не может содержать значение.|
|[Структура nullopt_t](../standard-library/nullopt-t-structure.md)|Описывает объект, который не удерживает значение.|
|[Класс bad_optional_access](../standard-library/bad-optional-access-class.md)|Описывает объект, вызываемый как исключение для сообщения о попытке доступа к значению, которое отсутствует.|

### <a name="objects"></a>Объекты

|||
|-|-|
|[нуллопт](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
