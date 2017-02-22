---
title: "fgets, fgetws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgets"
  - "fgetws"
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
  - "_fgetts"
  - "fgetws"
  - "fgets"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetts - функция"
  - "fgets - функция"
  - "fgetts - функция"
  - "fgetws - функция"
  - "потоки, получение строк из"
  - "потоки, чтение из"
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# fgets, fgetws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывание строки из потока.  
  
## Синтаксис  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `str`  
 Место хранения данных.  
  
 `n`  
 Наибольшее число символов для чтения.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает `str`.  `NULL` возвращается для отображения ошибки или конца файла.  Используйте `feof` или `ferror` для определения, произошла ли ошибка.  Если `str` или `stream` — нулевой указатель, или `n` меньше или равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `NULL`.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Функция `fgets` считывает строку из входного аргумента `stream` и сохраняет ее в `str`.  `fgets` считывает символы из потока начиная с текущей позиции и заканчивая первым символом новой строки \(включается в результат\), концом потока или считав `n` \- 1 символов.  Результат, сохраняющийся в `str`, дополняется нулевым символом.  Символ новой строки, если прочитан, включается в строку.  
  
 `fgetws` — это версия `fgets` для расширенных символов.  
  
 `fgetws` считывает в расширенную строку `str` как в расширенных символов или многобайтовых символов в зависимости от того, открыт ли `stream` в текстовом или бинарном режиме.  Дополнительные сведения о использовании текстового и бинарного режимов в юникоде и многобайтовом потоковом вводе\-выводе см. в разделах [Text and Binary Mode File I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) и [Unicode Stream I\/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fgets`|\<stdio.h\>|  
|`fgetws`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## Input: crt\_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Line one.  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)  
  
-   [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../Topic/fputs,%20fputws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../Topic/puts,%20_putws.md)