---
title: _beginthread, _beginthreadex | Документы Майкрософт
ms.custom: ''
ms.date: 02/27/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _beginthread
- _beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d56bcc5ec779b077305d9d80e4a4e6b5e511df5e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704663"
---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex

Создает поток.

## <a name="syntax"></a>Синтаксис

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>Параметры

*start_address*<br/>
Начальный адрес процедуры, который начинает выполнение нового потока. Для **_beginthread**, соглашение о вызовах [__cdecl](../../cpp/cdecl.md) (для машинного кода) или [__clrcall](../../cpp/clrcall.md) (для управляемого кода); для **_beginthreadex**, либо [__stdcall](../../cpp/stdcall.md) (для машинного кода) или [__clrcall](../../cpp/clrcall.md) (для управляемого кода).

*stack_size*<br/>
Размер стека нового потока или 0.

*arglist*<br/>
Список аргументов, передаваемых нового потока или **NULL**.

*Безопасность*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *безопасности* — **NULL**, дескриптор не наследуется. Должно быть **NULL** для приложений Windows 95.

*initflag*<br/>
Флаги, управляющие начальным состоянием нового потока. Задать *initflag* 0 для немедленного запуска, либо **CREATE_SUSPENDED** при создании потока в приостановленном состоянии; используйте [ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx) для выполнения потока. Задать *initflag* для **STACK_SIZE_PARAM_IS_A_RESERVATION** флаг для использования *stack_size* как первоначального Резервируемый размер стека в байтах, если этот флаг не указан, *stack_size* задает выделенный размер.

*thrdaddr*<br/>
Указывает на 32-разрядную переменную, которая получает идентификатор потока. Если это **NULL**, он не используется.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха каждая из этих функций возвращает дескриптор во вновь созданный поток; Однако если вновь созданный поток выполняет выход слишком быстро **_beginthread** может не возвращать допустимый дескриптор. (См. обсуждение в разделе "Заметки".) При возникновении ошибки **_beginthread** возвращает-1 L и **errno** равно **EAGAIN** Если слишком много потоков, значение **EINVAL** при аргументе Недопустимый или размер стека неверен, или к **EACCES** Если недостаточно ресурсов (например, памяти). При возникновении ошибки **_beginthreadex** возвращает 0, и **errno** и **_doserrno** заданы.

Если *start_address* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают -1.

Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Дополнительные сведения о **uintptr_t**, в разделе [стандартные типы](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Примечания

**_Beginthread** функция создает поток, который начинает выполнение процедуры в *start_address*. В процедуре *start_address* необходимо использовать **__cdecl** (для машинного кода) или **__clrcall** (для управляемого кода) соглашение о вызовах и не должно быть возвращаемого значения. При возврате потока из этой процедуры он завершается автоматически. Дополнительные сведения о потоках см. в разделе [Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** напоминает Win32 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) API более чем **_beginthread** does. **_beginthreadex** отличается от **_beginthread** одним из следующих способов:

- **_beginthreadex** имеет три дополнительных параметра: *initflag*, *безопасности*, и **threadaddr**. Новый поток можно создать в приостановленном состоянии, с заданными параметрами безопасности, а может быть получен с использованием *thrdaddr*, который является идентификатором потока.

- В процедуре *start_address* , передаваемое в **_beginthreadex** необходимо использовать **__stdcall** (для машинного кода) или **__clrcall** (для управляемый код) соглашение о вызовах и должен возвращать код завершения потока.

- **_beginthreadex** для сбоя, а не-1 L возвращает 0.

- Поток, который создается с помощью **_beginthreadex** завершается вызовом [_endthreadex](endthread-endthreadex.md).

**_Beginthreadex** функция предоставляет больший контроль над способ создания потока, чем **_beginthread** does. **_Endthreadex** функция является более гибкой. Например, с помощью **_beginthreadex**, можно использовать сведения о безопасности, задавать исходное состояние потока (выполняемого или приостановленного) и получить идентификатор только что созданного потока. Можно также использовать дескриптор потока, возвращаемый **_beginthreadex** с API синхронизации, что нельзя выполнить с помощью **_beginthread**.

Безопаснее использовать **_beginthreadex** чем **_beginthread**. Если поток, созданный **_beginthread** выполняет выход быстро, маркер, который возвращается вызывающему объекту **_beginthread** может быть недопустим или указывать на другой поток. Тем не менее дескриптор, возвращенный **_beginthreadex** должен быть закрыт вызывающим объектом **_beginthreadex**, поэтому он гарантированно является допустимым дескриптором Если **_beginthreadex** не вернул ошибку.

Можно вызвать [_endthread](endthread-endthreadex.md) или **_endthreadex** явным образом, чтобы завершить поток; Однако **_endthread** или **_endthreadex** вызывается автоматически при возврате потока из процедуры, что передается в качестве параметра. Завершение потока вызовом **_endthread** или **_endthreadex** помогает обеспечить правильное восстановление ресурсов, выделяемых для потока.

**_endthread** автоматически закрывает дескриптор потока, тогда как **_endthreadex** — нет. Таким образом, при использовании **_beginthread** и **_endthread**, не следует явно закрывать дескриптор потока, вызывая функцию Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API. Это поведение отличается от функции API Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) .

> [!NOTE]
> Для исполняемого файла, связанного с Libcmt.lib, не следует вызывать Win32 **ExitThread** API, чтобы вы не помешать системе времени выполнения освобождать выделенные ресурсы. **_endthread** и **_endthreadex** освобождают выделенные ресурсы потока и затем вызвать **ExitThread**.

Операционная система обрабатывает выделение стека при любом **_beginthread** или **_beginthreadex** вызываются; не нужно передавать адрес стека потоков любой из этих функций. Кроме того *stack_size* аргумент может быть 0, в случае чего операционная система использует то же значение как стек, указанный для основного потока.

*arglist* параметр должен быть передан только что созданного потока. Как правило, это адрес элемента данных, например строки символов. *arglist* может быть **NULL** , если он не является обязательным, но **_beginthread** и **_beginthreadex** должно быть задано либо значение для передачи новому потоку. Все потоки завершаются, если какой-либо поток вызывает [прервать](abort.md), **выхода**, **_exit**, или **ExitProcess**.

Языковой стандарт нового потока инициализируется с помощью данные каждого процесса глобального текущего языкового стандарта. Если языковой стандарт отдельного потока включен при вызове [_configthreadlocale](configthreadlocale.md) (глобально или для новых потоков только), поток может изменить его языковой стандарт независимо от других потоков, вызвав **setlocale** или **_wsetlocale**. Потоки, которые не имеют установлен флаг языкового стандарта отдельного потока может повлиять на сведения о локали в все потоки, кроме того, у которых нет флаг языкового стандарта отдельного потока, а также все вновь созданные потоки. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Для **/CLR** кода, **_beginthread** и **_beginthreadex** имеют две перегруженные версии. Одна имеет указатель функции соглашения о вызовах в машинном коде, а другая — **__clrcall** указатель функции. Первый перегруженный метод не является безопасным для домена приложения и никогда таковым не будет. При создании **/CLR** код, необходимо убедиться, что новый поток входит в правильный домен приложений, прежде чем он обращается к управляемым ресурсам. Это можно сделать, например, с помощью [функции call_in_appdomain](../../dotnet/call-in-appdomain-function.md). Вторая перегрузка является доменобезопасной; вновь созданный поток всегда завершается в домене приложения вызывающего объекта **_beginthread** или **_beginthreadex**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .

Для использования **_beginthread** или **_beginthreadex**, приложение должно быть связано с одной из многопотоковых библиотек времени выполнения C.

## <a name="example"></a>Пример

В следующем примере используется **_beginthread** и **_endthread**.

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

Чтобы закрыть приложение-пример, нажмите любую клавишу.

## <a name="example"></a>Пример

В следующем примере кода показано, как можно использовать дескриптор потока, возвращаемый **_beginthreadex** с помощью API синхронизации [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx). Основной поток ожидает завершения другого потока, прежде чем продолжить. Если второй поток вызывает **_endthreadex**, он заставляет его объект потока перейти в сигнальное состояние. Это позволяет продолжить выполнение основного потока. Это нельзя сделать с **_beginthread** и **_endthread**, так как **_endthread** вызовы **CloseHandle**, который удаляет поток Объект, прежде чем его можно перевести в сигнальное состояние.

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>См. также

- [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [abort](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)
