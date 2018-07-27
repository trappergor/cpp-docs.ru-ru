---
title: timespec_get, _timespec32_get, _timespec64_get1 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f00a59f8b5813398b47562b106f3ec0eff3363b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412837"
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

**Timespec_get** функции присваивает текущее время структуре, на который указывает *time_spec* аргумент. Все версии этой структуры имеют два члена **tv_sec** и **tv_nsec**. **Tv_sec** значение равно целому числу секунд и **tv_nsec** целое число наносекунд, округленное до разрешения системных часов с момента начала эпохи, указанной в *базового*.

**Блок, относящийся только к системам Microsoft**

Эти функции поддерживают только **TIME_UTC** как *базового* значение. Это задает *time_spec* до числа секунд и наносекунд с начала эпохи запустить полуночи 1 января 1970 года, универсальное глобальное (UTC). В **структуры** **_timespec32**, **tv_sec** — **__time32_t** значение. В **структуры** **_timespec64**, **tv_sec** — **__time64_t** значение. В **структуры** **timespec**, **tv_sec** — **time_t** тип, который является 32-разрядный или 64 бита в длину в зависимости от того, следует ли препроцессор определен макрос _USE_32BIT_TIME_T. **Timespec_get** функция является встроенная функция, которая вызывает **_timespec32_get** Если определен макрос _USE_32BIT_TIME_T; в противном случае он вызывает метод **_timespec64_get**.

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
