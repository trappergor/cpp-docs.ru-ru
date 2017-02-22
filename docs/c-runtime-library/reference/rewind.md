---
title: "rewind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rewind"
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
  - "rewind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "указатели файлов [C++]"
  - "указатели файлов [C++], изменение положения"
  - "изменение положения указателей файлов"
  - "rewind - функция"
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# rewind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемещает файловый указатель на начало файла.  
  
## Синтаксис  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру **FILE**.  
  
## Заметки  
 Функция **rewind** перемещает файловый указатель, связанный с `stream` на начало файла.  Вызов **rewind** аналогичен  
  
 **\(void\) fseek\(** `stream`**, 0L,** `SEEK_SET` **\);**  
  
 Однако в отличие от `fseek`, **rewind** удаляет индикаторы ошибок для потока, а также индикатор конца файла.  Кроме того, в отличие от `fseek`, **rewind** не возвращает значение, указывающее, успешно ли был перемещен указатель.  
  
 Чтобы очистить буфер клавиатуры, используйте **rewind** с потоком `stdin`, который по умолчанию связан с клавиатурой.  
  
 Если указателю передано `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает управление и `errno` принимает значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**rewind**|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## Output  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)