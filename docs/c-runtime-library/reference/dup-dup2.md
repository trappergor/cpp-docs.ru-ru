---
title: "_dup, _dup2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dup"
  - "_dup2"
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
  - "_dup2"
  - "_dup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_dup - функция"
  - "_dup2 - функция"
  - "dup - функция"
  - "dup2 - функция"
  - "файловые дескрипторы [C++], дублирование"
  - "файловые дескрипторы [C++], повторное назначение"
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _dup, _dup2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает второй идентификатор файла для открытого файла \(`_dup`\) или переназначает идентификатор файла \(`_dup2`\).  
  
## Синтаксис  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### Параметры  
 `fd`, `fd1`  
 Файловые идентификаторы, ссылающиеся на открытый файл.  
  
 `fd2`  
 Любой идентификатор файла.  
  
## Возвращаемое значение  
 `_dup` возвращает идентификатор нового файла.  `_dup2` возвращает 0 в случае успеха.  При возникновении ошибки, каждая функция возвращает –1 и устанавливает `errno` в `EBADF`, если идентификатор файла является недопустимым, или в `EMFILE`, если больше нет доступных идентификаторов фала.  В случае недопустимого идентификатора файла, функция также вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функции `_dup` и `_dup2` связывают второй идентификатор файла с открываемым в данный момент файлом.  Их можно использовать для связывания предопределенного идентификатора файла, например, идентификатора `stdout`, с другим файлом.  Операции с файлом могут быть выполнены с использованием любого файлового дескриптора.  Тип доступа к файлу не затрагивается созданием нового идентификатора.  `_dup` возвращает следующий доступный файловый идентификатор для указанного файла.  `_dup2` заставляет `fd2` ссылаться на тот же файл, что и `fd1`.  Если `fd2` связан с открытым файлом во время вызова, этот файл закрывается.  
  
 И `_dup`, и `_dup2` принимают идентификаторы файла в качестве параметров.  Для передачи потока `(FILE *)` в любую из этих функций, используйте [\_fileno](../Topic/_fileno.md).  Процедура `fileno` возвращает идентификатор файла в данный момент связанный с данным потоком.  В следующем примере показано, как связать `stderr` \(определяется как `FILE` `*` в Stdio.h\) с идентификатором файла:  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_dup`|\<io.h\>|  
|`_dup2`|\<io.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
  **This goes to stdout first**  
**This goes to stdout**  
**The file 'data' contains:**  
**This goes to file 'data'**   
## См. также  
 [Низкоуровневый ввод\-вывод](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../Topic/_close.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)