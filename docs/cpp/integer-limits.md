---
title: "Пределы целых чисел | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- LIMITS.H header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 67240b24df0c741a2441e17ebe9908c05bfca9f3
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="integer-limits"></a>Пределы целых чисел
**Блок, относящийся только к системам Майкрософт**  
  
 Ограничения для целочисленных типов представлены в следующей таблице. Эти ограничения также определены в стандартном файле заголовка LIMITS.H.  
  
### <a name="limits-on-integer-constants"></a>Ограничения для целочисленных констант  
  
|Константа|Значение|Значение|  
|--------------|-------------|-----------|  
|**CHAR_BIT**|Количество битов в наименьшей переменной, которая не является битовым полем.|8|  
|**SCHAR_MIN**|Минимальное значение для переменной типа **signed char**.|–128|  
|**SCHAR_MAX**|Максимальное значение для переменной типа **signed char**.|127|  
|**UCHAR_MAX**|Максимальное значение для переменной типа `unsigned char`.|255 (0xff)|  
|**CHAR_MIN**|Минимальное значение для переменной типа `char`.|–128 (или 0, если используется параметр /J)|  
|**CHAR_MAX**|Максимальное значение для переменной типа `char`.|–127 (или 255, если используется параметр /J)|  
|**MB_LEN_MAX**|Максимальное количество байтов в многосимвольной константе.|5|  
|**SHRT_MIN**|Минимальное значение для переменной типа **short**.|-32768|  
|**SHRT_MAX**|Максимальное значение для переменной типа **short**.|32767|  
|**USHRT_MAX**|Максимальное значение для переменной типа **unsigned short**.|65 535 (0xffff)|  
|**INT_MIN**|Минимальное значение для переменной типа `int`.|-2147483648|  
|**INT_MAX**|Максимальное значение для переменной типа `int`.|2147483647|  
|**UINT_MAX**|Максимальное значение для переменной типа `unsigned int`.|4 294 967 295 (0xffffffff)|  
|**LONG_MIN**|Минимальное значение для переменной типа **long**.|-2147483648|  
|**LONG_MAX**|Максимальное значение для переменной типа **long**.|2147483647|  
|**ULONG_MAX**|Максимальное значение для переменной типа `unsigned long`.|4 294 967 295 (0xffffffff)|  
|**_I64_MIN**|Минимальное значение для переменной типа `__int64`|-9223372036854775808|  
|**_I64_MAX**|Максимальное значение для переменной типа `__int64`|9223372036854775807|  
|**_UI64_MAX**|Максимальное значение для переменной типа **unsigned __int64**|18446744073709551615 (0xffffffffffffffff)|  
  
 Если значение превышает максимально возможное представление целочисленного типа, компилятор Microsoft выдает ошибку.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Пределы чисел с плавающей запятой](../cpp/floating-limits.md)
