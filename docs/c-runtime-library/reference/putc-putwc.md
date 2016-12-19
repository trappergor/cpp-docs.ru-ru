---
title: "putc, putwc | Microsoft Docs"
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
  - "putwc"
  - "putc"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_puttc"
  - "putwc"
  - "putc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_puttc - функция"
  - "знаки, написание"
  - "putc - функция"
  - "puttc - функция"
  - "putwc - функция"
  - "потоки, запись знаков в"
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# putc, putwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает символ в поток.  
  
## Синтаксис  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `c`  
 Символ, который требуется записать.  
  
 `stream`  
 Указатель на структуру **FILE**.  
  
## Возвращаемое значение  
 Возвращает записанный символ.  Чтобы указать условие ошибки или конца файла, `putc` и `putchar` возвращают `EOF`; `putwc` и `putwchar` возвращают **WEOF**.  Для всех четырех процедур используйте функцию [ferror](../../c-runtime-library/reference/ferror.md) или [feof](../../c-runtime-library/reference/feof.md) для проверки ошибок или конца файла.  Если `stream` является пустым указателем, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` или **WEOF** и устанавливают для `errno` значение `EINVAL`.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Процедура `putc` записывает один символ `c` в текущую позицию выходного потока `stream`.  Любое целое число может быть передано `putc`, но записываются только младшие 8 бит.  Процедура `putchar` идентична **putc\(** `c`**, stdout \)**.  Для каждой процедуры, если возникает ошибка чтения, для потока устанавливается индикатор ошибки.  `putc` и `putchar` аналогичны `fputc` и `_fputchar` соответственно, но реализованы как и функции, и макросы \(см. [Выбор между функциями и макросами](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)\).  `putwc` и `putwchar` \- версии `putc` и `putchar`для расширенных символов соответственно.  Поведение `putwc` и `putc` идентично, если поток открыт в режиме ANSI\-совместимости.  `putc` в настоящее время не поддерживает вывод в поток в юникоде.  
  
 Версии с суффиксом **\_nolock** идентичны за исключением того, что они не защищены от взаимодействия с другими потоками.  Дополнительные сведения см. в разделе **\_putc\_nolock, \_putwc\_nolock**.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`putc`|\<stdio.h\>|  
|`putwc`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## Output  
  
```  
This is the line of output  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)