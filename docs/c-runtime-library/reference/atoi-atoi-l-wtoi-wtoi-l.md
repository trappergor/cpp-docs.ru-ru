---
title: "atoi, _atoi_l, _wtoi, _wtoi_l | Microsoft Docs"
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
  - "_wtoi"
  - "_wtoi_l"
  - "atoi"
  - "_atoi_l"
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
  - "_tstoi"
  - "_wtoi"
  - "_ttoi"
  - "atoi"
  - "_atoi_l"
  - "_wtoi_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция _atoi_l"
  - "Функция ttoi"
  - "Функция atoi_l"
  - "преобразование строк, в целые числа"
  - "Функция _wtoi"
  - "Функция wtoi_l"
  - "Функция tstoi"
  - "Функция _ttoi"
  - "Функция _tstoi"
  - "Функция _wtoi_l"
  - "Функция atoi"
  - "Функция wtoi"
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atoi, _atoi_l, _wtoi, _wtoi_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование строки в целое число.  
  
## Синтаксис  
  
```  
int atoi(  
   const char *str   
);  
int _wtoi(  
   const wchar_t *str   
);  
int _atoi_l(  
   const char *str,  
   _locale_t locale  
);  
int _wtoi_l(  
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
 Каждая функция возвращает значение `int`, которое создается за счет интерпретации входных символов в виде числа.  Возвращаемое значение `atoi` и `_wtoi` равно 0, если входные данные невозможно преобразовать в значение этого типа.  
  
 В случае переполнения большими отрицательными целыми значениями возвращается `LONG_MIN`.  `atoi` и `_wtoi` возвращают `INT_MAX` и `INT_MIN` в следующих условиях.  Во всех случаях вне допустимого диапазона, параметр `errno` имеет значение `ERANGE`.  Если переданный параметр — `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают 0.  
  
## Заметки  
 Эти функции преобразуют символьную строку в целочисленное значение \(`atoi` и `_wtoi`\).  Входная строка — это последовательность символов, которая может быть интерпретирована как числовое значение указанного типа.  Функция прекращает чтение входной строки на первом знаке, который она не может распознать как часть числа.  Этот символ может быть нулевым символом \("\\0" или " L "\\0"\), которым завершается строка.  
  
 Аргумент `str` для `atoi` `` и `_wtoi` имеет следующую форму:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` состоит из пробелов и знаков табуляции, которые игнорируются; `sign` — плюс \(\+\) или минус \(–\); `digits` — одна или несколько десятичных цифр.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstoi`|`atoi`|`atoi`|`_wtoi`|  
|`_ttoi`|`atoi`|`atoi`|`_wtoi`|  
  
## Требования  
  
|Программы|Обязательный заголовок|  
|---------------|----------------------------|  
|`atoi`|\<stdlib.h\>|  
|`_atoi_l`, `_wtoi`, `_wtoi_l`|\<stdlib.h\> или \<wchar.h\>|  
  
## Пример  
 Эта программа показывает, как числа, хранящиеся в виде строки, могут преобразованы в числовые значения с помощью `atoi`.  
  
```  
// crt_atoi.c  
// This program shows how numbers   
// stored as strings can be converted to  
// numeric values using the atoi functions.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    int     value = 0;  
  
    // An example of the atoi function.  
    str = "  -2309 ";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function.  
    str = "31412764";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function   
    // with an overflow condition occuring.  
    str = "3336402735171707160320";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Function: atoi\( "  \-2309 " \) \= \-2309**  
**Function: atoi\( "31412764" \) \= 31412764**  
**Function: atoi\( "3336402735171707160320" \) \= 2147483647**  
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