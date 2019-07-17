---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: c73ad2ad94a5de29bc2c457fdf6ca8b9c783615c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268486"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Определяет необязательный класс шаблонов контейнеров и некоторые вспомогательные шаблоны.

## <a name="requirements"></a>Требования

**Заголовок:** \<необязательно >

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
> В дополнение к реляционной сравнивает \<необязательно > операторы также поддерживает сравнение с **nullopt** и `T`.

### <a name="functions"></a>Функции

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Делает объект необязательно.|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[hash]()||
|[необязательный класс](../standard-library/optional-class.md)|Описывает объект, который может или не может содержать значение.|
|[nullopt_t структуры](../standard-library/nullopt-t-structure.md)|Описывает объект, не удерживающие значение.|
|[Класс bad_optional_access](../standard-library/bad-optional-access-class.md)|Описывает объект, формировать исключение сообщить о попытке получить доступ к значение не существует.|

### <a name="objects"></a>Объекты

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
