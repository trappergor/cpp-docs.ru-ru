---
title: "Стандартные типы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__time64_t"
  - "_diskfree_t"
  - "_CRT_DUMP_CLIENT"
  - "_fsize_t"
  - "__timeb64"
  - "File"
  - "__utimeb64"
  - "jmp_buf"
  - "__finddata64_t"
  - "_wfinddata_t"
  - "_finddata_t"
  - "utimbuf64"
  - "wint_t"
  - "wctrans_t"
  - "wctype_t"
  - "_HFILE"
  - "_secerr_handler_func"
  - "clock_t"
  - "fpos_t"
  - "_dev_t"
  - "time64_t"
  - "wfinddata64_t"
  - "stat64"
  - "ldiv_t"
  - "_EXCEPTION_POINTERS"
  - "terminate_function"
  - "size_t"
  - "timeb64"
  - "tm"
  - "_HEAPINFO"
  - "unexpected_function"
  - "_CrtMemState"
  - "_se_translator_function"
  - "sig_atomic_t"
  - "_CRT_REPORT_HOOK"
  - "_complex"
  - "_w_finddatai64_t"
  - "_timeb"
  - "_onexit_t"
  - "_RTC_ErrorNumber"
  - "lconv"
  - "_PNH"
  - "_off_t"
  - "ptrdiff_t"
  - "time_t"
  - "_FPIEEE_RECORD"
  - "_exception"
  - "__w_finddata64_t"
  - "__stat64"
  - "_utimbuf"
  - "__utimbuf64"
  - "div_t"
  - "_CRT_ALLOC_HOOK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finddata64_t - тип"
  - "__stat64 - тип"
  - "__time64_t - тип"
  - "__timeb64 - тип"
  - "__utimbuf64 - тип"
  - "__wfinddata64_t - функция"
  - "_complex - функция"
  - "_CRT_ALLOC_HOOK - тип"
  - "_CRT_DUMP_CLIENT - тип"
  - "_CRT_REPORT_HOOK - тип"
  - "_dev_t - тип"
  - "_diskfree_t - тип"
  - "_exception - тип"
  - "_EXCEPTION_POINTERS - тип"
  - "_finddata_t - тип"
  - "_FPIEEE_RECORD - тип"
  - "_fsize_t - тип"
  - "_HEAPINFO - тип"
  - "_HFILE - тип"
  - "_locale_t - тип"
  - "_off_t - тип"
  - "_onexit_t - тип"
  - "_PNH - тип"
  - "_RTC_ErrorNumber - тип"
  - "_se_translater_function - тип"
  - "_secerr_handler_func - тип"
  - "_stat - тип"
  - "_timeb - тип"
  - "_utimbuf - тип"
  - "_wfinddata_t - тип"
  - "_wfinddatai64_t - тип"
  - "clock_t - тип"
  - "сложные типы"
  - "CRT - библиотека, стандартные типы"
  - "CRT_ALLOC_HOOK - тип"
  - "CRT_DUMP_CLIENT - тип"
  - "CRT_REPORT_HOOK - тип"
  - "CrtMemState - тип"
  - "dev_t - тип"
  - "diskfree_t - тип"
  - "div_t - тип"
  - "тип исключения"
  - "EXCEPTION_POINTERS - тип"
  - "FILE - константа"
  - "finddata_t - тип"
  - "FPIEEE_RECORD - тип"
  - "fpos_t - тип"
  - "HEAPINFO - тип"
  - "HFILE - тип"
  - "intptr_t - тип"
  - "jmp_buf - тип"
  - "lconv - тип"
  - "ldiv_t - тип"
  - "off_t - тип"
  - "onexit_t - тип"
  - "PNH - тип"
  - "ptrdiff_t - тип"
  - "RTC_ErrorNumber - тип"
  - "se_translater_function - тип"
  - "secerr_handler_func - тип"
  - "sig_atomic_t - тип"
  - "size_t - тип"
  - "stat - тип"
  - "terminate_function - тип"
  - "time_t - тип"
  - "timeb - тип"
  - "timeb64"
  - "tm - тип"
  - "uintptr_t - тип"
  - "unexpected_function typedef"
  - "utimbuf - тип"
  - "va_list - тип"
  - "wchar_t - тип"
  - "wctrans_t - тип"
  - "wctype_t - тип"
  - "wfinddata_t - тип"
  - "wfinddatai64_t - тип"
  - "wint_t - тип"
ms.assetid: 23312dd2-4a6a-4d70-9b48-2a5d0d8c9f28
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# Стандартные типы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека времени выполнения Microsoft определяет следующие стандартные типы и определения типов.  
  
### Целочисленные типы фиксированной ширины \(stdint.h\)  
  
|Имя|Эквивалентный встроенный тип|  
|---------|----------------------------------|  
|int8\_t, uint8\_t|char со знаком, char без знака|  
|int16\_t, int16\_t|short, short без знака|  
|int32\_t, uint32\_t|int, int без знака|  
|int64\_t, int64\_t|long long, long long без знака|  
|int\_least8\_t, uint\_least8\_t|char со знаком, char без знака|  
|int\_least16\_t, uint\_least16\_t|short, short без знака|  
|int\_least32\_t, uint\_least32\_t|int, int без знака|  
|int\_least64\_t, uint\_least64\_t|long long, long long без знака|  
|int\_fast8\_t, uint\_fast8\_t|char со знаком, char без знака|  
|int\_fast16\_t, uint\_fast16\_t|int, int без знака|  
|int\_fast32\_t, uint\_fast32\_t|int, int без знака|  
|int\_fast64\_t, uint\_fast64\_t|long long, long long без знака|  
|intmax\_t, uintmax\_t|long long, long long без знака|  
  
|Тип|Описание|Объявляется в|  
|---------|--------------|-------------------|  
|`clock_t` \(long\)|Хранит значения времени; используется [часами](../c-runtime-library/reference/clock.md).|TIME.H|  
|Структура `_complex`|Хранит реальные и мнимые части сложных чисел; используется [\_cabs](../Topic/_cabs.md).|MATH.H|  
|`_CRT_ALLOC_HOOK`|Определение типа для определенной пользователем функции\-ловушки.  Используется в [\_CrtSetAllocHook](../Topic/_CrtSetAllocHook.md).|CRTDBG.H|  
|`_CRT_DUMP_CLIENT`,<br /><br /> `_CRT_DUMP_CLIENT_M`|Определение типа для функции обратного вызова, вызываемой в [\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md).|CRTDBG.H|  
|Структура `_CrtMemState`|Содержит сведения о текущем состоянии отладочной кучи времени выполнения C.|CRTDBG.H|  
|`_CRT_REPORT_HOOK`,<br /><br /> `_CRT_REPORT_HOOKW`,<br /><br /> `_CRT_REPORT_HOOKW_M`|Определение типа для функции обратного вызова, вызываемой в [\_CrtDbgReport](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).<br /><br /> Параметры для данной функции: тип отчета, выходное сообщение и возвращаемое значение функции обратного вызова.|CRTDBG.H|  
|`dev_t`, `_dev_t` короткое целое или целое без знака|Представляет дескрипторы устройства.|SYS\\TYPES.H|  
|`_diskfree_t` структура|Содержит сведения о диске.  Используется [\_getdiskfree](../Topic/_getdiskfree.md)**.**|DOS.H и DIRECT.H|  
|Структуры `div_t`, `ldiv_t` и `lldiv_t`|Хранят значение, возвращаемые [div](../c-runtime-library/reference/div.md), [ldiv](../Topic/ldiv,%20lldiv.md) и [lldiv](../Topic/ldiv,%20lldiv.md), соответственно.|STDLIB.H|  
|Целое число `errno_t`|Используется для параметра или типа возвращаемого функцией значения, который относится к кодам ошибок `errno`.|STDDEF.H,<br /><br /> CRTDEFS.H|  
|Структура `_exception`|Хранит сведения об ошибке для [\_matherr](../c-runtime-library/reference/matherr.md).|MATH.H|  
|`_EXCEPTION_POINTERS`|Содержит запись исключения.  Дополнительные сведения см. в разделе [EXCEPTION\_POINTERS](http://msdn.microsoft.com/library/windows/desktop/ms679331).|FPIEEE.H|  
|`FILE` структура|Хранит сведения о текущем состоянии потока; используется во всех потоковых операциях ввода\-вывода.|STDIO.H|  
|Структуры `_finddata_t`, `_wfinddata_t`, `_finddata32_t`, `_wfinddata32_t`, `_finddatai64_t`, `_wfinddatai64_t`, `__finddata64_t`, `__wfinddata64_t`, `__finddata32i64_t`, `__wfinddata32i64_t`, `__finddata64i32_t`, `__wfinddata64i32_t`|Хранят информацию файлового атрибута, возвращаемую [\_findfirst, \_wfindfirst и связанные функции](../Topic/_findfirst,%20_findfirst32,%20_findfirst32i64,%20_findfirst64,%20_findfirst64i32,%20_findfirsti64,%20_wfindfirst,%20_wfindfirst32,%20_wfindfirst32i64,%20_wfindfirst64,%20_wfindfirst64i32,%20_wfindfirsti64.md) и [\_findnext, \_wfindnext и связанные функции](../Topic/_findnext,%20_findnext32,%20_findnext32i64,%20_findnext64,%20_findnext64i32,%20_findnexti64,%20_wfindnext,%20_wfindnext32,%20_wfindnext32i64,%20_wfindnext64,%20_wfindnext64i32,%20_wfindnexti64.md).  Дополнительные сведения о членах структур см. в разделе [Функции поиска имени файла](../c-runtime-library/filename-search-functions.md).|IO.H, WCHAR.H|  
|`_FPIEEE_RECORD` структура|Содержит информацию, связанную с исключением плавающей запятой IEEE; передается определяемому пользователем обработчику перехвата с помощью [\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md).|FPIEEE.H|  
|`fpos_t` \(длинное целое, `__int64` или структура, в зависимости от целевой платформы\)|Используется [fgetpos](../c-runtime-library/reference/fgetpos.md) и [fsetpos](../Topic/fsetpos.md) для записи сведений в целях уникального определения каждой позиции в файле.|STDIO.H|  
|`_fsize_t` \(длинное целое без знака\)|Используется для представления размера файла.|IO.H,<br /><br /> WCHAR.H|  
|Структура `_HEAPINFO`|Содержит сведения о следующей записи кучи для [\_heapwalk](../Topic/_heapwalk.md).|MALLOC.H|  
|`_HFILE` \(void \*\)|Дескриптор файла операционной системы.|CRTDBG.H|  
|`imaxdiv_t`|Тип значения, возвращаемого функцией [imaxdiv](../c-runtime-library/reference/imaxdiv.md), содержащий как частное, так и остаток.|inttypes.h|  
|`ino_t`, `_ino_t` \(short без знака\)|Для возвращения информации о состоянии.|WCHAR.H|  
|`intmax_t`|Тип целого числа со знаком, способный представлять любое значение любого типа целого числа со знаком.|stdint.h|  
|`intptr_t` \(длинное целое или `__int64`, в зависимости от целевой платформы\)|Хранит указатель \(или ДЕСКРИПТОР\) как на платформе Win32, так и на Win64.|STDDEF.H и другое, включая файлы|  
|Массив `jmp_buf`|Используется [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) для сохранения и восстановления среды программы.|SETJMP.H|  
|Структура `lconv`|Содержит правила форматирования для числовых значений в разных странах и регионах.  Используется [localeconv](../c-runtime-library/reference/localeconv.md).|LOCALE.H|  
|`_LDOUBLE`,<br /><br /> `_LONGDOUBLE`,<br /><br /> `_LDBL12` \(длинное double или массив char без знака\)|Используются для представления значения long double.|STDLIB.H|  
|Структура `_locale_t`|Сохраняет текущие значения языкового стандарта; используется во всех библиотеках времени выполнения C, привязанных к языковому стандарту.|CRTDEF.H|  
|`mbstate_t`|Отслеживает состояние преобразования многобайтового символа.|WCHAR.H|  
|`off_t`, `_off_t` длинное целое|Представляет значение смещения файла.|WCHAR.H, SYS\\TYPES.H|  
|`_onexit_t`,<br /><br /> Указатель `_onexit_m_t`|Возвращается [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md).|STDLIB.H|  
|Указатель на функцию `_PNH`|Тип аргумента для [\_set\_new\_handler](../Topic/_set_new_handler.md).|NEW.H|  
|`ptrdiff_t` \(длинное целое или `__int64`, в зависимости от целевой платформы\)|Результат вычитания двух указателей.|CRTDEFS.H|  
|`_purecall_handler`,<br /><br /> `_purecall_handler_m`|Определение типа для функции обратного вызова, которая вызывается при вызове чистой виртуальной функции.  Используется [\_get\_purecall\_handler \_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md).  Функция `_purecall_handler` должна иметь тип возвращаемого значения "void".|STDLIB.H|  
|Определение типа `_RTC_error_fn`|Определение типа для функции, которая будет обрабатывать проверки на ошибки времени выполнения.  Используется в [\_RTC\_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md).|RTCAPI.H|  
|Определение типа `_RTC_error_fnW`|Определение типа для функции, которая будет обрабатывать проверки на ошибки времени выполнения.  Используется в [\_RTC\_SetErrorFuncW](../c-runtime-library/reference/rtc-seterrorfuncw.md).|RTCAPI.H|  
|Перечисление `_RTC_ErrorNumber`|Определяет условия ошибки для [\_RTC\_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md) и [\_RTC\_SetErrorType](../Topic/_RTC_SetErrorType.md).|RTCAPI.H|  
|`_se_translator_function`|Определение типа для функции обратного вызова, преобразующей исключение.  Первый параметр является кодом исключения, а второй параметр — записью исключения.  Используется [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md).|EH.H|  
|Целое число `sig_atomic_t`|Тип объекта, который можно изменить как атомарную сущность даже при наличии асинхронных прерываний; используется с [сигналом](../c-runtime-library/reference/signal.md).|SIGNAL.H|  
|`size_t` \(\_\_int64 без знака или целое число без знака, в зависимости от целевой платформы\)|Результат оператора  `sizeof`.|CRTDEFS.H и другое, включая файлы|  
|Структура `_stat`|Содержит сведения о состоянии файла, возвращаемые [\_stat](../c-runtime-library/reference/stat-functions.md) и [\_fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md).|SYS\\STAT.H|  
|Структура `__stat64`|Содержит сведения о состоянии файла, возвращаемые [\_fstat64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) и [\_stat64](../c-runtime-library/reference/stat-functions.md), и [\_wstat64](../c-runtime-library/reference/stat-functions.md).|SYS\\STAT.H|  
|Структура `_stati64`|Содержит сведения о состоянии файла, возвращаемые [\_fstati64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [\_stati64](../c-runtime-library/reference/stat-functions.md) и [\_wstati64](../c-runtime-library/reference/stat-functions.md).|SYS\\STAT.H|  
|Определение типа `terminate_function`|Определение типа для функции обратного вызова, которая вызывается при вызове [terminate](../c-runtime-library/reference/terminate-crt.md).  Используется [set\_terminate](../c-runtime-library/reference/set-terminate-crt.md).|EH.H|  
|`time_t` \(\_\_int64 или длинное целое число\)|Представляет значения времени в [mktime](../Topic/mktime,%20_mktime32,%20_mktime64.md), [time](../Topic/time,%20_time32,%20_time64.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) и [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md).  Количество секунд, прошедших с 0:00 по UTC 1\-го января 1970 года.  Если \_USE\_32BIT\_TIME\_T определено, `time_t` — длинное целое число.  Если не определено, это 64\-разрядное целое число.|TIME.H,<br /><br /> SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|`__time32_t` \(длинное целое\)|Представляет значения времени в [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) и [localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md).|CRTDEFS.H, SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|`__time64_t` \(`__int64`\)|Представляет значения времени в [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md), [\_ctime64, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [\_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [\_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md) и [\_time64](../Topic/time,%20_time32,%20_time64.md).|TIME.H,<br /><br /> SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|Структура `_timeb`|Используется  [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md) для хранения текущего системного времени.|SYS\\TIMEB.H|  
|Структура `__timeb32`|Используется [\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md) для хранения текущего системного времени.|SYS\\TIMEB.H|  
|Структура `__timeb64`|Используется [\_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md) для хранения текущего системного времени.|SYS\\TIMEB.H|  
|Структура `tm`|Используется [asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md), [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), [localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md) и [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) для хранения и извлечения данных о времени.|TIME.H|  
|`uintmax_t`|Тип целого числа без знака, способный представлять любое значение любого типа целого числа без знака.|stdint.h|  
|`uintptr_t` \(длинное целое или `__int64`, в зависимости от целевой платформы\)|Целое число без знака или версия без знака \_\_int64 от `intptr_t`.|STDDEF.H и другое, включая файлы|  
|`unexpected_function`|Определение типа для функции обратного вызова, которая вызывается при вызове [unexpected](../Topic/unexpected%20\(CRT\).md).  Используется [set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md).|EH.H|  
|Структура `_utimbuf`|Хранит значения времени доступа к файлам и их изменения, используемые [\_utime, \_wutime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) и [\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для изменения дат изменения файлов.|SYS\\UTIME.H|  
|Структура `_utimbuf32`|Хранит значения времени доступа к файлам и их изменения, используемые [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) and [\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для изменения дат изменения файлов.|SYS\\UTIME.H|  
|Структура `__utimbuf64`|Используется [\_utime64, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) и [\_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для хранения текущего времени.|SYS\\UTIME.H|  
|Структура `va_list`|Используется для хранения сведений, необходимых макросам [va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) и [va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md).  Вызываемая функция объявляет переменную типа `va_list`, которую можно передать в качестве аргумента другой функции.|STDARG.H,<br /><br /> CRTDEFS.H|  
|Расширенный символ `wchar_t`|Полезен для создания переносимых программ для международных рынков.|STDDEF.H, STDLIB.H,<br /><br /> CRTDEFS.H,<br /><br /> SYS\\STAT.H|  
|Целое число `wctrans_t`|Представляет сопоставления символов, привязанные к языковому стандарту.|WCTYPE.H|  
|Целое число `wctype_t`|Может представлять все символы любой кодировки языка.|WCHAR.H,<br /><br /> CRTDEFS.H|  
|Целое число `wint_t`|Тип объекта данных, который может содержать любой расширенный символ или расширенное значение конца файла.|WCHAR.H,<br /><br /> CRTDEFS.H|  
  
## См. также  
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)