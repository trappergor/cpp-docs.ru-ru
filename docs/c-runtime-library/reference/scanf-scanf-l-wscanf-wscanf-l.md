---
title: "scanf, _scanf_l, wscanf, _wscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wscanf_l"
  - "scanf"
  - "_scanf_l"
  - "wscanf"
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
  - "_tscanf"
  - "_scanf_l"
  - "wscanf"
  - "_wscanf_l"
  - "scanf"
  - "_tscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_scanf_l - функция"
  - "_tscanf - функция"
  - "_tscanf_l - функция"
  - "_wscanf_l - функция"
  - "данные [C++], чтение из входящего потока"
  - "форматированные данные [C++], из входящих потоков"
  - "чтение данных [C++], из входящих потоков"
  - "scanf - функция"
  - "scanf_l - функция"
  - "tscanf - функция"
  - "tscanf_l - функция"
  - "wscanf - функция"
  - "wscanf_l - функция"
ms.assetid: 73eac607-117f-4be4-9ff0-4afd9cf3c848
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# scanf, _scanf_l, wscanf, _wscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из стандартного входного потока.  Существуют более безопасные версии этих функций; см. раздел [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).  
  
## Синтаксис  
  
```  
int scanf(  
   const char *format [,  
   argument]...   
);  
int _scanf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Параметры  
 `format`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращает число успешно преобразованных и назначенных полей; возвращаемое значение не включает поля, которые были считаны, но не назначены.  Возвращаемое значение 0 указывает, что поля не были присвоены.  
  
 Если параметр `format` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `scanf` считывает данные из стандартного входного потока `stdin` и записывает данные в расположение, указанное `argument`.  Каждый `argument` должен быть указателем на переменную, которая имеет тип, который соответствует спецификатору типа в `format`.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
> [!IMPORTANT]
>  При считывании строки с помощью `scanf` всегда надо указать ширину для формата `%s` \(например, `"%32s"` вместо `"%s"`\); в противном случае неправильно отформатированный входные данные могут вызвать переполнение буфера.  Кроме того, можно использовать [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) или [fgets](../../c-runtime-library/reference/fgets-fgetws.md).  
  
 `wscanf` — двухбайтовая версия `scanf`; аргумент `format` для `wscanf` \- строка двухбайтовых знаков.  Поведение `wscanf` и `scanf` идентично, если поток открыт в режиме ANSI\-совместимости.  `scanf` сейчас не поддерживает входные данные из потока ЮНИКОДА.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tscanf`|`scanf`|`scanf`|`wscanf`|  
|`_tscanf_l`|`_scanf_l`|`_scanf_l`|`_wscanf_l`|  
  
 Дополнительные сведения см. в разделе [Поля спецификации формата: функции wscanf и scanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`scanf`, `_scanf_l`|\<stdio.h\>|  
|`wscanf`, `_wscanf_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_scanf.c  
// compile with: /W3  
 /* This program uses the scanf and wscanf functions  
  * to read formatted input.  
  */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int   i, result;  
   float fp;  
   char  c, s[81];  
   wchar_t wc, ws[81];  
   result = scanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws ); // C4996  
   // Note: scanf and wscanf are deprecated; consider using scanf_s and wscanf_s  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
   result = wscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws ); // C4996  
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