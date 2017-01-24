---
title: "getc, getwc | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getwc"
  - "getc"
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
  - "_gettc"
  - "getwc"
  - "_gettchar"
  - "getc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettc - функция"
  - "знаки, чтение"
  - "getc - функция"
  - "gettc - функция"
  - "getwc - функция"
  - "getwchar - функция"
  - "чтение знаков из потоков"
  - "потоки, чтение знаков из"
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getc, getwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает символ из потока.  
  
## Синтаксис  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Входной поток.  
  
## Возвращаемое значение  
 Возвращает считанный символ.  Чтобы указать на ошибку чтения или конец файла, `getc` возвращает `EOF`, а `getwc` возвращает `WEOF`.  Для `getc` используйте `ferror` или `feof` для проверки на наличие ошибок или на конец файла.  Если `stream` равен `NULL`, то `getc` и `getwc` вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешается, эти функции возвращают `EOF` \(или `WEOF` для`getwc`\) и устанавливают для `errno` значение `EINVAL`.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Каждая процедура считывает один символ из текущей позиции в файле и увеличивает связанный файловый указатель \(если он определен\), чтобы он указывал на следующий символ.  Файл, связанный с объектом `stream`.  
  
 Эти функции блокируют вызывающий поток и, следовательно, являются потокобезопасными.  Для неблокирующей версии см. [\_getc\_nolock, \_getwc\_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md).  
  
 Замечания относительно особенностей процедур.  
  
|Подпрограмма|Примечания|  
|------------------|----------------|  
|`getc`|Аналогично `fgetc`, но с реализацией в виде функции и в качестве макроса.|  
|`getwc`|Версия `getc` для работы с расширенными символами.  Считывает многобайтовый или расширенный символ согласно тому, открыт ли `stream` в текстовом режиме или в бинарном режиме.|  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`getc`|\<stdio.h\>|  
|`getwc`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## Ввод: crt\_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Input was: Line one.  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [\_getch, \_getwch](../Topic/_getch,%20_getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)