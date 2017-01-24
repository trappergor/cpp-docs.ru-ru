---
title: "asctime_s, _wasctime_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wasctime_s"
  - "asctime_s"
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
  - "asctime_s"
  - "_wasctime_s"
  - "_tasctime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime_s - функция"
  - "_wasctime_s - функция"
  - "asctime_s - функция"
  - "tasctime_s - функция"
  - "преобразование структуры времени"
  - "время, преобразование"
  - "wasctime_s - функция"
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asctime_s, _wasctime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуют структуру времени `tm` в символьную строку.  Здесь представлены версии [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 \[out\] Указатель на буфер для хранения полученной символьной строки.  Эта функция принимает указатель на допустимое расположение в памяти, размер которого указан в `numberOfElements`.  
  
 `numberOfElements`  
 \[in\] Размер буфера, используемого для хранения результатов.  
  
 `_tm`  
 \[in\] Структура даты\/времени.  Эта функция принимает указатель на допустимый объект `struct` `tm`.  
  
## Возвращаемое значение  
 Ноль, если успешно.  Если проверка завершается с ошибкой, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает код ошибки.  Коды ошибок определенны в ERRNO.H.  Для получения дополнительной информации см. [Константы errno](../../c-runtime-library/errno-constants.md).  Фактические коды ошибок, возвращаемые для каждого условия ошибки, отображены в следующей таблице.  
  
### Условия возникновения ошибки  
  
|`buffer`|`numberOfElements`|`tm`|Return|Значение в `buffer`|  
|--------------|------------------------|----------|------------|-------------------------|  
|`NULL`|Any|Any|`EINVAL`|Без изменений|  
|Не`NULL` \(указывает на допустимый адрес памяти\)|0|Any|`EINVAL`|Без изменений|  
|Не `NULL`|0\< size \< 26|Any|`EINVAL`|Пустая строка|  
|Не `NULL`|\>\= 26|`NULL`|`EINVAL`|Пустая строка|  
|Не `NULL`|\>\= 26|Недопустимая структура времени или для компоненты времени выходят за пределы допустимого диапазона|`EINVAL`|Пустая строка|  
  
> [!NOTE]
>  Условия ошибки для `wasctime_s` аналогичны `asctime_s` за исключением того, что ограничение размера измеряется в словах.  
  
## Заметки  
 Функция `asctime` преобразует время, хранящееся в виде структуры, в символьную строку.  Значение `_tm` обычно получается из вызова функции `gmtime` или `localtime`.  Обе функции могут использоваться для заполнения структуры `tm`, как определено в TIME.H.  
  
|Член timeptr|Значение|  
|------------------|--------------|  
|`tm_hour`|Часы после полуночи \(0–23\)|  
|`tm_isdst`|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно.  Библиотека времени выполнения C принимает правила Соединенных Штатов для реализации проверки на летнее время \(DST\).|  
|`tm_mday`|День месяца \(1–31\)|  
|`tm_min`|Минуты после часа \(0–59\)|  
|`tm_mon`|Месяц \(0–11; Январь \= 0\)|  
|`tm_sec`|Секунды после минуты \(0–59\)|  
|`tm_wday`|День недели \(0–6; 0 \= воскресенье\)|  
|`tm_yday`|День года \(0–365; 1\-е января \= 0\)|  
|`tm_year`|Год \(текущий год минус 1900\)|  
  
 Преобразованная символьная строка также настраивается согласно параметрам зоны локального времени.  Обратитесь к функциям [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md), [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) за сведениями о настройке местного времени и к функции [\_tzset](../Topic/_tzset.md) за сведениями об определении среды временной зоны и глобальных переменных.  
  
 Итоговая строка, полученная с помощью `asctime_s`, содержит ровно 26 символов и имеет вид `Wed Jan 02 02:03:55 1980\n\0`.  Время в 24\-часовом формате.  Все поля имеют постоянную ширину.  Символ новой строки и нуль\-символ занимают две последние позиции строки.  Значение, переданное в качестве второго параметра, должно иметь по крайней мере такое значение.  Если оно меньше, то будет возвращен код ошибки `EINVAL`.  
  
 `_wasctime_s` — это двухбайтовая версия `asctime_s`.  В остальных случаях поведение `_wasctime_s` и `asctime_s` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`asctime_s`|\<time.h\>|  
|`_wasctime_s`|\<time.h\> или \<wchar.h\>|  
  
## Безопасность  
 Если указатель буфера не `NULL` и указатель не указывает на допустимый буфер, функция перезапишет все в указанном месте.  Это также может привести к нарушению доступа.  
  
 [buffer overrun](http://msdn.microsoft.com/library/windows/desktop/ms717795) может возникать, если переданный аргумент size превышает фактический размер буфера.  
  
## Пример  
 Программа помещает системное время в целочисленную переменную `aclock`, преобразует его в структуру `newtime` и затем преобразует его в строку для вывода с помощью функции `asctime_s`.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
  **Current date and time: Wed May 14 15:30:17 2003**   
## Эквивалент в .NET Framework  
  
-   <xref:System.DateTime.ToLongDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToLongTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToString%2A?displayProperty=fullName>  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)