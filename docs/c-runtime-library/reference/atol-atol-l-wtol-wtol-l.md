---
title: "atol, _atol_l, _wtol, _wtol_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atol"
  - "_wtol_l"
  - "_wtol"
  - "_atol_l"
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
  - "_atol_l"
  - "_ttol_l"
  - "_tstol_l"
  - "_tstol"
  - "_wtol"
  - "_ttol"
  - "_wtol_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция tstol"
  - "Функция atol"
  - "Функция ttol"
  - "Функция _atol_l"
  - "Функция _tstol_l"
  - "преобразование строк, в целые числа"
  - "Функция _tstol"
  - "Функция _ttol"
  - "Функция _ttol_l"
  - "Функция atol_l"
  - "Функция wtol_l"
  - "Функция _wtol_l"
  - "Функция wtol"
  - "Функция _wtol"
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# atol, _atol_l, _wtol, _wtol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строку в длинное целое число.  
  
## Синтаксис  
  
```  
long atol(  
   const char *str   
);  
long _atol_l(  
   const char *str,  
   _locale_t locale  
);  
long _wtol(  
   const wchar_t *str   
);  
long _wtol_l(  
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
 Каждая функция возвращает значение `long`, которое создается за счет интерпретации входных символов в виде числа.  Возвращаемое значение `atol` равно 0L, если входные данные невозможно преобразовать в значение этого типа.  
  
 В случае переполнения большими положительными целыми значениями `atol` возвращает `LONG_MAX`; в случае переполнения большими отрицательными целыми значениями — `LONG_MIN`.  Во всех случаях вне допустимого диапазона, параметр `errno` имеет значение `ERANGE`.  Если переданный параметр — `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают 0.  
  
## Заметки  
 Эти функции преобразуют символьную строку в длинное целочисленное значение \(`atol`\).  
  
 Входная строка — это последовательность символов, которая может быть интерпретирована как числовое значение указанного типа.  Функция прекращает чтение входной строки на первом знаке, который она не может распознать как часть числа.  Этот символ может быть символом `NULL` \('\\0' or L'\\0'\), которым завершается строка.  
  
 Аргумент `str` для `atol` имеет следующую форму:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` состоит из пробелов и знаков табуляции, которые игнорируются; `sign` — плюс \(\+\) или минус \(–\); `digits` — одна или несколько десятичных цифр.  
  
 `_wtol` идентично `atol`, за исключением того, что он принимает строку расширенных символов в качестве параметра.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstol`|`atol`|`atol`|`_wtol`|  
|`_ttol`|`atol`|`atol`|`_wtol`|  
  
## Требования  
  
|Программы|Обязательный заголовок|  
|---------------|----------------------------|  
|`atol`|\<stdlib.h\>|  
|`_atol_l`, `_wtol`, `_wtol_l`|\<stdlib.h\> и \<wchar.h\>|  
  
## Пример  
 Эта программа показывает, как числа, хранящиеся в виде строки, могут преобразованы в числовые значения с помощью `atol`.  
  
```  
// crt_atol.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the atol functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    long    value = 0;  
  
    // An example of the atol function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Function: atol\( "  \-2309 " \) \= \-2309**  
**Function: atol\( "314127.64" \) \= 314127**  
**Function: atol\( "3336402735171707160320" \) \= 2147483647**  
**Возникло условие переполнения.**   
## Эквивалент в .NET Framework  
  
-   [System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)  
  
-   [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)