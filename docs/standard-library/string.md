---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 80d5d297cc28cfb019dae99e9e9736e4b2eb654f
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957136"
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

- Объекты класса шаблона типа `basic_string`, которые обрабатывали все аргументы шаблона, аналогичные **символам**.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Тип, описывающий специализацию класса `basic_string` шаблона с элементами типа `string`char в виде.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Тип, описывающий специализацию класса `basic_string` шаблона с элементами типа `wstring`wchar_t в виде.|
|[u16string](../standard-library/string-typedefs.md#u16string)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char16_t`.|
|[u32string](../standard-library/string-typedefs.md#u32string)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char32_t`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator+](../standard-library/string-operators.md#op_add)|Сцепляет два строковых объекта.|
|[operator!=](../standard-library/string-operators.md#op_neq)|Проверяет, что строковый объект слева от оператора не равен строковому объекту справа от оператора.|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|Проверяет, равен ли строковый объект слева от оператора строковому объекту справа от оператора.|
|[оператор<](../standard-library/string-operators.md#op_lt)|Проверяет, что строковый объект слева от оператора меньше строкового объекта справа от оператора.|
|[оператор<=](../standard-library/string-operators.md#op_lt_eq)|Проверяет, что строковый объект слева от оператора меньше или равен строковому объекту справа от оператора.|
|[оператор<\<](../standard-library/string-operators.md#op_lt_lt)|Функция шаблона, вставляющая строку в выходной поток.|
|[оператор>](../standard-library/string-operators.md#op_gt)|Проверяет, что строковый объект слева от оператора больше строкового объекта справа от оператора.|
|[оператор>=](../standard-library/string-operators.md#op_gt_eq)|Проверяет, что строковый объект слева от оператора больше или равен строковому объекту справа от оператора.|
|[оператор>>](../standard-library/string-operators.md#op_gt_gt)|Функция шаблона, извлекающая строку из входного потока.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|||
|-|-|
|hash|Создает хэш строки.|
|[swap](../standard-library/string-functions.md#swap)|Меняет местами массивы символов двух строк.|
|[stod](../standard-library/string-functions.md#stod)|Преобразует последовательность символов в значение **типа Double**.|
|[stof](../standard-library/string-functions.md#stof)|Преобразует последовательность символов в тип **float**.|
|[stoi](../standard-library/string-functions.md#stoi)|Преобразует последовательность символов в целое число.|
|[stold](../standard-library/string-functions.md#stold)|Преобразует последовательность символов в длинное **Двойное**значение.|
|[stoll](../standard-library/string-functions.md#stoll)|Преобразует последовательность символов в длинную **длину**.|
|[stoul](../standard-library/string-functions.md#stoul)|Преобразует последовательность символов в **длину без знака**.|
|[stoull](../standard-library/string-functions.md#stoull)|Преобразует последовательность символов в длинную длину **без знака**.|
|[to_string](../standard-library/string-functions.md#to_string)|Преобразует значение в `string`.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Преобразует значение в двухбайтовое `string`.|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[Шаблон строки](../standard-library/string-functions.md#getline)|Извлекает строки из входного потока, последовательно по одной строке.|

### <a name="classes"></a>Классы

|Класс|Описание|
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

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
