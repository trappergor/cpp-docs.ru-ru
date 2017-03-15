---
title: "vscanf, vwscanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vscanf"
  - "vwscanf"
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
  - "vscanf"
  - "vwscanf"
  - "_vtscanf"
dev_langs: 
  - "C++"
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vscanf, vwscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из стандартного входного потока.  Существуют более безопасные версии этих функций; см. раздел [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md).  
  
## Синтаксис  
  
```  
int vscanf(  
   const char *format,  
   va_list arglist  
);  
int vwscanf(  
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
 Возвращает число успешно преобразованных и назначенных полей; возвращаемое значение не включает поля, которые были считаны, но были не назначены.  Возвращаемое значение 0 указывает, что поля не были присвоены.  
  
 Если параметр `format` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `vscanf` считывает данные из стандартного входного потока `stdin` и записывает данные в расположения, указанными списком аргументов `arglist`.  Каждый аргумент в списке должен быть указателем на переменную, которая имеет тип, который соответствует спецификатору типа в `format`.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
> [!IMPORTANT]
>  При использовании `vscanf` для чтения строки, всегда надо указать ширину для формата `%s` \(например, `"%32s"` вместо `"%s"`\); в противном случае неправильно отформатированный входные данные могут вызвать переполнение буфера.  В качестве альтернативы можно использовать [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md) или [fgets](../../c-runtime-library/reference/fgets-fgetws.md).  
  
 `vwscanf` — двухбайтовая версия `vscanf`; аргумент `format` для `vwscanf` \- строка двухбайтовых знаков.  Поведение `vwscanf` и `vscanf` идентично, если поток открыт в режиме ANSI\-совместимости.  `vscanf` не поддерживает входные данные из потока ЮНИКОДА.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vtscanf`|`vscanf`|`vscanf`|`vwscanf`|  
  
 Для получения дополнительной информации см. [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`vscanf`|\<stdio.h\>|  
|`vwscanf`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_vscanf.c  
// compile with: /W3  
// This program uses the vscanf and vwscanf functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vscanf(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
  **`71 98.6 h z-байтовые символы 36 92.3 y n Многобайтовые знаки`Количество ввода полей — 6**  
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
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md)