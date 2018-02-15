---
title: "_dup, _dup2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _dup
- _dup2
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _dup2
- _dup
dev_langs:
- C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 687c8e0d2f9f8f860e78a1c8e44cab6886e3cf04
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="dup-dup2"></a>_dup, _dup2
Создает второй дескриптор файла для открытого файла (`_dup`) или переназначает дескриптор файла (`_dup2`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fd`, `fd1`  
 Дескрипторы файлов, ссылающиеся на открытый файл.  
  
 `fd2`  
 Любой дескриптор файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_dup` возвращает новый дескриптор файла. Функция `_dup2` возвращает 0 в случае успеха. При возникновении ошибки каждая функция возвращает -1 и устанавливает `errno` для `EBADF` Если дескриптор файла является недопустимым или `EMFILE` Если доступных нет дополнительных дескрипторов файлов. В случае недопустимого дескриптора файла функция также вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функции `_dup` и `_dup2` связывают второй дескриптор файла с текущим открытым файлом. Их можно использовать для связывания предопределенного дескриптора файла, например `stdout`, с другим файлом. Операции с файлом можно выполнять с использованием любого дескриптора файла. При создании нового дескриптора тип доступа к файлу не изменяется. Функция `_dup` возвращает следующий доступный дескриптор файла для указанного файла. Функция `_dup2` принудительно устанавливает `fd2` на тот же файл, что и `fd1`. Если во время вызова дескриптор `fd2` связан с открытым файлом, этот файл закрывается.  
  
 Функции `_dup` и `_dup2` принимают в качестве параметров дескрипторы файлов. Для передачи потока `(FILE *)` в любую из этих функций используйте функцию [_fileno](../../c-runtime-library/reference/fileno.md). Подпрограмма `fileno` возвращает дескриптор файла, в данный момент связанный с заданным потоком. В следующем примере показано, как связать `stderr` (определяется как `FILE` `*` в Stdio.h) с дескриптором файла:  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_dup`|\<io.h>|  
|`_dup2`|\<io.h>|  
  
 Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью —`stdin`, `stdout`, и `stderr`— необходимо перенаправить, чтобы функции времени выполнения C можно использовать их в [! INCLUDEUWP приложения. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
This goes to stdout first  
This goes to stdout  
  
The file 'data' contains:  
This goes to file 'data'  
```  
  
## <a name="see-also"></a>См. также  
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)