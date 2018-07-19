---
title: '&lt;string&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- string/std::<string>
- <string>
dev_langs:
- C++
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e341b15baa54b57148582c92beb9d231da8c96bb
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954575"
---
# <a name="ltstringgt"></a>&lt;string&gt;

Определяет класс шаблонов контейнеров `basic_string` и некоторые вспомогательные шаблоны.

Дополнительные сведения о классе `basic_string` см. в разделе [Класс basic_string](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Синтаксис

```cpp
#include <string>
```

## <a name="remarks"></a>Примечания

Язык C++ и библиотека Standard C++ поддерживают два типа строк:

- Массивы символов, оканчивающиеся нулевым символов, часто называют строками C.

- Объекты класса шаблонов типа `basic_string`, обрабатывающие все **char**-, такие как аргументы шаблона.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Тип, описывающий специализацию класса шаблона `basic_string` с элементами типа **char** как `string`.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Тип, описывающий специализацию класса шаблона `basic_string` с элементами типа **wchar_t** как `wstring`.|
|[u16string](../standard-library/string-typedefs.md#u16string)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char16_t`.|
|[u32string](../standard-library/string-typedefs.md#u32string)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char32_t`.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|-|-|
|[operator+](../standard-library/string-operators.md#op_add)|Сцепляет два строковых объекта.|
|[оператор!=](../standard-library/string-operators.md#op_neq)|Проверяет, что строковый объект слева от оператора не равен строковому объекту справа от оператора. |
|[оператор==](../standard-library/string-operators.md#op_eq_eq)|Проверяет, равен ли строковый объект слева от оператора строковому объекту справа от оператора.|
|[оператор<](../standard-library/string-operators.md#op_lt)|Проверяет, что строковый объект слева от оператора меньше строкового объекта справа от оператора.|
|[оператор<=](../standard-library/string-operators.md#op_lt_eq)|Проверяет, что строковый объект слева от оператора меньше или равен строковому объекту справа от оператора.|
|[оператор<\<](../standard-library/string-operators.md#op_lt_lt)|Функция шаблона, вставляющая строку в выходной поток.|
|[оператор>](../standard-library/string-operators.md#op_gt)|Проверяет, что строковый объект слева от оператора больше строкового объекта справа от оператора.|
|[оператор>=](../standard-library/string-operators.md#op_gt_eq)|Проверяет, что строковый объект слева от оператора больше или равен строковому объекту справа от оператора.|
|[оператор>>](../standard-library/string-operators.md#op_gt_gt)|Функция шаблона, извлекающая строку из входного потока.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|||
|-|-|
|[swap](../standard-library/string-functions.md#swap)|Меняет местами массивы символов двух строк.|
|[stod](../standard-library/string-functions.md#stod)|Преобразует последовательность символов **двойные**.|
|[stof](../standard-library/string-functions.md#stof)|Преобразует последовательность символов **float**.|
|[stoi](../standard-library/string-functions.md#stoi)|Преобразует последовательность символов в целое число.|
|[stold](../standard-library/string-functions.md#stold)|Преобразует последовательность символов **long double**.|
|[stoll](../standard-library/string-functions.md#stoll)|Преобразует последовательность символов **long long**.|
|[stoul](../standard-library/string-functions.md#stoul)|Преобразует последовательность символов **unsigned long**.|
|[stoull](../standard-library/string-functions.md#stoull)|Преобразует последовательность символов **long long без знака**.|
|[to_string](../standard-library/string-functions.md#to_string)|Преобразует значение в `string`.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Преобразует значение в двухбайтовое `string`.|

### <a name="functions"></a>Функции

|Функция|Описание:|
|-|-|
|[getline шаблона](../standard-library/string-functions.md#getline)|Извлекает строки из входного потока, последовательно по одной строке.|

### <a name="classes"></a>Классы

|Класс|Описание:|
|-|-|
|[Класс basic_string](../standard-library/basic-string-class.md)|Класс шаблона, описывающий объекты, которые могут хранить последовательность произвольных символьных объектов.|
|[Структура char_traits](../standard-library/char-traits-struct.md)|Класс шаблона, описывающий атрибуты, связанные с символом типа CharType|

### <a name="specializations"></a>Специализации

|||
|-|-|
|[Структура char_traits\<char>](../standard-library/char-traits-char-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType> к элементу типа `char`.|
|[Структура char_traits<wchar_t>](../standard-library/char-traits-wchar-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType> к элементу типа `wchar_t`.|
|[Структура char_traits<char16_t>](../standard-library/char-traits-char16-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType> к элементу типа `char16_t`.|
|[Структура char_traits<char32_t>](../standard-library/char-traits-char32-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType> к элементу типа `char32_t`.|

## <a name="requirements"></a>Требования

- **Заголовок:** \<string>

- **Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
