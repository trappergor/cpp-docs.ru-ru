---
title: Хранилище базовых типов
ms.date: 10/02/2019
helpviewer_keywords:
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
ms.openlocfilehash: 64c642df4dd85e4aa09f90a143b8aa67c28b7dc2
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998760"
---
# <a name="storage-of-basic-types"></a>Хранилище базовых типов

В следующей таблице перечислены хранилища, связанные с каждым базовым типом.

## <a name="sizes-of-fundamental-types"></a>Размеры фундаментальных типов

|Type|Хранилище|
|----------|-------------|
|**char**, **char без знака**, знак **со знаком**|1 байт|
|**short**, **unsigned short**|2 байта|
|**int**, **unsigned int**|4 байта|
|**long**, **unsigned long**|4 байта|
|длинная **длинная**, **беззнаковая** длинная|8 байт|
|**float**|4 байта|
|**double**|8 байт|
|**long double**|8 байт|

Типы данных C разделяются на общие категории. *Целочисленные типы* включают **int**, **char**, **Short**, **Long**и **Long**. Эти типы можно уточнять с помощью **знаков со знаком** **или без знака,** а **неподписанные** данные можно использовать в качестве краткой формы для **неподписанного целого числа**. Типы перечисления (**enum**) также обрабатываются как целочисленные типы для большинства целей. *Плавающие типы включают тип* **float**, **double**и **long double**. *Арифметические типы* включают все плавающие и целочисленные типы.

## <a name="see-also"></a>См. также

[Объявления и типы](../c-language/declarations-and-types.md)
