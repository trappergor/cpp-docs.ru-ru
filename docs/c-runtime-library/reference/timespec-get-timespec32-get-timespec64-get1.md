---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 11/04/2016
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: c0517c974bf58d502133ccd9868149bd178790d6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957619"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

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

Значение *base* в случае успеха, в противном случае возвращается ноль.

## <a name="remarks"></a>Примечания

Функции **timespec_get** задают текущее время в структуре, на которую указывает аргумент *time_spec* . Все версии этой структуры имеют два члена: **tv_sec** и **tv_nsec**. Значение **tv_sec** устанавливается равным целому числу секунд, а **tv_nsec** — целому числу наносекунд, округленному до разрешения системных часов с начала эпохи, заданной *базовым*.

**Блок, относящийся только к системам Microsoft**

Эти функции поддерживают только **TIME_UTC** в качестве *базового* значения. При этом значение *time_spec* устанавливается равным числу секунд и наносекундах с момента начала эпохи, полночь 1 января 1970 г., время в формате UTC. В **структуре** **_timespec32** **tv_sec** является значением **__time32_t** . В **структуре** **_timespec64** **tv_sec** является значением **__time64_t** . В **структуре** **timespec** **tv_sec** — это тип **time_t** , который имеет длину 32 бит или 64 бит в зависимости от того, определен ли макрос препроцессора _USE_32BIT_TIME_T. Функция **timespec_get** является встроенной функцией, которая вызывает **_timespec32_get** , если определен _USE_32BIT_TIME_T. в противном случае он вызывает **_timespec64_get**.

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
