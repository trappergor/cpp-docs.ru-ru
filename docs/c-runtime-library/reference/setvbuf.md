---
title: "setvbuf | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setvbuf"
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
  - "setvbuf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "контроль потоковой буферизации"
  - "setvbuf - функция"
  - "потоковая буферизация"
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Контролирует потоковую буферизацию и размер буфера.  
  
## Синтаксис  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `buffer`  
 Выделенный пользователем буфер.  
  
 `mode`  
 Режим буферизации.  
  
 `size`  
 Размер буфера в байтах.  Допустимый диапазон: 2 \<\= `size` \<\= INT\_MAX \(2147483647\).  По сути, значение, заданное для `size`, округляется вниз до ближайшего числа, кратного 2.  
  
## Возвращаемое значение  
 Возвращает 0 в случае успеха.  
  
 Если `stream` имеет значение `NULL` или если `mode` или `size` имеет недопустимое значение, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает \-1 и устанавливает `errno` в `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `setvbuf` позволяет программе контролировать и буферизацию, и размер буфера для `stream`.  `stream` должен ссылаться на открытый файл, в котором не происходило операций ввода\-вывода с момента открытия.  Массив, на который указывает `buffer` используется в качестве буфера, если он не принимает значение `NULL`; в этом случае `setvbuf` использует автоматически выделенный буфер размером `size`\/2 \* 2 байт.  
  
 Режим должен быть `_IOFBF`, `_IOLBF` или `_IONBF`.  Если `mode` принимает значение `_IOFBF` или `_IOLBF`, то `size` используется как размер буфера.  Если `mode` принимает значение `_IONBF`, поток не буферизуется, и `size` и `buffer` игнорируются.  Значения для `mode` и их смысл:  
  
 `_IOFBF`  
 Полная буферизация; то есть `buffer` используется как буфер и `size` используется в качестве размера буфера.  Если `buffer` принимает значение `NULL`, используется автоматически выделенный буфер размером `size` байт.  
  
 `_IOLBF`  
 Для некоторых систем это обеспечивает линейную буферизацию.  Однако, для Win32, поведение совпадает с `_IOFBF` \- полной буферизацией.  
  
 `_IONBF`  
 Буфер не используется независимо от `buffer` или `size`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`setvbuf`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **'stream1' now has a buffer of 1024 bytes**  
**'stream2' now has no buffer**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../Topic/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)