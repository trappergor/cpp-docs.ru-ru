---
title: "printf, _printf_l, wprintf, _wprintf_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _printf_l
- wprintf
- _wprintf_l
- printf
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
apitype: DLLExport
f1_keywords:
- printf
- _tprintf
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- printf function
- printf_l function
- tprintf_l function
- tprintf function
- _printf_l function
- wprintf function
- writing to console
- wprintf_l function
- _tprintf_l function
- _wprintf_l function
- _tprintf function
- printf function, format specification fields
- printf function, using
- formatted text [C++]
ms.assetid: 77a854ae-5b48-4865-89f4-f2dc5cf80f52
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2ebdd4061b50646f9450bfdfaf2ea4db90b5774
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="printf-printfl-wprintf-wprintfl"></a>printf, _printf_l, wprintf, _wprintf_l
Выводит форматированные выходные данные в стандартный поток вывода. Существуют более безопасные версии этих функций. См. раздел [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int printf(  
   const char *format [,  
   argument]...   
);  
int _printf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `format`  
 Формат объекта.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает число выведенных символов или отрицательное значение в случае ошибки. Если параметр `format` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает `errno` в значение `EINVAL`. При обнаружении **EOF** (0xFFFF) в `argument` функция возвращает значение -1.  
  
 Дополнительные сведения о `errno` и кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `printf` форматирует и выводит последовательность символов и значений в стандартный поток вывода, `stdout`. Если за строкой `format` следуют аргументы, строка `format` должна содержать спецификации, которые определяют формат вывода для аргументов. Поведение функций `printf` и [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) идентично, за исключением того, что `printf` выводит данные в `stdout`, а не в место назначения типа `FILE`.  
  
 Функция `wprintf` — это версия `printf` с расширенными символами; `format` — строка расширенных символов. `wprintf` и `printf` ведут себя одинаково, если поток открыт в режиме ANSI. Функция `printf` на данный момент не поддерживает вывод данных в поток в кодировке Юникод.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
  
 Аргумент `format` состоит из обычных символов, escape-последовательностей и (если за `format` следуют аргументы) спецификаций формата. Обычные символы и escape-последовательности копируются в `stdout` в порядке их отображения. Например, в строке  
  
```  
printf("Line one\n\t\tLine two\n");   
```  
  
 выводятся следующие выходные данные:  
  
```  
Line one  
        Line two  
```  
  
 [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) всегда начинаются со знака процента (`%`) и читаются слева направо. Когда функция `printf` обнаруживает первую спецификацию формата (если таковые имеются), она преобразует значение первого после `format` аргумента и выводит его соответствующим образом. Вторая спецификация формата вызывает преобразование второго аргумента и его вывод и т. д. Если число аргументов превышает количество спецификаций формата, лишние аргументы игнорируются. Если число аргументов меньше количества спецификаций формата, результаты будут не определены.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
|`_tprintf_l`|`_printf_l`|`_printf_l`|`_wprintf_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`printf`, `_printf_l`|\<stdio.h>|  
|`wprintf`, `_wprintf_l`|\<stdio.h> или \<wchar.h>|  
  
Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout`, и `stderr`, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).
  
## <a name="example"></a>Пример  
  
```  
// crt_printf.c  
// This program uses the printf and wprintf functions  
// to produce formatted output.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char     ch = 'h',   
            *string = "computer";  
   wchar_t  wch = L'w',   
            *wstring = L"Unicode";  
   int      count = -9234;  
   double   fp = 251.7366;  
  
   // Display integers  
   printf( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  "  
           "Unsigned: %u\n",  
           count, count, count, count );  
  
   // Display decimals  
   printf( "Decimal %d as:\n   Hex: %Xh  "  
           "C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   // Display in different radixes  
   printf( "Digits 10 equal:\n   Hex: %i  "  
           "Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   // Display characters  
   printf("Characters in field (1):\n"  
          "%10c%5hc%5C%5lc\n",  
          ch, ch, wch, wch);  
   wprintf(L"Characters in field (2):\n"  
           L"%10C%5hc%5c%5lc\n",  
           ch, ch, wch, wch);  
  
   // Display strings  
   printf("Strings in field (1):\n%25s\n"  
          "%25.4hs\n   %S%25.3ls\n",  
          string, string, wstring, wstring);  
   wprintf(L"Strings in field (2):\n%25S\n"  
           L"%25.4hs\n   %s%25.3ls\n",  
           string, string, wstring, wstring);  
  
   // Display real numbers  
   printf("Real numbers:\n   %f %.2f %e %E\n",  
          fp, fp, fp, fp );  
  
   // Display pointer  
   printf( "\nAddress as:   %p\n", &count);  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Integer formats:  
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062  
Decimal -9234 as:  
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756  
Digits 10 equal:  
   Hex: 16  Octal: 8  Decimal: 10  
Characters in field (1):  
         h    h    w    w  
Characters in field (2):  
         h    h    w    w  
Strings in field (1):  
                 computer  
                     comp  
   Unicode                      Uni  
Strings in field (2):  
                 computer  
                     comp  
   Unicode                      Uni  
Real numbers:  
   251.736600 251.74 2.517366e+002 2.517366E+002  
  
Address as:   0012FF3C  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [_set_output_format](../../c-runtime-library/set-output-format.md)