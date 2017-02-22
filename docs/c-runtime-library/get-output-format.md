---
title: "_get_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_output_format"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_output_format"
  - "_get_output_format"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_output_format - функция"
  - "get_output_format - функция"
  - "форматирование вывода"
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _get_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает текущее значение флага формата вывода.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## Синтаксис  
  
```  
unsigned int _get_output_format();  
```  
  
## Возвращаемое значение  
 Текущее значение флага формата вывода.  
  
## Заметки  
 Флаг формата вывода задает особенности форматированного ввода\-вывода. В настоящее время флаг имеет два возможных значения: 0 и `_TWO_DIGIT_EXPONENT`. Если установлено значение `_TWO_DIGIT_EXPONENT`, числа с плавающей запятой выводятся только с двумя цифрами в показателе степени, если только значение показателя не требует третьей цифры. Если флаг равен нулю, то числа с плавающей запятой выводятся с тремя цифрами в показателе степени; при необходимости значение дополняется до трех цифр нулями.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_output_format`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)