---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 11/04/2016
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: 1591189ff2db78605c334e72ac3be13876afc81d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155554"
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get

Устанавливает интервал, на который указывает первый аргумент, в текущее календарное время в соответствии с заданной базой времени.

## <a name="syntax"></a>Синтаксис

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);
```

### <a name="parameters"></a>Параметры

*time_spec*<br/>
Указатель на структуру, которой присваивается время в секундах и наносекундах с начала эпохи.

*base*<br/>
Зависящее от реализации ненулевое значение, определяющее базу времени.

## <a name="return-value"></a>Возвращаемое значение

Значение *базового* при успешном завершении, в противном случае он возвращает ноль.

## <a name="remarks"></a>Примечания

**Timespec_get** функции задают текущее время в структуре, на которые указывают *time_spec* аргумент. Все версии этой структуры имеют два члена: **tv_sec** и **tv_nsec**. **Tv_sec** имеет значение целому числу секунд и **tv_nsec** в целое число наносекунд, округленное до разрешения системных часов с начала эпохи, указанной по *базового*.

**Блок, относящийся только к системам Microsoft**

Эти функции поддерживают только **TIME_UTC** как *базового* значение. Этот параметр задает *time_spec* число секунд и наносекунд с начала эпохи, полуночи 1 января 1970 года, время в формате UTC. В **структуры** **_timespec32**, **tv_sec** — **__time32_t** значение. В **структуры** **_timespec64**, **tv_sec** — **__time64_t** значение. В **структуры** **timespec**, **tv_sec** — **time_t** тип, который является 32-разрядный или 64 бита в длину в зависимости от того, следует ли препроцессора макрос _USE_32BIT_TIME_T определено. **Timespec_get** функция — это встраиваемая функция, которая вызывает **_timespec32_get** Если _USE_32BIT_TIME_T определено; в противном случае он вызывает **_timespec64_get**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h>, C++: \<ctime> или \<time.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
