---
title: freopen, _wfreopen | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs:
- C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e371076ce095116930908174d4fa29e9cfd876e5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen

Переназначает указатель файла. Существуют более безопасные версии этих функций; см. раздел [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

## <a name="syntax"></a>Синтаксис

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*path*<br/>
Путь к новому файлу.

*mode*<br/>
Тип разрешенного доступа.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на вновь открытый файл. Если возникает ошибка, исходный файл закрывается, и функция возвращает **NULL** значение указателя. Если *путь*, *режим*, или *поток* является пустым указателем, или если *filename* является пустой строкой, эти функции вызывают недопустимый параметр обработчик, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **NULL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Существуют более безопасные версии этих функций; см. раздел [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

**Freopen** функция закрывает файл, который сейчас связан с *поток* и переназначает *поток* в файл, заданный параметром *путь*. **_wfreopen** — это двухбайтовая версия **_freopen**; *путь* и *режим* аргументы **_wfreopen** , строки расширенных символов. **_wfreopen** и **_freopen** ведут себя идентично.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen** обычно используется для перенаправления заранее открытых файлов **stdin**, **stdout**, и **stderr** для файлов, указанных пользователем. Новый файл, связанный с *поток* открывается с *режиме*, который представляет собой строку символов, указывающие тип доступа, запрошенный для файла, следующим образом:

|*mode*|Access|
|-|-|
**"r"**|Открывает для чтения. Если файл не существует или не удается найти **freopen** вызов завершается с ошибкой.
**"w"**|Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.
**"a"**|Открывается для записи в конце файла (добавление) без удаления маркера в конце файла (EOF) перед записью новых данных в файл. Создает файл, если он не существует.
**"r+"**|Открывает для чтения и записи. Файл должен существовать.
**"w+"**|Открывает пустой файл для чтения и записи. Если файл существует, его содержимое удаляется.
**"a+"**|Открывается для чтения и добавления. Операция добавления включает удаления маркера EOF перед записью новых данных в файл. Маркер EOF не восстанавливается по окончании записи. Создает файл, если он не существует.

Используйте **«w»** и **«w +»** типы с осторожностью, как они могут приводить к уничтожению существующих файлов.

Если файл открыт с **«»** или **«+»** получить доступ к типу, все операции записи выполняются в конце файла. Несмотря на то, что указатель файла может быть перемещен с помощью [fseek](fseek-fseeki64.md) или [rewind](rewind.md), указатель файла он всегда возвращается в конец файла перед выполнением операции все записи. Поэтому перезаписать существующие данные невозможно.

**«»** Режим не удаляет маркер конца файла перед добавлением в файл. После добавления команда MS-DOS TYPE отображает данные только до первоначального маркера EOF и не отображает данные, добавленные в файл. **«+»** Режим удаляет маркер конца файла перед добавлением в файл. После добавления команда TYPE MS-DOS отображает все данные в файле. **«+»** Режиме необходим для добавления в потоковый файл, маркером конца файла CTRL + Z.

Когда **«r +»**, **«w +»**, или **«+»** задан тип доступа, чтение и запись разрешены (файл говорят, что открыт для «обновления»). Однако при переключении между чтением и записью необходимо выполнить промежуточную операцию [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) или [rewind](rewind.md). Текущее положение может быть указан для [fsetpos](fsetpos.md) или [fseek](fseek-fseeki64.md) при необходимости. Помимо вышеуказанных значений один из следующих символов может быть включено в *режим* строка для определения режима преобразования новых строк.

|*режим* модификатор|Режим преобразования|
|-|-|
**t**|Откройте файл в текстовом (переведенном) режиме.
**b**|При открытии в двоичном (непреобразованном) режиме преобразования, включающие символы возврата каретки и перевода строки, подавляются.

В текстовом (переведенном) режиме каретки return-перевода строки (CR-LF) преобразуются в символы одной перевода строки (LF) во входных данных; Символы перевода строки преобразуются на выходе в сочетания возврата каретки. Кроме того, при вводе символ CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или для чтения и записи с **«+»**, библиотеки времени выполнения проверяет наличие CTRL + Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование [fseek](fseek-fseeki64.md) и [ftell](ftell-ftelli64.md) для перемещения в файле может привести к [fseek](fseek-fseeki64.md) неправильное поведение ближе к концу файла. **t** параметр является расширением Майкрософт, не должны использоваться где требуемого требуется обеспечить переносимость ANSI.

Если **t** или **b** не указаны в параметре *режим*, режим преобразования по умолчанию определяется глобальной переменной [_fmode](../../c-runtime-library/fmode.md). Если **t** или **b** указан как префикс аргумента, функция завершается с ошибкой и возвращает **NULL**.

Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
