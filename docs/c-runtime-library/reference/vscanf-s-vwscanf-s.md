---
title: "vscanf_s, vwscanf_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vscanf_s"
  - "vwscanf_s"
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
  - "_vtscanf_s"
  - "vscanf_s"
  - "vwscanf_s"
dev_langs: 
  - "C++"
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vscanf_s, vwscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из стандартного входного потока.  В этих версиях [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int vscanf_s(  
   const char *format,  
   va_list arglist  
);   
int vwscanf_s(  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### Параметры  
 `format`  
 Строка управления форматом.  
  
 `arglist`  
 Список аргументов переменных.  
  
## Возвращаемое значение  
 Возвращает число успешно преобразованных и назначенных полей; возвращаемое значение не включает поля, которые были считаны, но не назначены.  Возвращаемое значение 0 указывает, что поля не были присвоены.  Возвращаемое значение равно `EOF` в случае ошибки или если при первой попытке считать символ встречается символ конца файла или конца строки.  Если параметр `format` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, `vscanf_s` и `vwscanf_s` возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `vscanf_s` считывает данные из стандартного входного потока `stdin` и записывает данные в расположения, заданные списком аргументов `arglist`.  Каждый аргумент в списке должен быть указателем на переменную, которая имеет тип, который соответствует спецификатору типа в `format`.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 `vwscanf_s` — двухбайтовая версия `vscanf_s`; аргумент `format` для `vwscanf_s` \- строка двухбайтовых знаков.  Поведение `vwscanf_s` и `vscanf_s` идентично, если поток открыт в режиме ANSI\-совместимости.  `vscanf_s` не поддерживает входные данные из потока ЮНИКОДА.  
  
 В отличие от `vscanf` и `vwscanf`, `vscanf_s` и `vwscanf_s` требуют, чтобы размер буфера был задан для всех входных параметров типа `c`, `C`, `s`, `S` или наборов строковых элементов управления, заключенных в `[]`.  Размер буфера в символах передается в качестве дополнительного параметра сразу после указателя в буфер или переменную.  Размер буфера в символах для строки `wchar_t` отличается от размера в байтах.  
  
 Размер буфера включает конечное значение NULL.  Можно использовать поле спецификации ширины может использоваться, чтобы гарантировать, что считываемый токен поместится в буфер.  Если не используется поле спецификации ширины, и токен считанный слишком велик чтобы влезть в буфер, ничего не записывается в этот буфер.  
  
> [!NOTE]
>  Параметр размера — типа `unsigned`, а не `size_t`.  
  
 Для получения дополнительной информации см. [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vtscanf_s`|`vscanf_s`|`vscanf_s`|`vwscanf_s`|  
  
 Для получения дополнительной информации см. [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`vscanf_s`|\<stdio.h\>|  
|`wscanf_s`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_vscanf_s.c  
// compile with: /W3  
// This program uses the vscanf_s and vwscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vscanf_s(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf_s(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,  
                           &wc, 1, s, _countof(s), ws, _countof(ws) );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                            &wc, 1, s, _countof(s), ws, _countof(ws) );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
 Если этой программе предоставляется ввод в этом примере, она создает следующий вывод:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
  **Число полей ввода — 6**  
**Содержимое: 71 98.599998 h z байтовые символы**  
**Число полей ввода — 6**  
**Содержимое: 36 92.300003 y n широкие символы**   
## Эквивалент в .NET Framework  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   См. также методы `Parse`, такие как [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md)