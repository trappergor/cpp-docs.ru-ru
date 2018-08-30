---
title: _popen, _wpopen | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _popen
- _wpopen
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
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
dev_langs:
- C++
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc7d2b959bd8ad3ed89ae270e1f7d93406526695
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218390"
---
# <a name="popen-wpopen"></a>_popen, _wpopen

Создает канал и выполняет команду.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
FILE *_popen(
const char *command,
const char *mode
);
FILE *_wpopen(
const wchar_t *command,
const wchar_t *mode
);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Команда для выполнения.

*mode*<br/>
Режим возвращенного потока.

## <a name="return-value"></a>Возвращаемое значение

Возвращает поток, связанный с одним концом созданного канала. Другой конец канала связан со стандартным инициированным потоком ввода и вывода команд. Эти функции возвращают значение **NULL** при возникновении ошибки. Если ошибка является недопустимым параметром, например, если *команда* или *режим* является пустым указателем, или *режим* не является допустимым режимом, **errno** имеет значение **EINVAL**. Сведения о допустимых режимах см. в разделе "Примечания".

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Popen** функция создает канал и асинхронно выполняет инициируемую копию обработчика команд с указанной строки *команда*. Строка символов *mode* определяет запрошенный тип доступа, как показано ниже.

**«r»** вызывающий процесс может считывать инициируемый поток вывода команд с помощью возвращенного потока.

**«w»** вызывающий процесс может записывать инициируемый поток ввода команд с помощью возвращенного потока.

**«b»** открыть в двоичном режиме.

**«t»** открытым в текстовом режиме.

> [!NOTE]
> Если в программе Windows, **_popen** функция возвращает указатель недопустимый файл, в результате чего программа перестает отвечать на запросы в течение неограниченного времени. **_popen** работает должным образом в консольном приложении. Чтобы создать приложение Windows, которое перенаправляет входные и выходные данные, см. в разделе [Создание дочернего процесса с помощью перенаправления входных и выходных данных](/windows/desktop/ProcThread/creating-a-child-process-with-redirected-input-and-output) в пакете Windows SDK.

**_wpopen** — это двухбайтовая версия **_popen**; *путь* аргумент **_wpopen** — строка расширенных символов. **_wpopen** и **_popen** идентично в противном случае.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_popen**|\<stdio.h>|
|**_wpopen**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_popen.c
/* This program uses _popen and _pclose to receive a
* stream of text from a system process.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{

   char   psBuffer[128];
   FILE   *pPipe;

        /* Run DIR so that it writes its output to a pipe. Open this
         * pipe with read text attribute so that we can read it
         * like a text file.
         */

   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )
      exit( 1 );

   /* Read pipe until end of file, or an error occurs. */

   while(fgets(psBuffer, 128, pPipe))
   {
      printf(psBuffer);
   }

   /* Close pipe and print return value of pPipe. */
   if (feof( pPipe))
   {
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );
   }
   else
   {
     printf( "Error: Failed to read the pipe to the end.\n");
   }
}
```

### <a name="sample-output"></a>Пример результатов выполнения

Эти выходные данные предполагают, что в текущем каталоге находится только один файл с расширением имени файла .c.

```Output
 Volume in drive C is CDRIVE
 Volume Serial Number is 0E17-1702

Directory of D:\proj\console\test1

 07/17/98  07:26p                   780 popen.c
               1 File(s)            780 bytes
                             86,597,632 bytes free

Process returned 0
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pclose](pclose.md)<br/>
[_pipe](pipe.md)<br/>
