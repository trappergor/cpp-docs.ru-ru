---
title: _popen, _wpopen
description: Справочник по функциям библиотеки Microsoft C Runtime (CRT), _popen и _wpopen.
ms.date: 01/28/2020
api_name:
- _popen
- _wpopen
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
no-loc:
- _popen
- _wpopen
- _tpopen
- _doserrno
- errno
- _sys_errlist
- _sys_nerr
- EINVAL
ms.openlocfilehash: 68531256fd688b50b659c885635ffa17d17773a5
ms.sourcegitcommit: 684181561490e0d1955cf601d222f67f09af6d00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/31/2020
ms.locfileid: "76894324"
---
# <a name="_popen-_wpopen"></a>_popen, _wpopen

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

*командная*\
Команда для выполнения.

*режим*\
Режим возвращенного потока.

## <a name="return-value"></a>Возвращаемое значение

Возвращает поток, связанный с одним концом созданного канала. Другой конец канала связан со стандартным инициированным потоком ввода и вывода команд. Эти функции возвращают значение **NULL** при возникновении ошибки. Если ошибка вызвана недопустимым параметром, **значение** аргумента « **еинвал**» задается равным. Сведения о допустимых режимах см. в разделе "Примечания".

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Заметки

Функция **_popen** создает канал. Затем он асинхронно выполняет порожденную копию обработчика команд и использует *команду* в качестве командной строки. Строка символов *mode* определяет запрошенный тип доступа, как показано ниже.

|Режим доступа|Описание|
|-|-|
|**"r"**|Вызывающий процесс может считывать инициируемый поток вывода команд с помощью возвращенного потока.|
|**"w"**|Вызывающий процесс может записывать инициируемый поток ввода команд с помощью возвращенного потока.|
|**"b"**|Открыть в двоичном режиме.|
|**"t"**|Открыть в текстовом режиме.|

> [!NOTE]
> При использовании в программе Windows функция **_popen** возвращает недопустимый указатель на файл, который приводит к тому, что программа перестает отвечать на запросы неограниченно долго. **_popen** правильно работает в консольном приложении. Сведения о создании приложения Windows, которое перенаправляет ввод и вывод, см. в разделе [Создание дочернего процесса с перенаправленным входом и выходом](/windows/win32/ProcThread/creating-a-child-process-with-redirected-input-and-output) в Windows SDK.

**_wpopen** — это версия **_popen**для расширенных символов; Аргумент *пути* к **_wpopen** является строкой расширенных символов. в противном случае **_wpopen** и **_popen** ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_popen**|\<stdio.h>|
|**_wpopen**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
      puts(psBuffer);
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

В выходных данных предполагается, что в текущем каталоге имеется только один файл с расширением `.c`.

```Output
Volume in drive C is CDRIVE
Volume Serial Number is 0E17-1702

Directory of D:\proj\console\test1

07/17/98  07:26p                   780 popen.c
               1 File(s)            780 bytes
                             86,597,632 bytes free

Process returned 0
```

## <a name="see-also"></a>См. также:

\ [управления процессами и средой](../../c-runtime-library/process-and-environment-control.md)
[_pclose](pclose.md)\
[_pipe](pipe.md)
