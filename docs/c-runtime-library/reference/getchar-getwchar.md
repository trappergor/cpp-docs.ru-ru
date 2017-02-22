---
title: "getchar, getwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getchar"
  - "getwchar"
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
  - "getwchar"
  - "GetChar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gettchar - функция"
  - "знаки, чтение"
  - "gettchar - функция"
  - "getwchar - функция"
  - "стандартный ввод, чтение из"
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# getchar, getwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает символ из стандартного входного потока.  
  
## Синтаксис  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## Возвращаемое значение  
 Возвращает считанный символ.  Чтобы указать на ошибку чтения или конец файла, `getchar` `returns EOF` и `getwchar` возвращает `WEOF`.  Для `getchar` используйте `ferror` или `feof` для проверки на наличие ошибок или на конец файла.  
  
## Заметки  
 Каждая процедура считывает один символ из `stdin` и увеличивает связанный указатель файла, чтобы он указывал на следующий символ.  `getchar` аналогично [\_fgetchar](../Topic/fgetc,%20fgetwc.md), но реализуется как функция и как макрос.  
  
 Эти функции блокируют вызывающий поток и, следовательно, являются потокобезопасными.  Для неблокирующей версии см. [\_getchar\_nolock, \_getwchar\_nolock](../Topic/_getchar_nolock,%20_getwchar_nolock.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`getchar`|\<stdio.h\>|  
|`getwchar`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`This text`Input was: This text**   
## Эквивалент в .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc, fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [\_getch, \_getwch](../Topic/_getch,%20_getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)