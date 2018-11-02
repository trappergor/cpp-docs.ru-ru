---
title: _get_timezone
ms.date: 11/04/2016
apiname:
- _get_timezone
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
- _get_timezone
- get_timezone
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
ms.openlocfilehash: 26cf8114ab766bdb394d2db9ad5842622a447bd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613919"
---
# <a name="gettimezone"></a>_get_timezone

Извлекает разницу в секундах между временем в формате UTC и местным временем.

## <a name="syntax"></a>Синтаксис

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>Параметры

*секунд*<br/>
Разница в секундах между временем в формате UTC и местным временем.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успешного выполнения или **errno** значение, если возникает ошибка.

## <a name="remarks"></a>Примечания

**_Get_timezone** функция извлекает разница в секундах между временем UTC и местного времени к целому числу. Значение по умолчанию — 28800 секунд (тихоокеанское время, на 8 часов отстающее от UTC).

Если *секунд* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_timezone**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
