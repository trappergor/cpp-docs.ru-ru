---
title: "strtold, _strtold_l, wcstold, _wcstold_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstold"
  - "strtold"
  - "_strtold_l"
  - "_wcstold_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstold_l"
  - "_wcstold_l"
  - "_tcstold"
  - "strtold"
  - "_strtold_l"
  - "wcstold"
dev_langs: 
  - "C++"
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# strtold, _strtold_l, wcstold, _wcstold_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строки в длинное значение удвоенной точности с плавающей запятой.  
  
## Синтаксис  
  
```  
long double strtold(  
   const char *nptr,  
   char **endptr   
);  
long double _strtold_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
long double wcstold(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
long double wcstold_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `nptr`  
 Строка, заканчивающаяся нулевым символом, для преобразования.  
  
 `endptr`  
 Указатель на символ, который останавливает сканирование.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `strtold` возвращает значение числа с плавающей запятой как `long double`, за исключением тех случаев, когда такое представление вызывает переполнение, в этом случае функция возвращает \+\/–`HUGE_VALL`.  Символ `HUGE_VALL` соответствует знаку значения, которое невозможно представить.  `strtold` возвращает 0, если преобразование не может быть выполнено, или происходит потеря точности.  
  
 `wcstold` возвращает значения аналогично `strtold`.  Для обеих функций `errno` присваивается значение `ERANGE`, если возникает переполнение или потеря точности и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая функция преобразует входную строку `nptr` в `long double`.  Функция `strtold` преобразует `nptr` к длинному значению двойной точности.  `strtold` прекращает чтение строки `nptr` на первом знаке, который она не может распознать как часть числа.  Это может быть конечный символ null.  версия двухбайтового символа `strtold` — `wcstold`; ее аргумент `nptr` — строка двухбайтовых символов.  В противном случае эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstold`|`strtold`|`strtold`|`wcstold`|  
|`_tcstold_l`|`_strtold_l`|`_strtold_l`|`_wcstold_l`|  
  
 Параметр категории `LC_NUMERIC` текущего языкового стандарта определяет распознавание символа системы счисления в `nptr`.  Для получения дополнительной информации см. [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции без суффикса `_l` они текущий языковой стандарт; `_strtold_l` и `_wcstold_l` идентичны `_strtold` и `_wcstold`, но используют переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если значение параметра `endptr` отлично от `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, сохраняется в расположении, на которое указывает параметр `endptr`.  Если выполнить преобразование невозможно \(не были найдены допустимые цифры, или было указано недопустимое основание\), значение `nptr` сохраняется в расположении, на которое указывает параметр `endptr`.  
  
 `strtold` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace` может включать в себя пробелы и знаки табуляции, которые игнорируются; `sign` — плюс \(`+`\) или минус \(`–`\); `digits` — одна или несколько десятичных цифр.  Если перед символом системы счисления нет цифр, то после него должна быть хотя бы одна цифра.  За десятичными цифрами может следовать Экспонента, которая состоит из вводной буквы \(`d`, `D`, `e` или `E`\) и, при необходимости, целого числа со знаком.  Если нет ни экспоненциальной части, ни символа системы счисления, то предполагается, что символ системы счисления следует за последней цифрой в строке.  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtold`, `_strtold_l`|\<stdlib.h\>|  
|`wcstold`, `_wcstold_l`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strtold.c  
// Build with: cl /W4 /Tc crt_strtold.c  
// This program uses strtold to convert a  
// string to a long double-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   long double x;  
  
   string = "3.1415926535898This stopped it";  
   x = strtold(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtold = %.13Lf\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
  **string \= 3.1415926535898This stopped it**  
 **strtold \= 3,1415926535898**  
 **Сканирование остановлено в: это остановило его**   
## Эквивалент в .NET Framework  
 [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)