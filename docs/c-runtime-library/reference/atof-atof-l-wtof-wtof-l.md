---
title: "atof, _atof_l, _wtof, _wtof_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtof_l"
  - "atof"
  - "_atof_l"
  - "_wtof"
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
  - "_tstof"
  - "_ttof"
  - "atof"
  - "stdlib/atof"
  - "math/atof"
  - "_atof_l"
  - "stdlib/_atof_l"
  - "math/_atof_l"
  - "_wtof"
  - "corecrt_wstdlib/_wtof"
  - "_wtof_l"
  - "corecrt_wstdlib/_wtof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция tstof"
  - "Функция atof_l"
  - "Функция _atof_l"
  - "Функция atof"
  - "Функция _tstof"
  - "Функция _ttof"
  - "Функция wtof"
  - "Функция _wtof_l"
  - "Функция ttof"
  - "Функция wtof_l"
  - "Функция _wtof"
  - "преобразование строк, в значения с плавающей запятой"
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# atof, _atof_l, _wtof, _wtof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразовать строку в тип double.  
  
## Синтаксис  
  
```  
double atof(  
   const char *str   
);  
double _atof_l(  
   const char *str,  
   _locale_t locale  
);  
double _wtof(  
   const wchar_t *str   
);  
double _wtof_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `str`  
 Строка для преобразования.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая функция возвращает значение `double`, которое создается за счет интерпретации входных символов в виде числа.  Возвращаемое значение равно 0.0, если входные данные невозможно преобразовать в значение этого типа.  
  
 Во всех случаях вне допустимого диапазона, параметр errno имеет значение `ERANGE`.  Если переданный параметр — `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают 0.  
  
## Заметки  
 Эти функции преобразовывают символьную строку к значению двойной точности с плавающей запятой.  
  
 Входная строка — это последовательность символов, которая может быть интерпретирована как числовое значение указанного типа.  Функция прекращает чтение входной строки на первом знаке, который она не может распознать как часть числа.  Этот символ может быть нулевым символом \("\\0" или " L "\\0"\), которым завершается строка.  
  
 Аргумент `str` для `atof` и `_wtof` имеет следующую форму:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E` }\[`sign`\]`digits`\]  
  
 `whitespace` состоит из пробелов и знаков табуляции, которые игнорируются; `sign` — плюс \(\+\) или минус \(–\); `digits` — одна или несколько десятичных цифр.  При отсутствии цифр перед десятичной запятой по крайней мере одна должна появиться после десятичной запятой.  За десятичными цифрами может следовать экспонента, которая состоит из вводной буквы \(`d`, `D`, `e` или `E`\) и, при необходимости, целого десятичного числа со знаком.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstof`|`atof`|`atof`|`_wtof`|  
|`_ttof`|`atof`|`atof`|`_wtof`|  
  
## Требования  
  
|Программа\(ы\)|Обязательный заголовок|  
|--------------------|----------------------------|  
|`atof`|\<math.h\> и \<stdlib.h\>|  
|`_atof_l`|\<math.h\> и \<stdlib.h\>|  
|`_wtof`, `_wtof_l`|\<stdlib.h\> или \<wchar.h\>|  
  
## Пример  
 Эта программа показывает, как числа, хранящиеся в виде строки, могут преобразованы в числовые значения с помощью `atof`.  
  
```  
// crt_atof.c  
//  
// This program shows how numbers stored as   
// strings can be converted to numeric  
// values using the atof function.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    double  value = 0;  
  
    // An example of the atof function  
    // using leading and training spaces.  
    str = "  3336402735171707160320 ";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // Another example of the atof function  
    // using the 'd' exponential formatting keyword.  
    str = "3.1412764583d210";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // An example of the atof function  
    // using the 'e' exponential formatting keyword.  
    str = "  -2309.12E-15";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
}  
```  
  
  **Function: atof\( "  3336402735171707160320 " \) \= 3.336403e\+021**  
**Function: atof\( "3.1412764583d210" \) \= 3.141276e\+210**  
**Function: atof\( "  \-2309.12E\-15" \) \= \-2.309120e\-012**   
## Эквивалент в .NET Framework  
  
-   [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
-   [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)