---
title: Диапазоны типов данных
ms.date: 05/07/2019
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
ms.openlocfilehash: 43eb5f34bc587e3ce86532c56d393da3e07c1b03
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301565"
---
# <a name="data-type-ranges"></a>Диапазоны типов данных

Компиляторы C++ Microsoft 32-bit и 64-bit распознают типы в таблице далее в этой статье.

- `int` (`unsigned int`)

- `__int8` (`unsigned __int8`)

- `__int16` (`unsigned __int16`)

- `__int32` (`unsigned __int32`)

- `__int64` (`unsigned __int64`)

- `short` (`unsigned short`)

- `long` (`unsigned long`)

- `long` `long` (`unsigned long long`)

Если имя начинается с двух символов подчеркивания (`__`), тип данных является нестандартным.

Диапазоны, представленные в следующей таблице, включают указанные значения.

|Имя типа|Байт|Другие имена|Диапазон значений|
|---------------|-----------|-----------------|---------------------|
|**int**|4|**signed**|От -2 147 483 648 до 2 147 483 647|
|**unsigned int**|4|**unsigned**|От 0 до 4 294 967 295|
|**__int8**|1|**char**|От -128 до 127|
|**неподписанный __int8**|1|**unsigned char**|От 0 до 255|
|**__int16**|2|**Short, короткое** **целое**, **короткое целое число со знаком**|От -32 768 до 32 767|
|**неподписанный __int16**|2|**короткое число без знака**, **короткое целое без знака**|От 0 до 65 535|
|**__int32**|4|**со знаком**, **целое число со знаком**, **целое** число|От -2 147 483 648 до 2 147 483 647|
|**неподписанный __int32**|4|**Неподписанное** **целое** число без знака|От 0 до 4 294 967 295|
|**__int64**|8|**длинный длинный** **знак** Long|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|
|**unsigned __int64**|8|**длинное целое без знака**|От 0 до 18 446 744 073 709 551 615|
|**bool**|1|Нет|**false** или **true**|
|**char**|1|Нет|от-128 до 127 по умолчанию<br /><br /> При компиляции при помощи [/J](../build/reference/j-default-char-type-is-unsigned.md) — от 0 до 255|
|**знак со знаком**|1|Нет|От -128 до 127|
|**unsigned char**|1|Нет|От 0 до 255|
|**short**|2|короткое **целое,** **короткое целое со знаком**|От -32 768 до 32 767|
|**unsigned short**|2|**unsigned short int**|От 0 до 65 535|
|**long**|4|**long int**, **длинное целое число со знаком**|От -2 147 483 648 до 2 147 483 647|
|**unsigned long**|4|**unsigned long int**|От 0 до 4 294 967 295|
|**long long**|8|нет (но эквивалентно **__int64**)|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|
|**длинное целое без знака**|8|нет (но эквивалентно **неподписанному __int64**)|От 0 до 18 446 744 073 709 551 615|
|**enum**|Возможны разные варианты|Нет| |
|**float**|4|Нет|3,4E +/- 38 (7 знаков)|
|**double**|8|Нет|1,7E +/- 308 (15 знаков)|
|**long double**|то же, что и **Double**|Нет|То же, что и **Double**|
|**wchar_t**|2|**__wchar_t**|От 0 до 65 535|

В зависимости от того, как он используется, переменная **__wchar_t** обозначает либо тип расширенных символов, либо многобайтовый символ. Чтобы указать константу расширенного символьного типа, перед символьной или строковой константой следует использовать префикс `L` .

знаки **со знаком** и **без знака** — это модификаторы, которые можно использовать с любым целочисленным типом, кроме **bool**. Обратите внимание **, что char, знак** **char**и **неподписанный символ** — это три различных типа для таких механизмов, как перегрузка и шаблоны.

**Целочисленные** и **неподписанные типы int** имеют размер четыре байта. Однако переносимый код не должен зависеть от размера **int** , так как языковой стандарт позволяет реализовать его в зависимости от реализации.

C и C++ в Visual Studio также поддерживают целочисленные типы с указанием размера. Дополнительные сведения см. в разделах [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) и [Пределы целых чисел](../cpp/integer-limits.md).

Дополнительные сведения об ограничениях размеров каждого типа см. [в разделе Встроенные типы](../cpp/fundamental-types-cpp.md).

Диапазон перечисляемых типов зависит от контекста языка и указанных флажков компилятора. Дополнительные сведения см. в статьях [Объявления перечислений C](../c-language/c-enumeration-declarations.md) и [Объявления перечислений C++](../cpp/enumerations-cpp.md).

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)