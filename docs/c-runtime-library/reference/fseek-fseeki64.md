---
title: "fseek, _fseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseeki64"
  - "fseek"
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
  - "fseek"
  - "_fseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseeki64 - функция"
  - "указатели файлов [C++]"
  - "указатели файлов [C++], перемещение"
  - "fseek - функция"
  - "fseeki64 - функция"
  - "искать указатели файлов"
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# fseek, _fseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемещает указатель файла в указанное местоположение.  
  
## Синтаксис  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `offset`  
 Число байт, начиная с `origin`.  
  
 `origin`  
 Первоначальная позиция.  
  
## Возвращаемое значение  
 Если операция завершилась удачно, `fseek` и `_fseeki64` возвращают 0.  В противном случае возвращается ненулевое значение.  Для устройств, которые не поддерживают поиск, возвращаемое значение не определено.  Если `stream` принимает пустой указатель или если `origin` не является одним из описанных ниже допустимых значений, `fseek` и `_fseeki64` вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  
  
## Заметки  
 Функции `fseek` и `_fseeki64` перемещают указатель файла \(если он есть\), связанный со `stream` в новое расположение, которое отстоит на `offset` байт от `origin`*.* Следующей операция в потоке происходит в новом расположении.  В потоке, открытом для обновления, следующая операция может быть либо операцией чтения, либо операцией записи.  Аргумент origin должен быть одной из следующих констант, определенных в STDIO.H:  
  
 `SEEK_CUR`  
 Текущая позиция указателя файла.  
  
 `SEEK_END`  
 Конец файла.  
  
 `SEEK_SET`  
 Начало файла.  
  
 `fseek` и `_fseeki64` можно использовать, чтобы изменить положение указателя на любое место файла.  Указатель также может быть размещен за пределами файла.  `fseek` и `_fseeki64`удаляют индикатор конца файла и отменяют эффект всех предыдущих вызовов `ungetc` для `stream`.  
  
 Когда файл открывается для добавления данных, текущее положение в файле определяется последней операцией ввода\-вывода, а не тем, где должна произойти запись.  Если в открытом для добавления файле еще не произошла операция ввода\-вывода, то позицией в файле является начало файла.  
  
 Для потоков, открытых в текстовом режиме, `fseek` и `_fseeki64`имеются ограничения использования, поскольку символы возврата каретки и перевода строки могут привести к тому, что `fseek` и `_fseeki64`будут давать непредвиденные результаты.  Единственными операциями `fseek` и `_fseeki64`, которые гарантировано работают с потоками, открытыми в текстовом режиме, являются:  
  
-   Поиск со смещением 0 относительно любого значения origin.  
  
-   Поиск от начала файла со значением offset, возвращенным из вызова `ftell`, при использовании `fseek`, или `_ftelli64`, при использовании`_fseeki64`.  
  
 Также в текстовом режиме CTRL\+Z интерпретируется как символ конца файла на входе.  В файлах, открытых для чтения или записи, `fopen` и все связанные процедуры проверяют наличие CTRL\+Z в конце файла и удаляют его, если это возможно.  Это делается потому, что использование комбинации `fseek` и `ftell`или`_fseeki64` и `_ftelli64` для перемещения в файле, который заканчивается CTRL\+Z, может вызвать неправильное поведение `fseek` или `_fseeki64` ближе к концу файла.  
  
 Когда библиотека CRT открывает файл, который начинается с метки порядка байтов \(BOM\), указатель файла помещается после метки \(то есть в начале фактического содержимого файла\).  Если необходимо использовать `fseek` в начале файла, используйте `ftell`, чтобы получить первоначальную позицию, и используйте `fseek` с этим значением, вместо значения 0.  
  
 Эта функция блокирует работу других потоков во время выполнения, поэтому потокобезопасна.  Для неблокирующей версии см. [\_fseek\_nolock, \_fseeki64\_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
  **File pointer is set to middle of first line.**  
**This is the file 'fseek.out'.**   
## Эквивалент в .NET Framework  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)