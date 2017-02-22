---
title: "ftell, _ftelli64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64"
  - "ftell"
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
  - "_ftelli64"
  - "ftell"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftelli64 - функция"
  - "указатели файлов [C++]"
  - "указатели файлов [C++], получение текущей позиции"
  - "ftell - функция"
  - "ftelli64 - функция"
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# ftell, _ftelli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущее положение указателя файла.  
  
## Синтаксис  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Целевая структура `FILE`.  
  
## Возвращаемое значение  
 `ftell` и `_ftelli64` возвращают текущее положение файла.  Значение, возвращаемое `ftell` и `_ftelli64`, не может отражать физическое смещение в байтах для потоков, открытых в текстовом режиме, поскольку текстовый режим вызывает преобразование возврата каретки — перевод строки \(CR\-LF\).  Используйте `ftell` с `fseek`или`_ftelli64`с`_fseeki64` для возврата к расположениям файлов правильно.  При ошибке, `ftell`и`_ftelli64` вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции возвращают –1L и set `errno` одной из двух констант, определенных в ERRNO.H.  Константа `EBADF` означает, что аргумент `stream` не является допустимым значением указателя файла или не ссылается на открытый файл.  `EINVAL` означает, что недопустимый аргумент `stream` передан функции.  Для устройств, неспособных выполнять поиск \(например, терминалы и принтеры\), или если `stream` не ссылается на открытый файл, возвращаемое значение не определено.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функции `ftell` и `_ftelli64`извлекают текущую позицию указателя файла \(если есть\), связанного с `stream`*.* Позиция представляется как смещение относительно начала потока.  
  
 Обратите внимание, что когда файл открывается для добавления данных, текущее положение в файле определяется последней операцией ввода\-вывода, а не тем, где должна произойти запись.  Например, если файл открывается для добавления, и последней операцией было чтение, то положением в файле является место, где должна произойти следующая операция чтения, а не следующая операция записи. \(Если файл открывается для добавления, позиция в файле перемещается в конец файла до любой операции записи\). Если в открытом для добавления файле еще не произошла операция ввода\-вывода, то позицией в файле является начало файла.  
  
 В текстовом режиме CTRL\+Z интерпретируется как символ конца файла на входе.  В файлах, открытых для чтения или записи, `fopen` и все связанные процедуры проверяют наличие CTRL\+Z в конце файла и удаляют его, если это возможно.  Это делается потому, что использование комбинации `ftell` и `fseek` или `_ftelli64` и `_fseeki64` для перемещения в файле, который заканчивается CTRL\+Z, может вызвать неправильное поведение `ftell` или `_ftelli64` ближе к концу файла.  
  
 Эта функция блокирует вызывающий поток во время выполнения, поэтому потокобезопасна.  Для неблокирующей версии см. `_ftell_nolock`.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательные заголовки|  
|-------------|----------------------------|------------------------------|  
|`ftell`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64`|\<stdio.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
  **Позиция после попытки считывания 100 байт: 100**   
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)