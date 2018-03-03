---
title: "Многопоточность и языковые стандарты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e60235bb011cb130b06a51a498cd8b5b88a56232
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-and-locales"></a>Многопоточность и языковые стандарты
Библиотеки времени выполнения C и стандартную библиотеку C++ поддерживают изменение языкового стандарта программы. В этом разделе рассматриваются проблемы, возникающие при использовании функций языковых стандартов обеих библиотек в многопоточных приложениях.  
  
## <a name="remarks"></a>Примечания  
 Библиотеки времени выполнения языка C, позволяет создавать многопоточные приложения, используя `_beginthread` и `_beginthreadex` функции. В этом разделе рассматриваются только многопоточные приложения, созданные с помощью этих функций. Дополнительные сведения см. в разделе [_beginthread и _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
 Чтобы изменить языковой стандарт, с помощью библиотеки времени выполнения C, используйте [setlocale](../preprocessor/setlocale.md) функции. В предыдущих версиях Visual C++ эта функция изменяла языковой стандарт во всем приложении. Нет реализована поддержка стандарт для каждого потока. Это делается с помощью [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) функции. Чтобы указать, что [setlocale](../preprocessor/setlocale.md) следует изменять только языкового стандарта текущего потока, вызовов `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` в этом потоке. И наоборот, вызов `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` вызовет потока для использования глобального языкового стандарта и любой вызов [setlocale](../preprocessor/setlocale.md) в том, что поток будет изменить языковой стандарт во всех потоках, которые явно не включены языкового стандарта отдельного потока.  
  
 Чтобы изменить языковой стандарт, с помощью библиотеки времени выполнения C++, используйте [класс locale](../standard-library/locale-class.md). Путем вызова [locale::global](../standard-library/locale-class.md#global) метод, измените языкового стандарта каждого потока, который не включен явно языкового стандарта отдельного потока. Чтобы изменить языковой стандарт в одном потоке или части приложения, просто создайте экземпляр `locale` объекта в этом потоке или части кода.  
  
> [!NOTE]
>  Вызов [locale::global](../standard-library/locale-class.md#global) изменяет языковой стандарт для стандартной библиотеки C++ и библиотеки времени выполнения C. Однако, при вызове [setlocale](../preprocessor/setlocale.md) только изменяет языковой стандарт для библиотеки времени выполнения C; стандартной библиотеки C++ не влияет.  
  
 В следующих примерах показано использование [setlocale](../preprocessor/setlocale.md) функции [класс locale](../standard-library/locale-class.md)и [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) функции для изменения языковой стандарт для приложения в нескольких различных сценариях.  
  
## <a name="example"></a>Пример  
 В этом примере главный поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, потоке B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток изменяет языковой стандарт при помощи [setlocale](../preprocessor/setlocale.md) функции библиотеки времени выполнения C.  
  
 Так как поток A имеет отдельного потока включен языковой стандарт только функции библиотеки времени выполнения C с помощью запуска потока A, использующие языковой стандарт «французский». Функции библиотеки времени выполнения C, в потоке B и в основном потоке продолжать использовать языковой стандарт «C». Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на стандартную библиотеку C++ языкового стандарта, все стандартной библиотеки C++ объекты продолжают использовать языковой стандарт «C».  
  
```  
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
 В этом примере главный поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, потоке B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток изменяет языковой стандарт при помощи [locale::global](../standard-library/locale-class.md#global) метод стандартной библиотеки C++.  
  
 Так как поток A имеет отдельного потока включен языковой стандарт только функции библиотеки времени выполнения C с помощью запуска потока A, использующие языковой стандарт «французский». Функции библиотеки времени выполнения C, в потоке B и в основном потоке продолжать использовать языковой стандарт «C». Однако, поскольку [locale::global](../standard-library/locale-class.md#global) метод изменяет языковой стандарт «глобально», все объекты стандартной библиотеки C++ во всех потоках начать использовать языковой стандарт «французский».  
  
```  
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
 В этом примере главный поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, потоке B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток B изменяет языковой стандарт при помощи [setlocale](../preprocessor/setlocale.md) функции библиотеки времени выполнения C.  
  
 Поскольку потоке B не включен языковой стандарт для отдельного потока, функции библиотеки времени выполнения C, в потоке B и в основном потоке начать использовать языковой стандарт «французский». Функции библиотеки времени выполнения C в потоке A продолжить использовать языковой стандарт «C», поскольку поток A включен языковой стандарт для отдельного потока. Кроме того, поскольку [setlocale](../preprocessor/setlocale.md) не влияет на стандартную библиотеку C++ языкового стандарта, все стандартной библиотеки C++ объекты продолжают использовать языковой стандарт «C».  
  
```  
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
 В этом примере главный поток создает два дочерних потока. Первый поток, поток A, позволяет языкового стандарта отдельного потока путем вызова `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Второй поток, потоке B, а также основной поток, не включайте языкового стандарта отдельного потока. Затем поток B изменяет языковой стандарт при помощи [locale::global](../standard-library/locale-class.md#global) метод стандартной библиотеки C++.  
  
 Поскольку потоке B не включен языковой стандарт для отдельного потока, функции библиотеки времени выполнения C, в потоке B и в основном потоке начать использовать языковой стандарт «французский». Функции библиотеки времени выполнения C в потоке A продолжить использовать языковой стандарт «C», поскольку поток A включен языковой стандарт для отдельного потока. Однако, поскольку [locale::global](../standard-library/locale-class.md#global) метод изменяет языковой стандарт «глобально», все объекты стандартной библиотеки C++ во всех потоках начать использовать языковой стандарт «французский».  
  
```  
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