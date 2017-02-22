---
title: "Многопоточность и языковые стандарты | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "язык и региональные стандарты [C++], многопоточность"
  - "многопоточность [C++], язык и региональные стандарты"
  - "языковой стандарт для отдельного потока"
  - "работа с потоками [C++], язык и региональные стандарты"
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Многопоточность и языковые стандарты
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

И библиотека C времени выполнения, и стандартная библиотека C\+\+ поддерживают изменение языкового стандарта программы.  В этом разделе рассматриваются задачи, которые встречаются в многопоточных приложениях при использовании функций языковых стандартов обеих библиотек.  
  
## Заметки  
 С помощью библиотеки C времени выполнения можно создавать многопоточные приложения, используя функции `_beginthread` и `_beginthreadex`.  В данном разделе рассматриваются только многопоточные приложения, созданные с помощью этих функций.  Для получения дополнительной информации см. [\_beginthread, \_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md).  
  
 Чтобы изменить языковой стандарт с помощью библиотеки C времени выполнения, воспользуйтесь функцией [setlocale](../preprocessor/setlocale.md).  В предыдущих версиях [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] эта функция изменяла языковой стандарт во всем приложении.  Теперь можно менять языковой стандарт для отдельного потока.  Для этого служит функция [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md).  Чтобы функция [setlocale](../preprocessor/setlocale.md) меняла языковой стандарт только в текущем потоке, нужно вызвать в этом потоке функцию `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  И наоборот, при вызове функции `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` поток будет использовать общий языковой стандарт, и любой вызов функции [setlocale](../preprocessor/setlocale.md) в этом потоке будет изменять стандарт во всех потоках, которым явно не присвоен языковой стандарт для одного потока.  
  
 Чтобы изменить языковой стандарт с помощью библиотеки C\+\+ времени выполнения, воспользуйтесь функцией [Класс locale](../standard-library/locale-class.md).  Вызов метода [locale::global](../Topic/locale::global.md) изменяет языковой стандарт во всех потоках, которым явно не присвоен языковой стандарт для одного потока.  Чтобы изменить языковой стандарт в одном потоке или части приложения, просто создайте в этом потоке или части кода экземпляр объекта `locale`.  
  
> [!NOTE]
>  Вызов метода [locale::global](../Topic/locale::global.md) изменяет языковой стандарт как для стандартной библиотеки C\+\+, так и для библиотеки C времени выполнения.  Однако вызов функции [setlocale](../preprocessor/setlocale.md) изменяет языковой стандарт только для библиотеки C времени выполнения; стандартная библиотека C\+\+ не затрагивается.  
  
 В следующих примерах показано, как использовать функции [setlocale](../preprocessor/setlocale.md), [Класс locale](../standard-library/locale-class.md) и [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) для изменения языкового стандарта приложения в нескольких различных скриптах.  
  
## Пример  
 В этом примере главный поток создает два дочерних потока.  В первом потоке, потоке A, включается языковой стандарт для отдельного потока путем вызова функции `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Во втором потоке, потоке B, языковой стандарт для отдельного потока не включен, как и в главном потоке.  Затем поток A изменяет языковой стандарт при помощи функции [setlocale](../preprocessor/setlocale.md) библиотеки C времени выполнения.  
  
 Поскольку в потоке A включен языковой стандарт для отдельного потока, "французский" языковой стандарт будут использовать только функции библиотеки C времени выполнения в потоке A.  Функции библиотеки C времени выполнения в потоке B и в главном потоке по\-прежнему будут использовать стандарт "С".  Кроме того, поскольку функция [setlocale](../preprocessor/setlocale.md) не влияет на стандартную библиотеку C\+\+, все объекты этой библиотеки также будут по\-прежнему использовать стандарт "С".  
  
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
  
  **\[Поток A\] Языковой стандарт по потокам включен.**  
**\[Thread A\] CRT locale is set to "French\_France.1252"**  
**\[Thread A\] locale::global is set to "C"**  
**\[Поток Б\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread B\] CRT locale is set to "C"**  
**\[Thread B\] locale::global is set to "C"**  
**\[Главный поток\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread main\] CRT locale is set to "C"**  
**\[Thread main\] locale::global is set to "C"**   
## Пример  
 В этом примере главный поток создает два дочерних потока.  В первом потоке, потоке A, включается языковой стандарт для отдельного потока путем вызова функции `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Во втором потоке, потоке B, языковой стандарт для отдельного потока не включен, как и в главном потоке.  Затем поток A изменяет языковой стандарт при помощи метода [locale::global](../Topic/locale::global.md) стандартной библиотеки C\+\+.  
  
 Поскольку в потоке A включен языковой стандарт для отдельного потока, "французский" языковой стандарт будут использовать только функции библиотеки C времени выполнения в потоке A.  Функции библиотеки C времени выполнения в потоке B и в главном потоке по\-прежнему будут использовать стандарт "С".  Однако в связи с тем, что метод [locale::global](../Topic/locale::global.md) изменяет языковой стандарт в глобальном режиме, все объекты стандартной библиотеки C\+\+ во всех потоках будут использовать "французский" стандарт.  
  
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
  
  **\[Поток A\] Языковой стандарт по потокам включен.**  
**\[Thread A\] CRT locale is set to "French\_France.1252"**  
**\[Thread A\] locale::global is set to "French\_France.1252"**  
**\[Поток Б\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread B\] CRT locale is set to "C"**  
**\[Thread B\] locale::global is set to "French\_France.1252"**  
**\[Главный поток\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread main\] CRT locale is set to "C"**  
**\[Thread main\] locale::global is set to "French\_France.1252"**   
## Пример  
 В этом примере главный поток создает два дочерних потока.  В первом потоке, потоке A, включается языковой стандарт для отдельного потока путем вызова функции `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Во втором потоке, потоке B, языковой стандарт для отдельного потока не включен, как и в главном потоке.  Затем поток B изменяет языковой стандарт при помощи функции [setlocale](../preprocessor/setlocale.md) библиотеки C времени выполнения.  
  
 Поскольку в потоке B не включен языковой стандарт для отдельного потока, функции библиотеки C времени выполнения в потоке B и в главном потоке будут использовать "французский" языковой стандарт.  Функции библиотеки C времени выполнения в потоке A по\-прежнему будут использовать языковой стандарт "С", так как в потоке A включен языковой стандарт для отдельного потока.  Кроме того, поскольку функция [setlocale](../preprocessor/setlocale.md) не влияет на стандартную библиотеку C\+\+, все объекты этой библиотеки также будут по\-прежнему использовать стандарт "С".  
  
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
  
  **\[Поток Б\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread B\] CRT locale is set to "French\_France.1252"**  
**\[Thread B\] locale::global is set to "C"**  
**\[Поток A\] Языковой стандарт по потокам включен.**  
**\[Thread A\] CRT locale is set to "C"**  
**\[Thread A\] locale::global is set to "C"**  
**\[Главный поток\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread main\] CRT locale is set to "French\_France.1252"**  
**\[Thread main\] locale::global is set to "C"**   
## Пример  
 В этом примере главный поток создает два дочерних потока.  В первом потоке, потоке A, включается языковой стандарт для отдельного потока путем вызова функции `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Во втором потоке, потоке B, языковой стандарт для отдельного потока не включен, как и в главном потоке.  Затем поток B изменяет языковой стандарт при помощи метода [locale::global](../Topic/locale::global.md) стандартной библиотеки C\+\+.  
  
 Поскольку в потоке B не включен языковой стандарт для отдельного потока, функции библиотеки C времени выполнения в потоке B и в главном потоке будут использовать "французский" языковой стандарт.  Функции библиотеки C времени выполнения в потоке A по\-прежнему будут использовать языковой стандарт "С", так как в потоке A включен языковой стандарт для отдельного потока.  Однако в связи с тем, что метод [locale::global](../Topic/locale::global.md) изменяет языковой стандарт в глобальном режиме, все объекты стандартной библиотеки C\+\+ во всех потоках будут использовать "французский" стандарт.  
  
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
  
  **\[Поток Б\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread B\] CRT locale is set to "French\_France.1252"**  
**\[Thread B\] locale::global is set to "French\_France.1252"**  
**\[Поток A\] Языковой стандарт по потокам включен.**  
**\[Thread A\] CRT locale is set to "C"**  
**\[Thread A\] locale::global is set to "French\_France.1252"**  
**\[Главный поток\] Языковой стандарт по потокам НЕ включен.**  
**\[Thread main\] CRT locale is set to "French\_France.1252"**  
**\[Thread main\] locale::global is set to "French\_France.1252"**   
## См. также  
 [Поддержка многопоточности для устаревшего кода \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [\_beginthread, \_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)   
 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Языковой стандарт](../c-runtime-library/locale.md)   
 [\<clocale\>](../standard-library/clocale.md)   
 [\<locale\>](../standard-library/locale.md)   
 [Класс locale](../standard-library/locale-class.md)