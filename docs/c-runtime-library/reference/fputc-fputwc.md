---
title: "fputc, fputwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fputc"
  - "fputwc"
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
  - "fputc"
  - "fputwc"
  - "_fputtc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputtc - функция"
  - "fputc - функция"
  - "fputtc - функция"
  - "fputwc - функция"
  - "потоки, запись знаков в"
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# fputc, fputwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает символ в поток.  
  
## Синтаксис  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `c`  
 Символ, который требуется записать.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает записанный символ.  Возвращаемое значение `EOF` для функции `fputc` указывает на ошибку.  Возвращаемое значение `WEOF` для функции `fputwc` указывает на ошибку.  Если `stream` имеет значение `NULL`, эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Каждая из этих функций записывает символ `c` в файл на позицию, указанную связанным индикатором позиции файла \(если определен\), и соответственно перемещает индикатор.  В случае `fputc` и `fputwc`, файл связан с `stream`*.* Если файл не поддерживает запросы размещения или открыт в режиме добавления, символ добавляется в конец потока.  
  
 Поведение этих функций идентично, если поток открыт в режиме ANSI\-совместимости.  `fputc` в настоящее время не поддерживает вывод в поток в Юникоде.  
  
 Версии с суффиксом `_nolock` идентичны за исключением того, что они не защищены от взаимодействия с другими потоками.  Для получения дополнительной информации см.[\_fputc\_nolock, \_fputwc\_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md).  
  
 Замечания относительно особенностей процедур.  
  
|Подпрограмма|Примечания|  
|------------------|----------------|  
|`fputc`|Эквивалентна `putc`, но реализуется только как функция, а не как функция и макрос.|  
|`fputwc`|Версия `fputc` для работы с расширенными символами.  Записывает `c` как многобайтовый или расширенный символ согласно тому, открыт ли `stream` в текстовом режиме или в бинарном режиме.|  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fputc`|\<stdio.h\>|  
|`fputwc`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **This is a test of fputc\!\!**   
## Эквивалент в .NET Framework  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)