---
title: _fsopen, _wfsopen | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce69c6789ba65f61c54957dde3dfa6965bc32e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen

Открывает поток с совместным доступом к файлу.

## <a name="syntax"></a>Синтаксис

```C
FILE *_fsopen(
   const char *filename,
   const char *mode,
   int shflag
);
FILE *_wfsopen(
   const wchar_t *filename,
   const wchar_t *mode,
   int shflag
);
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя файла, который необходимо открыть.

*mode*<br/>
Тип разрешенного доступа.

*shflag*<br/>
Разрешенный тип общего доступа.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на поток. Значение указателя null обозначает ошибку. Если *filename* или *режим* — **NULL** или является пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров ](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **NULL** и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Fsopen** функция открывает файл, указанный параметром *filename* виде потока и готовит файл для последующих общих операций чтения или записи, как определено режимом и *shflag*аргументы. **_wfsopen** — это двухбайтовая версия **_fsopen**; *filename* и *режим* аргументы **_wfsopen** , строки расширенных символов. **_wfsopen** и **_fsopen** ведут себя идентично.

Символьная строка *режим* указывает тип доступа, запрошенный для файла, как показано в следующей таблице.

|Термин|Определение|
|----------|----------------|
|**"r"**|Открывает для чтения. Если файл не существует или не удается найти **_fsopen** вызов завершается с ошибкой.|
|**"w"**|Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.|
|**"a"**|Открывает для записи в конец файла (добавление); сначала создает файл, если он не существует.|
|**"r+"**|Открывает для чтения и записи. (Файл должен существовать.)|
|**"w+"**|Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.|
|**"a+"**|Открывает для чтения и добавления; сначала создает файл, если он не существует.|

Используйте **«w»** и **«w +»** типы с осторожностью, как они могут приводить к уничтожению существующих файлов.

Если файл открыт с **«»** или **«+»** доступ к типу, все операции записи выполняются в конце файла. Указатель файла может быть перемещен с помощью [fseek](fseek-fseeki64.md) или [rewind](rewind.md), но он всегда возвращается в конец файла перед выполнением операции все записи. Поэтому перезаписать существующие данные невозможно. Когда **«r +»**, **«w +»**, или **«+»** задан тип доступа, чтение и запись разрешены (файл говорят, что открыт для обновления). Однако при переключении между чтением и записью необходима промежуточная операция [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) или [rewind](rewind.md). Текущее положение может быть указан для [fsetpos](fsetpos.md) или [fseek](fseek-fseeki64.md) при необходимости. Помимо вышеуказанных значений один из следующих символов может быть включено в *режим* для определения режима преобразования новых строк, а также для управления файлами.

|Термин|Определение|
|----------|----------------|
|**t**|Открывает файл в текстовом режиме (с преобразованием). В этом режиме каретки возврат строки веб-канала (CR-LF) преобразуются в веб-каналы одной строки (LF) на входе и символы перевода строки преобразуются на выходе в сочетания возврата каретки. Кроме того, при вводе символ CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или чтения/записи **_fsopen** проверяет наличие CTRL + Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование [fseek](fseek-fseeki64.md) и [ftell](ftell-ftelli64.md) для перемещения в файле, который заканчивается символом CTRL + Z, может вызвать [fseek](fseek-fseeki64.md) неправильное поведение ближе к концу файла.|
|**b**|Открывает файл в двоичном (непреобразованном) режиме; вышеописанные преобразования отключены.|
|**S**|Указывает, что кэширование оптимизировано для последовательного доступа с диска, но не ограничивается им.|
|**R**|Указывает, что кэширование оптимизировано для случайного доступа с диска, но не ограничивается им.|
|**T**|Определяет файл как временный. По возможности он не сбрасывается на диск.|
|**D**|Определяет файл как временный. Он удаляется, если закрывается последний указатель файла.|

Если символы **t** или **b** в параметре *mode* не указаны, режим преобразования определяется переменной режима по умолчанию **_fmode**. Если **t** или **b** указан как префикс аргумента, функция завершается с ошибкой и возвращает **NULL**. Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Аргумент *shflag* — это константное выражение, которое состоит из одной из следующих констант манифеста, определенных в Share.h.

|Термин|Определение|
|----------|----------------|
|**_SH_COMPAT**|Задает режим совместимости для 16 разрядных приложений.|
|**_SH_DENYNO**|Разрешает доступ на чтение и запись.|
|**_SH_DENYRD**|Запрещает доступ к файлу для чтения.|
|**_SH_DENYRW**|Запрещает доступ к файлу для чтения и записи.|
|**_SH_DENYWR**|Запрещает доступ к файлу для записи.|

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательные заголовки|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> Для константы манифеста для *shflag* параметра.|
|**_wfsopen**|\<stdio.h> или \<wchar.h>|\<share.h><br /><br /> Для константы манифеста для *shflag* параметра.|

## <a name="example"></a>Пример

```C
// crt_fsopen.c

#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   FILE *stream;

   // Open output file for writing. Using _fsopen allows us to
   // ensure that no one else writes to the file while we are
   // writing to it.
    //
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )
   {
      fprintf( stream, "No one else in the network can write "
                       "to this file until we are done.\n" );
      fclose( stream );
   }
   // Now others can write to the file while we read it.
   system( "type outfile" );
}
```

```Output
No one else in the network can write to this file until we are done.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
