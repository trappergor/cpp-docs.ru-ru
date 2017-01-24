---
title: "fread_s | Microsoft Docs"
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
  - "fread_s"
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
  - "fread_s"
  - "stdio/fread_s"
dev_langs: 
  - "C++"
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fread_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Читает данные из потока.  Эта версия [fread](../../c-runtime-library/reference/fread.md) имеет усовершенствованную безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `buffer`  
 Место хранения данных.  
  
 `bufferSize`  
 Размер буфера назначения в байтах.  
  
 `elementSize`  
 Размер элемента для чтения в байтах.  
  
 `count`  
 Максимальное количество элементов, которые требуется прочитать.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 `fread_s` возвращает количество \(полных\) элементов, считанных в буфер, которое может быть меньше `count` при возникновении ошибки или конца файла до считывания `count` байт.  Используйте функцию `feof` или `ferror` для того, чтобы отличить ошибку от конца файла.  Если `size` или `count` равны 0, `fread_s` возвращает 0 и не меняет содержимое буфера.  Если `stream` или `buffer` является пустым указателем, `fread_s` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает 0.  
  
 Дополнительные сведения о кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `fread_s` считывает до `count` элементов размером `elementSize` байтов из входного `stream` и сохраняет их в `buffer`.  Указатель файла, связанный с `stream` \(если такой есть\), увеличивается на число фактически считанных байтов.  Если данный поток открыт в текстовом режиме, пары возврата каретки\-перевода строки заменяются одиночными символами перевода строки.  Замена не влияет на указатель файла или возвращаемое значение.  Положение файлового указателя не определено при возникновении ошибки.  Значение частично прочитанного элемента невозможно определить.  
  
 Эта функция блокирует работу других потоков.  Если требуется неблокирующая версия, используйте `_fread_nolock`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fread_s`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```cpp  
  
// crt_fread_s.c  
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c  
//  
// This program opens a file that's named FREAD.OUT and  
// writes characters to the file. It then tries to open  
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
#define BUFFERSIZE 30  
#define DATASIZE 22  
#define ELEMENTCOUNT 2  
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)  
#define FILENAME "FREAD.OUT"  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   for ( i = 0; i < DATASIZE; i++ )  
      list[i] = (char)('z' - i);  
   list[DATASIZE] = '\0'; // terminal null so we can print it  
  
   // Open file in text mode:  
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )  
   {  
      // Write DATASIZE characters to stream   
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );  
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );  
      printf( "Wrote %d items\n\n", numwritten );  
      fclose( stream );  
   } else {  
      printf( "Problem opening the file\n" );  
      return -1;  
   }  
  
   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {  
      // Attempt to read in characters in 2 blocks of 11  
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );  
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );  
      printf( "Contents of buffer after write/read:\n\t%s\n", list );  
      fclose( stream );  
   } else {  
      printf( "File could not be opened\n" );  
      return -1;  
   }  
}  
```  
  
  **Contents of buffer before write\/read:**   
 **zyxwvutsrqponmlkjihgfe**  
 **Wrote 22 items**   
 **Number of 11\-byte elements read \= 2**   
 **Contents of buffer after write\/read:**   
 **zyxwvutsrqponmlkjihgfe**    
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)