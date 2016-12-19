---
title: "strtod, _strtod_l, wcstod, _wcstod_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstod"
  - "_wcstod_l"
  - "_strtod_l"
  - "strtod"
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
  - "_tcstod"
  - "strtod"
  - "wcstod"
  - "_strtod_l"
  - "_wcstod_l"
  - "stdlib/strtod"
  - "corecrt_wstdlib/wcstod"
  - "stdlib/_strtod_l"
  - "corecrt_wstdlib/_wcstod_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtod_l - функция"
  - "_tcstod - функция"
  - "_tcstod_l - функция"
  - "_wcstod_l - функция"
  - "преобразование строк, к значениям с плавающей запятой"
  - "strtod - функция"
  - "strtod_l - функция"
  - "tcstod - функция"
  - "tcstod_l - функция"
  - "wcstod - функция"
  - "wcstod_l - функция"
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
caps.latest.revision: 20
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtod, _strtod_l, wcstod, _wcstod_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуют строки к значению удвоенной точности.  
  
## Синтаксис  
  
```  
double strtod(  
   const char *nptr,  
   char **endptr   
);  
double _strtod_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
double wcstod(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
double wcstod_l(  
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
 `strtod` возвращает значение с плавающей запятой, за исключением тех случаев, когда такое представление вызывает переполнение, в этом случае функция возвращает \+\/–`HUGE_VAL`.  Символ `HUGE_VAL` соответствует знаку значения, которое невозможно представить.  `strtod` возвращает 0, если преобразование не может быть выполнено, или происходит потеря точности.  
  
 `wcstod` возвращает значения аналогично `strtod`.  Для обеих функций `errno` присваивается значение `ERANGE`, если возникает переполнение или потеря точности и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Каждая функция преобразует входную строку `nptr` в `double`.  Функция `strtod` преобразует `nptr` к значению двойной точности.  `strtod` прекращает чтение строки `nptr` на первом знаке, который она не может распознать как часть числа.  Это может быть конечный символ null.  `wcstod` — это двухбайтовая версия `strtod`; её аргумент `nptr` — строка двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstod`|`strtod`|`strtod`|`wcstod`|  
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|  
  
 Параметр категории `LC_NUMERIC` текущего языкового стандарта определяет распознавание основания системы счисления в `nptr`*;* дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции без суффикса `_l` используют текущий языковой стандарт; `_strtod_l` идентична `_strtod_l` за исключением того, что они используют переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не равен `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, хранится в ячейке памяти, на которую указывает `endptr`.  Если преобразование не может быть выполнено \(допустимые цифры не были найдены, или было указано недопустимое основание\), то значение `nptr` хранится в ячейке памяти, на которую указывает `endptr`.  
  
 `strtod` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace` может включать в себя пробелы и знаки табуляции, которые игнорируются; `sign` — плюс \(`+`\) или минус \(`–`\); `digits` — одна или несколько десятичных цифр.  Если перед символом системы счисления нет цифр, то после него должна быть хотя бы одна цифра.  За десятичными цифрами может следовать Экспонента, которая состоит из вводной буквы \(`d`, `D`, `e` или `E`\) и, при необходимости, целого числа со знаком.  Если нет ни экспоненциальной части, ни символа системы счисления, то предполагается, что символ системы счисления следует за последней цифрой в строке.  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtod`, `_strtod_l`|\<stdlib.h\>|  
|`wcstod`, `_wcstod_l`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_strtod.c  
// This program uses strtod to convert a  
// string to a double-precision value; strtol to  
// convert a string to long integer values; and strtoul  
// to convert a string to unsigned long-integer values.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char   *string, *stopstring;  
   double x;  
   long   l;  
   int    base;  
   unsigned long ul;  
  
   string = "3.1415926This stopped it";  
   x = strtod( string, &stopstring );  
   printf( "string = %s\n", string );  
   printf("   strtod = %f\n", x );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "-10110134932This stopped it";  
   l = strtol( string, &stopstring, 10 );  
   printf( "string = %s\n", string );  
   printf("   strtol = %ld\n", l );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "10110134932";  
   printf( "string = %s\n", string );  
  
   // Convert string using base 2, 4, and 8:  
   for( base = 2; base <= 8; base *= 2 )  
   {  
      // Convert the string:  
      ul = strtoul( string, &stopstring, base );  
      printf( "   strtol = %ld (base %d)\n", ul, base );  
      printf( "   Stopped scan at: %s\n", stopstring );  
   }  
}  
```  
  
  **string \= 3.1415926This stopped it**  
 **strtod \= 3.141593**  
 **Stopped scan at: This stopped it**  
**string \= \-10110134932This stopped it**  
 **strtol \= \-2147483648**  
 **Stopped scan at: This stopped it**  
**string \= 10110134932**  
 **strtol \= 45 \(base 2\)**  
 **Stopped scan at: 34932**  
 **strtol \= 4423 \(base 4\)**  
 **Stopped scan at: 4932**  
 **strtol \= 2134108 \(base 8\)**  
 **Stopped scan at: 932**   
## Эквивалент в .NET Framework  
 [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)