---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
ms.date: 4/2/2020
api_name:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
- _o__utime32
- _o__utime64
- _o__wutime32
- _o__wutime64
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
ms.openlocfilehash: 5c530f46877bdb23fc51fb49beab8abfc0c16b2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361207"
---
# <a name="_utime-_utime32-_utime64-_wutime-_wutime32-_wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64

Задают время изменения файла.

## <a name="syntax"></a>Синтаксис

```C
int _utime(
   const char *filename,
   struct _utimbuf *times
);
int _utime32(
   const char *filename,
   struct __utimbuf32 *times
);
int _utime64(
   const char *filename,
   struct __utimbuf64 *times
);
int _wutime(
   const wchar_t *filename,
   struct _utimbuf *times
);
int _wutime32(
   const wchar_t *filename,
   struct __utimbuf32 *times
);
int _wutime64(
   const wchar_t *filename,
   struct __utimbuf64 *times
);
```

### <a name="parameters"></a>Параметры

*Имени файла*<br/>
Указатель на строку, содержащую путь или имя файла.

*Раз*<br/>
Указатель на сохраненные значения времени.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если время изменения файла было изменено. Значение возврата -1 указывает на ошибку. Если передан недопустимый параметр, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции возвращаются -1 и **errno** устанавливается на одно из следующих значений:

|Значение errno|Условие|
|-|-|
| **EACCES** | Путь указывает каталог или файл, доступный только для чтения |
| **EINVAL** | Аргумент недействительных *времен* |
| **EMFILE** | Слишком много открытых файлов (чтобы изменить время изменения файла, файл необходимо открыть) |
| **ENOENT** | Путь или имя файла не найдены |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Дату файла можно изменить, если дата изменения лежит в диапазоне от полуночи 1-го января 1970 года до конечной даты используемой функции. **_utime** и **_wutime** использовать 64-битное значение времени, поэтому дата окончания 23:59:59, 31 декабря 3000, UTC. Если **_USE_32BIT_TIME_T** определен, чтобы заставить старое поведение, дата окончания 23:59:59 18 января 2038, UTC. **_utime32** или **_wutime32** использовать 32-битный тип времени независимо от того, определена **ли _USE_32BIT_TIME_T,** и всегда имеют более раннюю дату окончания. **_utime64** или **_wutime64** всегда используют 64-битный тип времени, поэтому эти функции всегда поддерживают более позднюю дату окончания.

## <a name="remarks"></a>Remarks

Функция **_utime** устанавливает время изменения файла, указанное *именем файла.* Для изменения времени процесс должен иметь разрешение на запись в файл. В операционной системе Windows можно изменить время доступа и время изменения в **структуре _utimbuf.** Если *время* является указателем **NULL,** время изменения устанавливается на текущее местное время. В противном *случае, времена* должны указывать на структуру **_utimbuf**типа, определяемую в SYS-UTIME. H.

**Структура _utimbuf** хранит файлы доступа и изменения раз, используемых **_utime** для изменения даты изменения файлов. Структура имеет следующие поля, которые являются как типа **time_t:**

| Поле |   |
|-------|---|
| **actime** | Время доступа к файлу |
| **modtime** | Время изменения файла |

Конкретные версии **_utimbuf** структуры **(_utimebuf32** и **__utimbuf64)** определяются с использованием 32-битной и 64-битной версий типа времени. Они используются в 32- и 64-разрядных версиях этой функции. **_utimbuf** по умолчанию использует 64-битный тип времени, если **_USE_32BIT_TIME_T** не определен.

**_utime** идентичен **_futime** за исключением того, что аргумент *имени файла* **_utime** является именем файла или путем к файлу, а не дескриптором файла открытого файла.

**_wutime** является широкохарактерным вариантом **_utime;** аргумент *имени файла* для **_wutime** является широкохарактерной строкой. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tutime**|**_utime**|**_utime**|**_wutime**|
|**_tutime32**|**_utime32**|**_utime32**|**_wutime32**|
|**_tutime64**|**_utime64**|**_utime64**|**_wutime64**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательные заголовки|Необязательные заголовки|
|-------------|----------------------|----------------------|
|**_utime,** **_utime32,** **_utime64**|\<sys/utime.h>|\<errno.h>|
|**_utime64**|\<sys/utime.h>|\<errno.h>|
|**_wutime**|\<utime.h> или \<wchar.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа использует **_utime** для установки времени изменения файла к текущему времени.

```C
// crt_utime.c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/utime.h>
#include <time.h>

int main( void )
{
   struct tm tma = {0}, tmm = {0};
   struct _utimbuf ut;

   // Fill out the accessed time structure
   tma.tm_hour = 12;
   tma.tm_isdst = 0;
   tma.tm_mday = 15;
   tma.tm_min = 0;
   tma.tm_mon = 0;
   tma.tm_sec = 0;
   tma.tm_year = 103;

   // Fill out the modified time structure
   tmm.tm_hour = 12;
   tmm.tm_isdst = 0;
   tmm.tm_mday = 15;
   tmm.tm_min = 0;
   tmm.tm_mon = 0;
   tmm.tm_sec = 0;
   tmm.tm_year = 102;

   // Convert tm to time_t
   ut.actime = mktime(&tma);
   ut.modtime = mktime(&tmm);

   // Show file time before and after
   system( "dir crt_utime.c" );
   if( _utime( "crt_utime.c", &ut ) == -1 )
      perror( "_utime failed\n" );
   else
      printf( "File time modified\n" );
   system( "dir crt_utime.c" );
}
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/09/2003  05:38 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
File time modified
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/15/2002  12:00 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[_futime, _futime32, _futime64](futime-futime32-futime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[Функции _stat, _wstat](stat-functions.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
