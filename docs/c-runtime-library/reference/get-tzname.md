---
title: _get_tzname
ms.date: 4/2/2020
api_name:
- _get_tzname
- _o__get_tzname
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
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: 50f1f6e4320e3ef905b4eda67ba1d458a5b1df08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344877"
---
# <a name="_get_tzname"></a>_get_tzname

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
Длина *строки,* включая нулевой терминатор.

*времяЗона*<br/>
Адрес строки символов для представления имени часового пояса или стандартного часового пояса (DST) дневного времени (DST), в зависимости от *индекса.*

*размерInBytes*<br/>
Размер строки символа *timeOneName* в байтах.

*Индекс*<br/>
Индекс, определяющий извлечение одного или двух названий часовых поясов.

|*Индекс*|Содержимое *timezoname*|значение по умолчанию *timeoneName*|
|-|-|-|
|0|Название часового пояса|"PST"|
|1|Название часового пояса с переходом на летнее время|"PDT"|
|> 1 или < 0|**errno** установлен на **EINVAL**|не изменено|

Если значения не изменяются явным образом во время выполнения, по умолчанию используются значения "PST" и "PDT" соответственно.

## <a name="return-value"></a>Возвращаемое значение

Нулевой, если успешно, в противном случае значение типа **errno.**

Если какой-либо *timeoneName* является **NULL,** или *размерInBytes* равен нулю или меньше нуля (но не оба), вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*pReturnValue*|*времяЗона*|*размерInBytes*|*Индекс*|Возвращаемое значение|Содержимое *timezoname*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Длина названия часового пояса|**Null**|0|0 или 1|0|не изменено|
|Длина названия часового пояса|any|> 0|0 или 1|0|Название часового пояса|
|не изменено|**Null**|> 0|any|**EINVAL**|не изменено|
|не изменено|any|нуль|any|**EINVAL**|не изменено|
|не изменено|any|> 0|> 1|**EINVAL**|не изменено|

## <a name="remarks"></a>Remarks

Функция **_get_tzname** извлекает представление строки персонажа текущего часового пояса или дневного стандартного часового пояса (DST) в адрес *timezoneName* в зависимости от значения индекса, а также размер строки в *pReturnValue.* Если *timeoneName* **null,** а *размерInBytes* равен нулю, размер строки, необходимой для удержания указанного часового пояса, и прекращение нулевых байтов возвращается в *pReturnValue.* Значения индекса должны быть либо 0 для стандартного часового пояса, либо 1 для стандартного часового пояса дневного света; любые другие значения *индекса* имеют неопределенные результаты.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="example"></a>Пример

Этот образец вызывает **_get_tzname,** чтобы получить необходимый размер буфера для отображения текущего стандартного часового пояса Daylight, выделяет буфер такого размера, вызывает **_get_tzname** снова для загрузки имени в буфере и печатает его на консоль.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>Выходные данные

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
