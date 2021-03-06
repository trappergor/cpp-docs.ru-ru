---
title: Пределы целых чисел в C и C++
ms.date: 10/21/2019
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: 1484b43719696578be437909351e24a550ec9869
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217120"
---
# <a name="c-and-c-integer-limits"></a>Пределы целых чисел в C и C++

**Блок, относящийся только к системам Microsoft**

Ограничения для целочисленных типов в C и C++ представлены в следующей таблице. Эти ограничения заданы в стандартном файле заголовка C `<limits.h>`. Стандартный файл заголовка C++ `<limits>` содержит `<climits>`, который включает в себя `<limits.h>`.

В Microsoft C также допускается объявление целочисленных переменных с указанием размера, которые относятся к целочисленным типам с размером 8, 16, 32 или 64 бит. Дополнительные сведения о них см. в статье [Целочисленные типы с указанием размера](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Ограничения для целочисленных констант

|**Константа**|Значение|Значение|
|------------------|-------------|-----------|
|**CHAR_BIT**|Количество битов в наименьшей переменной, которая не является битовым полем.|8|
|**SCHAR_MIN**|Минимальное значение для переменной типа **`signed char`** .|–128|
|**SCHAR_MAX**|Максимальное значение для переменной типа **`signed char`** .|127|
|**UCHAR_MAX**|Максимальное значение для переменной типа **`unsigned char`** .|255 (0xff)|
|**CHAR_MIN**|Минимальное значение для переменной типа **`char`** .|–128 (или 0, если используется параметр /J)|
|**CHAR_MAX**|Максимальное значение для переменной типа **`char`** .|–127 (или 255, если используется параметр /J)|
|**MB_LEN_MAX**|Максимальное количество байтов в многосимвольной константе.|5|
|**SHRT_MIN**|Минимальное значение для переменной типа **`short`** .|-32768|
|**SHRT_MAX**|Максимальное значение для переменной типа **`short`** .|32767|
|**USHRT_MAX**|Максимальное значение для переменной типа **`unsigned short`** .|65 535 (0xffff)|
|**INT_MIN**|Минимальное значение для переменной типа **`int`** .|-2147483647 - 1|
|**INT_MAX**|Максимальное значение для переменной типа **`int`** .|2147483647|
|**UINT_MAX**|Максимальное значение для переменной типа **`unsigned int`** .|4 294 967 295 (0xffffffff)|
|**LONG_MIN**|Минимальное значение для переменной типа **`long`** .|-2147483647 - 1|
|**LONG_MAX**|Максимальное значение для переменной типа **`long`** .|2147483647|
|**ULONG_MAX**|Максимальное значение для переменной типа **`unsigned long`** .|4 294 967 295 (0xffffffff)|
|**LLONG_MIN**|Минимальное значение для переменной типа **`long long`** .|–9 223 372 036 854 775 807 – 1|
|**LLONG_MAX**|Максимальное значение для переменной типа **`long long`** .|9 223 372 036 854 775 807|
|**ULLONG_MAX**|Максимальное значение для переменной типа **`unsigned long long`** .|18 446 744 073 709 551 615 (0xffffffffffffffff)|

Если значение превышает максимально возможное представление целочисленного типа, компилятор Microsoft выдает ошибку.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Целочисленные константы в C](../c-language/c-integer-constants.md)
