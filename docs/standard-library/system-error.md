---
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: b9ddb3117afe37060b8013be235bdb11a2a031ac
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898856"
---
# <a name="ltsystem_errorgt"></a>&lt;system_error&gt;

Включите заголовок \<system_error >, чтобы определить класс исключений `system_error` и связанные шаблоны для обработки низкоуровневых системных ошибок.

## <a name="requirements"></a>Требования

**Заголовок:** \<system_error>

**Пространство имен:** std

## <a name="members"></a>Члены

### <a name="objects"></a>Объекты

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Представляет категорию общих ошибок.|
|[is_error_code_enum_v](../standard-library/system-error-functions.md#is_error_code_enum_v)||
|[is_error_condition_enum_v](../standard-library/system-error-functions.md#is_error_condition_enum_v)||
|[system_category](../standard-library/system-error-functions.md#system_category)|Представляет категорию ошибок, вызванных переполнением системы низкого уровня.|

### <a name="functions"></a>Функции

|||
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Создает объект `error_code`.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Создает объект `error_condition`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор==](../standard-library/system-error-operators.md#op_eq_eq)|Проверяет равенство объекта слева от оператора объекту справа от оператора.|
|[оператор!= ](../standard-library/system-error-operators.md#op_neq)|Проверяет неравенство объекта слева от оператора объекту справа от оператора.|
|[оператор<](../standard-library/system-error-operators.md#op_lt)|Проверяет, меньше ли какой-либо объект переданного для сравнения объекта.|
|[оператор<<](../standard-library/system-error-operators.md#op_ostream)||

### <a name="enums"></a>перечислениям;

|||
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|Предоставляет символьные имена для всех макросов кода ошибки, определенных POSIX в `<errno.h>`.|

### <a name="classes-and-structs"></a>Классы и структуры

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|Представляет абстрактный, общий базовый класс для объектов, который описывает категорию кодов ошибок.|
|[error_code](../standard-library/error-code-class.md)|Представляет системные ошибки низкого уровня, относящиеся к конкретной специализации.|
|[error_condition](../standard-library/error-condition-class.md)|Представляет коды ошибок, определенные пользователем.|
|[hash](../standard-library/hash-structure.md#system_error)||
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|Представляет тип предиката, проверяющий перечисление [Класс error_code](../standard-library/error-code-class.md).|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|Представляет тип предиката, проверяющий перечисление [Класс error_condition](../standard-library/error-condition-class.md).|
|[system_error](../standard-library/system-error-class.md)|Представляет базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.|

## <a name="see-also"></a>См. также:

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
