---
title: _dup, _dup2
ms.date: 4/2/2020
api_name:
- _dup
- _dup2
- _o__dup
- _o__dup2
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dup2
- _dup
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
ms.openlocfilehash: 239f857bb40c9609cb6f7ff373295a7a1f8523a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348113"
---
# <a name="_dup-_dup2"></a>_dup, _dup2

Создает второй дескриптор файла для открытого файла **(_dup),** или переназначает дескриптор файла **(_dup2).**

## <a name="syntax"></a>Синтаксис

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Параметры

*fd*, *fd1*<br/>
Дескрипторы файлов, ссылающиеся на открытый файл.

*fd2*<br/>
Любой дескриптор файла.

## <a name="return-value"></a>Возвращаемое значение

**_dup** возвращает новый дескриптор файлов. **_dup2** возвращает 0, чтобы показать успех. При возникновении ошибки каждая функция возвращает -1 и устанавливает **errno** в **EBADF,** если дескриптор файла недействителен или **EMFILE,** если больше нет дескрипторов файлов. В случае недопустимого дескриптора файла функция также вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

**Функции _dup** и **_dup2** ассоциируют второй дескриптор файлов с открытым файлом. Эти функции могут быть использованы для ассоциировать предопределенный дескриптор файла, например, для **stdout,** с другим файлом. Операции с файлом можно выполнять с использованием любого дескриптора файла. При создании нового дескриптора тип доступа к файлу не изменяется. **_dup** возвращает следующий доступный дескриптор файла для данного файла. **_dup2** силы *fd2* для обозначения того же *файла, что и fd1*. Если *fd2* связан с открытым файлом во время вызова, этот файл закрывается.

Оба **_dup** и **_dup2** принимают дескрипторы файлов в качестве параметров. Чтобы передать поток`FILE *`() к любой из этих функций, используйте [_fileno.](fileno.md) **Fileno** рутина возвращает дескриптор файла, в настоящее время связанный с данным потоком. Следующий пример показывает, как связать **stderr** (определяется как `FILE *` в Stdio.h) с дескриптором файлов:

```C
int cstderr = _dup( _fileno( stderr ));
```

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью, **stdin,** **stdout**и **stderr,** должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
