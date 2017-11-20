---
title: "strtof, _strtof_l, wcstof, _wcstof_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
dev_langs: C++
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d454bbb9afd2448b63173386249329ea91b4af01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof, _strtof_l, wcstof, _wcstof_l
Преобразует строки в значение одиночной точности с плавающей точкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
float strtof(  
   const char *nptr,  
   char **endptr   
);  
float _strtof_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
float wcstof(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
float wcstof_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nptr`  
 Строка, завершающаяся символом NULL, для преобразования.  
  
 `endptr`  
 Указатель на символ, который останавливает сканирование.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `strtof`Возвращает значение числа с плавающей запятой, за исключением случаев, когда представление вызвало бы переполнение, в котором случае функция возвращает +/-`HUGE_VALF`. Знак `HUGE_VALF` соответствует знаку значения, которое не может быть представлено. `strtof` возвращает 0, если преобразование не может быть выполнено или происходит потеря значимости.  
  
 `wcstof` возвращает значения аналогично `strtof`. Для обеих функций `errno` получает значение `ERANGE` при возникновении переполнения или потери значимости, и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Каждая функция преобразует входную строку `nptr` в `float`. Функция `strtof` преобразует `nptr` в значение одиночной точности. `strtof` прекращает чтение строки `nptr` на первом символе, который она не может распознать как часть числа. Это может быть завершающий нуль-символ. `wcstof`— это версия `strtof` с расширенными символами; ее аргумент `nptr` — строка расширенных символов. В остальном эти функции работают одинаково.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstof`|`strtof`|`strtof`|`wcstof`|  
|`_tcstof_l`|`_strtof_l`|`_strtof_l`|`_wcstof_l`|  
  
 Параметр категории `LC_NUMERIC` текущего языкового стандарта определяет распознавание символа основания системы счисления в `nptr`; дополнительные сведения см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции без суффикса `_l` используют текущий языковой стандарт; функции с этим суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не является значением `NULL`, указатель на символ, который останавливает сканирование, хранится в расположении, на которое указывает `endptr`. Если не удается выполнить преобразование (не найдены допустимые цифры или указано недопустимое основание), значение `nptr` сохраняется в расположении, указанном `endptr`.  
  
 `strtof` ожидает, что `nptr` указывает на строку следующего вида:  
  
 [`whitespace`] [`sign`] [`digits`] [`.digits`] [ {`e` &#124; `E`}[`sign`]`digits`]  
  
 `whitespace` может содержать пробелы и символы табуляции, которые игнорируются; `sign` — это или плюс (`+`), или минус (`-`); `digits` — это одна или несколько десятичных цифр. Если перед символом основания системы счисления нет никаких цифр, то после него должна отображаться хотя бы одна цифра. За десятичными цифрами может следовать показатель степени, который состоит из вводной буквы (`e` или `E`) и при необходимости целого числа со знаком. Если не отображается ни экспоненциальная часть, ни символ основания системы счисления, то предполагается, что символ основания системы счисления следует за последней цифрой в строке. Первый символ, который не соответствует этой форме, останавливает сканирование.  
 
 UCRT-версии этих функций не поддерживают преобразование буквенных обозначений экспонент в стиле Fortran (`d` или `D`). Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода.
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strtof`, `_strtof_l`|C: \<stdlib.h> C++: &lt;cstdlib> или \<stdlib.h>|  
|`wcstof`, `_wcstof_l`|C: \<stdlib.h> или \<wchar.h> C++: &lt;cstdlib>, \<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_strtof.c  
// This program uses strtof to convert a  
// string to a single-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   float x;  
  
   string = "3.14159This stopped it";  
   x = strtof(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtof = %f\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
```Output  
string = 3.14159This stopped it  
   strtof = 3.141590  
   Stopped scan at: This stopped it  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)