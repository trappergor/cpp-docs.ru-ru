---
title: "printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_s_l"
  - "wprintf_s"
  - "_wprintf_s_l"
  - "printf_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "wprintf_s"
  - "printf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_s_l - функция"
  - "_tprintf_s - функция"
  - "_tprintf_s_l - функция"
  - "_wprintf_s_l - функция"
  - "форматированный текст [C++]"
  - "printf - функция, поля описания формата"
  - "printf - функция, использование"
  - "printf_s - функция"
  - "printf_s_l - функция"
  - "tprintf_s - функция"
  - "tprintf_s_l - функция"
  - "wprintf_s - функция"
  - "wprintf_s_l - функция"
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Печатает форматированный результат в стандартный поток вывода.  В этих версиях [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int printf_s(  
   const char *format [,  
   argument]...   
);  
int _printf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Параметры  
 `format`  
 Управление форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращает число напечатанных символов или отрицательное значение в случае ошибки.  
  
## Заметки  
 Функция `printf_s` форматирует и выводит ряд символов и значений в стандартный поток вывода, `stdout`.  Если аргументы идут за *строкой формата*, то строка `format` должна содержать спецификации, которые определяют формат вывода для аргументов.  
  
 Основное различие между `printf_s` и `printf` заключается в том, что `printf_s` проверяет строку форматирования на наличие допустимых символов форматирования, тогда как `printf` только проверяет, является ли строка формата указателем null.  Если проверка завершается с ошибкой, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает \-1 и устанавливает `errno` в значение `EINVAL`.  
  
 Дополнительные сведения о `errno` и кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Поведение `printf_s`и`fprintf_s` идентичны за исключением того, что `printf_s` выводит данные в `stdout`, а не в место назначения типа `FILE`.  Для получения дополнительной информации см. [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).  
  
 `wprintf_s` — двухбайтовая версия `printf_s`; `format` — двухбайтовая строка.  Поведение `wprintf_s` и `printf_s` идентично, если поток открыт в режиме ANSI\-совместимости.  `printf_s` в настоящее время не поддерживает вывод в поток в юникоде.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_unicode определена|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tprintf_s`|`printf_s`|`printf_s`|`wprintf_s`|  
|`_tprintf_s_l`|`_printf_s_l`|`_printf_s_l`|`_wprintf_s_l`|  
  
 Аргумент `format` состоит из обычных символов, escape\-последовательностей и \(если аргументы следуют за параметром `format`\) спецификаций формата.  Обычные символы и escape\-последовательности копируются в `stdout` в порядке их следования.  Например, в строке  
  
```  
printf_s("Line one\n\t\tLine two\n");   
```  
  
 создает выходные данные  
  
```  
Line one  
        Line two  
```  
  
 [Спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md) всегда начинаются со знака процента \(`%`\) и читаются слева направо.  При обнаружении `printf_s` первой спецификации формата \(если таковые имеются\) она преобразует значение первого аргумента после `format` и выводит его соответствующим образом.  Вторая спецификация формата приводит к преобразованию и выводу второго аргумента и так далее.  Если аргументов больше, чем спецификаций формата, дополнительные аргументы игнорируются.  Результаты будут не определены, если аргументов недостаточно для всех спецификаций формата.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`printf_s`, `_printf_s_l`|\<stdio.h\>|  
|`wprintf_s`, `_wprintf_s_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_printf_s.c  
/* This program uses the printf_s and wprintf_s functions  
 * to produce formatted output.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   char   ch = 'h', *string = "computer";  
   int    count = -9234;  
   double fp = 251.7366;  
   wchar_t wch = L'w', *wstring = L"Unicode";  
  
   /* Display integers. */  
   printf_s( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",  
           count, count, count );  
  
   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   /* Display in different radixes. */  
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   /* Display characters. */  
  
   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);  
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);  
  
   /* Display strings. */  
  
   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",  
   string, string, wstring, wstring);  
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",  
       string, string, wstring, wstring);  
  
   /* Display real numbers. */  
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );  
  
   /* Display pointer. */  
   printf_s( "\nAddress as:   %p\n", &count);  
  
}  
```  
  
## Пример результатов выполнения  
  
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
  
Address as:   0012FF78  
  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)