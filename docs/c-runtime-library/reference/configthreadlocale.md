---
title: "_configthreadlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_configthreadlocale"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_configthreadlocale"
  - "configthreadlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_configthreadlocale - функция"
  - "configthreadlocale - функция"
  - "язык и региональные стандарты, на поток"
  - "языковой стандарт для отдельного потока"
  - "языковой стандарт потока"
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _configthreadlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает параметры языкового стандарта для каждого потока.  
  
## Синтаксис  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
#### Параметры  
 `type`  
 Задаваемый параметр.  Один из параметров, перечисленных в следующей таблице:  
  
## Возвращаемое значение  
 Предыдущее состояние языкового стандарта отдельного потока \(`_DISABLE_PER_THREAD_LOCALE` или `_ENABLE_PER_THREAD_LOCALE`\) или \-1 при сбое.  
  
## Заметки  
 Функция `_configurethreadlocale` используется для контроля над использованием языковых стандартов, специфических для потока.  Следует использовать один из этих параметров, чтобы задать или определить состояние языкового стандарта отдельного потока:  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 Заставляет текущий поток использовать языковой стандарт, специфический для потока.  Последующие вызовы `setlocale` в этом потоке влияют только на собственный языковой стандарт потока.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 Заставляет текущий поток использовать глобальный языковой стандарт.  Последующие вызовы `setlocale` в этом потоке влияют на другие потоки, использующие глобальный языковой стандарт.  
  
 `0`  
 Получает текущий параметр для данного потока.  
  
 Эти функции влияют на поведение `setlocale`, `_tsetlocale`, `_wsetlocale`, `_beginthread` и  `_beginthreadex`.  Если для создания потоков используется другой метод, параметры языкового стандарта не оказывают влияния на потоки.  
  
 Когда языковой стандарт отдельного потока отключен, любой последующий вызов `setlocale` или `_wsetlocale` изменяет языковой стандарт всех потоков.  Когда языковой стандарт отдельного потока включен, `setlocale` или `_wsetlocale` влияют только на языковой стандарт текущего потока.  
  
 При использовании `_configurethreadlocale` для включения языкового стандарта для каждого потока, сразу же после этого рекомендуется вызывать `setlocale` или `_wsetlocale` для задания предпочтительного языкового стандарта в этом потоке.  
  
 Если `type` не является одним из значений, перечисленных в таблице, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает \-1.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_configthreadlocale`|\<locale.h\>|  
  
## Пример  
  
```  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using is two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
  
    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI)  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
  **The thread locale is now set to English\_United States.1252.**  
**The time in English locale is: 'Wednesday, May 12, 2004'**  
**The thread locale is now set to German\_Germany.1252.**  
**The time in German locale is: 'Mittwoch, 12.  Mai 2004'**    
## Эквивалент в .NET Framework  
 Неприменимо. Однако см. раздел [Использование свойства CurrentCulture](http://msdn.microsoft.com/ru-ru/3156042d-6082-4205-90b4-c917ae6a3ba6).  
  
## См. также  
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_beginthread, \_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Многопоточность и языковые стандарты](../../parallel/multithreading-and-locales.md)