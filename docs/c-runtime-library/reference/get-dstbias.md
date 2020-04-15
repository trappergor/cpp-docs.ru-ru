---
title: _get_dstbias
ms.date: 4/2/2020
api_name:
- _get_dstbias
- __dstbias
- _o___dstbias
- _o__get_dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: 969b6d2dfd83a1a136fdfb3d17f8f843337b792c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345232"
---
# <a name="_get_dstbias"></a>_get_dstbias

Получает смещение перехода на зимнее время в секундах.

## <a name="syntax"></a>Синтаксис

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Параметры

*Секунд*<br/>
Смещение перехода на зимнее время в секундах.

## <a name="return-value"></a>Возвращаемое значение

Нулевой, если успешно или **errno** значение, если ошибка происходит.

## <a name="remarks"></a>Remarks

**Функция _get_dstbias** получает количество секунд в летнее время в качестве целых. Если действует переход на зимнее время, смещение по умолчанию составляет 3600 секунд. Это число соответствует одному часу (хотя в некоторых регионах может применяться смещение на два часа).

Если *секунды* **NULL,** недействительный обработчик параметров вызывается, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

Мы рекомендуем вам использовать эту функцию вместо **макро-_dstbias** или амортизированной функции **__dstbias.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
