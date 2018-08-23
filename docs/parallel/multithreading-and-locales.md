---
title: Многопоточность и языковые стандарты | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0506c7f4efd288417c8fbdcd4784446651c362ac
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42540498"
---
# <a name="multithreading-and-locales"></a>Многопоточность и языковые стандарты
Библиотеки времени выполнения C и стандартной библиотеки C++ поддерживают изменение языкового стандарта программы. В этом разделе рассматриваются проблемы, возникающие при использовании функций языковых стандартов обе библиотеки в многопоточных приложениях.  
  
## <a name="remarks"></a>Примечания  

С помощью библиотеки среды выполнения C, можно создать многопотоковых приложений с помощью `_beginthread` и `_beginthreadex` функции. В этом разделе рассматриваются только многопоточные приложения, созданные с помощью этих функций. Дополнительные сведения см. в разделе [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
Чтобы изменить языковой стандарт, с помощью библиотеки времени выполнения C, используйте [setlocale](../preprocessor/setlocale.md) функции. В предыдущих версиях Visual C++ эта функция всегда изменить языковой стандарт во всем приложении. Есть теперь поддерживают стандарт для каждого потока. Это делается с помощью [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) функции. Чтобы указать, что [setlocale](../preprocessor/setlocale.md) следует изменять только языковой стандарт в текущем потоке и вызов `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` в этом потоке. И наоборот, вызвав `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` вызовет потока для использования глобального языкового стандарта, а также любой вызов [setlocale](../preprocessor/setlocale.md) тем, что поток будет изменить языковой стандарт во всех потоках, которые явно не включены языкового стандарта отдельного потока.  
  
Чтобы изменить языковой стандарт, использование библиотеки среды выполнения C++, используйте [класс locale](../standard-library/locale-class.md). Путем вызова [locale::global](../standard-library/locale-class.md#global) метод, изменить языковой стандарт в каждый поток, который не включен явно языкового стандарта отдельного потока. Чтобы изменить языковой стандарт в одном потоке или части приложения, просто создайте экземпляр `locale` объект в этом потоке или часть кода.  
  
> [!NOTE]
> Вызов [locale::global](../standard-library/locale-class.md#global) изменяет языковой стандарт для стандартной библиотеки C++ и библиотеки времени выполнения C. Однако, при вызове [setlocale](../preprocessor/setlocale.md) только изменяет языковой стандарт для библиотеки времени выполнения C; в стандартной библиотеке C++ не затрагивается.  
  
Следующие примеры показывают, как использовать [setlocale](../preprocessor/setlocale.md) функции [класс locale](../standard-library/locale-class.md)и [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) функции, чтобы изменить языковой стандарт для приложения в нескольких различных сценариях.  
  
## <a name="example"></a>Пример  
 
В этом примере основной поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, поток B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток изменения языкового стандарта с помощью [setlocale](../preprocessor/setlocale.md) функции библиотеки времени выполнения C.  
  
Так как поток A имеет отдельного потока включен языковой стандарт только функции библиотеки времени выполнения C с помощью запуска потока A, использующей языковой стандарт «французский». Функции библиотеки времени выполнения C в потоке B и в основном потоке продолжать использовать языковом стандарте «C». Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на языковом стандарте стандартной библиотеки C++ все стандартной библиотеки C++ объекты продолжают использовать языковом стандарте «C».  
  
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
  
## <a name="example"></a>Пример  
 
В этом примере основной поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, поток B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток изменения языкового стандарта с помощью [locale::global](../standard-library/locale-class.md#global) метод стандартной библиотеки C++.  
  
Так как поток A имеет отдельного потока включен языковой стандарт только функции библиотеки времени выполнения C с помощью запуска потока A, использующей языковой стандарт «французский». Функции библиотеки времени выполнения C в потоке B и в основном потоке продолжать использовать языковом стандарте «C». Однако, поскольку [locale::global](../standard-library/locale-class.md#global) метод изменяет языковой стандарт «глобально», все объекты стандартной библиотеки C++ во всех потоках начать использовать языковой стандарт «французский».  
  
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
  
## <a name="example"></a>Пример  
 
В этом примере основной поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, поток B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток B изменения языкового стандарта с помощью [setlocale](../preprocessor/setlocale.md) функции библиотеки времени выполнения C.  
  
Поскольку поток B не включен языковой стандарт отдельного потока, функции библиотеки времени выполнения C в потоке B и в основном потоке приступать к использованию языковой стандарт «французский». Функции библиотеки времени выполнения C в поток А дальнейшее использование языковом стандарте «C», так как имеет поток A языковой стандарт отдельного потока включен. Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на языковом стандарте стандартной библиотеки C++ все стандартной библиотеки C++ объекты продолжают использовать языковом стандарте «C».  
  
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
  
## <a name="example"></a>Пример  
 
В этом примере основной поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, поток B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток B изменения языкового стандарта с помощью [locale::global](../standard-library/locale-class.md#global) метод стандартной библиотеки C++.  
  
Поскольку поток B не включен языковой стандарт отдельного потока, функции библиотеки времени выполнения C в потоке B и в основном потоке приступать к использованию языковой стандарт «французский». Функции библиотеки времени выполнения C в поток А дальнейшее использование языковом стандарте «C», так как имеет поток A языковой стандарт отдельного потока включен. Однако, поскольку [locale::global](../standard-library/locale-class.md#global) метод изменяет языковой стандарт «глобально», все объекты стандартной библиотеки C++ во всех потоках начать использовать языковой стандарт «французский».  
  
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
  
## <a name="see-also"></a>См. также  

[Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
[setlocale](../preprocessor/setlocale.md)   
[Интернационализация](../c-runtime-library/internationalization.md)   
[Языковой стандарт](../c-runtime-library/locale.md)   
[\<clocale >](../standard-library/clocale.md)   
[\<locale>](../standard-library/locale.md)   
[Класс locale](../standard-library/locale-class.md)