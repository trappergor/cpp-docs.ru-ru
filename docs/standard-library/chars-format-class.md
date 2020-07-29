---
title: Перечисление chars_format
ms.date: 07/22/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: 4c1d495c943be02b66d52d1986a783b29a8009c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230186"
---
# <a name="chars_format-enum"></a>Перечисление chars_format

Используется с [\<charconv>](charconv.md) библиотекой для указания формата с плавающей запятой для числовых преобразований типа "примитив".

## <a name="syntax"></a>Синтаксис

```cpp
enum class chars_format {
    scientific = unspecified,
    fixed = unspecified,
    hex = unspecified,
    general = fixed | scientific
};
```

### <a name="members"></a>Участники

|Элемент|Описание|
|-|-|
| `scientific` | Приводит `from_chars()` к ожиданию и синтаксическому анализу экспоненты. Он похож на `'e'` `printf()` описатель формата, который форматируется для экспоненциального представления, например`"1.729e+01"` |
| `fixed` | `from_chars()`Не приводит к ожиданиям или синтаксическому анализу экспоненты. Он похож на `'f'` `printf()` описатель формата, который форматирует для операций с плавающей запятой, например `"17.29"` .|
| `hex` | Вызывает `from_chars()` Ожидание числа в шестнадцатеричном формате без начального символа "0x". |
| `general` | Приводит к тому, `from_chars()` что функция принимает (но не требует) показатель степени. Для `to_chars()` он похож на `g` описатель формата printf (), который переключается между экспоненциальной нотацией или фиксированным форматом. Он учитывает, что может быть экспонентой для создания достаточно компактного вывода. Например: `1e-5` результаты в `"1e-05"` , но `1e-4` результат `"0.001"` . `1e5`приводит к результату `100000` , а `1e6` в результате `1e+06` . `1e0`создает `1` .|

## <a name="remarks"></a>Remarks

Для функций [from_chars](charconv-functions.md#from_chars) это перечисление описывает предполагаемый тип входных данных.
Для функций [to_chars](charconv-functions.md#to_chars) он описывает, какой тип выходных данных следует выдавать.

## <a name="see-also"></a>См. также статью

[\<charconv>](../standard-library/charconv.md)  
[описатели формата printf ()](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
