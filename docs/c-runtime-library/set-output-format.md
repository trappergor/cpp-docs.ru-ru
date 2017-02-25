---
title: "_set_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_output_format"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_output_format"
  - "_set_output_format"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_output_format - функция"
  - "_TWO_DIGIT_EXPONENT - константа"
  - "форматирование вывода"
  - "set_output_format - функция"
  - "TWO_DIGIT_EXPONENT - константа"
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _set_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Настраивает форматы вывода, которые используются форматированными функциями ввода\-вывода.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## Синтаксис  
  
```  
unsigned int _set_output_format(  
   unsigned int format  
);  
```  
  
#### Параметры  
 \[in\] `format`  
 Значение, представляющее используемый формат.  
  
## Возвращаемое значение  
 Предыдущий формат вывода.  
  
## Заметки  
 `_set_output_format` используется для настройки вывода форматированных функций ввода\-вывода, таких как [printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md). В настоящее время единственное соглашение о форматировании, которое эта функция может изменить, — число цифр показателя степени в числах с плавающей запятой.  
  
 По умолчанию такие функции, как `printf_s`, `wprintf_s` и связанные функции в стандартной библиотеке C Visual C\+\+, выводят три цифры в показателе степени, даже если значение показателя не требует третьей цифры. Нули используются для заполнения значения тремя цифрами.`_set_output_format` позволяет изменить это поведение, чтобы только две цифры выводились в показателе степени, если только значение показателя не требует третьей цифры.  
  
 Чтобы включить показатели степени с двумя цифрами, вызовите эту функцию с параметром `_TWO_DIGIT_EXPONENT`, как показано в примере. Чтобы отключить показатели степени с двумя цифрами, вызовите эту функцию с аргументом 0.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_output_format`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Пример  
  
```  
// crt_set_output_format.c #include <stdio.h> void printvalues(double x, double y) { printf_s("%11.4e %11.4e\n", x, y); printf_s("%11.4E %11.4E\n", x, y); printf_s("%11.4g %11.4g\n", x, y); printf_s("%11.4G %11.4G\n", x, y); } int main() { double x = 1.211E-5; double y = 2.3056E-112; unsigned int old_exponent_format; // Use the default format printvalues(x, y); // Enable two-digit exponent format old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT); printvalues(x, y); // Disable two-digit exponent format _set_output_format( old_exponent_format ); printvalues(x, y); }  
```  
  
```Output  
1,2110e-005 2,3056e-112 1,2110E-005 2,3056E-112 1,211e-005  2,306e-112 1,211E-005  2,306E-112 1,2110e-05 2,3056e-112 1,2110E-05 2,3056E-112 1,211e-05  2,306e-112 1,211E-05  2,306E-112 1,2110e-005 2,3056e-112 1,2110E-005 2,3056E-112 1,211e-005  2,306e-112 1,211E-005  2,306E-112  
```  
  
## См. также  
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)   
 [\_get\_output\_format](../c-runtime-library/get-output-format.md)