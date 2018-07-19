---
title: _get_daylight | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
dev_langs:
- C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fbe7e36db2e5ca5365f43dc23281d9b5e79077d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398127"
---
# <a name="getdaylight"></a>_get_daylight

Получает смещение перехода на зимнее время в часах.

## <a name="syntax"></a>Синтаксис

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Параметры

*Часы*<br/>
Смещение перехода на зимнее время в часах.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успешного выполнения или **errno** значение, если возникает ошибка.

## <a name="remarks"></a>Примечания

**_Get_daylight** функция получает количество часов на зимнее время в виде целого числа. Если действует переход на зимнее время, смещение по умолчанию составляет один час (хотя в некоторых регионах может применяться смещение на два часа).

Если *часы* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

Рекомендуется использовать эту функцию вместо макроса **_daylight** или нерекомендуемой функции **__daylight**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_daylight**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
