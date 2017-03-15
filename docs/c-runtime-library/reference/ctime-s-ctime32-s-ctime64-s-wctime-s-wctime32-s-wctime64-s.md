---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64_s"
  - "_wctime32_s"
  - "ctime_s"
  - "_wctime64_s"
  - "_ctime32_s"
  - "_wctime_s"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ctime64_s"
  - "_ctime32_s"
  - "_tctime32_s"
  - "_ctime64_s"
  - "_wctime_s"
  - "_tctime_s"
  - "_tctime64_s"
  - "ctime_s"
  - "ctime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция _wctime32_s"
  - "Функция ctime64_s"
  - "Функция _tctime64_s"
  - "Функция _wctime_s"
  - "Функция tctime_s"
  - "Функция _wctime64_s"
  - "Функция ctime_s"
  - "Функция ctime32_s"
  - "Функция _ctime64_s"
  - "Функция tctime64_s"
  - "Функция wctime64_s"
  - "Функция wctime_s"
  - "Функция _tctime_s"
  - "Функция tctime32_s"
  - "Функция wctime32_s"
  - "время, преобразование"
  - "Функция _ctime32_s"
  - "Функция _tctime32_s"
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Здесь представлены версии функций [ctime \_ctime64, \_wctime, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### Параметры  
 \[out\] `buffer`  
 Должно быть достаточным для хранения 26 символов. Указатель на результирующую строку символов или `NULL`если:  
  
-   `time` представляет дату перед полуночью 1\-го января 1970 года, в формате UTC.  
  
-   Если вы используете `_ctime32_s` или `_wctime32_s` и `time` представляет дату после 23:59:59 18 января 2038 года, UTC.  
  
-   Если используется функция `_ctime64_s` или `_wctime64_s` и `time` представляет дату после 23:59:59 31\-го декабря 3000 года \(в формате UTC\).  
  
-   Если вы используете `_ctime_s` или `_wctime_s`, эти функции являются оболочками для предыдущей функции. См. раздел примeчаний.  
  
 \[in\] `numberOfElements`  
 Размер буфера.  
  
 \[in\] t`ime`  
 Указатель на сохраненное время.  
  
## Возвращаемое значение  
 Ноль при успешном завершении. Если происходит сбой из\-за недопустимого параметра, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, возвращается код ошибки. Коды ошибок определяются в ERRNO. H; Список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md). В следующей таблице показаны фактические коды ошибок создается для каждой ошибки.  
  
## Условия ошибок  
  
|`buffer`|`numberOfElements`|`time`|Назад|Значение `buffer`|  
|--------------|------------------------|------------|-----------|-----------------------|  
|`NULL`|any|any|`EINVAL`|Без изменений|  
|Не `NULL` \(указывает на допустимый адрес в памяти\)|0|any|`EINVAL`|Без изменений|  
|Не `NULL`|0\< size \< 26|any|`EINVAL`|Пустая строка|  
|Не `NULL`|\>\= 26|NULL|`EINVAL`|Пустая строка|  
|Не `NULL`|\>\= 26|\< 0|`EINVAL`|Пустая строка|  
  
## Заметки  
 `ctime_s` Функция преобразует значение времени хранится как [time\_t](../../c-runtime-library/standard-types.md) структуры в символьную строку. Значение `time` обычно получается из вызова функции [time](../Topic/time,%20_time32,%20_time64.md), которая возвращает количество секунд, истекших после полуночи \(00:00: 00\) 1\-го января 1970 года \(в формате UTC\). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Время в 24\-часовом формате. Все поля имеют постоянную ширину. Символ новой строки \(\\n\) и символ null \(«\\0»\) занимают две последние позиции строки.  
  
 Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. В разделе `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), и [localtime32\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) функции для получения сведений о настройке местного времени и [\_tzset](../Topic/_tzset.md) функция сведения об определении среды часового пояса и глобальных переменных.  
  
 `_wctime32_s` и `_wctime64_s` — версии функций `_ctime32_s` и `_ctime64_s` для расширенных символов; возвращают указатель на строку из расширенных символов. В остальном поведение функций `_ctime64_s`, `_wctime32_s` и `_wctime64_s` совпадает с поведением функции `_ctime32_s`.  
  
 `ctime_s` Встроенная функция, которая принимает значение является `_ctime64_s` и `time_t` эквивалентно `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32\-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `ctime_s` будет вычисляться как `_ctime32_s`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18\-го января 2038 года, и не поддерживается на 64\-разрядных платформах.  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Для получения дополнительной информации см. [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`ctime_s,`<br /><br /> `_ctime32_s,`<br /><br /> `_ctime64_s`|\<time.h\>|  
|`_wctime_s,`<br /><br /> `_wctime32_s,`<br /><br /> `_wctime64_s`|\<time.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## Пример результатов выполнения  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)