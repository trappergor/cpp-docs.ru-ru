---
title: Преобразования из целочисленных типов без знака
ms.date: 10/02/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: 3099f0113103223e392dc20560899b4a6e3ebf20
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998786"
---
# <a name="conversions-from-unsigned-integral-types"></a>Преобразования из целочисленных типов без знака

Если целое число без знака преобразуется в целочисленный тип или тип с плавающей запятой и при этом может быть представлено в результирующем типе, значение не изменяется.

При преобразовании целого числа без знака в целое число большего размера значение расширяется с дополнением нулями. При преобразовании в целое число меньшего размера старшие разряды усекаются. Результат интерпретируется как результирующий тип (см. пример).

```C
unsigned k = 65533;
short j;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

Если целое число без знака преобразуется в тип с плавающей запятой и при этом не может быть представлено точно в результирующем типе, результатом будет следующее более высокое или следующее более низкое представимое значение.

Сведения о размерах целочисленных типов и типов с плавающей запятой см. в статье [Хранение базовых типов](../c-language/storage-of-basic-types.md).

**Блок, относящийся только к системам Microsoft**

В компиляторе Майкрософт **unsigned** (или **unsigned int**) и **unsigned long** являются отдельными, но эквивалентными типами. Преобразование значения **unsigned int** выполняется так же, как и преобразование **unsigned long**.

**Завершение блока, относящегося только к системам Майкрософт**

В следующей таблице перечислены преобразования из целочисленных типов без знака.

## <a name="table-of-conversions-from-unsigned-integral-types"></a>Таблица преобразований из целочисленных типов без знака

|Исходный тип|Кому|Метод|
|----------|--------|------------|
|**unsigned char**|**char**|Сохранение битового шаблона; бит высокого порядка становится битом знака|
|**unsigned char**|**short**|Нулевое расширение|
|**unsigned char**|**long**|Нулевое расширение|
|**unsigned char**|**long long**|Нулевое расширение|
|**unsigned char**|**unsigned short**|Нулевое расширение|
|**unsigned char**|**unsigned long**|Нулевое расширение|
|**unsigned char**|**unsigned long long**|Нулевое расширение|
|**unsigned char**|**float**|Преобразование в значение **long**; преобразование значения **long** в значение **float**|
|**unsigned char**|**double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|
|**unsigned char**|**long double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|
|**unsigned short**|**char**|Сохранение байта низкого порядка|
|**unsigned short**|**short**|Сохранение битового шаблона; бит высокого порядка становится битом знака|
|**unsigned short**|**long**|Нулевое расширение|
|**unsigned short**|**long long**|Нулевое расширение|
|**unsigned short**|**unsigned char**|Сохранение байта низкого порядка|
|**unsigned short**|**unsigned long**|Нулевое расширение|
|**unsigned short**|**unsigned long long**|Нулевое расширение|
|**unsigned short**|**float**|Преобразование в значение **long**; преобразование значения **long** в значение **float**|
|**unsigned short**|**double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|
|**unsigned short**|**long double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|
|**unsigned long**|**char**|Сохранение байта низкого порядка|
|**unsigned long**|**short**|Сохранение слова низкого порядка|
|**unsigned long**|**long**|Сохранение битового шаблона; бит высокого порядка становится битом знака|
|**unsigned long**|**long long**|Нулевое расширение|
|**unsigned long**|**unsigned char**|Сохранение байта низкого порядка|
|**unsigned long**|**unsigned short**|Сохранение слова низкого порядка|
|**unsigned long**|**unsigned long long**|Нулевое расширение|
|**unsigned long**|**float**|Преобразование в значение **long**; преобразование значения **long** в значение **float**|
|**unsigned long**|**double**|Непосредственное преобразование в **double**|
|**unsigned long**|**long double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|
|**unsigned long long**|**char**|Сохранение байта низкого порядка|
|**unsigned long long**|**short**|Сохранение слова низкого порядка|
|**unsigned long long**|**long**|Сохранение младшего dword|
|**unsigned long long**|**long long**|Сохранение битового шаблона; бит высокого порядка становится битом знака|
|**unsigned long long**|**unsigned char**|Сохранение байта низкого порядка|
|**unsigned long long**|**unsigned short**|Сохранение слова низкого порядка|
|**unsigned long long**|**unsigned long**|Сохранение младшего dword|
|**unsigned long long**|**float**|Преобразование в значение **long**; преобразование значения **long** в значение **float**|
|**unsigned long long**|**double**|Непосредственное преобразование в **double**|
|**unsigned long long**|**long double**|Преобразование в значение **long**; преобразование значения **long** в значение **double**|

## <a name="see-also"></a>См. также

[Преобразования присваиваний](../c-language/assignment-conversions.md)
