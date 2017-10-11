---
title: "Хранение базовых типов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4f510ce5459ec24a11996f02829e7d40d1ef9a37
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
