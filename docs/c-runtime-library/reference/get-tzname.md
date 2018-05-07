---
title: _get_tzname | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_tzname
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
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 182bad39b461efc18b120875432d6ce07be2a884
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="gettzname"></a>_get_tzname

Возвращает представление названия часового пояса или названия часового пояса с переходом на летнее время (DST) в виде строки символов.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Длина строки *timeZoneName* включая символ конца строки.

*timeZoneName*<br/>
Адрес символьной строки для представления часового пояса имя или имя зоны (зима) переход на летнее (DST) в зависимости от *индекса*.

*sizeInBytes*<br/>
Размер *timeZoneName* символьные строки в байтах.

*Индекс*<br/>
Индекс, определяющий извлечение одного или двух названий часовых поясов.

## <a name="return-value"></a>Возвращаемое значение

Ноль при успешном завершении, в противном случае **errno** введите значение.

Если параметр *timeZoneName* — **NULL**, или *sizeInBytes* равно нулю или меньше нуля (но не оба), вызывается обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Условия ошибок

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*Индекс*|Возвращаемое значение|Содержимое *timeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Длина названия часового пояса|**NULL**|0|0 или 1|0|не изменено|
|Длина названия часового пояса|any|> 0|0 или 1|0|Название часового пояса|
|не изменено|**NULL**|> 0|any|**EINVAL**|не изменено|
|не изменено|any|нуль|any|**EINVAL**|не изменено|
|не изменено|any|> 0|> 1|**EINVAL**|не изменено|

## <a name="remarks"></a>Примечания

**_Get_tzname** функция получает строковое представление символа названия часовой пояс и летнее стандартное название часового пояса (DST) в адрес *timeZoneName* в зависимости от индекса значение, а также размер строки в *pReturnValue*. Если *timeZoneName* — **NULL** и *sizeInBytes* равно нулю, только что размер строки, либо времени зоны в байтах возвращается в *pReturnValue*. Значение индекса должно быть равно 0 для стандартного часового пояса или 1 для часового пояса с переходом на летнее время. Другие значения индекса дают неопределенные результаты.

### <a name="index-values"></a>Значения индекса

|*Индекс*|Содержимое *timeZoneName*|*timeZoneName* значение по умолчанию|
|-------------|--------------------------------|----------------------------------|
|0|Название часового пояса|"PST"|
|1|Название часового пояса с переходом на летнее время|"PDT"|
|> 1 или < 0|**errno** значение **EINVAL**|не изменено|

Если значения не изменяются явным образом во время выполнения, по умолчанию используются значения "PST" и "PDT" соответственно.  Размеры этих массивов знаков управляются **TZNAME_MAX** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[TZNAME_MAX](../../c-runtime-library/tzname-max.md)<br/>
