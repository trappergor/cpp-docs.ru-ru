---
title: _strtime, _wstrtime
ms.date: 11/04/2016
apiname:
- _wstrtime
- _strtime
apilocation:
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
ms.openlocfilehash: 9d874321418854a703886eb80ee23ac1cba57fa4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223101"
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

Копируют время в буфер. Существуют более безопасные версии этих функций. См. раздел [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*timestr*<br/>
Время в виде строки.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на результирующую строку символов *timestr*.

## <a name="remarks"></a>Примечания

**_Strtime** функция копирует текущее местное время в буфере, на которые указывают *timestr*. Время форматируется как **чч: мм:** где **hh** состоит из двух цифр, представляющие час в 24-часовом формате, **мм** состоит из двух цифр, представляющих минуты после начала часа, а **ss** состоит из двух цифр, представляющие секунды. Например, строка **18:23:44** представляет 23 минуты и 44 секунды после 6 часов Размер буфера должен быть не менее 9 байтов.

**_wstrtime** — это двухбайтовая версия **_strtime**; аргумент и возвращаемое значение **_wstrtime** представляют собой строки расширенных символов. В остальном эти функции ведут себя одинаково. Если *timestr* — **NULL** указатель или если *timestr* отформатирован неправильно, Недопустимая подпись вызывается обработчик параметров, как описано в разделе [параметр Проверка](../../c-runtime-library/parameter-validation.md). Если исключение может быть продолжено, эти функции возвращают **NULL** и задайте **errno** для **EINVAL** Если *timestr* был **NULL** или задать **errno** для **ERANGE** Если *timestr* имеет неправильный формат.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
