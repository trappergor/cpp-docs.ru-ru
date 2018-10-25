---
title: _get_tzname | Документы Майкрософт
ms.custom: ''
ms.date: 10/22/2018
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
ms.openlocfilehash: d773d5d98466963ef621cc3fa7bc5ab8b4acc40a
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990312"
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
Длина строки *timeZoneName* включая завершающий нуль-символ.

*timeZoneName*<br/>
Адрес символьной строки для представления названия часового пояса или летнее стандартное имя часового пояса (DST), в зависимости от *индекс*.

*sizeInBytes*<br/>
Размер *timeZoneName* символьные строки в байтах.

*Индекс*<br/>
Индекс, определяющий извлечение одного или двух названий часовых поясов.

|*Индекс*|Содержание *timeZoneName*|*timeZoneName* значение по умолчанию|
|-|-|-|
|0|Название часового пояса|"PST"|
|1|Название часового пояса с переходом на летнее время|"PDT"|
|> 1 или < 0|**errno** присвоено **EINVAL**|не изменено|

Если значения не изменяются явным образом во время выполнения, по умолчанию используются значения "PST" и "PDT" соответственно.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении, в противном случае **errno** введите значение.

Если параметр *timeZoneName* — **NULL**, или *sizeInBytes* равно нулю или меньше нуля (но не оба), вызывается обработчик недопустимого параметра, как описано в разделе [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Условия ошибок

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*Индекс*|Возвращаемое значение|Содержание *timeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Длина названия часового пояса|**NULL**|0|0 или 1|0|не изменено|
|Длина названия часового пояса|any|> 0|0 или 1|0|Название часового пояса|
|не изменено|**NULL**|> 0|any|**EINVAL**|не изменено|
|не изменено|any|нуль|any|**EINVAL**|не изменено|
|не изменено|any|> 0|> 1|**EINVAL**|не изменено|

## <a name="remarks"></a>Примечания

**_Get_tzname** функция получает символ строковое представление текущего часового пояса или летнее стандартное имя часового пояса (DST) в адрес *timeZoneName* в зависимости от значение, а также размер строки в индекса *pReturnValue*. Если *timeZoneName* — **NULL** и *sizeInBytes* нулю, то размер строки, необходимое для хранения указанный часовой пояс и в возвращаетсянуль-символавбайтах*pReturnValue*. Значения индекса должны быть либо 0 для стандартного часового пояса или 1 для перехода на летнее стандартного часового пояса; другие значения *индекс* имеют неопределенные результаты.

## <a name="example"></a>Пример

В этом примере вызывает **_get_tzname** получить необходимый размер буфера для отображения текущего перехода на летнее стандартное имя часового пояса, выделяет буфера этого размера, вызовы **_get_tzname** еще раз, чтобы загрузить имя в буфер и выводит его на консоль.

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

### <a name="output"></a>Вывод

```Output
The current Daylight standard time zone name is PDT.
```

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
