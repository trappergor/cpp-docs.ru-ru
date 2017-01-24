---
title: "_getw | Microsoft Docs"
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
  - "_getw"
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
  - "_getw"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getw - функция"
  - "getw - функция"
  - "целые числа, получение из потоков"
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает целое число из потока.  
  
## Синтаксис  
  
```  
int _getw(   
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 `_getw` возвращает прочитанное целочисленное значение.  Возвращаемое значение `EOF` показывает или ошибку, или конец файла.  Однако, поскольку значение `EOF` также является допустимым целочисленным значением, используйте `feof` или `ferror` для проверки на конец файла или ошибочное условие.  Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `EOF`.  
  
## Заметки  
 Функция `_getw` считывает следующее бинарное значение типа `int` из файла, связанного со `stream`, и увеличивает связанный указатель файла \(при наличии\) для указания на следующий непрочитанный символ.  `_getw` не имеет никакого специального выравнивания элементов в потоке.  Проблемы с миграцией могут возникать из\-за `_getw`, поскольку размер типа `int` и порядок байт внутри типа `int` различны в различных системах.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_getw`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_getw.c  
// This program uses _getw to read a word  
// from a stream, then performs an error check.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   int i;  
  
   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )  
      printf( "Couldn't open file\n" );  
   else  
   {  
      // Read a word from the stream:  
      i = _getw( stream );  
  
      // If there is an error...  
      if( ferror( stream ) )  
      {  
         printf( "_getw failed\n" );  
         clearerr_s( stream );  
      }  
      else  
         printf( "First data word in file: 0x%.4x\n", i );  
      fclose( stream );  
   }  
}  
```  
  
## Input: crt\_getw.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
First data word in file: 0x656e694c  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_putw](../../c-runtime-library/reference/putw.md)