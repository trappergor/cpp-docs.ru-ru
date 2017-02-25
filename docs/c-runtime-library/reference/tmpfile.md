---
title: "tmpfile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tmpfile"
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
  - "tmpfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "временные файлы"
  - "Функция tmpfile"
  - "временные файлы, создание"
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# tmpfile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает временный файл.  Не рекомендуется использовать эту функцию, поскольку доступна более безопасная версия; см. [tmpfile\_s](../Topic/tmpfile_s.md).  
  
## Синтаксис  
  
```  
FILE *tmpfile( void );  
```  
  
## Возвращаемое значение  
 В случае успеха `tmpfile` возвращает указатель потока.  В противном случае возвращается указатель `NULL`.  
  
## Заметки  
 Функция `tmpfile` создает временный файл и возвращает указатель на поток.  Временный файл создается в корневом каталоге.  Чтобы создать временный файл в каталоге, отличном от корневого, используйте функцию [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) или [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Если файл не может быть открыт, `tmpfile` возвращает `NULL`.  Этот временный файл автоматически удаляется при закрытии файла, нормальном завершении программы или при вызове `_rmtmp` при условии, что текущая рабочая папка не изменяется.  Временный файл открывается в режиме `w+b` \(бинарный чтения\/записи\).  
  
 Ошибка может возникать при попытке более чем TMP\_MAX \(см. STDIO.H\) вызовов `tmpfile`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`tmpfile`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
> [!NOTE]
>  Для выполнения этого примера в среде Windows Vista требуются права администратора.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
  **Temporary file 1 was created**  
**Temporary file 2 was created**  
**Temporary file 3 was created**  
**3 temporary files deleted**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_rmtmp](../Topic/_rmtmp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)