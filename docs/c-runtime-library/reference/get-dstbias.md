---
title: _get_dstbias
ms.date: 11/04/2016
api_name:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: a48cc4fe35a1bbd18342750571214ed0977cf3ee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955950"
---
# <a name="_get_dstbias"></a>_get_dstbias

Получает смещение перехода на зимнее время в секундах.

## <a name="syntax"></a>Синтаксис

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Параметры

*несколько*<br/>
Смещение перехода на зимнее время в секундах.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или **значение** пересчета при возникновении ошибки.

## <a name="remarks"></a>Примечания

Функция **_get_dstbias** Извлекает число секунд в летнем времени в виде целого числа. Если действует переход на зимнее время, смещение по умолчанию составляет 3600 секунд. Это число соответствует одному часу (хотя в некоторых регионах может применяться смещение на два часа).

Если значение *секунд* равно **null**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **еинвал**.

Рекомендуется использовать эту функцию вместо макроса **_dstbias** или устаревшей функции **__dstbias**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
