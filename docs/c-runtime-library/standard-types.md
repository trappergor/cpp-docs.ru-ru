---
title: Стандартные типы
ms.date: 11/04/2016
f1_keywords:
- __time64_t
- _diskfree_t
- _CRT_DUMP_CLIENT
- _fsize_t
- __timeb64
- File
- __utimeb64
- jmp_buf
- __finddata64_t
- _wfinddata_t
- _finddata_t
- utimbuf64
- wint_t
- wctrans_t
- wctype_t
- _HFILE
- _secerr_handler_func
- clock_t
- fpos_t
- _dev_t
- time64_t
- wfinddata64_t
- stat64
- ldiv_t
- _EXCEPTION_POINTERS
- terminate_function
- size_t
- timeb64
- tm
- _HEAPINFO
- unexpected_function
- _CrtMemState
- _se_translator_function
- sig_atomic_t
- _CRT_REPORT_HOOK
- _complex
- _w_finddatai64_t
- _timeb
- _onexit_t
- _RTC_ErrorNumber
- lconv
- _PNH
- _off_t
- ptrdiff_t
- time_t
- _FPIEEE_RECORD
- _exception
- __w_finddata64_t
- __stat64
- _utimbuf
- __utimbuf64
- div_t
- _CRT_ALLOC_HOOK
- int8_t
- uint8_t
- int16_t
- uint16_t
- int32_t
- uint32_t
- int64_t
- int_least8_t
- uint_least8_t
- int_least16_t
- uint_least16_t
- int_least32_t
- uint_least32_t
- int_least64_t
- uint_least64_t
- int_fast8_t
- uint_fast8_t
- int_fast16_t
- uint_fast16_t
- int_fast32_t
- uint_fast32_t
- int_fast64_t
- uint_fast64_t
- intmax_t
- uintmax_t
helpviewer_keywords:
- __timeb64 type
- tm type
- clock_t type
- intptr_t type
- diskfree_t type
- wctype_t type
- CRT_DUMP_CLIENT type
- sig_atomic_t type
- _PNH type
- time_t type
- wfinddata_t type
- timeb64
- CRT, standard types
- wint_t type
- _RTC_ErrorNumber type
- _diskfree_t type
- _dev_t type
- _wfinddata_t type
- HFILE type
- __utimbuf64 type
- div_t type
- _onexit_t type
- _secerr_handler_func type
- FPIEEE_RECORD type
- HEAPINFO type
- PNH type
- _CRT_ALLOC_HOOK type
- _se_translater_function type
- va_list type
- wctrans_t type
- secerr_handler_func type
- _locale_t type
- timeb type
- lconv type
- utimbuf type
- dev_t type
- unexpected_function typedef
- _complex type
- _off_t type
- off_t type
- RTC_ErrorNumber type
- _FPIEEE_RECORD type
- exception type
- _CRT_REPORT_HOOK type
- _HEAPINFO type
- ldiv_t type
- terminate_function type
- uintptr_t type
- _CRT_DUMP_CLIENT type
- _utimbuf type
- wfinddatai64_t type
- fpos_t type
- wchar_t type
- CRT_ALLOC_HOOK type
- _HFILE type
- __time64_t type
- _timeb type
- CrtMemState type
- __finddata64_t type
- _exception type
- stat type
- onexit_t type
- FILE constant
- _stat type
- finddata_t type
- __wfinddata64_t type
- ptrdiff_t type
- complex types
- _wfinddatai64_t type
- _EXCEPTION_POINTERS type
- jmp_buf type
- se_translater_function type
- size_t type
- EXCEPTION_POINTERS type
- __stat64 type
- _fsize_t type
- CRT_REPORT_HOOK type
- _finddata_t type
ms.assetid: 23312dd2-4a6a-4d70-9b48-2a5d0d8c9f28
ms.openlocfilehash: 38906579a449941d6dad767afa97a32d63fe3445
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231277"
---
# <a name="standard-types"></a>Стандартные типы

Библиотека времени выполнения Microsoft определяет следующие стандартные типы и определения типов.

### <a name="fixed-width-integral-types-stdinth"></a>Целочисленные типы фиксированной ширины (stdint.h)

|Имя|Эквивалентный встроенный тип|
|----------|-------------------------------|
|int8\_t, uint8\_t|char со знаком, char без знака|
|int16\_t, uint16\_t|short, short без знака|
|int32\_t, uint32\_t|int, int без знака|
|int64\_t, uint64\_t|long long, long long без знака|
|int_least8_t, uint_least8_t|char со знаком, char без знака|
|int_least16_t, uint_least16_t|short, short без знака|
|int_least32_t, uint_least32_t|int, int без знака|
|int_least64_t, uint_least64_t|long long, long long без знака|
|int_fast8_t, uint_fast8_t|char со знаком, char без знака|
|int_fast16_t, uint_fast16_t|int, int без знака|
|int_fast32_t, uint_fast32_t|int, int без знака|
|int_fast64_t, uint_fast64_t|long long, long long без знака|
|intmax_t, uintmax_t|long long, long long без знака|

|Тип|Описание|Объявляется в|
|----------|-----------------|-----------------|
|`clock_t` (long)|Хранит значения времени; используется [часами](../c-runtime-library/reference/clock.md).|TIME.H|
|Структура `_complex`|Хранит реальные и мнимые части сложных чисел; используется в [_cabs](../c-runtime-library/reference/cabs.md).|MATH.H|
|`_CRT_ALLOC_HOOK`|Определение типа для определенной пользователем функции-ловушки. Используется в [_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md).|CRTDBG.H|
|`_CRT_DUMP_CLIENT`,<br /><br /> `_CRT_DUMP_CLIENT_M`|Определение типа для функции обратного вызова, к которой обращается [_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md).|CRTDBG.H|
|Структура `_CrtMemState`|Содержит сведения о текущем состоянии отладочной кучи времени выполнения C.|CRTDBG.H|
|`_CRT_REPORT_HOOK`,<br /><br /> `_CRT_REPORT_HOOKW`,<br /><br /> `_CRT_REPORT_HOOKW_M`|Определение типа для функции обратного вызова, к которой обращается [_CrtDbgReport](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).<br /><br /> Параметры для данной функции: тип отчета, выходное сообщение и возвращаемое значение функции обратного вызова.|CRTDBG.H|
|`dev_t`, `_dev_t` короткое целое или целое без знака|Представляет дескрипторы устройства.|SYS\TYPES.H|
|Структура `_diskfree_t`|Содержит сведения о диске. Используется в [_getdiskfree](../c-runtime-library/reference/getdiskfree.md)**.**|DOS.H и DIRECT.H|
|Структуры `div_t`, `ldiv_t` и `lldiv_t`|Хранят значения, возвращаемые [div](../c-runtime-library/reference/div.md), [ldiv](../c-runtime-library/reference/ldiv-lldiv.md) и [lldiv](../c-runtime-library/reference/ldiv-lldiv.md), соответственно.|STDLIB.H|
|Целое число `errno_t`|Используется для параметра или типа возвращаемого функцией значения, который относится к кодам ошибок `errno`.|STDDEF.H,<br /><br /> CRTDEFS.H|
|Структура `_exception`|Хранит сведения об ошибке для [_matherr](../c-runtime-library/reference/matherr.md).|MATH.H|
|`_EXCEPTION_POINTERS`|Содержит запись исключения. Дополнительные сведения см. в разделе [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers).|FPIEEE.H|
|Структура `FILE`|Хранит сведения о текущем состоянии потока; используется во всех потоковых операциях ввода-вывода.|STDIO.H|
|Структуры `_finddata_t`, `_wfinddata_t`, `_finddata32_t`, `_wfinddata32_t`, `_finddatai64_t`, `_wfinddatai64_t`, `__finddata64_t`, `__wfinddata64_t`, `__finddata32i64_t`, `__wfinddata32i64_t`, `__finddata64i32_t`, `__wfinddata64i32_t`|Хранит информацию об атрибутах файла, которую возвращают [_findfirst, _wfindfirst и связанные с ними функции](../c-runtime-library/reference/findfirst-functions.md) или [_findnext, _wfindnext и связанные с ними функции](../c-runtime-library/reference/findnext-functions.md). Дополнительные сведения о членах структур вы найдете в статье [Функции поиска имени файла](../c-runtime-library/filename-search-functions.md).|IO.H, WCHAR.H|
|Структура `_FPIEEE_RECORD`|Содержит информацию, связанную с исключением плавающей запятой IEEE; передается определяемому пользователем обработчику перехвата с помощью [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md).|FPIEEE.H|
|`fpos_t`(длинное целое число, **`__int64`** или структура в зависимости от целевой платформы)|Используется в [fgetpos](../c-runtime-library/reference/fgetpos.md) и [fsetpos](../c-runtime-library/reference/fsetpos.md) для записи сведений, уникально определяющих каждую позицию в файле.|STDIO.H|
|`_fsize_t` (длинное целое без знака)|Используется для представления размера файла.|IO.H,<br /><br /> WCHAR.H|
|Структура `_HEAPINFO`|Содержит сведения о следующей записи кучи для [_heapwalk](../c-runtime-library/reference/heapwalk.md).|MALLOC.H|
|`_HFILE` (void \*)|Дескриптор файла операционной системы.|CRTDBG.H|
|`imaxdiv_t`|Тип значения, возвращаемого функцией [imaxdiv](../c-runtime-library/reference/imaxdiv.md), содержащий как частное, так и остаток.|inttypes.h|
|`ino_t`, `_ino_t` (short без знака)|Для возвращения информации о состоянии.|WCHAR.H|
|`intmax_t`|Тип целого числа со знаком, способный представлять любое значение любого типа целого числа со знаком.|stdint.h|
|`intptr_t`(длинное целое число или **`__int64`** , в зависимости от целевой платформы)|Хранит указатель (или ДЕСКРИПТОР) как на платформе Win32, так и на Win64.|STDDEF.H и другое, включая файлы|
|`jmp_buf` массив|Используется [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) для сохранения и восстановления окружения программы.|SETJMP.H|
|Структура `lconv`|Содержит правила форматирования для числовых значений в разных странах и регионах. Используется в [localeconv](../c-runtime-library/reference/localeconv.md).|LOCALE.H|
|`_LDOUBLE`,<br /><br /> `_LONGDOUBLE`,<br /><br /> `_LDBL12` (длинное double или массив char без знака)|Используются для представления значения long double.|STDLIB.H|
|Структура `_locale_t`|Сохраняет текущие значения языкового стандарта; используется во всех библиотеках времени выполнения C, привязанных к языковому стандарту.|CRTDEFS.H|
|`mbstate_t`|Отслеживает состояние преобразования многобайтового символа.|WCHAR.H|
|`off_t`, `_off_t` длинное целое|Представляет значение смещения файла.|WCHAR.H, SYS\TYPES.H|
|`_onexit_t`,<br /><br /> Указатель `_onexit_m_t`|Возвращается из [_onexit _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md).|STDLIB.H|
|Указатель на функцию `_PNH`|Тип аргумента для [_set_new_handler](../c-runtime-library/reference/set-new-handler.md).|NEW.H|
|`ptrdiff_t`(длинное целое число или **`__int64`** , в зависимости от целевой платформы)|Результат вычитания двух указателей.|CRTDEFS.H|
|`_purecall_handler`,<br /><br /> `_purecall_handler_m`|Определение типа для функции обратного вызова, которая вызывается при вызове чистой виртуальной функции. Используется в [_get_purecall_handler, _set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md). Функция `_purecall_handler` должна иметь тип возвращаемого значения "void".|STDLIB.H|
|Определение типа `_RTC_error_fn`|Определение типа для функции, которая будет обрабатывать проверки на ошибки времени выполнения. Используется в [_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md).|RTCAPI.H|
|Определение типа `_RTC_error_fnW`|Определение типа для функции, которая будет обрабатывать проверки на ошибки времени выполнения. Используется в [_RTC_SetErrorFuncW](../c-runtime-library/reference/rtc-seterrorfuncw.md).|RTCAPI.H|
|Перечисление `_RTC_ErrorNumber`|Определяет условия ошибки для [_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md) и[ _RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md).|RTCAPI.H|
|`_se_translator_function`|Определение типа для функции обратного вызова, преобразующей исключение. Первый параметр является кодом исключения, а второй параметр — записью исключения. Используется в [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).|EH.H|
|Целое число `sig_atomic_t`|Тип объекта, который можно изменить как атомарную сущность даже при наличии асинхронных прерываний; используется совместно с [signal](../c-runtime-library/reference/signal.md).|SIGNAL.H|
|`size_t` (__int64 без знака или целое число без знака, в зависимости от целевой платформы)|Результат **`sizeof`** оператора.|CRTDEFS.H и другое, включая файлы|
|Структура `_stat`|Содержит сведения о состоянии файла, возвращаемые [_stat ](../c-runtime-library/reference/stat-functions.md)и [_fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md).|SYS\STAT.H|
|Структура `__stat64`|Содержит сведения о состоянии файла, возвращаемые [_fstat64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [_stat64](../c-runtime-library/reference/stat-functions.md) и [_wstat64](../c-runtime-library/reference/stat-functions.md).|SYS\STAT.H|
|Структура `_stati64`|Содержит сведения о состоянии файла, возвращаемые [_fstati64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [_stati64](../c-runtime-library/reference/stat-functions.md) и [_wstati64](../c-runtime-library/reference/stat-functions.md).|SYS\STAT.H|
|Определение типа `terminate_function`|Определение типа для функции обратного вызова, которая вызывается при вызове [terminate](../c-runtime-library/reference/terminate-crt.md). Используется в [set_terminate](../c-runtime-library/reference/set-terminate-crt.md).|EH.H|
|`time_t` (__int64 или длинное целое число)|Представляет значения времени в функциях [mktime](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [time](../c-runtime-library/reference/time-time32-time64.md), [ctime _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [ctime _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) и [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md). Количество секунд, прошедших с 0:00 по UTC 1-го января 1970 года. Если _USE_32BIT_TIME_T определено, `time_t` — длинное целое число. Если не определено, это 64-разрядное целое число.|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|`__time32_t` (длинное целое)|Представляет значения времени в функциях [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) и [localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md).|CRTDEFS.H, SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|`__time64_t` (**`__int64`**)|Представляет значения времени в функциях [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [_ctime64, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md) и [_time64](../c-runtime-library/reference/time-time32-time64.md).|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|Структура `_timeb`|Используется в [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) для хранения текущего системного времени.|SYS\TIMEB.H|
|Структура `__timeb32`|Используется в [_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) для хранения текущего системного времени.|SYS\TIMEB.H|
|Структура `__timeb64`|Используется в [_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) для хранения текущего системного времени.|SYS\TIMEB.H|
|Структура `tm`|Используется в функциях [asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md), [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), [localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md) и [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) для хранения и извлечения данных о времени.|TIME.H|
|`uintmax_t`|Тип целого числа без знака, способный представлять любое значение любого типа целого числа без знака.|stdint.h|
|`uintptr_t`(длинное целое число или **`__int64`** , в зависимости от целевой платформы)|Целое число без знака или версия без знака __int64 от `intptr_t`.|STDDEF.H и другое, включая файлы|
|`unexpected_function`|Определение типа для функции обратного вызова, которая вызывается при вызове [unexpected](../c-runtime-library/reference/unexpected-crt.md). Используется в [set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md).|EH.H|
|Структура `_utimbuf`|Хранит значения времени доступа к файлам и их изменения, используемые в [_utime, _wutime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) и [_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для изменения дат изменения файлов.|SYS\UTIME.H|
|Структура `_utimbuf32`|Хранит значения времени доступа к файлам и их изменения, используемые в [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) и [_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для изменения дат изменения файлов.|SYS\UTIME.H|
|Структура `__utimbuf64`|Используется [_utime64, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) и [_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) для хранения текущего времени.|SYS\UTIME.H|
|Структура `va_list`|Используется для хранения сведений, необходимых макросам [va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) и [va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). Вызываемая функция объявляет переменную типа `va_list`, которую можно передать в качестве аргумента другой функции.|STDARG.H,<br /><br /> CRTDEFS.H|
|**`wchar_t`** Расширенная буква|Полезен для создания переносимых программ для международных рынков.|STDDEF.H, STDLIB.H,<br /><br /> CRTDEFS.H,<br /><br /> SYS\STAT.H|
|Целое число `wctrans_t`|Представляет сопоставления символов, привязанные к языковому стандарту.|WCTYPE.H|
|Целое число `wctype_t`|Может представлять все символы любой кодировки языка.|WCHAR.H,<br /><br /> CRTDEFS.H|
|Целое число `wint_t`|Тип объекта данных, который может содержать любой расширенный символ или расширенное значение конца файла.|WCHAR.H,<br /><br /> CRTDEFS.H|

## <a name="see-also"></a>См. также раздел

[Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)
