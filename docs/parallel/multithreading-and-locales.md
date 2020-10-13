---
title: Многопоточность и языковые стандарты
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
ms.openlocfilehash: 82b410c592e5b68737514dda5a864c7bd15f6dc3
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008592"
---
# <a name="multithreading-and-locales"></a>Многопоточность и языковые стандарты

И библиотека времени выполнения C, и стандартная библиотека C++ обеспечивают поддержку изменения языкового стандарта программы. В этом разделе обсуждаются проблемы, возникающие при использовании функций языковых стандартов обеих библиотек в многопоточном приложении.

## <a name="remarks"></a>Комментарии

С помощью библиотеки времени выполнения C можно создавать многопоточные приложения, используя `_beginthread` `_beginthreadex` функции и. В этом разделе рассматриваются только многопоточные приложения, созданные с помощью этих функций. Дополнительные сведения см. в разделе [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).

Чтобы изменить языковой стандарт с помощью библиотеки времени выполнения C, используйте функцию [setlocale](../preprocessor/setlocale.md) . В предыдущих версиях Visual C++ эта функция всегда будет изменять языковой стандарт во всем приложении. Теперь поддерживается Установка языкового стандарта на основе каждого потока. Это делается с помощью функции [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) . Чтобы указать, что [setlocale](../preprocessor/setlocale.md) должен изменить языковой стандарт только в текущем потоке, вызовите `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` в этом потоке. И наоборот, вызов `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` приведет к тому, что поток будет использовать глобальный языковой стандарт, а любой вызов [setlocale](../preprocessor/setlocale.md) в этом потоке изменит языковой стандарт во всех потоках, которые явно не включали языковой стандарт для каждого потока.

Чтобы изменить языковой стандарт с помощью библиотеки времени выполнения C++, используйте [класс locale](../standard-library/locale-class.md). Вызывая метод [locale:: Global](../standard-library/locale-class.md#global) , вы изменяете языковой стандарт в каждом потоке, который явно не включил языковой стандарт для каждого потока. Чтобы изменить языковой стандарт в одном потоке или части приложения, просто создайте экземпляр `locale` объекта в этом потоке или части кода.

> [!NOTE]
> Вызов [locale:: Global](../standard-library/locale-class.md#global) изменяет языковой стандарт как для стандартной библиотеки C++, так и для библиотеки времени выполнения C. Однако вызов [setlocale](../preprocessor/setlocale.md) изменяет только языковой стандарт для библиотеки времени выполнения C; на стандартную библиотеку C++ это не влияет.

В следующих примерах показано, как использовать функцию [setlocale](../preprocessor/setlocale.md) , [класс locale](../standard-library/locale-class.md)и функцию [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) для изменения языкового стандарта приложения в нескольких различных сценариях.

## <a name="example-change-locale-with-per-thread-locale-enabled"></a>Пример. изменение языкового стандарта с включенным локальом для каждого потока

В этом примере основной поток порождает два дочерних потока. Первый поток, поток а, включает языковой стандарт для каждого потока, вызывая `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Во втором потоке, в потоке B, а также в основном потоке не следует включать языковой стандарт для каждого потока. Затем поток а переходит к изменению языкового стандарта с помощью функции [setlocale](../preprocessor/setlocale.md) Библиотеки времени выполнения C.

Поскольку для потока а включен языковой стандарт для каждого потока, только функции библиотеки времени выполнения C в потоке A начинают использовать языковой стандарт "французский". Функции библиотеки времени выполнения C в потоке B и в основном потоке продолжают использовать языковой стандарт "C". Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на языковой стандарт стандартной библиотеки c++, все объекты стандартной библиотеки c++ по прежнему будут использовать языковой стандарт "C".

```cpp
// multithread_locale_1.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "C"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-with-per-thread-locale-enabled"></a>Пример. изменение глобального языкового стандарта с включенным локальом для каждого потока

В этом примере основной поток порождает два дочерних потока. Первый поток, поток а, включает языковой стандарт для каждого потока, вызывая `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Во втором потоке, в потоке B, а также в основном потоке не следует включать языковой стандарт для каждого потока. Затем поток а переходит к изменению языкового стандарта с помощью метода [locale:: Global](../standard-library/locale-class.md#global) стандартной библиотеки C++.

Поскольку для потока а включен языковой стандарт для каждого потока, только функции библиотеки времени выполнения C в потоке A начинают использовать языковой стандарт "французский". Функции библиотеки времени выполнения C в потоке B и в основном потоке продолжают использовать языковой стандарт "C". Однако поскольку метод [locale:: Global](../standard-library/locale-class.md#global) изменяет языковой стандарт глобально, все объекты стандартной библиотеки C++ во всех потоках начинают использовать языковой стандарт "французский".

```cpp
// multithread_locale_2.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "French_France.1252"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="example-change-locale-without-per-thread-locale-enabled"></a>Пример. изменение языкового стандарта без включения языкового стандарта для каждого потока

В этом примере основной поток порождает два дочерних потока. Первый поток, поток а, включает языковой стандарт для каждого потока, вызывая `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Во втором потоке, в потоке B, а также в основном потоке не следует включать языковой стандарт для каждого потока. Затем поток B переходит к изменению языкового стандарта с помощью функции [setlocale](../preprocessor/setlocale.md) Библиотеки времени выполнения C.

Так как в потоке B не включен языковой стандарт для каждого потока, функции библиотеки времени выполнения C в потоке B и в основном потоке начинают использовать языковой стандарт "французский". Функции библиотеки времени выполнения C в потоке A продолжают использовать языковой стандарт "C", так как для потока а включен языковой стандарт "на поток". Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на языковой стандарт стандартной библиотеки c++, все объекты стандартной библиотеки c++ по прежнему будут использовать языковой стандарт "C".

```cpp
// multithread_locale_3.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "C"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-without-per-thread-locale-enabled"></a>Пример. изменение глобального языкового стандарта без включения языкового стандарта для каждого потока

В этом примере основной поток порождает два дочерних потока. Первый поток, поток а, включает языковой стандарт для каждого потока, вызывая `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Во втором потоке, в потоке B, а также в основном потоке не следует включать языковой стандарт для каждого потока. Затем поток B переходит к изменению языкового стандарта с помощью метода [locale:: Global](../standard-library/locale-class.md#global) стандартной библиотеки C++.

Так как в потоке B не включен языковой стандарт для каждого потока, функции библиотеки времени выполнения C в потоке B и в основном потоке начинают использовать языковой стандарт "французский". Функции библиотеки времени выполнения C в потоке A продолжают использовать языковой стандарт "C", так как для потока а включен языковой стандарт "на поток". Однако поскольку метод [locale:: Global](../standard-library/locale-class.md#global) изменяет языковой стандарт глобально, все объекты стандартной библиотеки C++ во всех потоках начинают использовать языковой стандарт "французский".

```cpp
// multithread_locale_4.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "French_France.1252"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="see-also"></a>См. также статью

[Поддержка многопоточности для устаревшего кода (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)<br/>
[setlocale](../preprocessor/setlocale.md)<br/>
[Интернационализация](../c-runtime-library/internationalization.md)<br/>
[Локаль](../c-runtime-library/locale.md)<br/>
[\<clocale>](../standard-library/clocale.md)<br/>
[\<locale>](../standard-library/locale.md)<br/>
[Класс locale](../standard-library/locale-class.md)
