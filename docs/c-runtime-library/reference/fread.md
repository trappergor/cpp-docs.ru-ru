---
title: "fread | Microsoft Docs"
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
  - "fread"
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
  - "fread"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "данные [C++], чтение из входящего потока"
  - "fread - функция"
  - "чтение данных [C++], из входящих потоков"
  - "потоки [C++], чтение данных из"
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Читает данные из потока.  
  
## Синтаксис  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `buffer`  
 Место хранения данных.  
  
 `size`  
 Размер элемента в байтах.  
  
 `count`  
 Максимальное количество элементов, которые требуется прочитать.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 `fread` возвращает число полных фактически прочитанных элементов, которое может быть меньше `count` при возникновении ошибки или при достижении конца файла до `count`*.* Используйте функцию `feof` или `ferror` для того, чтобы отличить ошибку чтения от конца файла.  Если `size` или `count` равны 0, `fread` возвращает 0 и не меняет содержимое буфера.  Если `stream` или `buffer` является пустым указателем, `fread` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает 0.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Функция `fread` считывает до `count` элементов размером `size` байт из входного `stream` и сохраняет их в `buffer`*.* Указатель файла, связанный с `stream` \(если такой есть\), увеличивается на число фактически считанных байтов.  Если данный поток открыт в текстовом режиме, пары возврата каретки\-перевода строки заменяются одиночными символами перевода строки.  Замена не влияет на указатель файла или возвращаемое значение.  Положение файлового указателя не определено при возникновении ошибки.  Значение частично прочитанного элемента невозможно определить.  
  
 Эта функция блокирует работу других потоков.  Если требуется неблокирующая версия, используйте `_fread_nolock`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fread`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
  **Wrote 25 items**  
**Number of items read \= 25**  
**Contents of buffer \= zyxwvutsrqponmlkjihgfedcb**   
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)