---
title: "_flushall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_flushall"
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
  - "_flushall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция flushall"
  - "сохранение потоков"
  - "потоки, сохранение"
  - "Функция _flushall"
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _flushall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сбрасываются все потоки; очищаются все буферы.  
  
## Синтаксис  
  
```  
int _flushall( void );  
```  
  
## Возвращаемое значение  
 `_flushall` возвращает число открытых потоков \(ввода и вывода\).  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 По умолчанию функция `_flushall` записывает в соответствующие файлы содержимое всех буферов, связанных с открытыми потоками вывода.  Все буферы, связанные с открытыми входными потоками, очищаются. \(Эти буферы обычно обслуживаются операционной системой, которая определяет оптимальное время записи данных на диск автоматически: если буфер заполнен, при закрытии потока или когда нормально завершается выполнение программы без закрытия потоков\).  
  
 Если после чтения следует вызов `_flushall`, новые данные считываются из входных файлов в буферы.  Все потоки остаются открытыми после вызова `_flushall`.  
  
 Функция фиксации на диск библиотеки времени выполнения позволяет убедиться в том, что критические данные записаны непосредственно на диск, а не в буферы операционной системы.  Можно включить эту функцию без переписывания программы, связав объектные файлы программы с Commode.obj.  В появившемся исполняемом файле вызовы `_flushall` записывают содержимое всех буферов на диск.  Только `_flushall` и `fflush` подвержены влиянию Commode.obj.  
  
 Дополнительные сведения о управлении функцией фиксации на диск см. в разделах [Stream I\/O](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) и [\_fdopen](../Topic/_fdopen,%20_wfdopen.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_flushall`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
  **Были сброшены 3 потока**   
## Эквивалент в .NET Framework  
  
-   [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
-   [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)  
  
-   [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)  
  
-   [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../Topic/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)