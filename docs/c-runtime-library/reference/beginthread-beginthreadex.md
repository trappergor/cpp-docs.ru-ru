---
title: _beginthread, _beginthreadex
ms.date: 4/2/2020
api_name:
- _beginthread
- _beginthreadex
- _o__beginthread
- _o__beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: 2d2851a7e76a43501145b1e55e8028b72c2a8afb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348674"
---
# <a name="_beginthread-_beginthreadex"></a>_beginthread, _beginthreadex

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
Начальный адрес процедуры, который начинает выполнение нового потока. Для **_beginthread**, вызывающая конвенция либо [__cdecl](../../cpp/cdecl.md) (для родного кода), либо [__clrcall](../../cpp/clrcall.md) (для управляемого кода); для **_beginthreadex**, это либо [__stdcall](../../cpp/stdcall.md) (для родного кода) или [__clrcall](../../cpp/clrcall.md) (для управляемого кода).

*stack_size*<br/>
Размер стека нового потока или 0.

*arglist*<br/>
Список аргументов, который будет передан новому потоку, или **NULL.**

*Безопасность*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *безопасность* **NULL,** ручка не может быть унаследована. Должно быть **NULL** для Windows 95 приложений.

*флаг*<br/>
Флаги, управляющие начальным состоянием нового потока. Установите *initflag* до 0 для немедленного запуска или **для CREATE_SUSPENDED** для создания потока в приостановленном состоянии; используйте [ResumeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-resumethread) для выполнения потока. Установите *флаг,* чтобы **STACK_SIZE_PARAM_IS_A_RESERVATION** флаг, чтобы использовать *stack_size* в качестве первоначального размера резерва стека в байтах; если этот флаг не указан, *stack_size* указывает размер коммит.

*thrdaddr*<br/>
Указывает на 32-разрядную переменную, которая получает идентификатор потока. Если это **NULL,** он не используется.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха каждая из этих функций возвращает ручку в недавно созданный поток; однако, если вновь созданный поток выходит слишком быстро, **_beginthread** может не вернуть действительную ручку. (См. обсуждение в разделе Замечания.) При ошибке **_beginthread** возвращает -1L, а **errno** устанавливается **в EAGAIN,** если существует слишком много потоков, в **EINVAL,** если аргумент недействителен или размер стека неправильный, или **в EACCES,** если ресурсов недостаточно (например, в памяти). При ошибке **_beginthreadex** возвращает 0, а **также устанавливаются errno** и **_doserrno.**

Если *start_address* **NULL,** вызовуется обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EINVAL** и возвращают -1.

Для получения дополнительной информации об этих и других кодах возврата [_sys_nerr _sys_errlist _doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)см.

Для получения дополнительной информации о **uintptr_t,** [см.](../../c-runtime-library/standard-types.md)

## <a name="remarks"></a>Remarks

Функция **_beginthread** создает поток, который начинает выполнение рутины в *start_address.* Обычный режим в *start_address* должен использовать **__cdecl** (для родного кода) или **__clrcall** (для управляемого кода) вызывая конвенцию и не должен иметь значения возврата. При возврате потока из этой процедуры он завершается автоматически. Дополнительные сведения о потоках см. в разделе [Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** напоминает API Win32 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) более близко, чем **_beginthread.** **_beginthreadex** отличается от **_beginthread** следующим образом:

- **_beginthreadex** имеет три дополнительных параметра: *initflag,* *Security*и **threadaddr.** Новый поток может быть создан в подвешенном состоянии, с указанной безопасностью, и может быть доступен с помощью *thrdaddr*, который является идентификатором потока.

- Процедура в *start_address,* которая передается **_beginthreadex** должны использовать **__stdcall** (для родного кода) или **__clrcall** (для управляемого кода) вызова конвенции и должны вернуть код выхода потока потока.

- **_beginthreadex** возвращает 0 при сбое, а не -1L.

- Поток, созданный с помощью **_beginthreadex,** завершается вызовом [_endthreadex.](endthread-endthreadex.md)

Функция **_beginthreadex** дает вам больше контроля над созданием потока, чем **_beginthread.** Функция **_endthreadex** также более гибкая. Например, с **_beginthreadex**можно использовать информацию о безопасности, установить исходное состояние потока (запуск или приостановку) и получить идентификатор потока вновь созданного потока. Можно также использовать ручку потока, которая возвращается **_beginthreadex** с аПОГ синхронизации, что вы не можете сделать с **_beginthread.**

Безопаснее использовать **_beginthreadex,** чем **_beginthread.** Если поток, генерируемый **_beginthread,** быстро выходит, ручка, которая возвращается вызывающему **_beginthread** может быть недействительной или указать на другой поток. Тем не менее, ручка, которая возвращается **_beginthreadex** должна быть закрыта абонентом **_beginthreadex,** поэтому она гарантированно будет действительной ручкой, если **_beginthreadex** не вернули ошибку.

Можно позвонить [_endthread](endthread-endthreadex.md) или **_endthreadex** явно для завершения потока; однако **_endthread** или **_endthreadex** вызывается автоматически, когда поток возвращается из рутины, пройденой как параметр. Прекращение потока с вызовом **_endthread** или **_endthreadex** помогает обеспечить правильное восстановление ресурсов, выделенных для потока.

**_endthread** автоматически закрывает ручку потока, в то время как **_endthreadex** нет. Поэтому при использовании **_beginthread** и **_endthread,** не закрывайте ручку потока, вызывая API Win32 [CloseHandle.](/windows/win32/api/handleapi/nf-handleapi-closehandle) Это поведение отличается от функции API Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) .

> [!NOTE]
> Для исполняемого файла, связанного с Libcmt.lib, не звоните в API Win32 **ExitThread,** чтобы не препятствовать системе запускаемого времени рекультивировать выделенные ресурсы. **_endthread** и **_endthreadex** вернуть выделенные ресурсы потока, а затем вызвать **ExitThread**.

Операционная система обрабатывает распределение стека, когда вызывается **_beginthread** или **_beginthreadex;** вам не нужно передавать адрес стека потоков ни одной из этих функций. Кроме того, *аргумент stack_size* может быть 0, и в этом случае операционная система использует то же значение, что и стек, указанный для основного потока.

*arglist* — это параметр, который должен быть передан вновь созданному потоку. Как правило, это адрес элемента данных, например строки символов. *arglist* может быть **NULL,** если он не нужен, но **_beginthread** и **_beginthreadex** должны быть предоставлены некоторые значения, чтобы перейти к новому потоку. Все потоки прекращаются, если какой-либо поток вызывает [прерывание,](abort.md) **выход,** **_exit**или **ExitProcess.**

Локал нового потока инициализирован с помощью глобальной текущей информации о локальном потоке в процессе. Если локаль на поток включен вызовом [_configthreadlocale](configthreadlocale.md) (либо глобально, либо только для новых потоков), поток может изменить свой локаль независимо от других потоков, вызывая **setlocale** или **_wsetlocale.** Потоки, не имеюющие набора флагов локального потока на поток, могут влиять на информацию о локалье во всех других потоках, которые также не имеют набора флага локального флага для потока, а также всех вновь созданных потоков. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Для **/clr** кода, **_beginthread** и **_beginthreadex** имеют две перегрузки. Один принимает родной вызов-конвенции функции указателя, а другой принимает **__clrcall** функции указателя. Первый перегруженный метод не является безопасным для домена приложения и никогда таковым не будет. При написании **/clr** кода необходимо убедиться, что новый поток войдет в правильный домен приложения, прежде чем он получит доступ к управляемым ресурсам. Это можно сделать, например, с помощью [функции call_in_appdomain](../../dotnet/call-in-appdomain-function.md). Вторая перегрузка — это домен-безопасное применение; вновь созданный поток всегда будет в конечном итоге в домене приложения абонента **_beginthread** или **_beginthreadex.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .

Для использования **_beginthread** или **_beginthreadex**приложение должно связаться с одной из многопоточных библиотек c.time..

## <a name="example"></a>Пример

В следующем примере используются **_beginthread** и **_endthread**.

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

// Bounce - Thread to create and control a colored letter that moves
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

Следующий пример кода демонстрирует, как можно использовать ручку потока, которая возвращается **_beginthreadex** с синхронизационным API [WaitForSingleObject.](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) Основной поток ожидает завершения другого потока, прежде чем продолжить. Когда второй поток вызывает **_endthreadex,** это приводит к тому, что объект потока перешел в сигнальное состояние. Это позволяет продолжить выполнение основного потока. Это не может быть сделано с **_beginthread** и **_endthread,** потому что **_endthread** вызывает **CloseHandle**, который разрушает объект потока, прежде чем он может быть установлен в состоянии сигнала.

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

## <a name="see-also"></a>См. также раздел

- [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [Прервать](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
