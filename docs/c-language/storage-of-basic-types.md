---
title: "Хранение базовых типов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "арифметические операции [C++], типы"
  - "типы данных [C], описатели"
  - "типы данных [C], хранение"
  - "double - тип данных, хранение"
  - "числа с плавающей запятой, хранение"
  - "int - тип данных"
  - "целочисленные типы"
  - "целочисленные типы, хранение"
  - "long double - ключевое слово [C], хранение"
  - "long - ключевое слово [C]"
  - "short - тип данных"
  - "типы со знаком [C++], хранение"
  - "спецификаторы [C++], тип"
  - "хранение [C++], типы"
  - "сохранение типов [C++]"
  - "спецификаторы типов [C++], размеры"
  - "типы [C], арифметические"
  - "беззнаковые типы [C++], хранение"
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Хранение базовых типов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице перечислены хранилища, связанные с каждым базовым типом.  
  
### Размеры основных типов  
  
|Тип|Хранилище|  
|---------|---------------|  
|`char`, `unsigned char`, **signed char**|1 байт|  
|**short**, **unsigned short**|2 байта|  
|`int`, `unsigned int`|4 байта|  
|**long**, `unsigned long`|4 байта|  
|**float**|4 байта|  
|**double**|8 байт|  
|`long double`|8 байт|  
  
 Типы данных C разделяются на общие категории.  К целочисленным типам относятся `char`, `int`, **short**, **long**, **signed**, `unsigned` и `enum`.  К типам с плавающей запятой относятся **float**, **double** и `long double`.  Арифметические типы включают все целочисленные типы и типы с плавающей запятой.  
  
## См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)