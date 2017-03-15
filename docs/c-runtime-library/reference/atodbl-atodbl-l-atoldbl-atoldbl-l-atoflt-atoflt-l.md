---
title: "_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_atoldbl"
  - "_atoldbl_l"
  - "_atodbl"
  - "_atoflt"
  - "_atoflt_l"
  - "_atodbl_l"
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
  - "_atoflt"
  - "_atoflt_l"
  - "atodbl_l"
  - "atoflt_l"
  - "_atoldbl"
  - "_atoldbl_l"
  - "atodbl"
  - "_atodbl_l"
  - "atoldbl"
  - "atoflt"
  - "atoldbl_l"
  - "_atodbl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_atodbl - функция"
  - "_atoldbl_l - функция"
  - "atoflt - функция"
  - "atoflt_l - функция"
  - "atoldbl - функция"
  - "_atoldbl - функция"
  - "atodbl_l - функция"
  - "_atoflt_l - функция"
  - "atoldbl_l - функция"
  - "atodbl - функция"
  - "преобразование строк, в значения с плавающей запятой"
  - "_atoflt - функция"
  - "_atodbl_l - функция"
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование строки в число двойной точности с плавающей запятой\(`_atodbl`\), удлиненное число двойной точности с плавающей запятой \(`_atoldbl`\) или в число одинарной точности с плавающей запятой \(`_atoflt`\).  
  
## Синтаксис  
  
```  
int _atodbl(  
   _CRT_DOUBLE * value,  
   char * str  
);  
int _atodbl_l (  
   _CRT_DOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoldbl(  
   _LDOUBLE * value,  
   char * str  
);  
int _atoldbl_l (  
   _LDOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoflt(  
   _CRT_FLOAT * value,  
   const char * str  
);  
int _atoflt_l(  
   _CRT_FLOAT * value,  
   const char * str,  
   locale_t locale  
);  
```  
  
#### Параметры  
 `value`  
 Значение double, long double или float создается путем преобразования строки в число с плавающей запятой.  Значения имеют оболочку\-структуру.  
  
 `str`  
 Строка для разбора с целью преобразования в значение с плавающей запятой.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращает 0 в случае успеха.  Возможные коды ошибок — `_UNDERFLOW` или `_OVERFLOW`, которые определены в файле заголовка Math.h.  
  
## Заметки  
 Эти функции преобразуют строку в число с плавающей запятой.  Различие между этими функциями и функциями семейства `atof` в том, что эти функции не создают код с плавающей запятой и не вызывают исключений оборудования.  Вместо этого условия ошибки сообщаются через коды ошибок.  
  
 Если строка не имеет допустимого представления как число с плавающей запятой, `value` устанавливается в ноль и возвращаемое значение также равно нулю.  
  
 Версии этих функций с суффиксом `_l` идентичны версиям без суффикса, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта потока.  
  
## Требования  
  
|Программы|Обязательный заголовок|  
|---------------|----------------------------|  
|`_atodbl`, `_atoldbl`, `_atoflt`<br /><br /> `_atodbl_l`, `_atoldbl_l`, `_atoflt_l`|\<stdlib.h\>|  
  
## Пример  
  
```  
// crt_atodbl.c  
// Uses _atodbl to convert a string to a double precision  
// floating point value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
   char str1[256] = "3.141592654";  
   char abc[256] = "abc";  
   char oflow[256] = "1.0E+5000";  
   _CRT_DOUBLE dblval;  
   _CRT_FLOAT fltval;  
   int retval;  
  
   retval = _atodbl(&dblval, str1);  
  
   printf("Double value: %lf\n", dblval.x);  
   printf("Return value: %d\n\n", retval);  
  
   retval = _atoflt(&fltval, str1);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // A non-floating point value: returns 0.  
   retval = _atoflt(&fltval, abc);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // Overflow.  
   retval = _atoflt(&fltval, oflow);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   return 0;  
}  
```  
  
  **Double значение: 3.141593**  
**Возвращаемое значение: 0**  
**Float значение: 3.141593**  
**Возвращаемое значение: 0**  
**Float значение: 0.000000**  
**Возвращаемое значение: 0**  
**Float значение: 1.\#INF00**  
**Возвращаемое значение: 3**   
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)