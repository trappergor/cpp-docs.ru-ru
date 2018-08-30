---
title: _dup, _dup2 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 820172e1e6ab4ad007c89b2b40f03512134f0f0d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215957"
---
# <a name="dup-dup2"></a>_dup, _dup2

Создает второй дескриптор файла для открытого файла (**_dup**), или переназначает дескриптор файла (**_dup2**).

## <a name="syntax"></a>Синтаксис

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Параметры

*Fd*, *fd1*<br/>
Дескрипторы файлов, ссылающиеся на открытый файл.

*fd2*<br/>
Любой дескриптор файла.

## <a name="return-value"></a>Возвращаемое значение

**_dup** возвращает новый дескриптор файла. **_dup2** возвращает 0 в случае успеха. При возникновении ошибки каждая функция возвращает -1 и задает **errno** для **значение EBADF** Если дескриптор файла является недопустимым, или чтобы **EMFILE** Если больше нет дескрипторов файлов. В случае недопустимого дескриптора файла функция также вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Dup** и **_dup2** функции связать второй дескриптор файла с текущим открытым файлом. Эти функции могут использоваться для связывания предопределенного дескриптора файла, например, для **stdout**, используя другой файл. Операции с файлом можно выполнять с использованием любого дескриптора файла. При создании нового дескриптора тип доступа к файлу не изменяется. **_dup** возвращает следующий доступный дескриптор файла для заданного файла. **_dup2** заставляет *fd2* для ссылки на тот же файл *fd1*. Если *fd2* связан с открытым файлом во время вызова, этот файл закрывается.

Оба **_dup** и **_dup2** принимают в качестве параметров дескрипторы файлов. Для передачи потока (`FILE *`) в любую из этих функций используйте [_fileno](fileno.md). **Fileno** процедура возвращает дескриптор файла, в настоящее время связанный с заданным потоком. В следующем примере показано, как связать **stderr** (определяется как `FILE *` в Stdio.h) с дескриптором файла:

```C
int cstderr = _dup( _fileno( stderr ));
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_dup.c
// This program uses the variable old to save
// the original stdout. It then opens a new file named
// DataFile and forces stdout to refer to it. Finally, it
// restores stdout to its original state.

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

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
