---
title: Хранение базовых типов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14c8483671e806adb9170429f2e17d4487de0cfd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090494"
---
# <a name="storage-of-basic-types"></a>Хранение базовых типов

В следующей таблице перечислены хранилища, связанные с каждым базовым типом.

### <a name="sizes-of-fundamental-types"></a>Размеры основных типов

|Тип|Хранилище|
|----------|-------------|
|`char`, `unsigned char`, **signed char**|1 байт|
|**short**, **unsigned short**|2 байта|
|`int`, `unsigned int`|4 байта|
|**long**, `unsigned long`|4 байта|
|**float**|4 байта|
|**double**|8 байт|
|`long double`|8 байт|

Типы данных C разделяются на общие категории. К "целочисленным" типам относятся `char`, `int`, **short**, **long**, **signed**, `unsigned` и `enum`. К типам "с плавающей запятой" относятся **float**, **double** и `long double`. Арифметические типы включают все целочисленные типы и типы с плавающей запятой.

## <a name="see-also"></a>См. также

[Объявления и типы](../c-language/declarations-and-types.md)